# sf
`sf` is a wrapper script around `sshfs` to make mounting/unmounting easier. It probably doesn't deserve its own package, but I use it on so many machines that it might just be worth it.

## Usage

```
# Mount the host 'kartoffel' locally
$ sf mount root@kartoffel:22
SSHFS version 2.5
Server version: 3
Extension: posix-rename@openssh.com <1>
Extension: statvfs@openssh.com <2>
Extension: fstatvfs@openssh.com <2>
Extension: hardlink@openssh.com <1>

# Now it's available locally
$ ls ~/Mounts/kartoffel_root_22/
bin  boot  dev  etc  home   initrd.img  initrd.img.old  lib  lib64  lost+found  ...

# Unmount it again
$ sf umount root@kartoffel:22
```

## Installation
**Debian-based systems:**   
1. Either download a `.deb`-file from the [release page](https://github.com/binwiederhier/sf/releases)   
2. Or: Add my [Debian/APT archive](http://archive.philippheckel.com/apt/):

```bash
wget -qO - http://archive.philippheckel.com/apt/Release.key | sudo apt-key add -
sudo sh -c "echo deb http://archive.philippheckel.com/apt/release/ release main > /etc/apt/sources.list.d/archive.philippheckel.com.list"
sudo apt-get update
sudo apt-get install sf
```

**Other Linux systems:**   
Put the `sf` script in a folder inside your `$PATH` and install `sshfs`.

## License
The script is licensed as GPLv3.
