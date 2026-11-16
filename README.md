# Dell PowerEdge T40 — EFI OpenCore

EFI OpenCore 1.0.9 (DEBUG) yang disiapkan untuk instalasi macOS 15 Sequoia pada Dell PowerEdge T40. Salinan ini berasal dari konfigurasi instalasi berbasis pemindaian ACPI setelah perubahan ke AHCI. macOS berhasil dipasang pada mesin sumber. Konfigurasi aktif setelah instalasi dan pemasangan driver belum dibandingkan dengan salinan ini.

| Komponen | Konfigurasi mesin sumber |
| --- | --- |
| Chipset | Intel C246 |
| CPU | Intel Xeon E-2224G (Coffee Lake-S) |
| GPU | GeForce GTX 1650 SUPER dan Intel UHD Graphics P630 |
| Ethernet | Intel I219-LM |
| Firmware | UEFI, SATA AHCI |
| Monitor saat instalasi | Acer K202HQL |

## Menggunakan EFI

1. Cadangkan EFI yang sedang digunakan sebelum menguji salinan ini.
2. Isi `SystemSerialNumber`, `MLB`, `SystemUUID`, dan `ROM` pada `EFI/OC/config.plist` → `PlatformInfo` → `Generic` dengan identitas sendiri. Nilai identitas mesin sumber sudah dibersihkan. Pertahankan model SMBIOS yang tercantum saat membuat identitas baru.
3. Validasi konfigurasi dengan `ocvalidate` dari OpenCore 1.0.9. Salin folder `EFI` ke partisi EFI yang ditujukan untuk OpenCore.
4. Untuk mencoba akselerasi GTX 1650 SUPER, ikuti dokumentasi NullMoth setelah macOS bisa boot. Paket ini berisi konfigurasi boot. Driver macOS dan berkas instalasi Apple tersedia dari sumbernya masing-masing.

Pada mesin sumber, monitor menampilkan `Input Not Supported` setelah beralih ke 1080p. Gunakan resolusi bawaan monitor saat pengujian awal.

## Sumber komponen

- [OpenCorePkg](https://github.com/acidanthera/OpenCorePkg) dan [OcBinaryData](https://github.com/acidanthera/OcBinaryData)
- [1401](https://github.com/nullmoth/1401) dan [NullMoth NVIDIA Driver](https://github.com/nullmoth/nvidia-macos-driver)
- [OpCore Simplify](https://github.com/lzhoang2801/OpCore-Simplify) dan [USBToolBox](https://github.com/USBToolBox/kext)
- [Panduan OpenCore Dortania](https://dortania.github.io/OpenCore-Install-Guide/)

Berkas OpenCore, driver UEFI, dan kext mengikuti lisensi dan pemberitahuan hak cipta masing-masing proyek.
