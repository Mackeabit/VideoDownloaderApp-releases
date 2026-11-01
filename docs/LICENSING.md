# Licensing and corresponding source

Starting with version 0.1.6, the copyright holder's own application code uses the VideoDownloaderApp Binary Distribution License in LICENSE. It permits free use and binary redistribution while keeping the original application source private. The owner confirmed rights to the reused application code. Previous GPL-3.0-or-later releases keep their original grants; making their repository private does not revoke recipients' rights. No rights to downloaded media are granted.

## What travels with a binary release

Provide the portable app ZIP, all matching third-party source ZIP parts, source manifest/inventory and checksums together on the distribution release page without an additional fee or access restriction. Keep the corresponding third-party sources available while distributing the binary. A changing upstream branch or expiring CI artifact is not a replacement for those exact sources. Version 0.1.6 does not require distribution of the application's original source ZIP under its own license, provided the third-party component boundaries and obligations described here remain satisfied. Do not distribute an older GPL application binary without its matching application source obligations.

The binary includes the application terms, third-party notices, dependency versions, runtime provenance and source index. The **앱 정보 · 라이선스** button opens these notices. The application's original source repository stays private. A separate public distribution repository contains user documentation and release assets; its automatically generated Source code ZIP contains only those public repository files.

## Component boundaries and replacement

- The own Python modules are compiled to native Windows .pyd files with Cython, then packaged with PyInstaller. The entry dispatcher remains bytecode. This raises the difficulty of reconstructing own code; it does not prevent reverse engineering or hide strings and behavior. No own original .py, generated C or debugging-symbol files belong in the application ZIP.
- Cython 3.3.0 is an Apache-2.0 build tool; its applicable license/attribution is retained under `_internal/notices/runtime/Cython-3.3.0-LICENSE.txt`. It is not installed on users' systems.
- Mutagen is GPL-2.0-or-later. The application does not use its optional thumbnail-tagging features; version 0.1.6 excludes Mutagen from the binary and runtime requirements. The installed development environment is not the runtime inventory.
- Qt Core/Gui/Widgets, PySide6 and shiboken6 are used under LGPLv3 with their third-party terms. Their DLLs, .pyd files and Python support modules remain external under `_internal/PySide6` and `_internal/shiboken6`, rather than being compiled into own modules or embedded as Python bytecode. The release provides the exact QtBase and PySide sources, license texts, build files and attributions. No incompatible GPL-only Qt module is included.
- To replace these LGPL libraries, close the app, back up the portable folder, build a compatible Python 3.14/Qt 6.12 Windows x64 version following the supplied Qt/PySide source instructions, and replace the matching DLL/.pyd/.py files in those directories. Keep the same module/file paths and compatible ABI. No signing key, developer authorization or application-source recompilation is required for a compatible replacement. The application terms permit library replacement, modifications needed for it, debugging those modifications by reverse engineering and redistribution under the applicable licenses. Frozen acceptance checks that modified external package initializers actually execute.
- FFmpeg and ffprobe are separate command-line programs invoked through files and arguments, not libraries linked into own application code. The selected BtbN build enables GPL and version3, without nonfree. Its source set includes the exact revision, build scripts, patches and statically linked dependencies.
- yt-dlp is used from its Unlicense Python package; the licensing of a different upstream prebuilt EXE is not substituted for this package. yt-dlp-ejs includes Unlicense, MIT and ISC material; retain its bundled notices.
- certifi is MPL-2.0. Its exact corresponding source and notice remain in the source set. Other Python dependencies retain their respective notices.
- Node uses MIT plus bundled third-party terms. Python uses PSF plus bundled third-party terms. PyInstaller's bootloader license includes its bootloader exception. Build-only packages in the inventory are not all shipped runtime code.
- Pretendard 1.3.9 Regular and SemiBold are unmodified OFL-1.1 fonts. Their original files, full copyright/license and pinned provenance remain beside the fonts under `_internal/assets/fonts/pretendard`, with notices under `_internal/notices/fonts`. No system-wide font installation occurs.

## FFmpeg provenance and rebuilding

Selected binary: BtbN `autobuild-2026-10-30-13-01`, `ffmpeg-n9.0.2-39-g7adfbe40dc-win64-gpl-9.0.zip`.

- CI run: https://github.com/BtbN/FFmpeg-Builds/actions/runs/41053493863
- Build scripts: `5031c6f1082414e53688d39e521849905071070d`
- FFmpeg source: `7adfbe40dcde598f93a6963d2f7b22cd75202ccc`
- Target image both produced and consumed by that run: `sha256:f5d2004dc8f0b8390042b8b7454c4aa99a84a945559b2ddd089fd5c071eef0b7`
- The exact dependency archives named by the target image build log are collected from that run's download-cache artifact. The release source manifest records content hashes, not only cache-key names.

The upstream source archive includes Docker build scripts, variant `win64 gpl 9.0`, patches and download recipes. Dependency sources belong at the build tree's `.cache/downloads` paths recorded in the manifest. Consult `vendor/FFMPEG_SOURCE.md` for exact inputs, additional Rust dependencies, reproduction steps and verification limits. We test the upstream binary; we do not claim to have independently rebuilt it bit for bit.

Qt/PySide sources include their build instructions; Qt requires its supported Windows C++ toolchain. General-purpose operating systems, compilers and system libraries are not part of the corresponding-source archive set.

Primary references: [GNU GPLv3](https://www.gnu.org/licenses/gpl-3.0.html), [Qt LGPL obligations](https://www.qt.io/development/open-source-lgpl-obligations), [FFmpeg license and legal considerations](https://ffmpeg.org/legal.html), [PyInstaller license](https://pyinstaller.org/en/stable/license.html).
