# Third-party components

The Windows bundle contains Python, PySide6/shiboken6, Qt Core/Gui/Widgets and the Windows/ICO/JPEG/GIF plugins, yt-dlp and its runtime dependencies, yt-dlp-ejs, Node, FFmpeg and ffprobe. Exact Python package versions and copied distribution notices are in `_internal/notices/dependency-inventory.json`. This inventory also contains build-only packages; it is not a claim that every installed Qt module is shipped.

| Component | Version / source | License summary |
| --- | --- | --- |
| VideoDownloaderApp | 0.1.8 | VideoDownloaderApp Binary Distribution License |
| Pretendard | 1.3.9; unmodified Regular and SemiBold OpenType fonts | SIL Open Font License 1.1; copyright and license in `_internal/notices/fonts/Pretendard-OFL.txt` |
| Python | 3.14.10; official Windows x64 NuGet package and matching source archive | PSF and included third-party terms |
| PySide6 / shiboken6 / QtBase | 6.12.0; exact Qt/PySide source archives | Open-source LGPL/GPL options and third-party terms |
| yt-dlp | 2026.8.19; exact source distribution | Unlicense |
| yt-dlp-ejs | 0.8.0; exact source distribution | Unlicense AND MIT AND ISC |
| Cython generated runtime | 3.3.0; build tool is not shipped | Apache-2.0; license retained in runtime notices |
| certifi | 2026.10.23; exact corresponding source | MPL-2.0 |
| Node | v24.22.2; official Windows x64 archive | MIT and bundled third-party terms |
| FFmpeg / ffprobe | n9.0.2-39-g7adfbe40dc-20261030; BtbN win64-gpl-9.0 | GPLv3 build with included dependency terms; no nonfree flag |
| PyInstaller bootloader | 6.22.3 | GPL with bootloader exception |

Full application and third-party license texts are under `_internal/notices`; QtBase/PySide attributions and FFmpeg dependency notices retain source-relative paths. Qt/PySide/shiboken DLLs, extension modules and Python support files remain external and replaceable.

Pretendard is loaded from the portable bundle without a system font installation. Its exact unmodified font files, copyright/license and pinned upstream provenance are included under `_internal/assets/fonts/pretendard`. The font remains OFL-1.1, independently of the application's license. Upstream: https://github.com/orioncactus/pretendard/releases/tag/v1.3.9.

Corresponding source is provided as matching release source ZIP parts, indexed by `source-manifest.json`. Distribute all source parts alongside the binary; do not substitute generic upstream links or expiring CI artifacts. See SOURCE_AND_LICENSES.md in the portable folder or [Licensing and sources](LICENSING.md) for redistribution, library replacement and source instructions.

Primary upstream projects: https://www.python.org/ · https://www.qt.io/ · https://github.com/yt-dlp/yt-dlp · https://github.com/yt-dlp/ejs · https://nodejs.org/ · https://github.com/BtbN/FFmpeg-Builds · https://pyinstaller.org/
