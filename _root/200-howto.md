---
title: How to
title_nav: How to
slug: howto
---

### Installation instructions

PEFS can be installed from official FreeBSD package repository, [ports](http://www.freshports.org/sysutils/pefs-kmod/) or
by building from [sources](https://github.com/glk/pefs).

~~~~~~~~
# pkg install pefs-kmod
~~~~~~~~

~~~~~~~~
# cd ports/sysutils/pefs-kmod
# make install
~~~~~~~~

~~~~~~~~
# git clone git://github.com/glk/pefs.git pefs
# cd pefs
# make obj all
# make install
# make clean
~~~~~~~~

### Create encrypted directory

Start by creating new directory and populating it with key chain database
(.pefs.db) containing your password protected key.
Note that database file is always created on unencrypted file system.
Mount PEFS, in this example we are using the same directory ~/Private as both
source and target mount point.
As a final step, add key to the file system. -c option is there to verify
password in database.

~~~~~~~~
% mkdir ~/Private
% pefs addchain -fZ ~/Private
Enter parent key passphrase:
Reenter parent key passphrase:
% pefs mount ~/Private ~/Private
% pefs addkey -c ~/Private
Enter passphrase:
~~~~~~~~


