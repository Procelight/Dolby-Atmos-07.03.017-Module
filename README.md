# Dolby-Atmos-07.03.017-Module
Systemless Magisk / KernelSU module for Motorola Dolby Atmos (v07.03.017) on AOSP custom ROMs.
# Motorola Dolby Atmos (`07.03.017`) — Stable Module

A systemless audio mod that brings **Motorola's Dolby Atmos (`v07.03.017`)** sound engine and equalizer UI to AOSP-based custom ROMs for richer stereo separation, bass boost, and spatial audio.

---

## ✨ Features
- Official Motorola Dolby Atmos (`07.03.017`) equalizer & spatial audio UI
- Custom sound profiles (**Smart Audio**, **Music**, **Movie**, **Game**, **Podcast**, and **Custom 10-band EQ**)
- Systemless integration via **Magic Mount (`magic_mount_rs`)**
- Works for both built-in stereo speakers and wired/Bluetooth headphones

---

## 📋 Requirements & Compatibility
- **Root:** KernelSU / KernelSU Next, APatch, or Magisk v24.0+
- **Mount Metamodule (Required for KernelSU / APatch):** **`magic_mount_rs`** (`meta-magic_mount-rs`) must be installed and active so system/vendor audio libraries and XMLs mount properly without OverlayFS conflicts.
- **Tested On:** **Android 16 QPR2** (AOSP / Pixel-based custom ROMs)
- **Architecture:** `arm64-v8a`
- **Important:** Remove or disable any other audio mods (ViPER4Android, JamesDSP, Dirac, or older Dolby modules) before flashing to prevent audio server crashes or bootloops.

---

## 📥 Download
Grab the latest `.zip` module from the **[Releases](../../releases)** page.

---

## 🛠️ Installation Guide
1. Ensure **`magic_mount_rs`** is already installed and active (if using KernelSU / KernelSU Next / APatch).
2. Download `Dolby_Atmos_07.03.017_Stable_Module.zip` from **Releases**.
3. Open **KernelSU** / **APatch** / **Magisk** → go to **Modules** → **Install from storage**.
4. Select the downloaded `.zip` file and wait for flashing to complete.
5. **Reboot** your device.
6. Open the **Dolby Atmos** app from your app drawer (or via **Settings > Sound & vibration > Dolby Atmos**) and configure your sound profile.

---

## ⚠️ Troubleshooting & Notes
- **Module not mounting / App crashing on boot:** Make sure **`magic_mount_rs`** is active and no conflicting metamodules (`meta-overlayfs` without magic rules) are blocking the mount.
- **App icon missing from app drawer:** Access Dolby Atmos through **Settings > Sound & vibration**, or add the **Dolby Atmos Quick Settings tile** from your notification shade.
- **No audio processing:** Disable **AudioFX / MusicFX** in `Settings > Apps` (show system apps) if your ROM includes it.
- **Bootloop Recovery:** Boot into Safe Mode or delete the module folder inside `/data/adb/modules/` via custom recovery.

---

## 🙏 Credits
- Motorola Mobility for the original Dolby Atmos (`07.03.017`) system files
- `magic_mount_rs` developers & Android audio modding community
- 
