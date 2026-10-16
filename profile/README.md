<h1 align="center">Flourite</h1>

<p align="center">
  <strong>LineageOS 24</strong> &nbsp; / &nbsp; <strong>Google ACK 6.1</strong> &nbsp; / &nbsp; <strong>Source-built kernel</strong>
</p>

<p align="center">
  <strong>One device family. One maintainer. Open development.</strong><br>
  I develop and maintain LineageOS for <strong>POCO M8 Pro 5G</strong> and <strong>Redmi Note 15 Pro+ 5G</strong>.<br>
  Device codename: <code>flourite</code> · Platform: <code>SM7635 / volcano</code>
</p>

<p align="center">
  <a href="https://github.com/xiaomi-flourite-sm7635/android_device_xiaomi_flourite#readme">Device tree</a> &nbsp;·&nbsp;
  <a href="https://github.com/xiaomi-flourite-sm7635/android_kernel_xiaomi_flourite-build#readme">Kernel build guide</a> &nbsp;·&nbsp;
  <a href="https://github.com/xiaomi-flourite-sm7635/firmware_xiaomi_flourite/releases">Firmware dumps</a>
</p>

---

## What I'm building

<table>
  <tr>
    <td width="33%" valign="top">
      <h3>Source-built kernel</h3>
      <p>Google Android Common Kernel 6.1, with device drivers, modules, DTB and DTBO compiled as part of the ROM.</p>
    </td>
    <td width="33%" valign="top">
      <h3>Xiaomi Parts</h3>
      <p>Device controls in one place: manual CPU/GPU tuning, battery and thermal information, and selectable TCP algorithms.</p>
    </td>
    <td width="33%" valign="top">
      <h3>Xiaomi Camera</h3>
      <p>MiCamera 6.7 integration with Flourite-specific configuration, extraction fixes and matching proprietary libraries.</p>
    </td>
  </tr>
</table>

I bring together LineageOS power management, device-specific hardware support
and variant-aware configuration for the POCO and Redmi family.

> **Independently maintained, not an official LineageOS release.** Development and
> testing are ongoing; behavior can differ between hardware variants.
> The kernel is built from source, but Android vendor components, Xiaomi Camera
> and device firmware still require proprietary files.

## Explore the sources

### Device & camera

| Repository | What's inside |
| :--- | :--- |
| [Device tree](https://github.com/xiaomi-flourite-sm7635/android_device_xiaomi_flourite) | ROM configuration, Xiaomi Parts, power hints, overlays, SELinux policy and vendor extraction. |
| [Xiaomi Camera integration](https://github.com/xiaomi-flourite-sm7635/android_device_xiaomi_flourite-miuicamera) | App patches, permissions, overlays and extraction rules. |
| [Xiaomi Camera vendor](https://github.com/xiaomi-flourite-sm7635/android_vendor_xiaomi_flourite-miuicamera) | The matching proprietary app and libraries. |
| [Qualcomm audio HAL](https://github.com/xiaomi-flourite-sm7635/android_hardware_qcom_audio-ar) | Audio HAL sources used by the device. |
| [Stock firmware dumps](https://github.com/xiaomi-flourite-sm7635/firmware_xiaomi_flourite) | Global and Chinese extraction inputs, checksums and reproduction instructions. |

### Kernel & build

| Repository | What's inside |
| :--- | :--- |
| [Kernel](https://github.com/xiaomi-flourite-sm7635/android_kernel_xiaomi_sm7635) | Google ACK-based kernel with Flourite support and CPU/TCP controls. |
| [Hardware modules](https://github.com/xiaomi-flourite-sm7635/android_kernel_xiaomi_sm7635-modules) | Device modules built from source, including GPU controls. |
| [Device trees](https://github.com/xiaomi-flourite-sm7635/android_kernel_xiaomi_sm7635-devicetrees) | Hardware descriptions used to build DTB and DTBO. |
| [Kernel build integration](https://github.com/xiaomi-flourite-sm7635/android_kernel_xiaomi_flourite-build) | Build scripts, toolchain requirements and a manifest with pinned source revisions. |

<details>
  <summary><strong>Looking for the old prebuilt kernel?</strong></summary>

The [prebuilt repository](https://github.com/xiaomi-flourite-sm7635/android_device_xiaomi_flourite-kernel)
contains the earlier stock kernel, modules and DTBO. It is not required by the
current source-kernel build. Use the kernel repositories above for new builds.

</details>

## Build & contribute

1. Start with the [device tree build instructions](https://github.com/xiaomi-flourite-sm7635/android_device_xiaomi_flourite#build).
2. Follow the [kernel build guide](https://github.com/xiaomi-flourite-sm7635/android_kernel_xiaomi_flourite-build#lineage-build) and use its pinned manifest so the kernel, modules and device trees match.
3. Extract the required proprietary files from the [documented firmware sources](https://github.com/xiaomi-flourite-sm7635/firmware_xiaomi_flourite#readme). Add the camera repositories if building with MiCamera.

I welcome small, focused contributions. When reporting a problem, include the exact
device variant, ROM build, kernel version and steps to reproduce it. Remove
personal information from logs before sharing them publicly.

> **Firmware dumps are extraction inputs, not installable ROM updates.**
> Follow the device-specific instructions; do not flash arbitrary partitions
> from a different variant.

---

<p align="center">
  Developed and maintained independently.<br>
  <sub>Based on upstream work from LineageOS, Google, Qualcomm and Xiaomi.</sub>
</p>
