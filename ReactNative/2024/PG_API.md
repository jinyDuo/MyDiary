<h1> KG 모빌리언스 api 연동 </h1>

<h2>안드로이드 설정</h2>
.AndoroidManifest.xml 설정 함
각 외부앱은 각각으로 package에 해당 app_scheme 등록함
<manifest xmlns:android="http://schemas.android.com/apk/res/android">

    <uses-permission android:name="android.permission.INTERNET" />
    <uses-permission android:name="android.permission.ACCESS_FINE_LOCATION" />
    <uses-permission android:name="android.permission.ACCESS_COARSE_LOCATION" />
    <!-- rn 웹뷰 외부앱 열기위해 등록 -->
    <queries>
        <package android:name="com.kakao.talk" /> <!-- 카카오톡 -->
        <package android:name="com.shcard.smartpay" /> <!-- 신한페이판 -->
        <package android:name="com.shinhancard.smartshinhan" /> <!-- 신한페이판-공동인증서 -->
        <package android:name="com.hyundaicard.appcard" /> <!-- 현대카드 -->
        <package android:name="com.lumensoft.touchenappfree" /> <!-- 현대카드-공동인증서 -->
        <package android:name="kr.co.samsungcard.mpocket" /> <!-- 삼성카드 -->
        <package android:name="nh.smart.nhallonepay" /> <!-- 올원페이 -->
        <package android:name="com.kbcard.cxh.appcard" /> <!-- KB Pay -->
        <package android:name="com.kbstar.liivbank" /> <!-- Liiv(KB국민은행) -->
        <package android:name="com.kbstar.reboot" /> <!-- Liiv Reboot(KB국민은행) -->
        <package android:name="kvp.jjy.MispAndroid320" /> <!-- ISP/페이북 -->
        <package android:name="com.lcacApp" /> <!-- 롯데카드 -->
        <package android:name="com.hanaskcard.paycla" /> <!-- 하나카드 -->
        <package android:name="kr.co.hanamembers.hmscustomer" /> <!-- 하나멤버스 -->
        <package android:name="kr.co.citibank.citimobile" /> <!-- 씨티모바일 -->
        <package android:name="com.wooricard.wpay" /> <!-- 우리페이 -->
        <package android:name="com.wooricard.smartapp" /> <!-- 우리카드 -->
        <package android:name="com.wooribank.smart.npib" /> <!-- 우리WON뱅킹 -->
        <package android:name="viva.republica.toss" /> <!-- 토스뱅크 -->
        <package android:name="com.nhnent.payapp" /> <!-- PAYCO -->
        <package android:name="com.ssg.serviceapp.android.egiftcertificate" /> <!-- SSGPAY -->
        <package android:name="com.kakao.talk" /> <!-- 카카오페이 -->
        <package android:name="com.kakaopay.app" /> <!-- 카카오페이 -->
        <package android:name="com.nhn.android.search" /> <!-- 네이버페이 -->
        <package android:name="com.lotte.lpay" /> <!-- L.pay -->
        <package android:name="com.lottemembers.android" /> <!-- L.POINT -->
        <package android:name="com.samsung.android.spay" /> <!-- 삼성페이 -->
        <package android:name="com.samsung.android.spaylite" /> <!-- 삼성페이 -->
        <package android:name="com.lge.lgpay" /> <!-- 엘지페이 -->
        <package android:name="com.lguplus.paynow" /> <!-- 페이나우 -->
        <!--계좌이체 외부앱-->
        <package android:name="com.kftc.bankpay.android" /> <!-- 뱅크페이 -->
        <package android:name="com.kbstar.reboot" /> <!-- 리브Next -->
        <package android:name="com.nh.cashcard" /> <!-- 농협앱캐시 -->
        <package android:name="kr.co.kfcc.mobilebank" /> <!-- MG상상뱅크 -->
        <package android:name="com.knb.psb" /> <!-- 경남은행 -->
    </queries>
    <application
      android:name=".MainApplication"
      android:usesCleartextTraffic="true"
      android:label="@string/app_name"
      android:icon="@mipmap/ic_launcher"
      android:roundIcon="@mipmap/ic_launcher_round"
      android:allowBackup="false"
      android:requestLegacyExternalStorage="true"
      android:theme="@style/AppTheme">
      
      <meta-data
            android:name="com.naver.maps.map.CLIENT_ID"
            android:value="7l9hvqpjvs" />
      <activity
        android:name=".MainActivity"
        android:label="@string/app_name"
        android:configChanges="keyboard|keyboardHidden|orientation|screenLayout|screenSize|smallestScreenSize|uiMode"
        android:launchMode="singleTask"
        android:windowSoftInputMode="adjustResize"
        android:screenOrientation="portrait"
        android:exported="true">
        <intent-filter> 
            <action android:name="android.intent.action.MAIN" />
            <category android:name="android.intent.category.LAUNCHER" />
        </intent-filter>
          <intent-filter>
              <action android:name="android.intent.action.VIEW" />
              <category android:name="android.intent.category.DEFAULT" />
              <category android:name="android.intent.category.BROWSABLE" />
              <data android:scheme="externalapp" />
          </intent-filter>
      </activity>
    </application>
</manifest>

<p>
    1. 외부앱 app_scheme 을 설정한다 (안드로이드, iOS 동일함)
    2. 웹뷰에서 외부앱 실행시 해당 링크에서 앱이없으면 앱 store로 이동시키고 앱이있으면 해당앱을 실행시킴
    3.
</p>

<p>
    1. 버그사항
        - 안드로이드 intent-filter 설정에서 해당
              <action android:name="android.intent.action.VIEW" />
              <category android:name="android.intent.category.DEFAULT" />
              <category android:name="android.intent.category.BROWSABLE" />
              <data android:scheme="externalapp" />
        - 해당 외부앱 실행 intent 와 MAIN intent 부분이 같이 코드에 포함되어
</p>
