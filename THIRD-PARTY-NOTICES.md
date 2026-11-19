# Third-party notices

This repository publishes the official Chroma Studio release binaries. Chroma Studio is licensed under the [MIT License](LICENSE).
It depends on the following third-party components, each under its own license.

## Libraries linked into the application (NuGet)

| Component | Version | License | Project |
|---|---|---|---|
| NAudio (Core, Wasapi, WinMM, WinForms) | 2.2.1 | MIT | https://github.com/naudio/NAudio |
| SharpDX, SharpDX.DXGI, SharpDX.Direct3D11, SharpDX.Direct2D1, SharpDX.MediaFoundation | 4.2.0 | MIT | https://github.com/sharpdx/SharpDX |
| Microsoft.Windows.SDK.Contracts | 10.0.19041.x | MIT | https://www.nuget.org/packages/Microsoft.Windows.SDK.Contracts |
| Microsoft.NETFramework.ReferenceAssemblies (build only) | 1.0.3 | MIT | https://github.com/Microsoft/dotnet |

Test-only dependencies (xUnit, Microsoft.NET.Test.Sdk) are not shipped.

## FFmpeg (separate program, not linked)

Chroma Studio does **not** link against FFmpeg. It launches `ffmpeg.exe` as an
independent process and exchanges data with it through standard pipes.
FFmpeg is therefore a separate work ("mere aggregation"), and the MIT license
of Chroma Studio is unaffected.

- **"Full" release package:** for convenience, the `ChromaStudio-<version>-win-full.zip`
  release asset and the installer include an unmodified FFmpeg build from
  [BtbN/FFmpeg-Builds](https://github.com/BtbN/FFmpeg-Builds) (`win64-gpl`).
  That build is licensed under the **GNU General Public License v3** because it
  includes libx264. Its complete license text is shipped next to the binary as
  `ffmpeg/LICENSE.txt`, and the exact corresponding source code is available from
  https://github.com/BtbN/FFmpeg-Builds/releases and https://ffmpeg.org/download.html.
- **"Portable" release package:** contains no FFmpeg. Users supply their own build
  (any license). For an LGPL-only setup use an `lgpl` build; the CPU x264 encoder
  is then unavailable, while NVENC / Quick Sync / AMF hardware encoders still work.

FFmpeg is a trademark of Fabrice Bellard, originator of the FFmpeg project.
https://ffmpeg.org/legal.html

## Artwork

The application icon (`src/ChromaStudio/Assets/app.ico`, `app.png`) and all
vector icons in `Themes/Icons.xaml` are original work created for this project
and are covered by the project's MIT license.

## Fonts

The UI uses Segoe UI and Consolas, which ship with Windows. No fonts are redistributed.
