---
tags:
  - No Category
---
## Overview

[Windows](windows.md) Vista stores
[thumbnails](thumbnails.md) in the following directory:

    \Users\%username%\AppData\Local\Microsoft\Windows\Explorer

This directory contains following files:

- thumbcache_idx.db
- thumbcache_32.db, thumbcache_96.db, thumbcache_256.db, and
  thumbcache_1024.db
- thumbcache_sr.db

Thumbnails are stored in *thumbcache_NN.db* files in different formats.
There are several tools that can work with Vista thumbcache database
(see below) and individual images can be extracted using [file
carving](file_carving.md). Unfortunately, there is no
information in the thumbcache database that can easily link thumbnails
with original files in all cases. One of the ways to link the thumbnails
with original files is to use the contents of the [Windows Search
(windows.edb)](windows_desktop_search.md) database.

## Thumbcache Format

*Thumbcache format is described [here](http://www.noxa.org/blog/?p=5).*

In general, every thumbnail in cache is associated with two 64-bit
variables. First variable (sometimes called *Unique ID*, *Secret*, *File
ID*) associates data in file *thumbcache_idx.db* with thumbnail data in
*thumbcache_NN.db* files; the purpose of this variable is unclear.
Another variable is *Thumbnail Cache ID* (sometimes called *Thumbnail
filename* (in [FTK](ftk.md) is used to link
thumbnails with original files. Actually, *Thumbnail Cache ID* is
represented as Unicode string of HEX encoding.

## Thumbnail Creation Process

[Windows](windows.md) Vista creates thumbnails for files on
different media types, including:

- Removable devices
- Network drives
- Encrypted containers (e.g. [PGP](pgp.md) Desktop,
  [TrueCrypt](truecrypt.md), [BestCrypt](bestcrypt.md))

[Windows](windows.md) Vista doesn't create thumbnails for files
encrypted using [EFS](efs.md) unless thumbcache directory is
encrypted too; [Windows](windows.md) Vista doesn't delete
thumbnails for files after they were encrypted using
[EFS](efs.md).

Some programs may generate thumbnails for some file types which are
displayed in Windows Explorer, but not stored in the thumbcache (e.g.
Ascon Kompas).

## Linking thumbnails with original files

### Using Windows Indexer

![](WindowsPowerShellThumbnails.jpg "WindowsPowerShellThumbnails.jpg")

One way to link thumbnails with original files is to use Windows Indexer
database, which stores association between **indexed** files and
*ThumbnailCacheIDs* with some metadata. The windows.edb database file
contents can be extracted using [Windows Search Index
Extractor](http://www.simplecarver.com/tool.php?toolname=Windows%20Search%20Index%20Extractor)

#### Using Windows PowerShell

Windows PowerShell provides easy way to access this database using SQL
queries. Note that most forensic tools (like [FTK](ftk.md)
display *ThumbnailCacheID* ([ftk](ftk.md) calls it *Thumbnail
filename*) in hexadecimal, but Windows PowerShell returns the result in
decimal.

#### Using HEX editor

You can also search for *ThumbnailCacheID* value in *Windows.edb* file
using your favorite HEX editor.

### Vista Windows Photo Gallery

Windows Vista includes a built-in picture previewing tool called Windows
Photo Gallery (the LIVE edition may also be installed by the user). Both
of these programs create the files *pictures.pd4* and *pictures.pd5*
respectively containing the *ThumbnailCacheID* and file path information
of previewed pictures and videos. The contents of the pictures.pd4 and
pictures.pd5 can be extracted using [WPG
Viewer](http://www.simplecarver.com/tool.php?toolname=WPG%20Viewer)

## External Links

- [Forensic Implications of Windows Vista, Barrie Stewart,
  2007](http://www.whereisyourdata.co.uk/data/modules/wfdownloads/visit.php?cid=4&lid=9)
- [Windows Explorer Thumbnail Cache database (thumbcache.db)
  format](http://code.google.com/p/libwtcdb/downloads/detail?name=Windows%20Explorer%20Thumbnail%20Cache%20database%20format.pdf),
  by the [libwtcdb project](libwtcdb.md)

### ThumbnailCacheId

- \[<http://msdn.microsoft.com/en-us/library/windows/desktop/bb787580(v=vs.85>).aspx
  System.ThumbnailCacheId\]
- \[<http://msdn.microsoft.com/en-us/library/bb774628(VS.85>).aspx
  IThumbnailCache interface\]

### Non-English

- [Использование централизованных баз данных эскизов для исследования
  графических файлов на зашифрованных
  разделах](http://itdefence.ru/content/articles/Thumbnails.Suhanov/),
  ITDefence, 2009 ([extended
  version](http://www.securitylab.ru/analytics/370474.php))

## Tools

- [dmThumbs](http://www.dmthumbs.com/)
- [FTK](ftk.md)
- [Thumbs.db Viewer](http://www.janusware.com/fetch.php?page=412,2)
- [Thumbcache-viewer](http://code.google.com/p/thumbcache-viewer/)
- [WinThumbs](http://www.simplecarver.com/tool.php?toolname=WinThumbs%20Extractor)