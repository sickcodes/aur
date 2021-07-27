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