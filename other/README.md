# Other


## libguestfs testing thing

Play with these lines:

```
ENV SUPERMIN_KERNEL=/boot/vmlinuz-linux
ENV SUPERMIN_MODULES=/lib/modules/5.12.14-arch1-1
ENV SUPERMIN_KERNEL_VERSION=5.12.14-arch1-1
ENV KERNEL_PACKAGE_URL=https://archive.archlinux.org/packages/l/linux/linux-5.12.14.arch1-1-x86_64.pkg.tar.zst
ENV KERNEL_HEADERS_PACKAGE_URL=https://archive.archlinux.org/packages/l/linux/linux-headers-5.12.14.arch1-1-x86_64.pkg.tar.zst
ENV LIBGUESTFS_PACKAGE_URL=https://archive.archlinux.org/packages/l/libguestfs/libguestfs-1.44.1-6-x86_64.pkg.tar.zst
```

```bash
docker build -f Dockerfile.libguestfs .
```