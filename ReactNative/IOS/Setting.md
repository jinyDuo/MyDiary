pod install 오류시

lottie-ios@3.1.8 lottie-react-native@3.5.0 

yarn add 로 설치

---

```
pod 초기화
1. rm -rf ~/Library/Caches/CocoaPods

2. rm -rf Pods

3. rm -rf ~/Library/Developer/Xcode/DerivedData/*

4. pod deintegrate

5. pod setup

6. pod install
```

출처:

[https://shoveller.tistory.com/entry/Cocoapod-완전히-리셋하는-방](https://shoveller.tistory.com/entry/Cocoapod-%EC%99%84%EC%A0%84%ED%9E%88-%EB%A6%AC%EC%85%8B%ED%95%98%EB%8A%94-%EB%B0%A9%EB%B2%95)

---

프로젝트 실행

- workspace로 실행하여 pod install 한다.

오류해결

packjson 설정

버전 맞추기

ios 배포설정

1. 테스트플라이트등록
2. 무결성 검증사이트 ipa 추출 후 등록
- administrator / 1234

컴파일 시행은 archives 눌러 시행

window 탭 메뉴

- device
- organizer

프로젝트설정

identity 설정에서 버전이름, 버전 build +1 로 설정하여 컴파일시행

에러가날시

signing설정

automatice 선택 체크 해제 후 재선택

앱 추출 및 테스트플라이트 등록

orgainzer 에서 upload 시행시 테스트플라이트 등록( 여기서안되면 다시 다운받아시행)

같은 창에서 export 하면 ipa 가 추출됨

무결성검증 사이트 등록

orgainzer 에서 앱 추출 (ipa)

카카오톡 관련 키스토어변경 내 키스토어경로체크 후 변경시행

없는 키스토어 생성되면 카카오 디벨로퍼 키해시에등록해야함

키스토어 debug 변경 app/debug.keystore 있음

키값 카카오 디벨로퍼에 등록되있는 키갑적용

mrp-release-key.keystore

`keytool -exportcert -alias androiddebugkey -keystore ~./android/app/debug.keystore -storepass android -keypass android | openssl sha1 -binary | openssl base64`

---

---

설치과

ad-hoc ⇒ ipa.추출

xcode→window→device and similator 에서 추출한 ipa 드래그앤드랍 하면 설치됨 +(app)
