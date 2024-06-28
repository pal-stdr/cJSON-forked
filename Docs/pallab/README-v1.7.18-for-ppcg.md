# v1.7.17-for-pluto
Specially prepared to integrate with Pluto. Added `configure.ac` and `Makefile.am` to handle the autoconf tool inside pluto.

## Prepare this `v1.7.18-for-ppcg` branch

### File Removal List

- Following things are not required. Later we are going to remove them with `git rm` command.
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

- Commands to remove.
```sh
git rm -r library_config/

git rm fuzzing/afl-prepare-linux.sh fuzzing/CMakeLists.txt fuzzing/afl.sh fuzzing/ossfuzz.sh .travis.yml appveyor.yml CMakeLists.txt Makefile test.c valgrind.supp
```


## How to add this `cJSON` repo in other git project as `submodule`

1.  Run the following command.
```sh
git submodule add -b v1.7.18-for-ppcg --name cJSON https://github.com/pal-stdr/cJSON-forked.git cJSON

# Returns
Cloning into '/path/to/parent-repo/cJSON'...
remote: Enumerating objects: 4120, done.
remote: Counting objects: 100% (81/81), done.
remote: Compressing objects: 100% (61/61), done.
remote: Total 4120 (delta 29), reused 59 (delta 17), pack-reused 4039
Receiving objects: 100% (4120/4120), 2.42 MiB | 5.26 MiB/s, done.
Resolving deltas: 100% (2659/2659), done.
```
**Explanation:**
You will see the `cJSON/` is cloned to your parent repo. There it will automatically create git `index` and the following snippet inside `.gitmodules` file. You don't have to do anything manually. Donot worry about all the dumped files in the `cJSON/` submodule. Those `cJSON/` submodule files will not be tracked by the parent git repo.

```sh
[submodule "cJSON"]
	path = cJSON
	url = https://github.com/pal-stdr/cJSON-forked.git
	branch = v1.7.18-for-ppcg
```

To be sure, if you give following command to check

```sh
git status

# Returns
On branch branch_name
Your branch is up to date with 'origin/how-to-setup-ppcg'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        modified:   .gitmodules
        new file:   cJSON
```



2. Then commit and push the changes in the parent repo. You are done.


