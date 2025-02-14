---
tags:
  -  Windows
  -  Disk Analysis
---
## Volume Shadow Copy Service

Windows has included the Volume Shadow Copy Service in it's releases
since Windows XP. The Shadow Copy Service creates differential backups
periodically to create restore points for the user. Windows 7
Professional and Ultimate editions include tools to work with and manage
the Volume Shadow Copy Service, including the ability to mount shadow
volumes on disk images. In Windows 8 the shadow volumes seem to have
been superseded by File History. For now it looks like it uses similar
structures as its predecessors.

Windows Shadow Copy is a service that either manually or automatically
creates backup copies of disk volumes. These backups are automatically
created when Windows performs either a scheduled backup or a system
restore point. This happens before Windows Updates are installed, or
when Windows determines that it is time to create a new system restore
point, which is determined by both system idle time and the time since a
previous system restore point was created. In Windows Vista, this is one
day. On Windows 7 and newer, this is seven days. Windows XP creates them
every 24 hours regardless of system activity.

Shadow copies are initially created as block-level clones of entire
drives. From there, only the changes to the drive are tracked. This
means that in a forensic investigation, not all relevant information may
be in the same Shadow Copy.

## History

Shadow copies were first available in the Windows XP and Server 2003
operating systems, and are still present in each subsequent Windows and
Server operating systems, including the present day Windows 10.

Although all present Windows and Server operating systems contain shadow
volume capability, the process in which each operating system creates
and accesses them varies, and is explained below.

### Windows XP and Server 2003

Windows first added Volume Snapshot Service to windows XP, which is used
by NTBackup. The creation of persistent snapshots has been added within
Windows Server 2003. This addition gives the ability of having up to 512
snapshots to exist for a single volume. Windows 2003 is used to create
incremental snapshots of the data that have changed.

In Windows XP, the process of system restore, or the creation of the
shadow copies is different from the more recent versions of windows.
Windows XP uses a simple mechanism- the moment an application attempts
to overwrite any system file, Windows XP makes a copy of the file and
saves that file to a separate folder. That way, in windows XP, system
restore will not affect a user's documents, but only files such as dll,
exe, and registry files, along with a few others.

### Windows Vista, Windows 7, and Server 2008

Many of the components of Windows have been updated to make use of
Shadow copies in these versions. The backup and restore utility within
these windows versions, use both shadow copies of files in both
file-based and sector-by -sector backups. VSS is used by the System
Protection components, which creates and maintains periodic copies of
system and user data on the same local volume, allows it to be locally
accessed by the System Restore Utility.

### Windows 8 and Server 2012

These versions of Microsoft’s operating systems support persistent
shadow copies. However, Windows 8 is lacking a GUI portion that is
necessary to easily browse the shadow copies. So, within Windows 8 the
Previous versions tab of the properties dialog of files was removed for
local volumes, so the ability to browse, search or recover older
versions of files is not present.

### Windows 10

This version of Microsoft Windows has restored the Previous versions tab
within the properties dialog of files. However, it now depends on the
the File History feature instead of Volume shadow Copy.

## Shadow Volume Copies in Digital Forensics

### Why Shadow Copies are Important to Forensics

Windows Shadow Volumes are important to digital forensics because they
can provide additional data that otherwise would not be available. They
can allow a forensic investigator to recover deleted files, and to learn
what was taking place on a system before he/she began the investigation.
They are an excellent tool for discovering data that was previously
deleted by a system user.

### Limitations of Shadow Copies in forensic investigations

Although Shadow Copies can provide forensic investigators with files
that have been deleted between the time the Shadow Copy was made and the
time the investigation began, they only provide one previous version of
files. If previous changes to files were made before the Shadow Copy was
created, those changes will not be known. Because Shadow Copies clone on
a block-level rather than a file-level, changes to individual files may
not be enough to cause Windows to make the changes in a corresponding
Shadow Copy.

Additionally, depending on the user’s individual settings, the Shadow
Copy service might be turned off, resulting in no Shadow Copies being
stored. Other times, the disk space settings might be set too low for
multiple Shadow Copies to be saved, or even for one Shadow Copy to be
saved if it is larger than what the settings allow. Windows
automatically overwrites Shadow Copies when the disk space limit is
reached. For these reasons, Shadow Copies should be an aid in a forensic
investigation, but they are not guaranteed as a means to discover useful
information.

