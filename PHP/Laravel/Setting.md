맥 개발환경설정중

pecl install swoole

pecl 경로 잘 확인해야함 (brew update 시 swoole pecl 심볼링링크 pcre2.h 이 사라지는현상있음)

확인항목

pecl 경로 pecl2 경로 체크 php 버전체크 경로

ln -s /opt/homebrew/Cellar/pcre2/[pecl2  버전]/include/pcre2.h /opt/homebrew/Cellar/php/[PHP version]/include/php/ext/pcre/pcre2.h

swoole 경로 [swoole.so](http://swoole.so/) 파일없 에러뜰시

/opt/homebrew/lib/php/pecl/20210902/[swoole.so](http://swoole.so/) 에서 복사하여

/opt/homebrew/Cellar/php/8.1.2/lib/php/20210902 에 붙여넣기

brew install swoole 시

system.php 294 line 에러시

심볼링크제거

rm /usr/local/Cellar/php/[PHP version]/pecl

php ini 위치 찾기

php --ini | grep php.ini

옥탄의 설정들을 설치

composer require laravel/octane

php artisan octane:install 옥탄 설치 1번swoole

chokidar 오류시

`npm i -g npm`

npm update 후 옥탄 시작

개발 수정시 즉시반영

`php artisan octane:start --watch`

옥탄 강제리로드

`php artisan octane:reload`

옥탄 멈춤

`php artisan octane:stop`

서버 상태확인

`php artisan octane:status`
