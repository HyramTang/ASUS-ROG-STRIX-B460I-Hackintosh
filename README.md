# ASUS ROG STRIX B460I Hackintosh Open Core EFI

Open Core Hackintosh based on ASUS ROG Strix B460I GAMING

## EFI

OpenCore: 0.6.6

macOS Big Sur 11.4

## Screenshot

## Hardware

| Components  | Type                                                                                                                                                                                                                                                                                                  |
| ----------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Motherboard | [ASUS ROG STRIX B460-I GAMMING](https://rog.asus.com.cn/motherboards/rog-strix/rog-strix-b460-i-gaming-model)                                                                                                                                                                                         |
| CPU         | [Intel Core i5-10600](https://ark.intel.com/content/www/cn/zh/ark/products/199273/intel-core-i5-10600-processor-12m-cache-up-to-4-80-ghz.html)                                                                                                                                                        |
| GPU         | Intel UHD630                                                                                                                                                                                                                                                                                          |
| WiFi module | [Intel Wi-Fi 6 AX200](https://ark.intel.com/content/www/cn/zh/ark/products/189347/intel-wi-fi-6-ax200-gig.html)                                                                                                                                                                                       |
| RAM         | [Kingston HyperX FURY DDR4 2666 MHz 8GB*2](https://www.kingston.com/cn/gaming/hyperx-fury-ddr4)                                                                                                                                                                                                       |
| Storage     | [SAMSUNG 970 EVO Plus NVMe M.2](https://www.samsung.com/cn/memory-storage/nvme-ssd/970-evo-plus-nvme-m-2-500gb-mz-v7s500bw/) For Windows<br />[Western Digital WD_BLACK SN750 NVMe M.2](https://shop.westerndigital.com/zh-cn/products/internal-drives/wd-black-sn750-nvme-ssd#WDS500G3X0C) For macOS |


## Detail

### BIOS

### AHPI：SSDT

- SSDT-AWAC (enable the legacy RTC clock)
- SSDT-EC-USBX (Fix embedded controller)
- SSDT-PLUG (Power management)
- SSDT-RHUB (reset USB controller)

### Kext

- [AppleALC.kext](https://github.com/acidanthera/AppleALC) - Audio
- [FakePCIID.kext](https://github.com/RehabMan/OS-X-Fake-PCI-ID) and FakePCIID_Intel_HDMI_Audio.kext - Also needed for audio to work
- [IntelMausi.kext](https://github.com/acidanthera/IntelMausi) - Ethernet
- [Lilu.kext](https://github.com/acidanthera/Lilu) - Enables various patching
- [NVMeFix.kext](https://github.com/acidanthera/NVMeFix) - Better NVMe support
- [VirtualSMC](https://github.com/acidanthera/VirtualSMC) SMCProcessor.kext, SMCSuperIO.kext, VirtualSMC.kext - SMC emulator
- USB-Map.kext - Available from the kexts folder in this repo. This maps the 6 USB3 ports and the two internal ones used for Bluetooth and the Aura header. See USB section.
- [WhateverGreen.kext](https://github.com/Pavo-IM/AGPMInjector) - Various graphics related patches
- [XHCI-unsupported.kext](https://github.com/RehabMan/OS-X-USB-Inject-All) - There is a patched version of this in this repo. Needed for USB3 to work.
- [HibernationFixup.kext](https://github.com/acidanthera/HibernationFixup) - Added this back as it seems like my computer crashed when in sleep mode for more than 24h. Need more testing to see if this fixes it though.
- [AirportItlwm.kext](https://github.com/OpenIntelWireless/itlwm) - Intel Wi-Fi AX200 Drivers for macOS
- [USBInjectAll.kext](https://github.com/Sniki/OS-X-USB-Inject-All) - Kext to inject all USB ports for the installed Intel EHCI/XHCI chipset automatically.

### USB
### Benchmark