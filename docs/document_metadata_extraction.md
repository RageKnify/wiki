---
tags:
  -  Tools
---
Here are tools that will extract metadata from document files.

# Office Files

[antiword](antiword.md)
<http://www.winfield.demon.nl/>

<!-- -->

[Belkasoft](belkasoft.md) Evidence Center
<http://belkasoft.com/>

Extracts metadata from various [Microsoft](microsoft.md) Office
files (both 97-2003 and 2007-2013 formats), as well as Open Office
documents. Besides, can extract plain texts (combining all texts from
all XLS/XLSX/ODS pages and PPT/PPTX/ODP slides) and embedded objects.
The tool can visualize pictures embedded in a document.

<!-- -->

[catdoc](catdoc.md)
<http://www.45.free.net/~vitus/software/catdoc/>

<!-- -->

[laola](laola.md)
<http://user.cs.tu-berlin.de/~schwartz/pmh/index.html>

<!-- -->

[word2x](word2x.md)
<http://word2x.sourceforge.net/>

<!-- -->

[wvWare](wvware.md)
<http://wvware.sourceforge.net/>

Extracts metadata from various [Microsoft](microsoft.md) Word
files ([doc](doc.md). Can also convert doc files to other
formats such as HTML or plain text.

<!-- -->

[Outside In](outside_in.md)
<http://www.oracle.com/technology/products/content-management/oit/oit_all.html>

Originally developed by Stellant, supports hundreds of file types.

<!-- -->

[FI Tools](fi_tools.md)
<http://forensicinnovations.com/>

More than 100 file types.

# StickyNotes

StickyNotes Parser

Windows 7 StickyNotes follow the [MS Compound Document binary
format](http://msdn.microsoft.com/en-us/library/dd942138%28v=prot.13%29.aspx);
the StickyNotes Parser extracts metadata (time stamps) from the OLE
format, including the text content (not the RTF contents) of the notes
themselves. Sn.exe also extracts the modified time of the Root Entry to
the Compound Document; all times are displayed in UTC format


<http://code.google.com/p/winforensicaanalysis/downloads/list>

# PDF Files

[Belkasoft](belkasoft.md) Evidence Center
<http://belkasoft.com/>

Extracts metadata from [PDF](pdf.md) files. Besides, can extract
texts and embedded objects. For pictures, embedded into a PDF document,
the tool can visualize them all right in its user interface.

<!-- -->

[xpdf](xpdf.md)
<http://www.foolabs.com/xpdf/>

[pdfinfo](pdfinfo.md) (part of the [xpdf](xpdf.md)
package) displays some metadata of [PDF](pdf.md) files.

(See [PDF](pdf.md))

# Images

[Belkasoft](belkasoft.md) Evidence Center
<http://belkasoft.com/>

Extracts [EXIF](exif.md) metadata from [JPEG](jpeg.md)
files as well as many digital camera raw files. The tool allows a user
to create complex filters based on various criteria on EXIF properties.
Photos with GPS coordinates can be shown on Google Maps and Google
Earth. Evidence Center can analyze existing Thumbs.db files and Thumbs
Cache as well as carve deleted thumbnails.

<!-- -->

[Exiftool](exiftool.md)
<http://www.sno.phy.queensu.ca/~phil/exiftool/>

Free, cross-platform tool to extract metadata from many different file
formats. Also supports writing

<!-- -->

[jhead](jhead.md)
<http://www.sentex.net/~mwandel/jhead/>

Displays or modifies [Exif](exif.md) data in
[JPEG](jpeg.md) files.

<!-- -->

[vinetto](vinetto.md)
<http://vinetto.sourceforge.net/>

Examines [Thumbs.db](thumbs.db.md) files.

<!-- -->

[libexif](libexif.md)
<http://sourceforge.net/projects/libexif> EXIF tag Parsing Library

<!-- -->

[Adroit Photo Forensics](adroit_photo_forensics.md)
<http://digital-assembly.com/products/adroit-photo-forensics/>

Displays meta data and uses date and camera meta-data for grouping,
timelines etc.

<!-- -->

Exif Viewer
<http://araskin.webs.com/exif/exif.html>

Add-on for Firefox and Thunderbird that displays various
[JPEG](jpeg.md)/JPG metadata in local and remote images.

<!-- -->

exiftags
<http://johnst.org/sw/exiftags/>

open source utility to parse and edit [exif](exif.md) data in
[JPEG](jpeg.md) images. Found in many Debian based
distributions.

<!-- -->

exifprobe
<http://www.virtual-cafe.com/~dhh/tools.d/exifprobe.d/exifprobe.html>

Open source utility that reads [exif](exif.md) data in
[JPEG](jpeg.md) and some "RAW" image formats. Found in many
Debian based distributions.

<!-- -->

Exiv2
<http://www.exiv2.org>

Open source C++ library and command line tool for reading and writing
metadata in various image formats. Found in almost every GNU/Linux
distribution

<!-- -->

pngtools
<http://www.stillhq.com/pngtools/>

Open source suite of commands (pnginfo, pngchunks, pngchunksdesc) that
reads metadata found in [PNG](png.md) files. Found in many
Debian based distributions.

<!-- -->

pngmeta
<http://sourceforge.net/projects/pmt/files/>

Open source command line tool that extracts metadata from
[PNG](png.md) images. Found in many Debian based distributions.

# General

These general-purpose programs frequently work when the special-purpose
programs fail, but they generally provide less detailed information.

[Metadact-e](metadact-e.md)
"Patented server-based metadata cleaning software that previews, cleans
and converts documents in Microsoft Outlook, Web Access email, tablets
and smartphones, as well as desktop-based documents."

<http://www.litera.com/Products/Metadact-e.aspx>

<!-- -->

[Metadata Extraction Tool](metadata_extraction_tool.md)
"Developed by the National Library of New Zealand to programmatically
extract preservation metadata from a range of file formats like PDF
documents, image files, sound files Microsoft office documents, and many
others."

<http://meta-extractor.sourceforge.net/>

<!-- -->

[Metadata Assistant](metadata_assistant.md)
<http://www.thepaynegroup.com/products/metadata/>

<!-- -->

[hachoir-metadata](hachoir.md)
Extraction tool, part of **[Hachoir](hachoir.md)** project

<!-- -->

[file](file.md)
The UNIX **file** program can extract some metadata

<!-- -->

[GNU libextractor](gnu_libextractor.md)
<http://gnunet.org/libextractor/> The libextractor library is a plugable
system for extracting metadata

<!-- -->

[Directory Lister Pro](directory_lister_pro.md)
Directory Lister Pro is a Windows tool which creates listings of files
from selected directories on hard disks, CD-ROMs, DVD-ROMs, floppies,
USB storages and network shares. Listing can be in HTML, text or CSV
format (for easy import to Excel). Listing can contain standard file
information like file name, extension, type, owner and date created, but
especially for forensic analysis file meta data can be extracted from
various formats: 1) executable file information (EXE, DLL, OCX) like
file version, description, company, product name. 2) multimedia
properties (MP3, AVI, WAV, JPG, GIF, BMP, MKV, MKA, MPEG) like track,
title, artist, album, genre, video format, bits per pixel, frames per
second, audio format, bits per channel. 3) Microsoft Office files (DOC,
DOCX, XLS, XLSX, PPT, PPTX) like document title, author, keywords, word
count. For each file and folder it is also possible to obtain its CRC32,
MD5, SHA-1 and Whirlpool hash sum. Extensive number of options allows to
completely customize the visual look of the output. Filter on file name,
date, size or attributes can be applied so it is possible to limit the
files listed.

<http://www.krksoft.com>

<!-- -->

[Apache Tika](apache_tika.md)
Apache Tika extracts metadata from a wide range of file formats and
normalizes metadata keys to Dublin Core when possible. In recent
versions of Tika, we have focused on extracting more information about
"authors" (original author, comment authors, last-saved-by, editors,
etc.) in general formats and more granular information for to/from/bcc
info in .msg files. We've also added extraction of "original paths,"
when available, that might allow examiners to see the full path that the
file or its attachments were stored. Finally, we've enriched extraction
from XMP to allow identification of uuids and ancestor uuids. Tika can
run in batch mode from input directory to output directory, and we
recommend the RecursiveParserWrapper (-J -t options in the commandline
app or /rmeta endpoint in
[tika-server](https://wiki.apache.org/tika/TikaJAXRS)) to capture
metadata from embedded documents.

<http://tika.apache.org/>

