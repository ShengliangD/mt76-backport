mt76x2u and mt7921u driver backported from Linux 5.19 for Linux 5.10.

# Motivation

I wanted to use a WiFi 6 USB adapter (CF-953AX) on Jetson Xavier NX, but the corresponding driver is not available in the Linux 5.10 kernel that comes with JetPack 5.0.
Compiling a newer kernel for Jetson without breaking GPU drivers may require a lot of work, so I decided to backport the driver to the 5.10 kernel.
This repo could also be used on other platforms that run Linux 5.10.
Enjoy the 500+Mbps WiFi 6 speed!

# Usage

1. Prepare your kernel source tree of Linux 5.10.
  For Jetson boards, it is recommended to follow the [official guide](https://docs.nvidia.com/jetson/archives/r35.1/DeveloperGuide/text/SD/Kernel/KernelCustomization.html#kernel-customization).
2. Replace `drivers/net/wireless/mediatek/mt76` with this folder.
3. Adjust your kernel config to include mt76x2u and mt7921u, and exclude other mt76 drivers since I have not backported them yet.
