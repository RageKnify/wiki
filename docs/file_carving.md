---
tags:
  - No Category
---
**File Carving,** or sometimes simply **Carving,** is the practice of
searching an input for files or other kinds of objects based on content,
rather than on metadata. File carving is a powerful tool for recovering
files and fragments of files when directory entries are corrupt or
missing, as may be the case with old files that have been deleted or
when performing an analysis on damaged media. Memory carving is a useful
tool for analyzing physical and virtual memory dumps when the memory
structures are unknown or have been overwritten.

Most file carvers operate by looking for file headers and/or footers,
and then "carving out" the blocks between these two boundaries.
[Semantic Carving](semantic_carving.md) performs carving based
on an analysis of the contents of the proposed files.

File carving should be done on a [disk image](disk_image.md),
rather than on the original disk.

File carving tools are listed on the
[Tools:Data_Recovery](tools:data_recovery.md) wiki page.

Many carving programs have an option to only look at or near sector
boundaries where headers are found. However, searching the entire input
can find files that have been embedded into other files, such as
[JPEGs](jpeg.md) being embedded into
[Microsoft](microsoft.md) [Word documents](DOC "wikilink"). This
may be considered an advantage or a disadvantage, depending on the
circumstances.

The majority of file carving programs will only recover files that are
contiguous on the media (in other words files that are not fragmented).

## Fragmented File Recovery

[Simson Garfinkel](simson_garfinkel.md) estimated that upto 58%
of outlook, 17% of jpegs and 16% of MS-Word files are fragmented and,
therefore, appear corrupted or missing to a user using traditional data
carving. The first set of file carving programs that can handle
fragmented files automatically have finally arrived. [A.
Pal](user:pashapal.md), [N. Memon](User:NasirMemon "wikilink").
T. Sencar and K. Shanmugasundaram have introduced a technique called
[SmartCarving](file_carving:smartcarving.md) that can recover
fragmented files.

## File Carving Taxonomy

[Simson Garfinkel](simson_garfinkel.md) and [Joachim
Metz](joachim_metz.md) have proposed the following file carving
taxonomy:

Carving
General term for extracting data (files) out of undifferentiated blocks
(raw data), like "carving" a sculpture out of soap stone.

<!-- -->

Block-Based Carving
Any carving method (algorithm) that analyzes the input on block-by-block
basis to determine if a block is part of a possible output file. This
method assumes that each block can only be part of a single file (or
embedded file).

<!-- -->

Statistical Carving
Any carving method (algorithm) that analyzes the input on characteristic
or statistic for example, entropy) to determine if the input is part of
a possible output file.

<!-- -->

Header/Footer Carving
A method for carving files out of raw data using a distinct header
(start of file marker) and footer (end of file marker).

<!-- -->

Header/Maximum (file) size Carving
A method for carving files out of raw data using a distinct header
(start of file marker) and a maximum (file) size. This approach works
because many file formats (e.g. JPEG, MP3) do not care if additional
junk is appended to the end of a valid file.

<!-- -->

Header/Embedded Length Carving
A method for carving files out of raw data using a distinct header and a
file length (size) which is embedded in the file format

<!-- -->

File structure based Carving
A method for carving files out of raw data using a certain level of
knowledge of the internal structure of file types. Garfinkel called this
approach "Semantic Carving" in his DFRWS2006 carving challenge
submission, while Metz and Mora called the approach "Deep Carving."

<!-- -->

Semantic Carving
A method for carving files based on a linguistic analysis of the file's
content. For example, a semantic carver might conclude that six blocks
of french in the middle of a long HTML file written in English is a
fragment left from a previous allocated file, and not from the
English-language HTML file.

<!-- -->

Carving with Validation
A method for carving files out of raw data where the carved files are
validated using a file type specific validator.

<!-- -->

Fragment Recovery Carving
A carving method in which two or more fragments are reassembled to form
the original file or object. Garfinkel previously called this approach
"Split Carving."

<!-- -->

Repackaging Carving
A carving method that modifies the extracted data by adding new headers,
footers, or other information so that it can be viewed with standard
utilities. For example, Garfinkel's [ZIP Carver](zip_carver.md)
looks for individual components of a ZIP file and repackages them with a
new Central Directory so that they can be opened with a standard unzip
utility.

## File Carving challenges and test images

[File Carving Challenge](http://www.dfrws.org/2006/challenge/) -
[DFRWS](digital_forensic_research_workshop.md) 2006

[File Carving Challenge](http://www.dfrws.org/2007/challenge/) -
[DFRWS](digital_forensic_research_workshop.md) 2007

[FAT Undelete Test \#1](http://dftt.sourceforge.net/test6/index.html) -
Digital Forensics Tool Testing Image (dftt \#6)

[NTFS Undelete (and leap year) Test
\#1](http://dftt.sourceforge.net/test7/index.html) - Digital Forensics
Tool Testing Image (dftt \#7)

[Basic Data Carving Test -
fat32](http://dftt.sourceforge.net/test11/index.html), Nick Mikus -
Digital Forensics Tool Testing Image (dftt \#11)

[Basic Data Carving Test -
ext2](http://dftt.sourceforge.net/test12/index.html), Nick Mikus -
Digital Forensics Tool Testing Image (dftt \#12)

## See also

- [File Carving Tools](tools:data_recovery#carving.md)
- [File Carving Bibliography](file_carving_bibliography.md)
- [Carver 2.0 Planning Page](carver_2.0_planning_page.md)
- [SmartCarving](file_carving:smartcarving.md)

# Memory Carving

## External Links

- [Measuring and Improving the Quality of File Carving
  Methods](http://sourceforge.net/projects/revit/files/Documentation/Master%20Thesis%20-%20Advanced%20File%20Carving/),
  by [Bas Kloet](bas_kloet.md), October 2007
- [Advanced File Carving Approaches for Multimedia
  Files](http://isyou.info/jowua/abstracts/jowua-v2n4-3.htm)
  ([pdf](http://isyou.info/jowua/papers/jowua-v2n4-3.pdf)), by [Rainer
  Poisel](mailto:rainer.poisel@gmail.com), Simon Tjoa, and Paul
  Tavolato, December 2011