# Changelog

## [v1.0.0] 2023-01-29

### Changed
- ✍🏼 Changed software name from "NDIScopes" to "LiveScopes.tv"
- 🔖 Changed still file extension from ".ndis" to ".lsstill"
- 🐞 Fixed: Version checker unstable JSON parsings

## [v0.8.1-beta] 2023-01-23

### Added
- 🧙🏼‍♂️ Added Installer 
- 📜 Added End-User-License-Agreement `EULA.txt`
- 📃 Added About Text in About Menu

### Changed
- 🚀 Improved rendering performance by optimizing GPU memory management
- 🐞 Fixed: Application not shutting down completely and staying active in background in some cases
- ⌨ Changed keyboard shortcuts to 
  - <kbd>T</kbd> Timecode
  - <kbd>A</kbd> Alpha Grid
- ⏫ Upgraded NDI SDK from 5.5.1 to 5.5.2

## [v0.8.0-beta] 2022-11-06

### Added
- 🎨 Added colorspace differentiation for vectorscope and CIE chromaticity scope
- 🎨 Added rec601 colorspace to CIE 1931 scope
### Changed
- 🚀 Improved window animations for settings, metadata, and colorfilters
-  ↕ Zoomed in the CIE 1931 scope
- 📏 Vectorscope lines now correspond to the primary and secondary color vectors
- 🔳 Mask now works on stills
- 🔳 Mask background now stays visible
- 🚀 Improved mask performance
### Fixed
- 🐞 Fixed #9 metadata table selection not working correctly
- 🐞 Fixed wrong calculation of vectorscope squares

## [v0.7.3-beta] 2022-11-01

### Added
- Implemented request #10: Fractional Aspect Ratio e.g. **16:9**
### Changed
- Fixed #6: startup failure "Error Loading Audio Devices" when VB-Audio Virtual Cable is present.

## [v0.7.2-beta] 2022-10-20

### Added
- Added Support for GPU Compute Capability 8.9 and 9.0 "Ada Lovelace" (RTX 40 Series and RTX 6000) and "Hopper" (H100)
  - Please report in the discussion of this release if this software works on the GPUs I have [not tested yet](https://github.com/MindStudioOfficial/livescopestv#gpu-support)
- Added Metadata Table with more data about a NDI Source based on #5. Currently includes:
  - Source Name
  - Source IP Address
  - Resolution
  - Framerate
  - Aspect Ratio
  - FourCC
- Improved performance due to updated rendering and removal of unnecessary memory zeroing
- Added window title bar on loading screen to close the app in case of an error message.

### Changed
- Fixed: GPU Version not checked correctly 
- Fixed: Texture exception on startup

## [v0.7.1-beta] 2022-09-12

### Changed
- Implement better way to wait for NDI/Audio/Renderer to shut down resulting in faster closing time
- Added Links to Bug Reports, Feature Requests, and Discussions to about/help-menu
- Add GPU Compute Capability (GPU Version) to about/help-menu


## [v0.7.0-beta] 2022-09-06

### Added
- ✨ CIE 1931 Chromaticity Scope
- 🎨 Color filter matrix with presets for color/alpha channel isolation and more
- 📁 Open file location button in framebrowser
- ❓ Help/About button with some useful links

### Fixed
- 💻 Fixed scrolling with laptop trackpad guestures not working

### Changed
- ⏫ Upgraded to NDI 5.5
- Adjusted layout of the framebrowser
- Saved reference frame thumbnails are now cached correctly to avoid re-rendering
- Improved error handling on startup

## [v0.6.2-beta] 2022-08-29

### Added
- View timecode (in milliseconds not frames)
- View embedded XML-metadata


## [v0.6.1-beta] 2022-08-02

### Added
- Added option in config to enable accurate rendering of scopes:
- Reduces noise at the cost of performance
  
### Changed
- Fixed: black lines caused by rounding errors in scopes
- Fixed: #7 stuck on loading settings



## [v0.6.0-beta] 2022-07-22

### Added
- ✨New Waveform: YUV Parade
- ✨New Waveform: 15% RGB Black Level
- Modular waveform rendering increases performance because only selected scopes need to be rendered
- Waveform type is now switchable in a dropdown menu above each scope
- Waveform overlay now customizable for each type in a seperate menu ●●●
- Visual improvements and hover/focus feedback to buttons and menus
- Menus can now be traversed in the correct order using <kbd>Tab</kbd> and the arrow keys
- ⌨ Added keyboard shortcuts (see Readme) for several actions
- 🔊 Audio output device is now selectable via the settings menu

### Changed
- Fixed: Framebrowser not listening to File changes on first start of the app
- Fixed: Reference Frame not visible when no input present
- Fixed: NDI Reconnect when saving reference frame (causing lag)
- Fixed: DRPC not updating when

## [v0.5.1-beta] 2022-07-08

### Fixed
- Fix scope layout initializing to all luminance scopes when updating from `v0.4.1`

If you have started the version `v0.5.0` you have to change the layout back manually in the `config.json` located at:
`C:\Users\<username>\AppData\Roaming\com.mindstudio\ndiscopes`

Here change the value of `scopeLayout` from `[0,0,0]` to `[0,1,2]`.

## [v0.5.0-beta] 2022-07-08

### Changed
- Changed Image rendering from using the slow CustomPaint to the much faster Texture workflow:

This Improves Performance by up to 400% (4 times the amount of frames processed per second)

| Resolution  | CustomPaint | Texture   | Average<br>Improvement |
| ----------- | ----------- | --------- | ----------- |
| 1280 x 720  | 8 - 20 ms<br>50 - 125 fps | 3 - 6ms<br>170 - 330 fps  | 300%        |
| 1920 x 1080 | 15 - 50ms<br>20 - 70 fps   | 7 - 10ms<br>100 - 140 fps  | 350%        |
| 2560 x 1440 | 40 - 70ms<br>15 - 25 fps   | 12 - 20ms<br>50 - 85 fps | 340%        |
| 3840 x 2160 | 80 - >200ms<br>5 - 12 fps | 20 - 50ms<br>20 - 50 fps | 400%        |

Thanks to @alexmercerind and the people from the FlutterDev Discord for helping with the implementation.

For more detail and how these numbers were aquired look at this pullrequest #6.

- Other performance improvements in the user interface
- More responsive Sourceselector
- Option to stop receiving frames in Sourceselector
- Vectorscope is now colorized
- Audiometers are now colorful 
- Added performance statistics: 
  - image resolution
  - framerates (actual vs. metadata)
  - renderdelay

### Fixed
- Luminance Scope: Values from 16 to 235 are now mapped to the whole range of 0 - 255
- Audiometers were not visible if no audio data is received
- Vectorscope: Colored Squares were at the wrong saturation levels. (Now 100% and 75%)

### Other
- Added debugging messages for developers
- Disconnecting NDI connection before closing the app
- Added shutdown status text
- Adjusted window button colors
