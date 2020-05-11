# glibc-all-in-one

this repo helps you to download & debug & complie glibc easily.

__feature__

- download glibc binary
- download glibc debug file
- extract custom glibc
- download & complie glibc source code


# usage

## download
check supported packages. remember to run `update_list` at first.

```
➜  glibc-all-in-one ./update_list
[+] Common list has been save to "list"
[+] Old-release list has been save to "old_list"

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
......

➜  glibc-all-in-one cat old_list
2.21-0ubuntu4.3_amd64
2.21-0ubuntu4.3_amd64
2.21-0ubuntu4_amd64
2.21-0ubuntu4_amd64
2.24-3ubuntu1_amd64
2.24-3ubuntu1_amd64
2.24-3ubuntu2.2_amd64
2.24-3ubuntu2.2_amd64
2.24-9ubuntu2.2_amd64
2.24-9ubuntu2.2_amd64
......
```

download. 

__Note__: use `download` for packages in the `list`; use `download_old` for packages in the `old_list`.

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

```
➜  glibc-all-in-one ./download_old 2.24-3ubuntu2.2_amd64
......
```

needed glibc not in my list ?

you can download the debs on your own, then use `extract`.

```sh
./extract ~/libc6_2.26-0ubuntu2_i386.deb /tmp/test
./extract ~/libc6-dbg_2.26-0ubuntu2_i386.deb /tmp/test_dbg
```

## compile

supported version: 2.19, 2.23-2.29

supported arch: i686, amd64

__note__: you may fail to build older version of glibc. ( not my problem ) . my friend says that ubuntu 16.04 is perfect to build all of them.

__note__: change the `GLIBC_DIR` in the `build`, if you don't want to build them on `/glibc`.

```sh
./build 2.29 i686
```