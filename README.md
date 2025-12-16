# Speech Note Custom Models

This repository contains a custom `models.json` configuration file for the [Speech Note](https://github.com/mkiol/dsnote) application.

## Motivation

The default models provided with Speech Note use `q5_0` quantization (5-bit quantization). On some hardware configurations, this aggressive quantization may not provide significant performance benefits over higher-precision models like 16-bit floating-point (`FP16`) or 8-bit quantization (`q8_0`), while potentially reducing accuracy.

This repository provides a configuration that includes `FP16` and `q8_0` variants of WhisperCpp models, allowing users to choose the precision level that works best for their specific hardware and accuracy requirements.

## Contents

This repository contains a `models.json` file that adds the following WhisperCpp model variants to Speech Note:

- **FP16 variants** (16-bit floating-point):
  - English: Small, Medium, Distil Medium, Distil Large-v3.5, Large-v3, Large-v3 Turbo
  - Multilingual (Large-v3, Large-v3 Turbo) - also available for Russian and French
  
- **q8_0 variants** (8-bit quantization):
  - English: Small, Medium

## How to Use

To use the custom models defined in this repository, you need to replace the `models.json` file in your Speech Note configuration directory with the one from this repository.

1.  Clone this repository or download the `models.json` file.
2.  Locate the Speech Note data directory on your system.
    *   It is typically at `~/.local/share/net.mkiol/dsnote/`.
    *   For Flatpak at `~/.var/app/net.mkiol.SpeechNote/data/net.mkiol/dsnote/`.
3.  Backup your existing `models.json` file.
4.  Copy the `models.json` file from this repository to the Speech Note data directory.
5.  Restart Speech Note.

The new models should now be available in the model selection menu.

For more details on how to add custom models to Speech Note, please refer to the [official documentation](https://github.com/mkiol/dsnote#how-to-enable-a-custom-model).
