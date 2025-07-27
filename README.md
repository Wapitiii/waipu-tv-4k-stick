# waipu-tv-4k-stick
A repo for the popular waipu tv 4k stick

## Specifications
### Core Hardware
* **Model**: waipu.tv 4K Stick
* **Processor (CPU)**: Amlogic S905Y4 (Quad-Core Cortex-A35) [Datasheet](https://dl.khadas.com/products/vim1s/datasheet/amlogic_s905y4_datasheet_v0.7.pdf)
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

### Power
* **Stick Input**: 5V / 1A
* **Power Consumption**: < 2.5W (in operation) | < 0.5W (standby)
* **Power Adapter**: Input: 220V | Output: 5V

---

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

---

## PCB Photos

Click on a title to expand, then click the image to see the full-resolution version.

<details>
  <summary>pcb_back_1.jpg</summary>
  <a href="/pcb-photos/pcb_back_1.jpg"><img src="/pcb-photos/pcb_back_1.jpg" alt="PCB Back 1" width="400"></a>
</details>
<details>
  <summary>pcb_back_2.JPG</summary>
  <a href="/pcb-photos/pcb_back_2.JPG"><img src="/pcb-photos/pcb_back_2.JPG" alt="PCB Back 2" width="400"></a>
</details>
<details>
  <summary>pcb_back_emmc_closeup.jpg</summary>
  <a href="/pcb-photos/pcb_back_emmc_closeup.jpg"><img src="/pcb-photos/pcb_back_emmc_closeup.jpg" alt="PCB eMMC Closeup" width="400"></a>
</details>
<details>
  <summary>pcb_front_1.jpg</summary>
  <a href="/pcb-photos/pcb_front_1.jpg"><img src="/pcb-photos/pcb_front_1.jpg" alt="PCB Front 1" width="400"></a>
</details>
<details>
  <summary>pcb_front_2.jpg</summary>
  <a href="/pcb-photos/pcb_front_2.jpg"><img src="/pcb-photos/pcb_front_2.jpg" alt="PCB Front 2" width="400"></a>
</details>
<details>
  <summary>pcb_front_3.JPG</summary>
  <a href="/pcb-photos/pcb_front_3.JPG"><img src="/pcb-photos/pcb_front_3.JPG" alt="PCB Front 3" width="400"></a>
</details>
<details>
  <summary>pcb_front_cpu_pinout_closeup_1.jpg</summary>
  <a href="/pcb-photos/pcb_front_cpu_pinout_closeup_1.jpg"><img src="/pcb-photos/pcb_front_cpu_pinout_closeup_1.jpg" alt="CPU Pinout Closeup 1" width="400"></a>
</details>
<details>
  <summary>pcb_front_cpu_pinout_closeup_2.jpg</summary>
  <a href="/pcb-photos/pcb_front_cpu_pinout_closeup_2.jpg"><img src="/pcb-photos/pcb_front_cpu_pinout_closeup_2.jpg" alt="CPU Pinout Closeup 2" width="400"></a>
</details>
<details>
  <summary>pcb_front_wifi_closeup.JPG</summary>
  <a href="/pcb-photos/pcb_front_wifi_closeup.JPG"><img src="/pcb-photos/pcb_front_wifi_closeup.JPG" alt="WIFI Closeup" width="400"></a>
</details>
<details>
  <summary>pcb_front_wifi_pinout_maybe_closeup.jpg</summary>
  <a href="/pcb-photos/pcb_front_wifi_pinout_maybe_closeup.jpg"><img src="/pcb-photos/pcb_front_wifi_pinout_maybe_closeup.jpg" alt="WIFI Pinout Maybe Closeup" width="400"></a>
</details>

---

## Misc

This device contains a UART port, one is able to connect to it but not able to properly interact with it (autoboot timer is not enabled)

The baud rate for the UART port is 921600, anything else will output garbled mess

The UART output (u-boot log) can be found here: [uart_output.txt](/uart/uart_output.txt)

There are tools for a development board that uses the same processor, might be useful: https://dl.khadas.com/products/vim1s/

## U-Boot

u-boot's CONFIG_AUTOBOOT_DELAY is probably set to -2, so that means we can't just interrupt the boot sequence and enter the u-boot shell, for that we would require to do fault-injection to the eMMC DAT0 point to bring us to the u-boot shell.

The eMMC's DAT0 point can be found in the Datasheet provided in Specifications, one might be able to make a flexible pcb like the one thats used for the nintendo switch oled's eMMC for modding it or just hold a thin needle at the point which should also work. With that it should be able to short it successfully and bring us to u-boot shell.

That still doesn't mean we would have access, SEI Robotics could've added a password to the u-boot shell.

More information about AML secure boot and dumping of u-boot and such can be found in this blog post about another amlogic based device: https://oddsolutions.github.io/Pixel-Tablet-Dock-Secure-Boot-Bypass/
