# 固件

[English](README.md) | [简体中文](README_ZH.md)

ESP32-S3-Touch-AMOLED-2.41 V1 和 V2 的出厂 BIN。请按开发板硬件版本选择文件，V1 与 V2 固件不能混用。两份 BIN 均保留原文件名和内容。

| 硬件版本 | 文件 | 用途 |
| --- | --- | --- |
| V2（PCB 标识 Rev2.0） | [ESP32-S3-Touch-AMOLED-2.41-V2_FactoryOnly_20260601.bin](ESP32-S3-Touch-AMOLED-2.41-V2_FactoryOnly_20260601.bin) | V2 出厂固件，恢复开箱演示 |
| V1（旧版开发板） | [ESP32-S3-Touch-AMOLED-2.41-Factory.bin](ESP32-S3-Touch-AMOLED-2.41-Factory.bin) | 从 V1 仓库保留的原出厂固件 |

以上文件均为从 `0x0` 烧录的合并镜像。将 `<PORT>` 替换为串口，将 `<FIRMWARE.bin>` 替换为上表中对应硬件版本的文件名：

```bash
python -m pip install esptool
esptool.py --chip esp32s3 --port <PORT> erase_flash
esptool.py --chip esp32s3 --port <PORT> write_flash 0x0 <FIRMWARE.bin>
```

[`examples/factory`](../examples/factory/README_ZH.md) 中的出厂程序源码仅适用于 V2。V1 仅保留出厂 BIN，不包含 V1 示例和出厂程序源码。
