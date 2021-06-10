# Manjaro Linux (Host System)

I start with a fresh install on a old notebook. Manjaro version is 21.0.6 KDE.

- `uname -a` Linux manjo 5.10.41-1-MANJARO #1 SMP PREEMPT Fri May 28 19:10:32 UTC 2021 x86_64 GNU/Linux
- pacman overview: https://wiki.manjaro.org/index.php/Pacman_Overview
- use `sudo pacman -Syu` to update the package database and update all packages on the system
- use `sudo pacman -S package_name` to install a package
- make a shell script executable: `sudo chmod +x filename.sh` and run it with `./filename.sh`

# Youtube Tutorial

https://www.youtube.com/watch?v=IXA0GNTLf_Q

# Linux From Scratch (LFS) Book

Version: LFS-BOOK-10.1

```
cat > $LFS/etc/group << "EOF"
Hello World!
EOF
```

This format is used when creating configuration files. The first command tells the system to create the file `$LFS/etc/group` from whatever is typed on the following lines until the sequence End Of File (`EOF`) is encountered. Therefore, this entire section is generally typed as seen.

# Part II --  Preparing for the Build

## Chapter 2 Preparing the Host System

### 2.1 Introduction

### 2.2 Host System Requirements

Install the required packages. Use the script `install_packages.sh`:

```
#!/bin/bash

sudo pacman -S \
    bash \
    binutils \
    bison \
    bzip2 \
    coreutils \
    diffutils \
    findutils \
    gawk \
    gcc \
    glibc \
    grep \
    gzip \
    m4 \
    make \
    patch \
    perl \
    python \
    sed \
    tar \
    texinfo \
    xz
```

Use the `version_check.sh` script:

```
bash, version 5.1.8(1)-release
/bin/sh -> /usr/bin/bash
Binutils: (GNU Binutils) 2.36.1
bison (GNU Bison) 3.7.6
yacc is bison (GNU Bison) 3.7.6
bzip2,  Version 1.0.8, 13-Jul-2019.
Coreutils:  8.32
diff (GNU diffutils) 3.7
find (GNU findutils) 4.8.0
GNU Awk 5.1.0, API: 3.0 (GNU MPFR 4.1.0, GNU MP 6.2.1)
/usr/bin/awk -> /usr/bin/gawk
gcc (GCC) 11.1.0
g++ (GCC) 11.1.0
(GNU libc) 2.33
grep (GNU grep) 3.6
gzip 1.10
Linux version 5.10.41-1-MANJARO (builduser@LEGION) (gcc (GCC) 11.1.0, GNU ld (GNU Binutils) 2.36.1) #1 SMP PREEMPT Fri May 28 19:10:32 UTC 2021
m4 (GNU M4) 1.4.18
GNU Make 4.3
GNU patch 2.7.6
Perl version='5.34.0';
Python 3.9.5
sed (GNU sed) 4.8
tar (GNU tar) 1.34
texi2any (GNU texinfo) 6.7
xz (XZ Utils) 5.2.5
g++ compilation OK
```

### 2.3 Building LFS in Stages

### 2.4 Creating a New Partition


