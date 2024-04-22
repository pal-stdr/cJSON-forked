# v1.7.17-for-pluto
Specially prepared to integrate with Pluto. Added `configure.ac` and `Makefile.am` to handle the autoconf tool inside pluto.

# File Removal List
- This is just for tracking purpose. YOU DONOT HAVE TO DO IT.
```sh
library_config/
fuzzing/afl-prepare-linux.sh
fuzzing/CMakeLists.txt
fuzzing/afl.sh
fuzzing/ossfuzz.sh
.travis.yml
appveyor.yml
CMakeLists.txt
Makefile
test.c
valgrind.supp
```

- Commands
```sh
git rm -r library_config/

git rm fuzzing/afl-prepare-linux.sh fuzzing/CMakeLists.txt fuzzing/afl.sh fuzzing/ossfuzz.sh .travis.yml appveyor.yml CMakeLists.txt Makefile test.c valgrind.supp
```