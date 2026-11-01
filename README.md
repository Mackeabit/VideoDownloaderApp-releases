# 영상 다운로드 · VideoDownloader

Windows 64비트에서 여러 영상 링크를 대기열에 모아 다운로드하는 무료 앱입니다.

**[⬇ v0.1.6 Windows 무설치 ZIP 다운로드](https://github.com/Mackeabit/VideoDownloaderApp-releases/releases/download/v0.1.6/VideoDownloader-0.1.6-win-x64.zip)**

[최신 버전](https://github.com/Mackeabit/VideoDownloaderApp-releases/releases/latest) · [사용 안내](docs/USER_GUIDE.md) · [문제 해결](docs/SUPPORT.md) · [문제 제보](https://github.com/Mackeabit/VideoDownloaderApp-releases/issues/new/choose)

![가상 대기열 예시](docs/images/app.png)

1. 위의 실행 ZIP을 내려받아 **전체 압축을 풉니다**.
2. `VideoDownloader.exe`를 실행합니다. 옆의 `_internal` 폴더도 필요합니다.
3. 영상 링크를 한 줄씩 넣고 저장 폴더·화질을 선택합니다.
4. **대기열에 추가 → 다운로드 시작**을 누릅니다.

Python·Node·FFmpeg·AI 계정이나 API 키를 별도로 준비할 필요가 없습니다. 관리자 권한과 설치 프로그램도 필요하지 않습니다.

여러 링크의 순차 다운로드, 취소·재시도·지원되는 부분 파일 이어받기, 완료 파일 검사, 작은 창 배치, Pretendard 글꼴을 제공합니다. 실패 항목의 **문제 해결**에서 원인 안내·링크 재분석·진단 보고서를 확인하고, **업데이트 확인**으로 새 공개 버전을 조회할 수 있습니다. 보고서 자동 전송과 업데이트 자동 설치는 하지 않습니다.

업데이트는 앱을 닫고 새 ZIP을 별도 폴더에 푼 뒤 실행하면 됩니다. 기존 대기열과 설정은 `%LOCALAPPDATA%\VideoDownloaderApp`에 보존되고, 영상은 선택한 저장 폴더에 남습니다. [개인정보 안내](docs/PRIVACY.md)

공개 단일 영상 중심이며, 모든 사이트 지원을 보장하지 않습니다. 로그인·쿠키 가져오기·DRM·실시간 방송·재생목록 확장은 지원하지 않습니다. 사이트 변경과 접근 조건에 따라 실패할 수 있습니다. 본인이 다운로드할 권한이 있는 콘텐츠에 사용하세요. 전자서명은 포함하지 않습니다. 파일의 SHA-256은 릴리스의 `SHA256SUMS.txt`로 확인할 수 있습니다.

이 저장소는 **사용 안내와 실행 파일 배포용**입니다. 자체 원본 소스는 비공개이며, [앱 이용 조건](LICENSE)에 따라 무료 사용·바이너리 재배포가 가능합니다. 자체 모듈은 기계어로 컴파일하지만 역분석을 완전히 막는 것은 아닙니다. 이전 GPL 버전의 이용자 권리는 유지됩니다.

외부 구성요소의 [라이선스와 대응 소스](docs/LICENSING.md)는 유지합니다. 일반 사용자는 `VideoDownloader-0.1.6-win-x64.zip` 하나만 받으면 됩니다. `third-party-sources` ZIP은 외부 구성요소 소스이고, GitHub가 자동 생성하는 `Source code (zip)`은 이 문서 저장소의 파일입니다. 둘 다 앱 실행에 필요하지 않습니다.
