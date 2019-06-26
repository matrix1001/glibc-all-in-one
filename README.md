# glibc-all-in-one

this repo helps you to download & debug glibc easily.

__feature__

- download glibc binary
- download glibc debug file
- extract custom glibc

__note__

full support for ubuntu official glibc 2.23/2.27/2.28/2.29 .

for other glibc, you need to download them on your own.

# usage

check supported packages.

```
➜  glibc-all-in-one cat list
2.23-0ubuntu10_amd64
2.23-0ubuntu10_i386
2.23-0ubuntu11_amd64
2.23-0ubuntu11_i386
2.23-0ubuntu3_amd64
2.23-0ubuntu3_i386
2.27-3ubuntu1_amd64
2.27-3ubuntu1_i386
2.28-0ubuntu1_amd64
2.28-0ubuntu1_i386
2.29-0ubuntu2_amd64
2.29-0ubuntu2_i386
```

download.

```
➜  glibc-all-in-one ./download 2.23-0ubuntu10_i386
Getting 2.23-0ubuntu10_i386
  -> Location: https://mirror.tuna.tsinghua.edu.cn/ubuntu/pool/main/g/glibc/libc6_2.23-0ubuntu10_i386.deb
  -> Downloading libc binary package
  -> Extracting libc binary package
  -> Package saved to libs/2.23-0ubuntu10_i386
  -> Location: https://mirror.tuna.tsinghua.edu.cn/ubuntu/pool/main/g/glibc/libc6-dbg_2.23-0ubuntu10_i386.deb
  -> Downloading libc debug package
  -> Extracting libc debug package
  -> Package saved to libs/2.23-0ubuntu10_i386/dbg
➜  glibc-all-in-one ls libs/2.23-0ubuntu10_i386
. .. .debug  ld-2.23.so  libc-2.23.so  libpthread.so.0   ......
➜  glibc-all-in-one ls libs/2.23-0ubuntu10_i386/.debug
ld-2.23.so  libc-2.23.so   ......
```

needed glibc not in my list ?

you can download the debs on your own, then use `extract`.

you can find ubuntu glibc from `2.19` to `2.26` in `http://old-releases.ubuntu.com/ubuntu/pool/main/g/glibc/`.

```sh
./extract ~/libc6_2.26-0ubuntu2_i386.deb /tmp/test
./extract ~/libc6-dbg_2.26-0ubuntu2_i386.deb /tmp/test_dbg
```
