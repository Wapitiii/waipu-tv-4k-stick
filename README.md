# waipu-tv-4k-stick
A repo for the popular waipu tv 4k stick

## Specifications
### Core Hardware
* **Model**: waipu.tv 4K Stick
* **Processor (CPU)**: Amlogic S905Y4 (Quad-Core Cortex-A35)
* **RAM**: 2 GB CXMT LPDDR4X SDRAM [Datasheet](https://lcsc.com/datasheet/lcsc_datasheet_2410121605_CXMT-CXDB4CBAM-MK-A_C20598565.pdf)
* **Internal Storage**: 8 GB eMMC FORSEE FEMDNN008G-08A39 [Datasheet](https://jlcpcb.com/api/file/downloadByFileSystemAccessId/8588886680569065472)

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
* **Wi-Fi**: IEEE 802.11 b/g/n/ac (2.4 GHz & 5.0 GHz) MEDIATEK MT7663BSN [Datasheet](https://mediatek-marketing.files.svdcdn.com/production/documents/MT7663BSN-Datasheet-Brief_v1.3.pdf?dm=1714749331)
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

v11.7.6958 [Download (Google OTA)](https://android.googleapis.com/packages/ota-api/package/7c929e57d44207cd4065a12f26aa6fb301cc1e30.zip) or [Download (Github)](https://github.com/Wapitiii/waipu-tv-4k-stick/releases/tag/v11.7.6958)

## Misc

This device contains a UART port, one is able to connect to it but not able to properly interact with it (probably locked down)

There are tools for a development board that uses the same processor, might be useful: https://dl.khadas.com/products/vim1s/