## Also see

- [Windows](windows.md)
- [File History](windows_file_history.md)
- How to: [Mount shadow volumes on disk
  images](mount_shadow_volumes_on_disk_images.md)

## External Links

### How to analyze Shadow Volumes

- [VISTA and Windows 7 Shadow Volume
  Forensics](http://computer-forensics.sans.org/blog/2008/10/10/shadow-forensics/),
  by [Rob Lee](rob_lee.md), October 2008
- [Accessing Volume Shadow
  Copies](http://windowsir.blogspot.ch/2011/01/accessing-volume-shadow-copies.html),
  by [Harlan Carvey](harlan_carvey.md), January 2011
- [More VSCs](http://windowsir.blogspot.ch/2011/01/more-vscs.html), by
  [Harlan Carvey](harlan_carvey.md), January 2011
- [A Little Help with Volume Shadow
  Copies](http://journeyintoir.blogspot.ch/2011/04/little-help-with-volume-shadow-copies.html),
  by [Corey Harrell](corey_harrell.md), April 2011
- [Volume Shadow Copy with
  ProDiscover](http://toorcon.techpathways.com/uploads/VolumeShadowCopyWithProDiscover-0511.pdf),
  May 2011
- [HowTo: Mount and Access
  VSCs](http://windowsir.blogspot.ch/2011/09/howto-mount-and-access-vscs.html),
  by [Harlan Carvey](harlan_carvey.md), September 2011
- [Shadow Timelines And Other VolumeShadowCopy Digital Forensics
  Techniques with the Sleuthkit on
  Windows](http://computer-forensics.sans.org/blog/2011/09/16/shadow-timelines-and-other-shadowvolumecopy-digital-forensics-techniques-with-the-sleuthkit-on-windows/),
  by [Rob Lee](rob_lee.md), September 2011
- [Ripping Volume Shadow Copies –
  Introduction](http://journeyintoir.blogspot.ch/2012/01/ripping-volume-shadow-copies.html),
  by [Corey Harrell](corey_harrell.md), January 2012
- [Ripping VSCs – Practitioner
  Method](http://journeyintoir.blogspot.ch/2012/02/ripping-vscs-practitioner-method.html),
  by [Corey Harrell](corey_harrell.md), February 2012
- [Ripping VSCs – Practitioner
  Examples](http://journeyintoir.blogspot.ch/2012/02/ripping-vscs-practitioner-examples.html),
  by [Corey Harrell](corey_harrell.md), February 2012
- [Ripping VSCs – Developer
  Method](http://journeyintoir.blogspot.ch/2012/02/ripping-vscs-developer-method.html),
  by [Corey Harrell](corey_harrell.md), February 2012
- [Ripping VSCs – Developer
  Examples](http://journeyintoir.blogspot.ch/2012/02/ripping-vscs-developer-examples.html),
  by [Corey Harrell](corey_harrell.md), February 2012
- [Examining VSCs with GUI
  Tools](http://journeyintoir.blogspot.ch/2012/02/examining-vscs-with-gui-tools.html),
  by [Corey Harrell](corey_harrell.md), February 2012
- [VSC Toolset: A GUI Tool for Shadow
  Copies](http://dfstream.blogspot.ch/2012/03/vsc-toolset-gui-tool-for-shadow-copies.html),
  by [Jason Hale](jason_hale.md), March 2012
- [Examining Volume Shadow Copies – The Easy
  Way!](http://encase-forensic-blog.guidancesoftware.com/2012/06/examining-volume-shadow-copies-easy-way.html),
  by [Simon Key](simon_key.md), June 2012
- [Getting Ready for a Shadow Volume
  Exam](http://justaskweg.com/?p=351), by [Jimmy
  Weg](jimmy_weg.md), June 2012
- [Mounting Shadow Volumes](http://justaskweg.com/?p=466), by [Jimmy
  Weg](jimmy_weg.md), July 2012
- [Examining the Shadow Volumes with X-Ways
  Forensics](http://justaskweg.com/?p=518), by [Jimmy
  Weg](jimmy_weg.md), July 2012
- [“Weg, I’m afraid that I don’t have VMware. How do I Examime Shadow
  Volumes?”](http://justaskweg.com/?p=710), by [Jimmy
  Weg](jimmy_weg.md), August 2012
- ["Examining shadow copies with Reconnoitre (and without vssadmin),
  it's as easy as 1, 2,
  3"](http://sandersonforensics.com/forum/content.php?168-Reconnoitre),
  by [Paul Sanderson](paul_sanderson.md), January 2013

<!-- -->

- [Volume Shadow Copy Part
  2](http://computerforensicsblog.champlain.edu/2014/02/05/volume-shadow-copy-part-2/),
  by Ryan Montelbano, Scott Barrett, Jacob Blend, February 5, 2014
- [Volume Shadow Copy Part
  3](http://computerforensicsblog.champlain.edu/2014/02/26/volume-shadow-copy-part-3/),
  by Scott Barrett, February 26, 2014
- [Volume Shadow Copy Part
  4](http://computerforensicsblog.champlain.edu/2014/03/26/volume-shadow-copy-part-4/),
  by Ryan Montelbano, March 26, 2014

### Shadow Volumes in depth

- [Reliably recovering evidential data from Volume Shadow Copies in
  Windows Vista and Windows
  7](http://www.qccis.com/docs/publications/WP-VSS.pdf), by [James
  Crabtree](james_crabtree.md) and [Gary
  Evans](gary_evans.md), 2010
- [Into The
  Shadows](http://forensic4cast.com/2010/04/19/into-the-shadows/) and
  [Presentation](http://www.forensic4cast.com/2010/04/presentation-into-the-shadows/),
  by [Lee Whitfield](lee_whitfield.md), April 2010
- [Volume Shadow Snapshot
  format](https://googledrive.com/host/0B3fBvzttpiiSZDZXRFVMdnZCeHc/Volume%20Shadow%20Snapshot%20(VSS)%20format.pdf),
  by the [libvshadow project](libvshadow.md), March 2011
- [Windowless Shadow Snapshots - Analyzing Volume Shadow Snapshots (VSS)
  without using
  Windows](https://googledrive.com/host/0B3fBvzttpiiSZDZXRFVMdnZCeHc/Paper%20-%20Windowless%20Shadow%20Snapshots.pdf)
  and [OSDFC
  2012](http://www.basistech.com/about-us/events/open-source-forensics-conference/)
  [Slides](https://googledrive.com/host/0B3fBvzttpiiSZDZXRFVMdnZCeHc/Slides%20-%20Windowless%20Shadow%20Snapshots.pdf),
  by [Joachim Metz](joachim_metz.md), October 2012

### Other

- [Lurking in the Shadows – Hack3rcon
  II](http://lanmaster53.com/talks/#hack3rcon2)
- [Volume Shadow Copies - The Lost
  Post](http://pauldotcom.com/2012/10/volume-shadow-copies---the-los.html),
  [Mark Baggett](mark_baggett.md), October 2012

## Tools

- [EnCase](encase.md) with VSS Examiner Enscript (available from
  the downloads section of the GSI Support Portal)
- [libvshadow](libvshadow.md)
- [ProDiscover](prodiscover.md)
- [ShadowExplorer](http://www.shadowexplorer.com/)
- [VSC Toolset](http://dfstream.blogspot.ch/p/vsc-toolset.html)
- [X-Ways Forensics](x-ways_ag.md)
- [Reconnoitre](http://sandersonforensics.com/forum/content.php?168-Reconnoitre)
- Vssadmin - Command Line utility included in Windows XP and later,
  which can list, create, or delete volume shadow copies. This utility
  will also list the installed shadow copy writers and providers.
- [Forensic Tool Kit](forensic_toolkit.md)

## Sources

[1](http://blog.szynalski.com/2009/11/volume-shadow-copy-system-restore/)
\[<https://msdn.microsoft.com/en-us/library/windows/desktop/aa378910(v=vs.85>).aspx\]

