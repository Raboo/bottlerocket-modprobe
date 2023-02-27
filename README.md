# bottlerocket-modprobe

Bootstrap container for bottlerocket-os (v1.13 or later) that can execute modprobe against fixed set of modules (<https://github.com/bottlerocket-os/bottlerocket/issues/2409#issuecomment-1443369565>).

I guess this is a temporary work-around until someone adds support for loading kernel modules directly from the user-data context or something.

All modules are listed here <https://github.com/Raboo/bottlerocket-modprobe/pkgs/container/bottlerocket-modprobe>.
The image tags specifies which module it loads.

Example:  
Use this as user-data to load the ip_vs_lc module.

```ini
[settings.bootstrap-containers.bootstrap]
source = "ghcr.io/raboo/bottlerocket-modprobe:ip_vs_lc"
mode = "always"
essential = true
```

Note that I haven't tested this yet since bottlerocket-os v1.13 hasn't been released yet. Also I have tried to build multi-arch builds for amd64, arm64 and arm but I haven't tested that part either.
