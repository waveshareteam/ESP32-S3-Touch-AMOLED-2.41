# Firmware

[English](README.md) | [简体中文](README_ZH.md)

Factory binaries for ESP32-S3-Touch-AMOLED-2.41 V1 and V2. Select the file for your board revision; V1 and V2 firmware is not interchangeable. Both binaries retain their original contents. Use the board revision in the table below to select the correct file.

| Board revision | File | Purpose |
| --- | --- | --- |
| V2 (PCB marked Rev2.0) | [ESP32-S3-Touch-AMOLED-2.41_FactoryOnly_20260601.bin](ESP32-S3-Touch-AMOLED-2.41_FactoryOnly_20260601.bin) | V2 factory firmware, restores the out-of-box demo |
| V1 (original board) | [ESP32-S3-Touch-AMOLED-2.41_FactoryOnly_20260506.bin](ESP32-S3-Touch-AMOLED-2.41_FactoryOnly_20260506.bin) | Original V1 factory firmware, retained from the V1 repository |

These are merged images flashed at `0x0`. Replace `<PORT>` with your serial port and `<FIRMWARE.bin>` with the file selected above:

```bash
python -m pip install esptool
esptool.py --chip esp32s3 --port <PORT> erase_flash
esptool.py --chip esp32s3 --port <PORT> write_flash 0x0 <FIRMWARE.bin>
```

The factory application source in [`examples/factory`](../examples/factory/) is for V2 only. V1 is provided as a binary only; V1 examples and factory application source are not included.
