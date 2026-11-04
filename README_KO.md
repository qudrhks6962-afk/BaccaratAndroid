# 바카라 모니터 Android 프로젝트

## 포함 기능
- P/B/T 결과 수동 입력 및 휴대폰 내부 저장
- 최근 결과 로드 표시, 기초 통계와 연속 흐름
- 모의 정산 및 자금관리
- 시작 잔액 ₱80,000 / 목표 ₱100,000 / 손실 중단선 ₱70,000
- 모의 베팅 단위 ₱500, ₱400, ₱300, ₱200, ₱100
- 오프라인 WebView 기반 앱

## APK 빌드 방법
이 프로젝트는 Android Studio에서 열 수 있는 Android 앱 소스입니다.
현재 제작 환경에는 Android SDK/Gradle 빌드 환경이 없어 서명된 APK 바이너리까지 검증해 생성하지 못했습니다.

1. PC에 Android Studio를 설치합니다.
2. Android Studio에서 이 폴더 `BaccaratAndroid`를 Open 합니다.
3. Gradle Sync가 끝날 때까지 기다립니다. JDK 17 및 Android SDK Platform 35가 필요합니다.
4. 메뉴에서 Build > Build Bundle(s) / APK(s) > Build APK(s)를 선택합니다.
5. 빌드 성공 시 `app/build/outputs/apk/debug/app-debug.apk`가 생성됩니다.
6. APK를 Android 휴대폰으로 옮겨 설치합니다. 휴대폰 설정에서 해당 파일 관리자/브라우저의 '알 수 없는 앱 설치'를 허용해야 할 수 있습니다.

## 주의
- 실제 카지노 사이트를 조작하거나 자동 베팅하지 않습니다.
- 기록은 앱이 설치된 기기의 WebView 로컬 저장소에 보관됩니다. 앱 데이터 삭제/앱 제거 시 기록이 지워질 수 있습니다.
- 통계와 과거 패턴은 미래 결과를 예측하거나 보장하지 않습니다.
- 현재 빅로드는 최근 결과를 단순 표시하는 로드형 기록판이며, 카지노의 정식 빅로드 규칙을 완전 복제한 것은 아닙니다.

## PC 없이 휴대폰만으로 APK 빌드하기 (GitHub Actions)
이 프로젝트에는 `.github/workflows/build-apk.yml` 자동 빌드 작업이 포함되어 있습니다.

1. 휴대폰 Chrome에서 https://github.com 에 로그인/가입합니다.
2. `New repository`를 눌러 새 저장소를 만들고 이름을 `BaccaratAndroid`로 지정합니다.
3. 저장소 화면에서 `Add file` → `Upload files`를 선택합니다.
4. ZIP 압축을 푼 프로젝트 안의 파일과 폴더를 업로드합니다. 숨김 폴더 `.github`도 반드시 포함해야 합니다. GitHub 모바일 화면에서 숨김 폴더 업로드가 불편하면 GitHub의 웹 업로드가 가능한 브라우저 데스크톱 사이트 모드를 사용하거나, ZIP을 업로드하는 대신 파일 업로드 화면에서 폴더 내용을 선택합니다.
5. `Commit changes`를 누릅니다.
6. 저장소의 `Actions` 탭에서 `Build Android APK` 작업을 엽니다. 자동 실행이 안 되면 `Run workflow`를 누릅니다.
7. 빌드가 끝나면 해당 실행 페이지 아래 `Artifacts`의 `BaccaratMonitor-debug-apk`를 눌러 ZIP을 다운로드합니다.
8. 다운로드한 ZIP 안의 `app-debug.apk`를 열어 설치합니다. Android에서 설치 허용을 요청할 수 있습니다.

GitHub 계정이 필요하며, 이 과정은 GitHub의 무료 Actions 사용량 범위 안에서 실행될 수 있습니다. APK는 debug 서명 빌드이며 Play 스토어 배포용 서명 릴리스가 아닙니다.
