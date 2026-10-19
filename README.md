# Nubia X (NX616J) — LOS 22.2 / Android 15 BPF kernel work

This repository is the build workspace for a Nubia X (NX616J, Snapdragon 845) kernel based on the LineageOS 22.2 kernel tree.

## Baseline

- Kernel source: https://github.com/LineageOS/android_kernel_nubia_sdm845/tree/lineage-22.2
- Device tree: https://github.com/LineageOS/android_device_nubia_nx616j/tree/lineage-22.2
- Common device tree: https://github.com/LineageOS/android_device_nubia_sdm845-common/tree/lineage-22.2
- Xiaomi SDM845 kernel is a reference only; device-specific Xiaomi changes must not be copied wholesale.

## Current status

The upstream Nubia SDM845 lineage-22.2 config already enables core Android BPF-related options including CONFIG_CGROUP_BPF, CONFIG_BPF_SYSCALL, CONFIG_NETFILTER_XT_MATCH_BPF, CONFIG_INET_UDP_DIAG, and CONFIG_NET_CLS_BPF. The workflow checks the resulting config and builds the kernel artifact.

This initial setup does not claim that newer BPF source patches have been merged or that a bootable boot.img has been produced. BPF source changes must be reviewed against the 4.9 kernel before being applied. A matching NX616J boot image is also needed to repack a device-specific boot.img safely.

## Build

Open Actions → Build NX616J kernel and run the workflow manually. The output Image.gz-dtb is uploaded as an artifact if the build succeeds.

Do not flash an untested image. Keep a copy of the known-good boot image and recovery path.
