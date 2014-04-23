## Extended Attribute support

StoRM uses the Extended Attributes (EA) on files to store some metadata related to the file (e.g. the checksum value); therefore in order to ensure a proper running, the EA support needs to be enabled on the underlying file system and work properly.
Note: Depending on OS kernel distribution, for Reiser3, ext2 and ext3 file systems, the default kernel configuration should not enable the EA.

**To check**:

```bash
$ touch testfile
$ setfattr -n user.testea -v test testfile
$ getfattr -d testfile
# file: testfile
user.testea="test"
$ rm -f testfile

If the getfattr and setfattrl commands are not available on your host, **install** *attr* package:

```bash
$ yum install attr
```

To **enable** EA (if needed) you must add the *user\_xattr* property to the relevant file systems in your /etc/fstab file. For example:

```bash
$ vi /etc/fstab
  ...
/dev/hda3     /storage     ext3     defaults,acl,user_xattr     1 2
  ...
```

Then you need to remount the affected partitions as follows:

```bash
$ mount -o remount /storage
```
