---
title: About
title_nav: About
slug: about
---

[PEFS (Private Encrypted File System)]({{site.url}}) is a kernel level stacked cryptographic file system for [FreeBSD](https://www.freebsd.org/). PEFS transparently encrypts data and runs on top of any existing file system. Leveraging capabilities of the underlying file system helps to reduce configuration complexity and eliminates necessity of additional storage devices. 

Primary usecase for PEFS has historically been **encryption of the user home directory**. Besides, PEFS may prove useful in the following cases: 

 - Encryption of the data shared over network or on cloud storage 
 - Encryption of the data on portable storage like USB thumb drive 
 - Setting up multiple encrypted folders for sensitive information
 - Login with PEFS password and automatic decryption of the home directory (pam module)
 - Support of multiple keys makes it possible to hide encrypted directories, similar to the hidden secondary volumes concept. 
{: .list-long }

**Enterprise environments** will additionally benefit from complete **POSIX semantics** provided by PEFS, e.g. sparse files, hardlinks, and atomic rename. **Incremental backups** and improved reliability in case of the system crash are achieved by each PEFS-encrypted file being self-contained, and elimination of external metadata associated with file or directory. File system operates at kernel level providing better performance comparing to user-level file systems.

PEFS is tuned for **optimal and secure operation** out-of-the-box. It means there is no user configurable options that could change behavior of the system lowering its overall security.
Only standard and up to date encryption algorithms are used (AES and Camellia in XTS mode, PKCS#5v2 and HKDF for key generation). 

There is a number of techniques PEFS employs to **mitigate off-line attacks**. Files with the same plaintexts are indistinguishable even when
encrypted with the same key because of a new random tweak generated for each file.
The same applies to file names, i.e. the same file name will be encrypted differently in any two directories.

PEFS is [open source](https://github.com/glk/pefs) free software available under the BSD license.
 
### Author

<div class="pull-left img-thumbnail" style="margin-right: 2em;">
<img src="/assets/img/Gleb_Kurtsou_PEFS.jpg" class="img-rounded" alt="Gleb Kurtsou" style="width: 192px; height: 192px;">
</div>

[Gleb Kurtsou](https://github.com/glk) started to work on PEFS in 2009 while participating in the Google Summer of Code. 
Gleb continues to develop the project mostly by his own with support by other open source community enthusiasts. He is a FreeBSD src committer, and specializes in data security, storage systems, and high performance networking.

When not coding, Gleb enjoys playing bass and exploring California nature with his Samoyed dog Redwood. 
