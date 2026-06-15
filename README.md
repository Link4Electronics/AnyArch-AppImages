## **AnyArch AppImages**

![Downloads](https://img.shields.io/endpoint?url=https://cdn.jsdelivr.net/gh/Link4Electronics/AnyArch-AppImages@main/.github/badge.json)

Designed to run seamlessly on any Linux distribution, including very very old distributions and musl-based ones. Our AppImages bundle all the needed dependencies and do not depend on host libraries to work, unlike most other AppImages, **all while being significantly smaller thanks to [DwarFS](https://github.com/mhx/dwarfs) and [optimized packages](https://github.com/pkgforge-dev/archlinux-pkgs-debloated)**.

Most of the AppImages are made with [sharun-C](https://github.com/Link4Electronics/sharun-C). We also use an alternative better [uruntime-C](https://github.com/Link4Electronics/uruntime-C).

The uruntime [automatically falls back to using namespaces](https://github.com/Link4Electronics/uruntime-C?tab=readme-ov-file#built-in-configuration) if FUSE is not available at all, and if namespaces are not possible it falls back to extract and run, so we **truly have 0 requirements:**

| Format | Requirements |
| --- | --- |
| Traditional AppImages (made by linuxdeploy or similar tools) | **Hard dependency on glibc** (rarely works on distros older than 4 years), also has a soft dependency on **FUSE** since the user has to manually extract when FUSE is unavailable, they also need an FHS compliant system to work. |
| Flatpak | **Hard dependency on bubblewrap and FUSE**. Must be supported by your distribution or be manually built and installed systemwide which requires elevated rights. |
| Snap | Similar requirements to flatpak minus bubblewrap, has a **hard dependency on systemd**. |
| **AnyArch AppImages** (made with sharun) | Use **FUSE if available**, else **fallback to using namespaces** and if that is not possible then we automatically extract to `TMPDIR` and run with post cleanup, we **do not need an FHS filesystem** and **do not depend on the host libc**, so eh make sure you have `/bin/sh` and write access to `/tmp`??? (If you can boot to a graphical session you already met those requirements). **How is this possible?** See: [How to guide](https://github.com/Link4Electronics/AnyArch-AppImages/blob/main/HOW-TO-MAKE-THESE.md) |
| **AnyLinux AppImages** (made with RunImage) | Similar to sharun AppImages but have a **Hard dependency on namespaces**, Lutris and virt-manager are the only ones that use this method, pending migration to sharun. |

For more useful documentation about Anylinux-AppImages, see the pages below:

- [FAQ](FAQ.md)
- [How to make these](HOW-TO-MAKE-THESE.md)
- [Size comparison](disk-usage-vs-flatpak.md)
- [Build tools and scripts](useful-tools/)
- [appimagetool-C](https://github.com/Link4Electronics/appimagetool-C)

<!-- APPS_LIST_START -->

---

| Applications |
| --- |
| [12to11](https://github.com/Link4Electronics/12to11-AppImage) |
| [ZSNES](https://github.com/Link4Electronics/ZSNES-AppImage) |

---

<!-- APPS_LIST_END -->

---

**Didn't find what you were looking for?** Open an issue [here](https://github.com/Link4Electronics/AnyArch-AppImages/issues) and we will see what we can do.
