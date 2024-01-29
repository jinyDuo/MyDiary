오픈 프로젝트

android/gradle → open

bodoc.xcworkspace

ios/

안드로이드 환경변수

~/.base_profile

export ANDROID_PATH=/Users/duoduet/Library/Android

export PATH=$PATH:$ANDROID_PATH/sdk/platform-tools

~/.zrhrc 환경병수 추가

export ANDROID_SDK_ROOT=$HOME/Library/Android/sdk

---

프로젝트 경로에서 설치 해야할것

yarn install 또는 npm install

로컬 서버실행

npm start

설치후

react-native link 실행(특정 환경이 변하면 실행명령어)

---

시뮬레이터 포트설정

[**adb reverse tcp:8081 tcp:8081**](https://gitlab.allisnull.com/bodoc/mobile)

캐시지우고 restart(디바이스 찾지못할때)

error: more than one device/emulator

- File > Invalidata Caches / Restart

adb 설치

brew cask install android-platform-tools

시뮬레이터 종료

adb kill-server

(앱 완전종료 후)

---

wrapper :app 오류시

build.bundle 추가

task wrapper(type: Wrapper) {

gradleVersion = '0.9'

}
