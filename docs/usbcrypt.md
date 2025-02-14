---
tags:
  -  Encryption
  -  Windows
  -  Tools
  -  Disk Encryption
---
**USBCrypt** is a commercial (closed source) software intended primarily
to encrypt external USB drives. (However, the encryption is not limited
to the external drives or to the USB connection: any drive that is
recognized by Windows as a valid drive with read-write access can be
encrypted with USBCrypt.) USBCrypt software is [Windows 7, Vista, XP,
2000](windows.md)-only. It supports [AES](aes.md), and
[Twofish](twofish.md) encryption with the 128- and 256-bit keys,
in the [XTS](xts.md) and [CBC](cbc.md) encryption modes.

## Recognizing drives encrypted with USBCrypt

USBCrypt encrypts drives by creating the file-based Virtual Encrypted
Disks on them. In addition to one or more files that contain the
encrypted data, USBCrypt also puts a portable software on the drive, to
enable its use on other computers. While the encrypted data files
contain no identifying information (and thus support [plausible
deniability](plausible_deniability.md), the presence of other
supporting files makes it easy to identify the drives encrypted with
USBCrypt: the root folder of the encrypted drive contains the file
USBCrypt.exe as well as a folder named USBCrypt-system. The latter
contains the encrypted data files as well as USBCrypt software files
(DLL and SYS). The file USBCrypt.ini is a text-only file that contains
settings as well as license information (including the name of the
person or business who has purchased the software).

## Spare-key file

When the user is encrypting a drive with USBCrypt software, s/he has the
option to create a "spare key" file on the user's computer. This file
contains a copy of the encryption key that can be used by the user if
s/he forgets the main encryption password. Or, it can be used by a
system administrator to get access to the encrypted data in case the
employees leave the company and take the passwords with them. Each spare
key file contains a copy of just one encryption key for the specific
encrypted drive it was created for. It cannot be used to decrypt any
other drive, even if the user has used the same password and encryption
algorithm. USBCrypt can automatically detect whether it can decrypt a
specific drive with a spare key.

## Forensic Acquisition

If you encounter a system that has a live USBCrypt drive, it is
imperative that you capture the contents of the encrypted drive before
disconnecting the drive or shutting down the system. Once the system is
shutdown, the contents becomes inaccessible unless you have the proper
encryption key generated by a user's password. If the encrypted drive in
not live, it is imperative to secure access to the user's computer that
was used to encrypt the drive: there is a possibility that the computer
still has the "spare key" file stored on its hard drive, assuming the
user has the selected the option to create such a file when encrypting
the drive.

## Attacks

If the "spare key" file for the encrypted drive has not been obtained,
then the only option for acquiring the content of a dismounted USBCrypt
drive is to do a brute-force password guessing attack. USBCrypt software
itself contains a built-in command to perform the brute-force attack on
the drives it encrypts.

## External Links

- [Official website](http://www.winability.com/usbcrypt/)
- [USBCrypt web site](http://www.usbcrypt.com/)