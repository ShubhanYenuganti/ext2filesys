# Hey! I'm Filing Here

In this lab, I successfully implemented a 1 MiB ext2 file system that contains 2 directories -- a root directory and a lost+found directory, a regular file (hello-world) with the contents "Hello World\n" and a symbolic link (hello) that points to the hello-world file. 

## Building
To build the project run
```shell
make
```

## Running
To run the project run the following commands in order
This creates the executable that runs the file system image. 
```shell
./ext2-create
```
Create a directory to mount the filesystem. 
``` shell
mkdir {name}
```
This mounts the filesystem onto the root directory that you created in the previous command, and lets you use the file hello-world file.
```shell
sudo mount -o loop cs111-base.img {name}
```
Once you are done with the filesystem you can unmount the filesystem.
```shell
sudo umount {name}
```
Then delete the directory that you created earlier
```shell
rmdir {name}
```

Additional helpful commands
dump2efs dumps the filesystem information
```shell
dump2efs cs111-base.img 
```
Run this to check if the filesystem implementation is correct.
```shell
fsck.ext2 cs111-base.img
```

## Cleaning up
Run
```shell
make clean
```