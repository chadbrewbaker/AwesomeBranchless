# Awesome Superoptmize

Homeless for now, will probably move this list


## Clang
[redhat article](https://developers.redhat.com/blog/2020/07/06/profile-guided-optimization-in-clang-dealing-with-modified-sources/)
```bash
-fprofile-instr-generate
-fprofile-instr-generate= #Send profile to specific path/name
LLVM_PROFILE_FILE="code-%p.profraw" ./code # Set path as environment variable
-fcoverage-mapping  #Code coverage
-flto=thin #ThinLTO
-flto #Full LTO
```
[code coverage](https://clang.llvm.org/docs/SourceBasedCodeCoverage.html#compiling-with-coverage-enabled)

## LLVM
```bash
-fprofile-generate
```



## macOS aarch64
[Profiling with sample](https://gist.github.com/loderunner/36724cc9ee8db66db305)


## LLVM/GCC PGO

2020 LLVM Developers meeting
PGO instrumentation https://www.youtube.com/watch?v=GBtQrYx_Jbc
IPC future optimization https://www.youtube.com/watch?v=uC-x_Je_sIw
IPC deep dive https://www.youtube.com/watch?v=I4Iv-HefknA
Clang static analyzer https://www.youtube.com/watch?v=nTslG8HtKeA
PGO instrumentation https://www.youtube.com/watch?v=kauauderlAU
Code size optimizations https://www.youtube.com/watch?v=puZ2B408VsM
lld performance (2013)https://www.youtube.com/watch?v=ONGVraXbJOo
Paquette LLVM basics https://www.youtube.com/watch?v=3QQuhL-dSys
weaving instrumentation for PGO https://www.youtube.com/watch?v=T8qGbze3apo
Alive2 https://www.youtube.com/watch?v=paJhdBp_iA4
Hot cold splitting pass https://www.youtube.com/watch?v=Q8rqGg6vHAE
Propeller https://www.youtube.com/watch?v=DySuXFGmB40
SOUPER https://www.youtube.com/watch?v=5eSOWM0upN8
Portable SIMD with zig https://www.youtube.com/watch?v=CRSmOlCxHZE
https://github.com/ziglang/zig/blob/master/test/stage1/behavior/vector.zig

Android PGO
https://source.android.com/devices/tech/perf/pgo


Linux Kernel PGO at Microsoft
https://linuxplumbersconf.org/event/7/contributions/642/contribution.pdf
[LTO, PGO, and AutoFDO in the kernel](https://www.youtube.com/watch?v=FFjV9f_Ub9o&t=3780s)
https://linuxplumbersconf.org/event/7/timetable/?print=1&view=standard#150-lto-pgo-and-autofdo-in-the

## BOLT PGO


#Fedora
https://fedoramagazine.org/wsl-fedora-33/
wget https://github.com/fedora-cloud/docker-brew-fedora/raw/33/x86_64/fedora-33.20201110-x86_64.tar.xz
unxz fedora-33.20201110-x86_64.tar.xz
mv fedora-33.20201110-x86_64.tar /mnt/d/
#switch to windows
 wsl --import Fedora-33 D:\wsl\Fedora-33  D:\fedora-33.20201110-x86_64.tar
 dnf upate 
dnf install wget curl sudo ncurses dnf-plugins-core dnf-utils passwd findutils apt

## Getting Packages
https://gist.githubusercontent.com/ishad0w/788555191c7037e249a439542c53e170/raw/3822ba49241e6fd851ca1c1cbcc4d7e87382f484/sources.list



https://blog.packagecloud.io/eng/2015/04/20/working-with-source-rpms/
https://www.cyberciti.biz/faq/how-to-get-source-code-of-package-using-the-apt-command-on-debian-or-ubuntu/#Getting_source_code_of_package_on_Ubuntu
https://wiki.debian.org/BuildingTutorial#Get_the_source_package

```bash
 #get list of dependencies
 yum deplist <package name>
 dnf deplist  <package name>
 apt-cache depends <package name>
 #just download
dnf download package-name
apt-get install --download-only package_name
yumdownloader --source redis
```

```bash
#  deb <--> RPM
alien linuxconf-devel-1.16r10-2.i386.rpm
sudo alien -r libsox1_14.2.0-1_i386.deb

#hack the spec for RPM
rpmrebuild -pe tunesviewer-1.4-2.noarch.rpm
```

```bash
deb http://archive.ubuntu.com/ubuntu/ focal main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ focal-updates main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-updates main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ focal-security main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-security main restricted universe multiverse

deb http://archive.ubuntu.com/ubuntu/ focal-backports main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ focal-backports main restricted universe multiverse

deb http://archive.canonical.com/ubuntu focal partner
deb-src http://archive.canonical.com/ubuntu focal partner
sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 3B4FE6ACC0B21F32

```


