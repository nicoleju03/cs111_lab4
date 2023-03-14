## UID: 605691503

(IMPORTANT: Only replace the above numbers with your true UID, do not modify spacing and newlines, otherwise your tarfile might not be created correctly)

# Hey! I'm Filing Here

Creation of a file system with two directories, a file, and a symlink to the file, including allocation of data blocks and constructing inodes.

## Building

Build the executable with ```make```.

## Running

Run ```./ext2-create``` to build the cs111-base.img file. Then make a mount directory with ```mkdir mnt```, and mount the file system with ```sudo mount -o loop cs111-base.img mnt```. You can then run ```ls -ain /mnt``` and observe the output. An example output is:
```
total 7
     2 drwxr-xr-x 3    0    0 1024 Mar 13 21:37 .
942318 drwxrwx--- 3 1000 1000 4096 Mar 13 21:37 ..
    13 lrw-r--r-- 1 1000 1000   11 Mar 13 21:37 hello -> hello-world
    12 -rw-r--r-- 1 1000 1000   12 Mar 13 21:37 hello-world
    11 drwxr-xr-x 2    0    0 1024 Mar 13 21:37 lost+found
```
## Cleaning up

Unmount the filesystem with ```sudo umount mnt```, and remove the mount directory with ```rmdir mnt```. Clean up binary files with ```make clean```.
