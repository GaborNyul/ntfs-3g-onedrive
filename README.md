# ntfs-3g-onedrive

 Reupload of the source of ntfs-3g-onedrive-bin, created by jp-andre

This ntfs-3g pluging solves issues related to the onedrive's reparsing points and allows you to access the onedrive folder from your linux distro.

Additional Build instructions:

Install dependencies using your package manager:

```
fuse
ntfs-3g-dev
libfuse-dev
```

Depending on your system you make need other dependencies that are not listed here.

Clone the repository and acess the folder:

```
git clone https://github.com/gbrielgustavo/ntfs-3g-onedrive/
cd ntfs-3g-onedrive
```

Then you must config the makefile

```
libtoolize --force
aclocal
autoheader
automake --force-missing --add-missing
autoconf
./configure
```

Now you just make and install:

```
make
sudo make install
```

# Important

The plugin files should be copied to your ntfs-3g lib folder, but sometimes this doesn't happen.

In this case, you check the output of the *make install* command to identify where the files were installed.

Then you copy the .so (and maybe the .la) file to the right path (*sudo cp /pathTo.soFile/*.SOfile /pathtoNTFS-3gLibs/*.soFile*)

In fedora 38 it was */usr/lib64/ntfs-3g*, but you should check in your distro

Now you should be abble to access your onedrive files.
