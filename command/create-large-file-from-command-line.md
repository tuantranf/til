# Create a Large File from the Command Line Mac OS

The simplest way to instantly generate a large empty file is to use the ‘mkfile’ command, which can immediately create a file of any size, whether fairly small in bytes or huge in gigabytes.
Syntax for mkfile is as follows:
```
mkfile -n size[b|k|m|g] filename
```

For example, to create a 1GB file called “LargeTestFile” on the desktop, the command would be:
```
mkfile -n 1g ~/Desktop/LargeTestFile
```
The file is created instantly and takes up the full size. Big files created from mkfile are full of zeroes.

The only downside to the mkfile command is that it appears limited to Mac OS X, thus if you’re looking for a cross-platform compatible solution that will work across other unix and linux variations you will want to use “dd” instead.
```
dd if=/dev/zero of=FileName bs=1024 count=1000
```
Another approach is to use the seek flag with some simple multiplication of a megabyte block size (1024), thus the following command would create a file that is 100MB in size (1024 x 100):
```
dd if=/dev/zero of=LargeTestFile.img bs=1024 count=0 seek=$[1024*100]
```

Ref [Create a Large File from the Command Line](http://osxdaily.com/2013/05/31/create-large-file-mac-os-x/)
