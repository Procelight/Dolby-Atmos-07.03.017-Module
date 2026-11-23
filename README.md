# 🎧 Dolby Atmos + Spatial Sound 3D Bundle (by Procelight)

> # ⚠️ DO NOT FLASH THIS ZIP DIRECTLY!
> **This archive is a bundle containing two separate modules.** Flashing this parent `.zip` directly in Magisk, KernelSU, or APatch will fail. 
> **You MUST extract this zip first**, then flash the two individual `.zip` files inside separately.

---

## 📦 What's Inside the Archive?

1. **Dolby Atmos Stable (by Procelight)** – Core audio engine and updated UI.
2. **Spatial Sound 3D Add-on** – Companion module for virtualized 3D surround depth.

---

## ✨ User Changelog & Highlights

This isn't a blind re-upload; the core package has been reworked for modern Android builds:

* **Updated Dolby UI Application:** Integrated the latest Dolby Atmos user interface for smoother controls and updated visual layout.
* **Magic Mount RS Architecture:** Migrated away from legacy mounting to **Magic Mount RS**, ensuring cleaner systemless injection and better compatibility on newer Android 16+ QPR builds without bootloops or broken overlays.
* **Tested On:** Motorola Moto G54 5G (PixelOS17) Android 17 qpr0
* **Native Spatial Sound Hook:** Patched the audio routing and policy flags so the core Dolby service communicates seamlessly with the Spatial Sound add-on.
* **Spatial Sound 3D Add-on:** Packaged alongside the main module to unlock 3D head-tracking/spatial virtualization capabilities on supported stereo/wired/Bluetooth outputs.

---

## 🛠️ Developer & Technical Notes

For ROM maintainers and module developers inspecting the internals, here is what was modified under the hood compared to older ports:

* **Mount Mechanics:** Replaced standard Magisk mirror/overlay mounting logic with `Magic Mount RS` scripts to handle read-only `/vendor` and `/system_ext` partitions cleanly on modern A/B devices.
* **System & Vendor Props (`system.prop`):** Adjusted `ro.vendor.dolby.*` and `persist.vendor.audio.*` flags to prevent session conflicts with AOSP `AudioFX` / `MusicFX` and to force-enable spatializer support (`ro.audio.spatializer_enabled=true`).
* **Audio Policy & Effects (`audio_effects.xml`):** Updated UUID bindings and library paths (`libswdap.so` / `libdlbpreg.so`) so the Spatializer HAL hooks into the Dolby post-processing chain without dropping down to 48kHz fallback.
* **SELinux & Permissions:** Cleaned up `sepolicy.rule` entries required for the newer UI APK to bind to `vendor.dolby.hardware.dms` without triggering silent denials.

---

## 📲 Installation Guide

1. **Extract** the downloaded `Dolby-Atmos-Proselight-AIO-Bundle.zip` using ZArchiver or your file manager.
2. Open **Magisk / KernelSU / APatch** and go to the **Modules** tab.
3. Flash the **Dolby Atmos Stable** zip first. *(Do not reboot yet)*
4. Flash the **Spatial Sound 3D Add-on** zip second.
5. **Reboot** your device.
6. *(Optional)* Disable or freeze built-in `AudioFX` / `MusicFX` if you notice any equalizer conflicts.

---

## 🙏 Credits & Acknowledgments

All core binaries and foundational reverse-engineering belong to their respective creators:

* **CREDITS:-**
* **Dolby Atmos Base:** [Night_wolf19 (Ravi-Kishor)](https://github.com/Ravi-Kishor) — *For the original Dolby Atmos base port and vendor libraries.*
* **Spatial Sound 3D Engine:** [Rei Ryuki (reiryuki)](https://github.com/reiryuki/Dolby-Atmos-Spatial-Sound-Moto-Edge-30-Ultra-Magisk-Module) — *Internal spatializer libraries and framework files sourced from Rei Ryuki's Moto Edge 30 Ultra Spatial Sound module.*
* **Rework, UI Update & Magic Mount RS Integration:** **Procelight**
