# aur
Sick Codes AUR Packages

[https://aur.archlinux.org/packages/?K=sickcodes&SeB=m](https://aur.archlinux.org/packages/?K=sickcodes&SeB=m)

Contact methods:

[DM on Twitter](https://twitter.com/sickcodes)

[Sick.Codes Contact Form](https://sick.codes)

```bash
# internal use only:

# update .SRCINFO
makepkg --printsrcinfo > .SRCINFO

# patch
git format-patch -1 HEAD

# makepkg clean
makepkg -sci
```


```bash
cd /tmp
PACKAGE=libguestfs-dev
rm -rf /tmp/aur
cd /tmp
git clone https://github.com/sickcodes/aur
cd "aur/${PACKAGE}"
PARENT_COMMIT="$(git log --branches -1  --pretty=format:"%H"  | tail -n1)"
git clone "https://aur.archlinux.org/${PACKAGE}.git" "./.${PACKAGE}"
cp -rf * "./.${PACKAGE}/"
cd "./.${PACKAGE}/"
makepkg --printsrcinfo > .SRCINFO

git remote add label "ssh://aur@aur.archlinux.org/${PACKAGE}.git"
git fetch --all
git add .SRCINFO PKGBUILD
git ls-files --modified | xargs git add
git status
git commit -m "Update to https://github.com/sickcodes/aur/commit/${PARENT_COMMIT}"
# git checkout -b label

GIT_SSH_COMMAND='ssh -i ~/.ssh/id_aur' git push label master
```


