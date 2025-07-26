# waipu-tv-4k-stick
A repo for the popular waipu tv 4k stick

## Specifications
### Core Hardware
* **Model**: waipu.tv 4K Stick
* **Processor (CPU)**: Amlogic S905Y4 (Quad-Core Cortex-A35)
* **RAM**: 2 GB DDR
* **Internal Storage**: 8 GB eMMC

---

### Software
* **Operating System**: Android 11 for Android TV (at launch)

---

### Audio & Video
* **Video Resolution**: 4K, 1080p/i, 720p, HDR
* **Video Codecs**: H.265, H.264, VP9, AV1, AVS2-P2, MPEG-1/2/4 ASP, AVS+
* **Audio Codecs**: Dolby Digital Plus, MPEG-1/2/4, MP3, AAC/HE-AAC, FLAC, OGG

---

### Connectivity
* **Wi-Fi**: IEEE 802.11 b/g/n/ac (2.4 GHz & 5.0 GHz)
* **HDMI**: HDMI 2.1 with HDCP 2.2 support

---

### Power 🔌
* **Stick Input**: 5V / 1A
* **Power Consumption**: < 2.5W (in operation) | < 0.5W (standby)
* **Power Adapter**: Input: 220V | Output: 5V

## Firmware (OTA)

Firmware can be extracted by using [android-ota-payload-extractor](https://github.com/tobyxdd/android-ota-payload-extractor).

After extracting it, you will get:

* boot.img
* bootloader.img
* dtbo.img
* odm.img
* odm_ext.img
* product.img
* system.img
* system_ext.img
* vbmeta.img
* vbmeta_system.img
* vendor.img
* vendor_boot.img

v11.7.6958 [Download](https://android.googleapis.com/packages/ota-api/package/7c929e57d44207cd4065a12f26aa6fb301cc1e30.zip)

## Misc

This device contains a UART port, one is able to connect to it but not able to properly interact with it (probably locked down)
