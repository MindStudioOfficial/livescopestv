<div style="background-color: #0a0c10;padding:40px "><img src="blob/LiveScopesTV_Logo_full_white.png"></img></div>
<h2 align="center"> <b>LiveScopes.tv</b></h1>
<p align="center">
<a href="https://ndi.tv">NDI®</a> enabled windows tool for <a href="https://github.com/MindStudioOfficial/livescopestv#waveformsscopes">Waveforms/Scopes</a>
</p>


<div align="center">

<a href="https://github.com/MindStudioOfficial/livescopestv/releases">
<img src="https://img.shields.io/github/downloads-pre/MindStudioOfficial/livescopestv/total?style=flat&label=Downloads"></a>
<a href="https://github.com/MindStudioOfficial/livescopestv/releases">
<img src="https://img.shields.io/github/downloads-pre/MindStudioOfficial/livescopestv/latest/total?style=flat&label=Downloads@latest"></a>

</div>
<div align="center">

<a href="https://github.com/MindStudioOfficial/livescopestv/releases">
<img src="https://img.shields.io/github/v/release/MindStudioOfficial/livescopestv?style=flat&include_prereleases&label=Version"></a>


</div>
<div align="center">

<a href="https://github.com/MindStudioOfficial/livescopestv">
<img src="https://img.shields.io/github/stars/MindStudioOfficial/livescopestv?style=flat"></a>
<a href="https://github.com/MindStudioOfficial/livescopestv">
<img src="https://img.shields.io/github/watchers/MindStudioOfficial/livescopestv?style=flat"></a>

</div>
<div align="center">
<a href="https://reddit.com/r/livescopestv">
<img alt="Subreddit subscribers" src="https://img.shields.io/reddit/subreddit-subscribers/livescopestv?label=r%2Flivescopestv&style=social">
</a>
</div>
<br>

![Screenshot](blob/sc7.jpg)

| Luminance: ![Luma Waveform](blob/sc_luma.jpg)                      | RGB Overlayed: ![RGB Waveform](blob/sc_rgb.jpg)                      | RGB Parade: ![RGB Parade](blob/sc_rgbParade.jpg)                        |
| ------------------------------------------------------------------ | -------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **15% RGB Blacklevel:**  ![Black Level](blob/sc_blacklevel.jpg)    | **YCbCr Parade:** ![YUV Parade](blob/sc_yuvparade.jpg)               | **YUV Vectorscope:** ![Vectorscope](blob/sc_vectorscope.jpg)            |
| **With Alpha background:**  ![Alpha Background](blob/sc_alpha.jpg) | **Without Alpha Background:**![Alpha Background](blob/sc_alpha2.jpg) | **Audiometers dBu:** <br><img src="blob/sc_audiometers.jpg" height=200> |

| False Color: ![False Color](blob/sc_falseColor2.jpg) | Splitscreen:![Splitscreen](blob/sc_splitscreen.jpg) |
| ---------------------------------------------------- | --------------------------------------------------- |

## Requirements

The software uses **CUDA** to compute the frames and scopes. A **NVIDIA GPU** is required to run this software. See [GPU Support](https://github.com/MindStudioOfficial/livescopestv#gpu-support) to see exaxtly what GPUs are supported.

- OS: 
  | Windows | Tested |
  | ------- | ------ |
  | 11      | ✔      |
  | 10      | ✔      |
- CPU: x64, >= 4 Cores
- GPU: See [GPU Support](https://github.com/MindStudioOfficial/livescopestv#gpu-support)
- RAM: Software uses at max 2GB (rarely)
- NVIDIA Driver: >= 452.39 (522.06 recommended)
- Networking: NDI® works best on a wired >=1GBit/s ethernet link.

## Platform Support

![Windows](https://upload.wikimedia.org/wikipedia/commons/thumb/4/48/Windows_logo_-_2012_%28dark_blue%29.svg/88px-Windows_logo_-_2012_%28dark_blue%29.svg.png)

## Features

### Waveforms/Scopes
- [x] Luminance Waveform
- [x] RGB Waveform
- [x] RGB Parade
- [x] CbCr/UV Vectorscope
- [x] False Color
- [x] YUV Parade
- [x] CIE 1931 Chromaticity
- [x] RGBA Channel Isolation

### Settings
- [x] Scale vectorscope x0.5 to x5
- [x] Toggle waveform scale labels
- [x] Waveform scale as percentage
- [x] Waveform scale as 8Bit value
- [x] Save and load settings on startup
- [x] Enable Audiometer 
- [x] Select Audio Device

### Audio
- [x] Audiometer for every audio channel of the NDI® source in dBu scale
- [x] Audio playback to default audio device (toggleable) 
- [x] Selectable audio device

### Other
- [x] Reference Frame
  - [x] Save/Load
  - [x] Overlay on source as splitscreen
  - [x] Overlay on scopes as splitscreen
  - [x] Show thumbnails in frame browser
- [x] Draw Masks on source frame
- [x] View Timecode
- [x] View Embeded Metadata
### NDI® Codec support
- [x] UYVY (most common, fastest)
- [x] BGRA (stills and alpha)

## Keyboard Shortcuts

- <kbd>A</kbd> Toggle `A`lpha Grid
- <kbd>B</kbd> Toggle Frame `B`rowser
- <kbd>C</kbd> Toggle False `C`olor
- <kbd>D</kbd> Toggle Split `D`irection
- <kbd>F</kbd> `F`lip Split Side
- <kbd>M</kbd> Toggle `M`ask
- <kbd>S</kbd> Select `S`ource
- <kbd>T</kbd> Toggle `T`imecode
- <kbd>X</kbd> Toggle Settings
- <kbd>+</kbd> Capture new Reference Frame
- <kbd>Del</kbd> Disable Reference Frame Overlay

(Feel free to suggest alternative shortcuts as a Feature Request Issue)

## GPU Support
NVIDIA Cards only:
  | CC      | Name                 | Cards                                                               | Compatible | Tested |
  | ------- | -------------------- | ------------------------------------------------------------------- | ---------- | ------ |
  | 9.0     | Hopper               | H100                                                                | ✔          | ?      |
  | 8.9     | Ada Lovelace         | RTX 40 Series, RTX 6000                                             | ✔          | ?      |
  | 8.0-8.7 | Ampere               | RTX 30 Series, RTX A Series                                         | ✔          | ✔      |
  | 7.x     | Volta/Turing         | RTX 20 Series, GTX 16 Series, Quadro RTX Series, TITAN RTX, TITAN V | ✔          | ✔      |
  | 6.x     | Pacal                | GTX 10 Series, Titan X, Quadro P Series                             | ✔          | ✔      |
  | 5.x     | Maxwell              | GTX 750 - GTX 980 Ti                                                | ✔          | ?      |
  | >= 3.5  | Kepler               | GT 640 - GTX 780 Ti, TITAN Z                                        | ✔          | ?      |
  | < 3.5   | Kepler, Fermi, Tesla |                                                                     | ❌          |        |

  

## Download

Download the latest version under [Releases](https://github.com/MindStudioOfficial/livescopestv/releases).


## License

[End User License Agreement](LICENSE.md)

## Author

developed by [**Marc Bach** _"MindStudio"_](https://github.com/MindStudioOfficial/)

<hr> 

*NDI® is a registered trademark of Vizrt Group.*