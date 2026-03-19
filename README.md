# AppImage Info

A simple Bash script to analyze AppImage files and `.zsync` metadata files.

## Usage

To use this script, provide an AppImage file or a `.zsync` file as an argument. AppImage files must be executable.

```sh
./appimageinfo <appimage-file-or-zsync-file>
```

## Output Example

```sh
➜ appimageinfo appimagetool-x86_64.AppImage
Analyzing AppImage: appimagetool-x86_64.AppImage
Filesystem type: squashfs
Filesystem offset: 692512
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

For `.zsync` files:

```sh
➜ appimageinfo Claude-x86_64.AppImage.zsync
Analyzing zsync: Claude-x86_64.AppImage.zsync
Zsync version: 0.6.2
Target filename: Claude-x86_64.AppImage
Target mtime: Thu, 19 Mar 2026 01:40:42 +0000
Block size: 4096
Target length: 128611520
Hash lengths: 2,2,5
Target URL: Claude-x86_64.AppImage
SHA-1: 8122eeb1380c0a153244969f5bde2d756fd1b753
```

If zsync update information is embedded in the AppImage:

```sh
----------------------------------------
Update type: gh-releases-zsync
Update URL: probonopd|AppImageKit|continuous|appimagetool-x86_64.AppImage.zsync
```

If no update information is found:

```sh
----------------------------------------
zsync update info not found (no .upd_info section)
```

## Dependencies

* unsquashfs (squashfs-tools)
* objdump (binutils)
* gawk

## Licence

This project is licensed under the MIT License. See the [LICENSE](https://github.com/kem-a/appimageinfo?tab=MIT-1-ov-file) file for details.
