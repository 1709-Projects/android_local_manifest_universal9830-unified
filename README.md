Unified manifest - Samsung Exynos 9830
======================================

One ROM for the whole Exynos 9830 family. The phone identifies itself as
**Samsung Universal9830**; the real variant is detected at boot.

Supported devices
-----------------
| Codename | Device | Model |
|----------|--------|-------|
| x1s | Galaxy S20 5G | SM-G981B |
| y2s | Galaxy S20+ | SM-G986B |
| z3s | Galaxy S20 Ultra | SM-G988B |
| r8s | Galaxy S20 FE | SM-G780F |
| c1s | Galaxy Note20 | SM-N980F |
| c2s | Galaxy Note20 Ultra | SM-N986B |

Usage
-----
Local manifest (adds the two unified repositories to an existing LineageOS 24
checkout):

```
mkdir -p .repo/local_manifests
cp universal9830-local.xml .repo/local_manifests/
repo sync -c -j$(nproc) --force-sync
```

Or use `universal9830-full.xml` as the only manifest of a minimal checkout.

Build
-----
```
source build/envsetup.sh
brunch universal9830
```

The resulting zip is `lineage-24.0-*-UNOFFICIAL-universal9830.zip`.

Note
----
The kernel lives outside these repositories. Per-device kernel config
fragments (`x1s.config`, `y2s.config`, ...) and the DTBO config are handled by
the kernel backport tree.
