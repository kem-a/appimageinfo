# AppImage Info

A simple Bash script to analyze AppImage files and extract filesystem information.


## Usage

To use this script, you need to provide an AppImage file as an argument. AppImage file must be executable.

```sh
./appimageinfo <appimage-file>
```


## Output Example

```sh
➜ appimageinfo appimagetool-x86_64.AppImage  
Analyzing AppImage: appimagetool-x86_64.AppImage
SquashFS offset: 692512
----------------------------------------
Found a valid SQUASHFS 4:0 superblock on appimagetool-x86_64.AppImage.
Creation or last append time Thu Jan  1 03:00:00 1970
Filesystem size 11938687 bytes (11658.87 Kbytes / 11.39 Mbytes)
Compression zstd
Block size 131072
Filesystem is exportable via NFS
Inodes are compressed
Data is compressed
Uids/Gids (Id table) are compressed
Fragments are compressed
Tailends are not packed into fragments
Xattrs are compressed
Duplicates are removed
Number of fragments 1
Number of inodes 19
Number of ids 1
Number of xattr ids 0

```


## Dependencies

* unsquashfs (squashfs-tools)


## Licence

This project is licensed under the MIT License. See the [LICENSE](https://github.com/kem-a/appimageinfo?tab=MIT-1-ov-file) file for details.
