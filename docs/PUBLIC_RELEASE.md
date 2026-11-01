# Release verification — 0.1.6

Date: 2026-11-01. Target: Windows x64 on this Windows host. Distribution target: https://github.com/Mackeabit/VideoDownloaderApp-releases/releases/tag/v0.1.6 . The original source repository remains private.

## Changes

Troubleshooting advice, extraction-only link probing, sanitized report preview/copy/export, explicit anonymous update checks, and maintainer report/reproduction tooling. Report exports exclude original URLs, titles, paths, account data and raw logs by default; hostname inclusion is explicit opt-in. Probe tasks run in supervised child processes with bounded timeouts/cancellation and owned temporary-directory cleanup. Updates only open a release page; they do not install executable code.

Own code is compiled with Cython 3.3.0 and MSVC 2022 into 17 native modules. The ZIP contains no original own .py or own .pyc/PYZ modules. The minimal launch dispatcher remains bytecode. This increases reconstruction difficulty; it is not a guarantee against reverse engineering. Distinct new numeric-page URLs retain full-URL hash names; legacy numeric filenames are recognized only when their files already exist, preserving resumable output without merging new URLs by numeric ID alone. Historic personal site strings and default custom registrations were removed; neutral fixtures retain adapter boundary coverage. Engine-provided site names are not the creator's browsing history.

The new own-code binary license permits free use/redistribution and retains third-party rights. Earlier GPL grants remain valid. Unused optional Mutagen is excluded; Qt/PySide/shiboken Python support files and DLL/.pyd files remain external and replaceable. Exact required external sources/notices remain supplied, including GPL FFmpeg as separate command-line programs and MPL certifi. This is not an assertion that compiler settings alone satisfy license obligations.

## Evidence

- 92 source regression tests passed, and all 92 passed with the 17 native own modules loaded. The source-child portions of that suite still launch development Python; separate frozen acceptance verifies the compiled subprocess path. Legacy media-file detection runs only in the download worker; queue identity calculation does not scan media directories on the Qt event thread.
- Relocated frozen EXE passed with Windows-only PATH, a Korean/spaced folder and isolated state: worker communication, queued success/failure, full media decode, cancellation, HTTP Range resume, preservation of complete/partial outputs, storage failure behavior, compact layout, normal shutdown, icon and Pretendard glyph/weight checks.
- Frozen support worker found metadata on a controlled HTML5 page, left the original job unchanged and removed its temporary directory. Report preview excluded a sentinel URL token; update dialog behavior passed. Unit tests additionally cover update API validation, offline/rate-limit/missing-release outcomes, report schema/size limits, hostile report types and export failures.
- Native GUI layouts at 100%, 125% and 150% display scaling passed. The 760×440 minimum window keeps two full queue rows and visible action buttons. Troubleshooting and update dialogs were rendered and inspected.
- PYZ inspection found no own modules, no Mutagen and no PySide6/shiboken6 Python modules. A runtime probe confirmed all 17 own modules load from .pyd files and Mutagen is absent. Modified external PySide6 and shiboken6 initializers executed, demonstrating the tested Python library replacement path. Source-original library files were restored in the isolated copy afterwards.
- Maintainer CLI inspect is offline; probe and download completed against controlled loopback media in fresh directories, with sanitized JSON output. Existing-output rejection and queue/media preservation were tested.
- Installed 0.1.6 file hashes match all 3,058 files in the accepted ZIP; the desktop shortcut remains valid. The real profile was not launched during acceptance. Existing queue/preferences hashes and modification times were preserved; real download folders were excluded from all mutations.
- Final live installed-worker check: one public YouTube sample (jNQXAC9IVRw) completed at 320×240, 19.063583 seconds and 533,931 bytes; the W3C-hosted direct-MP4 sample completed at 854×480, 52.208333 seconds and 4,372,373 bytes. Both passed full decode. The W3C sample had returned HTTP 403 / anti-bot access denial during an earlier check, demonstrating that live access can change. No claim of universal site support, challenge bypass, other Windows versions or signed binaries is made.

## Distribution assets

The ordinary-user file is `VideoDownloader-0.1.6-win-x64.zip` (217,810,360 bytes), SHA-256 `1b96507707f63ec448436a4f98600a46912dd707702cf85bd794905d087ad311`.

Two third-party source ZIP parts contain all 414 indexed source/provenance members, each validated against the retained manifest and read back after streaming from the prior verified release. No additional extracted source cache was created. The other assets are source-manifest.json, source-file-inventory.json, release-manifest.json and SHA256SUMS.txt. No own application source ZIP is included. GitHub's automatic source ZIP for the public distribution repository contains its documentation only.

The source manifests describe exact inputs and upstream build provenance; no independent bit-for-bit rebuild of third-party runtimes is claimed. Refer to LICENSING.md and the accompanying source-part instructions for redistribution and library replacement.
