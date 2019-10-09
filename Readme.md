Hunter ALIAS target issue demo with old cmake.
===

cmake versions < 3.11 do not support ALIAS of imported targets that are now used by Hunter. 

Hunter documentation needs to be updated to indicate:

```
cmake_minimum_required(VERSION 3.11)
```
