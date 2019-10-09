Hunter ALIAS target issue demo with older cmake versions.
===

cmake versions lower than 3.11 do not support ALIAS of imported targets that are now used by Hunter. 

Hunter documentation needs to be updated to indicate:

```
cmake_minimum_required(VERSION 3.11)
```

Quick test:
```
cd /tmp && \
rm -rf hunterbugtest && \
mkdir -p hunterbugtest && \
cd hunterbugtest && \
git clone https://github.com/hunterdevel/hunter_alias_issue.git && \
mkdir -p build_hunter_alias_issue && \
cd build_hunter_alias_issue && \
cmake ../hunter_alias_issue; cd /tmp
```

Example error (cmake <3.11):
```
tmp/hunterbugtest/build_hunter_alias_issue/hunterroot/_Base/9a3594a/511a137/48401e9/Install/lib/cmake/ZLIB/ZLIBConfig.cmake:36 (add_library):
  add_library cannot create ALIAS target "ZLIB::ZLIB" because target
  "ZLIB::zlib" is IMPORTED.
Call Stack (most recent call first):
  CMakeLists.txt:36 (find_package)
```
