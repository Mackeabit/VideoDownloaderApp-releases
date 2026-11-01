# 라이선스와 외부 구성요소 소스

## 앱 이용 조건

이 앱은 [VideoDownloaderApp Binary Distribution License](../LICENSE)에 따라 무료 사용과 실행 파일 재배포가 가능합니다. 자체 원본 소스는 제공하지 않습니다. 다운로드하는 콘텐츠의 이용 권한은 별도로 확인해야 합니다.

외부 구성요소에는 각자의 라이선스가 적용됩니다. 이 앱의 이용 조건은 해당 구성요소가 부여하는 권리를 제한하지 않습니다. 구성요소 목록은 [외부 구성요소 고지](THIRD_PARTY_NOTICES.md), 전체 라이선스 원문과 고지는 실행 ZIP의 `_internal/notices`에서 확인할 수 있습니다. 앱의 **앱 정보 · 라이선스**에서도 고지 폴더를 열 수 있습니다.

## 소스 자료 내려받기

[v0.1.8 릴리스](https://github.com/Mackeabit/VideoDownloaderApp-releases/releases/tag/v0.1.8)에서 다음 자료를 함께 제공합니다.

- `VideoDownloader-0.1.8-third-party-sources-01.zip`
- `VideoDownloader-0.1.8-third-party-sources-02.zip`
- `source-manifest.json`, `source-file-inventory.json`
- 파일 검증용 `SHA256SUMS.txt`

두 소스 ZIP은 서로 다른 외부 구성요소 자료를 담으므로 모두 받으세요. 일반적인 앱 실행에는 실행 ZIP만 필요합니다. GitHub가 자동 생성하는 `Source code` 압축 파일은 이 안내 문서 저장소의 내용이며 위의 대응 소스 자료를 대신하지 않습니다.

실행 파일을 재배포할 때는 앱 이용 조건, 외부 구성요소의 라이선스·고지와 필요한 대응 소스 접근 정보를 함께 유지하세요. 대응 소스는 실행 파일과 같은 배포 위치에서 추가 비용이나 접근 제한 없이 제공하고, 실행 파일을 배포하는 동안 이용할 수 있도록 유지해야 합니다.

## 구성요소별 안내

- **Qt Core/Gui/Widgets, PySide6, shiboken6**: LGPLv3와 포함된 외부 구성요소 약관을 적용합니다. QtBase와 PySide의 해당 버전 소스, 빌드 자료, 라이선스와 저작권 고지를 제공합니다.
- **FFmpeg·ffprobe**: 별도 명령줄 프로그램으로 실행합니다. 포함된 BtbN 빌드는 GPLv3 설정이며 nonfree 옵션을 사용하지 않습니다. 대응 소스에는 정확한 FFmpeg 리비전, 빌드 스크립트, 패치와 정적으로 연결된 의존성이 포함됩니다.
- **certifi**: MPL-2.0 고지와 해당 버전 대응 소스를 제공합니다.
- **yt-dlp·yt-dlp-ejs**: Python 패키지에 적용되는 Unlicense 및 MIT·ISC 고지를 유지합니다.
- **Python·Node**: 각각 PSF·MIT 및 함께 제공되는 외부 구성요소 약관을 적용합니다.
- **PyInstaller 부트로더**: 부트로더 예외가 포함된 라이선스를 적용합니다.
- **Cython 생성 런타임**: Apache-2.0 고지는 `_internal/notices/runtime/Cython-3.3.0-LICENSE.txt`에 포함됩니다.
- **Pretendard 1.3.9**: 수정하지 않은 Regular·SemiBold 글꼴을 OFL-1.1로 제공합니다. 원본 글꼴·저작권·라이선스는 `_internal/assets/fonts/pretendard`와 `_internal/notices/fonts`에 포함됩니다.

세부 조건은 각 구성요소의 라이선스 원문을 따릅니다.

## LGPL 라이브러리 교체

Qt/PySide/shiboken의 DLL·확장 모듈·Python 지원 파일은 `_internal/PySide6`, `_internal/shiboken6` 등에 별도 파일로 배치되어 있습니다.

1. 앱을 닫고 전체 프로그램 폴더를 백업합니다.
2. 제공된 Qt/PySide 소스의 빌드 안내에 따라 Python 3.14·Qt 6.12·Windows x64와 호환되는 라이브러리를 준비합니다.
3. 모듈 경로와 호환되는 ABI를 유지하면서 해당 DLL·.pyd·.py 파일과 필요한 의존성을 교체합니다.

호환되는 교체에 제작자의 승인·서명 키·자체 앱 소스 재컴파일은 필요하지 않습니다. 앱 이용 조건은 라이브러리 교체에 필요한 수정, 수정 사항의 디버깅을 위한 역분석 및 해당 라이선스에 따른 재배포를 허용합니다.

## 외부 구성요소 빌드 자료

소스 묶음의 `FFMPEG_SOURCE.md`에는 정확한 입력 자료와 재빌드 절차가 있습니다. `source-manifest.json`은 각 소스 자료의 내용 체크섬과 출처를 기록합니다. Qt/PySide 소스에도 각 프로젝트의 빌드 안내가 포함되어 있습니다.

FFmpeg 빌드 식별 정보:

- 배포 바이너리: BtbN `autobuild-2026-10-30-13-01`, `ffmpeg-n9.0.2-39-g7adfbe40dc-win64-gpl-9.0.zip`
- 빌드 스크립트: `5031c6f1082414e53688d39e521849905071070d`
- FFmpeg 리비전: `7adfbe40dcde598f93a6963d2f7b22cd75202ccc`
- 빌드 실행: https://github.com/BtbN/FFmpeg-Builds/actions/runs/41053493863
- 해당 실행에서 생성·사용한 대상 이미지: `sha256:f5d2004dc8f0b8390042b8b7454c4aa99a84a945559b2ddd089fd5c071eef0b7`

정확한 의존성 아카이브와 빌드 자료는 릴리스 소스 묶음에 포함됩니다. 일반 운영체제·컴파일러·시스템 라이브러리는 이 묶음의 제공 범위에 포함하지 않습니다. 외부 바이너리를 독립적으로 비트 단위까지 동일하게 재빌드했다는 의미는 아닙니다.

참고: [GNU GPLv3](https://www.gnu.org/licenses/gpl-3.0.html) · [Qt LGPL 안내](https://www.qt.io/development/open-source-lgpl-obligations) · [FFmpeg 라이선스](https://ffmpeg.org/legal.html) · [PyInstaller 라이선스](https://pyinstaller.org/en/stable/license.html)
