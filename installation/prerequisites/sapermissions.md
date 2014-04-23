## Storage-Area's permissions

All the Storage Areas managed by StoRM needs to be owned by the STORM\_USER.

Assuming that you site manages a storage-area named _test_ and StoRM Backend is executed by ```storm``` user, _test_'s root directory permissions must be:

```bash
drwxr-x---+  2 storm storm
```

The site administrator has to take care of it. YAIM StoRM doesn't change the storage-area permissions, except if the root directory doesn't exist and needs to be created with the correct rights.
If you need to set the correct permission on o storage-area (assuming that Backend is executed by user ```storm```), you can launch the following commands:

```bash
chown -RL storm:storm <sa-root-directory>
chmod -R o-rwx,g+r <sa-root-directory>
```

If StoRM GridHTTPs is enabled, it needs to access the storage-area files. By default, StoRM GridHTTPs is executed by ```gridhttps``` user. To allow the ```gridhttps``` user to access/modify the files you can use the following command: 

```bash
find <sa-root-directory> -type d -exec setfacl -m g:gridhttps:x {} \;
```
