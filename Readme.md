Hunter ALIAS target issue demo with older cmake versions.
===

Hunter commit: [ccf74c7](https://github.com/cpp-pm/hunter/commit/ccf74c7c2d2c1b9442a6863ca232a252e35720fb)

Cmake versions lower than 3.11 do not support ALIAS of imported targets that are now used by Hunter. 

Hunter documentation needs to be updated to indicate:

```
cmake_minimum_required(VERSION 3.11)
```

Travis failure:
---
[![Build Status](https://travis-ci.com/hunterdevel/hunter_alias_issue.svg?branch=master)](https://travis-ci.com/hunterdevel/hunter_alias_issue)

Quick test:
---
```bash
cd /tmp &&\
wget -O cmake.sh https://cmake.org/files/v3.10/cmake-3.10.3-Linux-x86_64.sh &&\ 
mkdir -p cmakebin &&\
sudo sh cmake.sh --skip-license --exclude-subdir --prefix=`pwd`/cmakebin &&\
rm -rf hunterbugtest && \
mkdir -p hunterbugtest && \
cd hunterbugtest && \
git clone https://github.com/hunterdevel/hunter_alias_issue.git && \
mkdir -p build && \
cd build && \
/tmp/cmakebin/bin/cmake ../hunter_alias_issue; cd /tmp


```

Example error (cmake <3.11):
```
tmp/hunterbugtest/build_hunter_alias_issue/hunterroot/_Base/9a3594a/511a137/48401e9/Install/lib/cmake/ZLIB/ZLIBConfig.cmake:36 (add_library):
  add_library cannot create ALIAS target "ZLIB::ZLIB" because target
  "ZLIB::zlib" is IMPORTED.
Call Stack (most recent call first):
  CMakeLists.txt:36 (find_package)
```


