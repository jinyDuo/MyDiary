<h1> Rest Api error 해결</h1>
<h3> post / multipart</h3>
<p>
  react native multipart form 데이터 전송시
  <h3>error 내용</h3>
  내용  : request에 이미지 데이터 와 텍스트 데이터를 함께 request 할때 발생
  request 전송 content-type 을 'multipart' 로 선언하여도 content-type은 변경되었으나 서버에서 Content type 'application/octet-stream' not supported
오류가 리턴되는현상이있음 <br/>
  정상 : 포스트맨 요청 ![스크린샷 2024-02-13 오전 10 49 07](https://github.com/jinyDuo/MyDiary/assets/118492667/b1ddea67-5c5c-459d-ae10-66869b4069b4)
  오류 요청 : ![스크린샷 2024-02-07 오후 3 36 50](https://github.com/jinyDuo/MyDiary/assets/118492667/b65132ce-df4d-4b68-b883-0e1d9291c237)
  원인 : 짐작으로는 자동으로 form 데이터가 string으로 변환되는듯하다 위에 이미지에서 보다싶이 이미지는 정상적으로 boundary 되나 text 항목들이 data 형태가 전혀다르게 요청됨.
  해결책
  <ul>
    <li>1. request 요청에 text 관련 데이터를 json string 으로변환후 요청 결과 : 실패</li>
    <li>2. axios 에서 transformRequest 에서 form 데이터를 그데를 보낼수 있게 그대로 리턴 결과 : 실패</li>
    <li>3. request text 데이터를 blob으로 변환하여 요청 결과 : 실패</li>
    <li>4. api 요청을 axois 에서 fetch 로변경 하고 위와같은 절차를 통해 해결하려고함 결과 : 실패</li>
    <li>5. 최종 해결책으로 어쩔수없이 서버 개발자에게 요청하여 2가지 api를만듬 text form 전달 api 와 이미지전송 api 두가지를 만들어서 해결
    </li>
  </ul>
=> 최종적으로 이미지와 텍스트를 같이 보내는방법은 해결책 찾지못함
근본적으로 app 에서 요청할떄의 문제인지, react-native 자체의문제인지
api 서버의요청 axios,fetch 의 문제인지 정확한 원인이 불분명함.
</p>
