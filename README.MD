# Git Tricks
Useful Git tricks found in the internet.

## Cherry-pick from different remote
```sh
$ git --git-dir=../<some_other_repo>/.git \
format-patch -k -1 --stdout <commit SHA> | \
git am -3 -k
```
### Note
> git format-patch command creates a patch from some_other_repo's commit specified by its SHA (-1 for one single commit alone). This patch is piped to git am, which applies the patch locally (-3 means trying the three-way merge if the patch fails to apply cleanly).


Ref: [URL](https://stackoverflow.com/a/9507417)