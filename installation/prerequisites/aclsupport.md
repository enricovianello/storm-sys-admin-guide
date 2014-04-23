## ACL support

StoRM uses the ACLs on files and directories to implement the security model. In so doing, StoRM uses the native access to the file system. Therefore in order to ensure a proper running, ACLs need to be enabled on the underlying file system (sometimes they are enabled by default) and work properly.

**To check**:
    
```bash
$ touch test
$ setfacl -m u:storm:rw test
```

Note: the storm user adopted to set the ACL entry **must** exist.

```bash
$ getfacl test
# file: test
# owner: root
# group: root
user::rw-
user:storm:rw-
group::r--
mask::rw-
other::r--
$ rm -f test
```

If the getfacl and setfacl commands are not available on your host you have to **install** *acl* package:

```bash
$ yum install acl
```

To **enable** ACL (if needed), you must add the acl property to the relevant file system in your /etc/fstab file. For example:

```bash
$ vi /etc/fstab
  ...
/dev/hda3     /storage      ext3     defaults, acl     1 2
  ...
```
 
Then you need to remount the affected partitions as follows:

```bash
$ mount -o remount /storage
```

This is valid for different file system types (i.e., ext3, xfs, gpfs and others).