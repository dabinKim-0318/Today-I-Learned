
# Network

<h2>전산 기본</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>OSI 7계층에 대해서 설명해주세요.</strong></span></summary>
<hr>
   <p>나눈 이유 : 통신이 일어나는 과정을 단계별로 알수있고, 문제가 생기면 그 단계만 수정하면 됨</p>
   <ul>
      <li><strong>물리 </strong>: 데이터 전송 ex) 리피터, 케이블, 허브</li>
   </ul>
   <ul>
      <li><strong>데이터링크 </strong>: 물리 계층으로 송수신되는 정보 관리, Mac 주소로 통신 ex) 브릿지, 스위치</li>
   </ul>
   <ul>
      <li><strong>네트워크 </strong>: 데이터를 목적지까지 전달, 라우터로 경로를 선택해 IP 지정, 경로에 따라 패킷 전달 ex) 라우터, IP</li>
   </ul>
   <ul>
      <li><strong>전송 </strong>: 통신을 활성화 ex) TCP, UDP</li>
   </ul>
   <ul>
      <li><strong>세션 </strong>: 데이터가 통신하기 위한 논리적 연결 담당 ex) API, Socket</li>
   </ul>
   <ul>
      <li><strong>표현 </strong>: 데이터 표현에 대한 독립성을 제공하고 암호화 ex) JPEG, MPEG</li>
   </ul>
   <ul>
      <li><strong>응용 </strong>: 최종 목적지, 응용프로그램과 연관하여 서비스 수행 ex) HTTP, FTP, DNS</li>
   </ul>
   <figure/></a></figure>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>TCP/IP 4계층에 대해서 설명해주세요.</strong></span></summary>
<hr>
   <p>1계층 네트워크 액세스 : 물리+데이터링크, MAC주소 사용</p>
   <p>2계층 인터넷 : 네트워크, 통신 노드간의 IP패킷을 전송하는 기능과 라우팅 기능 담당</p>
   <p>3계층 전송 : 전송, 통신 노드간의 연결 제어 및 신뢰성 있는 데이터 전송 담당</p>
   <p>4계층 응용 : 세션+표현+응용, 응용 프로그램 구현</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>DNS가 무엇인가요?</strong></span></summary>
<hr>
   <p>IP주소를 문자로 표현한 주소로 바꾸는 시스템 혹은 서버</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>www.naver.com에 접속할때 일어나는 일에 대해 설명해주세요.</strong></span></summary>
<hr>
   <ol>
      <li>사용자가 브라우저에 도메인 네임(<a href="http://www.naver.xn--com%29-8040a/">www.naver.com)을</a> <strong>입력</strong>한다.</li>
   </ol>
   <ol>
      <li>사용자가 입력한 URL 주소 중에서 <strong>도메인 네임(Domain Name) 부분을 DNS 서버에서 검색</strong>하고, DNS 서버에서 해당 도메인 네임에 해당하는 <strong>IP 주소를 찾아 사용자가 입력한 URL 정보와 함께 전달</strong>한다.</li>
   </ol>
   <ol>
      <li>페이지 URL 정보와 전달받은 IP 주소는 <strong>HTTP 프로토콜을 사용하여 HTTP 요청 메시지를 생성</strong>하고, 이렇게 생성된 HTTP 요청 메시지는 <strong>TCP 프로토콜을 사용하여 인터넷을 거쳐 해당 IP 주소의 컴퓨터로 전송</strong>된다.</li>
   </ol>
   <ol>
      <li>이렇게 도착한 HTTP 요청 메시지는 HTTP 프로토콜을 사용하여 웹 페이지 URL 정보로 변환되어 <strong>웹 페이지 URL 정보에 해당하는 데이터를 검색</strong>한다.</li>
   </ol>
   <ol>
      <li>검색된 웹 페이지 데이터는 또 다시 <strong>HTTP 프로토콜을 사용하여 HTTP 응답 메시지를 생성</strong>하고 <strong>TCP 프로토콜을 사용하여 인터넷을 거쳐 원래 컴퓨터로 전송</strong>된다.</li>
   </ol>
   <ol>
      <li>도착한 <strong>HTTP 응답 메시지는 HTTP 프로토콜을 사용하여 웹 페이지 데이터로 변환</strong>되어 웹 브라우저에 의해 출력되어 사용자가 볼 수 있게 된다.</li>
   </ol>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>도메인 이름으로 실제 IP를 어떻게 찾을 수 있는지 흐름을 설명해 주세요.</strong></span></summary>
<hr>
   <p><strong>Recursive Query를 통해 접근 : Local DNS 서버 -&gt; Root DNS 서버 -&gt; com DNS 서버 -&gt; naver.com DNS 서버</strong></p>
   <ol>
      <li>로컬 DNS서버에 해당 url이 등록되어있는지 확인</li>
   </ol>
   <ol>
      <li>루트 DNS서버에 문의 후 최상위 도메인 .com이 등록된 네임 서버의 IP주소 전달</li>
   </ol>
   <ol>
      <li>로컬 DNS서버는 com DNS 서버에 해당 url을 문의함. 로컬 DNS서버에 naver.com DNS 서버의 IP 주소 알려줌</li>
   </ol>
   <ol>
      <li>naver..com에 해당 url 문의함. 로컬 DNS는 IP 주소를 받을수있음</li>
   </ol>
   <figure/></a></figure>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>유니캐스트, 멀티캐스트, 브로드캐스트란?</strong></span></summary>
<hr>
   <p>유니캐스트 : 특정 대상과 1:1 통신</p>
   <p>멀티캐스트 : 특정 다수와 1:N 통신</p>
   <p>브로드캐스트 : 네트워크에 있는 모든 대상과 통신</p>
   <p></p>

<hr>
</details>

<p></p>
<h2>TCP/UDP</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>TCP와 UDP의 차이에 대해서 설명해 주세요.</strong></span></summary>
<hr>
   <p><strong>TCP</strong></p>
   <ul>
      <li>신뢰성 있는 데이터 전송을 지원하는 연결 지향형 프로토콜</li>
   </ul>
   <ul>
      <li>흐름제어, 혼잡제어, 오류제어 지원</li>
   </ul>
   <ul>
      <li>연결 설정시 3 way handshake를, 연결 해제시 4 way handshake 진행</li>
   </ul>
   <ul>
      <li>UDP보다 속도가 느리다</li>
   </ul>
   <ul>
      <li><strong>EX)</strong> 웹 http 통신, 이메일, 파일 전송</li>
   </ul>
   <p><strong>UDP</strong></p>
   <ul>
      <li>데이터를 데이터그램 단위로 처리하는 프로토콜</li>
   </ul>
   <ul>
      <li>신뢰성 낮음</li>
   </ul>
   <ul>
      <li>속도가 빠르고 부하가 적다</li>
   </ul>
   <ul>
      <li><strong>EX)</strong> Real Time Protocol(RTP), Multicast, DNS</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>TCP 헤더에 대해서 설명해 주세요.</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>MTU가 무엇인가요?</strong></span></summary>
<hr>
   <p><strong>Maximum Transmission Unit</strong></p>
   <ul>
      <li>패킷이나 프레임의 최대 크기</li>
   </ul>
   <ul>
      <li>데이터의 크기가 크다면 단편화해야함</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>3-way hand shake, 4-way hand shake 흐름에 대해서 설명해주세요.</strong></span></summary>
<hr>
   <h3>3 way handshake</h3>
   <ul>
      <li>TCP/IP 프로토콜을 사용해 통신을 진행할떄, 두 종단간 정확한 데이터 전송 보장하기 위해 연결을 설정</li>
   </ul>
   <ul>
      <li>SYN(Synchronize Sequence Number)</li>
   </ul>
   <ul>
      <li>ACK(Acknowledgement)</li>
   </ul>
   <ol>
      <li><strong><mark class="highlight-yellow_background">클라이언트</mark></strong> → <strong><mark class="highlight-purple_background">서버</mark></strong> : <mark class="highlight-red">서버 접속 요청 </mark><mark class="highlight-red"><strong>SYN 패킷</strong></mark> 보냄</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-purple_background">서버</mark></strong> → <strong><mark class="highlight-yellow_background">클라이언트</mark></strong> : <mark class="highlight-orange">요청 수락 응답 </mark><mark class="highlight-orange"><strong>ACK 패킷</strong></mark>과 <mark class="highlight-teal">포트 열어달라는 </mark><strong><mark class="highlight-teal">SYN 패킷</mark></strong> 보냄</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-yellow_background">클라이언트</mark></strong> → <strong><mark class="highlight-purple_background">서버</mark></strong> : <mark class="highlight-blue">확인 응답으로 </mark><mark class="highlight-blue"><strong>ACK 패킷</strong></mark> 보냄</li>
   </ol>
   <ul>
      <li>
         <details>
            <summary>사진</summary>
<hr>
            <figure/></a></figure>
         </details>
      </li>
   </ul>
   <h3>4 way handshake</h3>
   <ul>
      <li>연결 설정 해제함</li>
   </ul>
   <ol>
      <li><strong><mark class="highlight-yellow_background">클라이언트</mark></strong>→ <strong><mark class="highlight-purple_background">서버</mark></strong> : <mark class="highlight-red">연결 해제하겠다는 </mark><strong><mark class="highlight-red">FIN 패킷</mark></strong> 보냄</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-purple_background">서버</mark></strong> → <strong><mark class="highlight-yellow_background">클라이언트</mark></strong> : <mark class="highlight-orange">응답으로</mark><strong><mark class="highlight-orange"> ACK 패킷</mark></strong> 보냄</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-purple_background">서버</mark></strong> → <strong><mark class="highlight-yellow_background">클라이언트</mark></strong>: 처리해야할 모든 통신 끝내고 <mark class="highlight-teal">연결 종료하겠다는 </mark><strong><mark class="highlight-teal">FIN 패킷</mark></strong> 보냄</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-yellow_background">클라이언트</mark></strong>→ <strong><mark class="highlight-purple_background">서버</mark></strong> : <mark class="highlight-blue">확인 응답으로 </mark><strong><mark class="highlight-blue">ACK 패킷</mark></strong> 보냄</li>
   </ol>
   <ul>
      <li>
         <details>
            <summary>사진</summary>
<hr>
            <figure/></a></figure>
         </details>
      </li>
   </ul>

<hr>
</details>

<p></p>
<h2>HTTP</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>HTTP 프로토콜에 대해서 아는대로 말해주세요.</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>HTTP와 HTTPS 의 차이는 무엇인가요?</strong></span></summary>
<hr>
   <p>HTTP는 인터넷 상에서 클라이언트와 서버가 자원을 주고받기 위한 통신규약인데, 텍스트로 자원을 주고받기 때문에 네트워크를 가로챈다면 내용이 유출되는 보안 이슈가 발생할 수 있습니다.</p>
   <p>이를 해결하는 것이 HTTPS입니다.</p>
   <p>HTTPS에 SSL 프로토콜을 사용해 정보를 암호화하는데, 메모리나 리소스를 더 많이 쓸 수 있다는 특징이 있습니다.</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>HTTPS가 동작하는 방식에 대해서 설명해 주세요.</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>HTTP Method 종류 및 역할</strong></span></summary>

- `기타 메소드` : 잘 사용되지 않는 메소드들
   - HEAD : GET과 동일하지만 메시지 바디를 제외하고 반환
   - OPTIONS : 대상 리소스에 대한 통신을 설정하는 데 사용
   - CONNECT : 대상 자원으로 식별되는 서버에 대한 터널을 설정
   - TRACE : 대상 리소스에 대한 경로를 따라 메시지 루프백 테스트를 수행
   
**[대표적으로 5개가 있다]**   

- `GET` 
   - 리소스의 조회에 사용한다. 
   - 서버에 전달하고 싶은 데이터를 (쿼리스트링 = 이름과 값으로 쌍을 이루는 파라미터)을 통해 전달한다.
   - GET 요청은 중요한 정보를 다루면 안된다 → 쿼리스트링에 다 노출이 되기 때문에

- `POST`
   - 메시지 바디를 통해 서버로 요청 데이터를 전달한다. 
   - 서버는 메시지 바디를 통해 들어온 데이터를 처리하는 모든 기능을 수행한다.
   -  GET 보다는 보안이 좋지만, 암호화되어 있지 않으면 body의 내용도 볼 수 있음 

- `PUT`
  - 목적 리소스를 현재 메시지의 값으로 생성하거나 만약 존재한다면 기존 리소스를 삭제하고 덮어쓰기 한다. 

- `PATCH`
  - 리소스를 부분적으로 변경한다.
  - 지원하지 않는 경우도 있어 이런 경우 POST로 대체하여 사용

- `DELETE`
  - 특정 리소스의 삭제를 요청하는 데 사용

   <br>
   
- 💡HTTP GET과 POST의 차이는 무엇인가요?   
  - `사용목적`: 조회VS데이터생성
  - `바디`: GET도 바디를 가질 수 있지만 통상적으로 사용하지 않기 때문에 요청에 body 유무
  - `멱등성`: GET은 멱등 / POST는 비멱등 (여러번 베서드 적용시 결과가 달라지나, POST요청시 서버 데이터 변경)
 : GET을 통해 서버에 리소스를 요청할 때 웹 캐시가 요청을 가로채 서버로부터 리소스를 다시 다운로드하는 대신 리소스의 복사본을 반환한다. HTTP 헤더에서 cache-control 헤더를 통해 캐시 옵션을 지정할 수 있다.
  - `캐싱` :  GET 방식의 요청은 브라우저에서 Caching 할 수 있다. 때문에 POST 방식으로 요청해야 할 것을 보내는 데이터의 크기가 작고 보안적인 문제가 없다는 이유로 GET 방식으로 요청한다면 기존에 caching 되었던 데이터가 응답될 가능성이 존재한다. 때문에 목적에 맞는 기술을 사용해야 하는 것이다.
  - `브라우저 히스토리`: GET 요청은 브라우저 히스토리에 남음 / POST는 안남음
  - `요청길이제한`: GET 요청은 길이 제한 존재 /POST는 없음
  - `보안`: GET 요청은 중요한 정보를 다루면 안된다. (쿼리 스트링에 노출될 보안)

   
- 💡POST와 PUT은 어떻게 구분해서 사용할까?
   - PUT은 POST와 다르게 클라이언트가 리소스의 위치를 알고 URI를 지정해 주어야 한다!
   - ex) PUT /members/100
 
   
- 💡`GET` 은 정말 바디를 보낼 수 없을까?
   - 메소드와 request body를 독립적으로 보고 GET에 body값을 실어 요청할 수도 있다.
   - 하지만 설계가 뒤죽박죽될 수 있고 GET에 body를 보내지 않게 지원되는 RestTemplate들이 있다 이처럼 특정 클라이언트나 서버에서 Get body가 무시되는 경우가 왕왕있다
   =>설계가 뒤죽박죽 될 가능성, GET의 body를 지원하지 않는 클라이언트를 고려해 Get에서 Body를 제거하는게 일반적이다.
 
- 💡`GET`에 바디를 보내면 어떻게 되나?
   - HTTP통신을 위해 제공되는 라이브러리마다 다르다
   - HttpClient는 body를 불일 수 있는데
   - body를 무시하거나 예외를 던지는 라이브러리들도 있다
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>HTTP 1.0과 1.1의 차이는 무엇인가요?</strong></span></summary>

 - `HTTP 1.0`  
   - 연결을 할 때마다 TCP 세션을 맺어야 함(3way-handshaking)
   - 데이터 전송 완료시 바로 연결을 끊는다
      - 커넥션 하나당 요청 하나랑 응답 하나만 처리해줄수 있다 근데 이게 매번 요청이 하나올때마다 연결해줘야하니까 매번 새로운 연결로 성능저하, 서버 부하 비용이 큼
   
 - `HTTP 1.1`  
   - 퍼시스턴트 커넥션: Keep-Alive속성. 지정한 시간동안 커넥션을 닫지 않는거라 한 커넥션을 열어두면 여러 요청이 이 커넥션을 사용할 수 있다
   그래서 이전에 사용했던 단기 커넥션과 비교하면 네트워크 사용시간이 많이 줄었다
   -  파이프라이닝: 응답 안받고 다음 요청 보낼 수 있음
      - HTTP 요청은 원래 순차적으로 응답을 처리 1번에 대한 요청 응답이 들어와야 2,3번 요청 응답을 처리할 수 있음
   근데 이러면 하나의 커넥션을 위해 응답 대기 시간도 있고 ,, 그래서 하나의 커넥션에서 응답을 기다리지 않고 순차적인 여러 요청을 연속적으로 보내 그 순서에 맞춰 응답을 받는 방식으로 지연 시간을 줄이는 방법
   
- HTTP 2.0
   - 기존 http/1.x버전의 **성능향상**에 초점을 맞춘 프로토콘
   - 표준의 대체가 아닌 **확장**
   - 한번에 커넥션으로 동시에 여러개의 데이터 주고받기 가능
   - 헤더압축: 파이프라이닝할때  연속된 요청이라 헤더의 중복이 있을수잇는데 중복을 그대로 보냈었음 HTTP 2.0에선 압축
   - 서버푸시: 클라이언트가 요청하지 않았지만 필요할거라고 생각한 리소스를 미리 보냄

</details>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>HTTP 헤더의 구조에 대해서 설명해 주세요.</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>keep-alive 헤더에 대해서 설명해 주세요.</strong></span></summary>
<hr>
   <p>HTTP는 매번 연결을 끊고 새로 생성함</p>
   <p>HTTP 1.1부터는 Keep/alive를 지원</p>
   <p>특정 시간까지는 access가 없더라도 기다리고 연결된 상태를 유지함, 이미 열려있는 곳에 요청</p>

<hr>
</details>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>쿠키와 세션에 대해서 설명해 주세요.</strong></span></summary>

[얄코](https://www.youtube.com/watch?v=OpoVuwxGRDI)   
   
- `쿠키와 세션을 사용하는 이유`
  - HTTP는 통신이 끝나면 상태를 유지하지 않는 특징
  - 연결을 끊는 순간 클라이언트와 서버의 통신이 끝나며 상태 정보는 유지하지 않는 특성이 있다.
  - 쿠키와 세션은 위의 두 가지 특징을 해결하기 위해 사용합니다.
  - 예를 들어, 쿠키와 세션을 사용하지 않으면 쇼핑몰에서 옷을 구매하려고 로그인을 했음에도, 페이지를 이동할 때 마다 계속 로그인을 해야 합니다.

쿠키와 세션을 사용했을 경우, 한 번 로그인을 하면 어떠한 방식에 의해서 그 사용자에 대한 인증을 유지하게 됩니다.
- `쿠키`
  - 쿠키는 클라이언트(브라우저) **로컬에 저장**되는 **작은 데이터 파일**을 의미한다(키와 값으로 이루어짐)
  - 쿠키에는 이름, 값, 만료 날짜, 도메인, 경로 정보가 포함되어 있다
  - Response Header에 Set-Cookie 속성을 사용하면 클라이언트에 쿠키를 만들 수 있습니다.
  - 쿠키는 사용자가 따로 요청하지 않아도 브라우저가 Request시에 Request Header를 넣어서 자동으로 서버에 전송합니다
  - 지워져도 상관 없고, 가로채이더라도 큰 문제가 없는 정보들을 저장
   
- `쿠키의 동작 방식`
  - 1. 클라이언트가 페이지를 요청
  - 2. 서버에서 쿠키를 생성
  - 3. HTTP 헤더에 쿠키를 포함 시켜 응답
  - 4. 브라우저가 종료되어도 쿠키 만료 기간이 있다면 클라이언트(브라우저)에서 보관하고 있음
  - 5. 같은 요청을 할 경우 HTTP 헤더에 쿠키를 함께 보냄
  - 6. 서버에서 쿠키를 읽어 이전 상태 정보를 변경 할 필요가 있을 때 쿠키를 업데이트 하여 변경된 쿠키를 HTTP 헤더에 포함시켜 응답
- `쿠키의 사용 예시`
    - 팝업에서 '오늘 이 창을 더 이상 보지 않음'에 체크를 했음을 저장
    - 아이디와 비밀번호를 저장한다는걸 체크했음을 저장->자동로그인
   
   <br>
   
- `세션`
  - 세션은 **쿠키를 기반으로 하고 있지만**, 사용자 정보 파일을 브라우저에 저장하는 쿠키와 달리 **세션은 서버 측에서 관리.(세션은 쿠키의 일종이다)**
  - 서버에서는 클라이언트를 구분하기 위해 **세션 ID**를 부여하며, 웹브라우저가 서버에 접속하여 웹브라우저를 종료할 때까지 인증 상태를 유지한다
  - 보안이 쿠키보다 좋지만, **사용자가 많아질수록 서버 메모리의 차지량이 늘어난다 
  → 동접이 많은 사이트의 경우, 서버에 과부하를 주게 된다

- `세션의 동작 방식`
    - 클라이언트가 서버에 접속 시 **세션 ID를 발급**받습니다.
    - 클라이언트는 **세션 ID를 쿠키에 저장해서** 가지고 있습니다.
    - 클라이언트는 서버에 요청할 때, 이 쿠키의 **세션 ID를 서버에 전달**합니다.
    - 서버는 세션 ID를 전달 받아서 별다른 작업없이 세션 ID로 세션에 있는 클라이언트 정보를 가져옵니다. = 어떤 사용자가 네이버에 로그인 이미 되어있는 상태에서 네이버 쇼핑 화면에 들어가면 또 로그인할 필요가 없다 즉 로그인되어있다는 정보
    - 클라이언트 정보를 가지고 서버 요청을 처리하여 클라이언트에게 응답합니다.
    - 타인에게 노출되면 안되는 중요 정보를 저장
- `세션의 사용 예시`
    - 로그인->네이버쇼핑페이지 들어가도 로그인되어있음=인증되어있음
 
- `캐시`   
  - 캐시는 후에 필요할 것 같은 요소를 저장하기 위한 임시 저장소이다.

   
- `쿠키와 세션의 차이`
  - 1. **저장 위치**: 쿠키는 브라우저에 저장, 세션은 서버에 저장
  - 2. **보안** : **세션이 쿠키에 비해 보안이 우수하다.** 쿠키는 값이 변질될 수도 있고, request를 보내는 중간에 스니핑당할  우려가 있기 때문. 반면 세션은 sessionid만을 클라이언트에서 저장하고 그 이외는 모두 서버에서 처리하므로 훨씬 보안이 우수하다.
  - 3. 속도 : **쿠키가 세션보다 속도가 더 빠르다.** 세션의 경우에는 서버에 접근하는 처리가 요구되어 속도가 더 느리다
  - 4. **라이프 사이클**:  쿠키는 파일로 저장되기 때문에, 브라우저가 종료되어도 **만료기간까지 남아있다**. 반면, 세션은 만료기간이 남았더라도 브라우저가 종료되면 그에 상관없이 삭제된다
   
- `쿠키와 캐시의 차이` = 만료시간
  - 쿠키는 만료시간이 있어 시간이 지나면 자동삭제
  - 한번 캐시에 저장되면 브라우저를 참고하기 때문에 서버에서 변경이 되어도 사용자는 변경되지 않게 보일 수 있음
  - 사용자가 직접 수동으로 삭제해주거나
  - 서버에서 클라이언트로 응답을 보낼 때 header에 캐시 만료시간을 명시하는 방법
   
   
</details>

<p></p>
<h2>웹</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>www.naver.com에 접속할때 일어나는 일</strong></span></summary>
   
   https://hongjuzzang.github.io/web/web_browser2/
   
```kotlin
1. 브라우저 주소창에 www.naver.com을 입력한다  
2. DNS를 통해 IP주소를 획득한다  
3. 획득한 IP주소에 있는 서버와 TCP 3 Way Handshake를 진행한다  
4. 통신을 맺은 서버에 Http Request를 한다  
5. 서버에서 보낸 Http Response를 통해 HTML 파일을 받는다  
6. 브라우저가 HTML을 분석해서 화면으로 그린다  
```
- `브라우저 주소창에 www.naver.com을 입력한다`     
   - 브라우저: 서버-클라이언트가 쌍방향으로 통신하고 HTML 문서나 파일을 출력하는 그래픽 사용자 인터페이스 기반의 응용 소프트웨어
   - 브라우저의 주요 기능은 사용자가 선택한 자원을 서버에 요청하고 브라우저에 표시하는 것
   - 주요 웹 브라우저로는 구글의 크롬, 사파리 등이 있습니다
   
- `4개의 DNS에 캐싱된 IP주소 있는지 확인`
  - `로컬 DNS 서버`에 해당 url이 등록되어 있는 지 확인 후 있으면=캐싱되어있으면 바로 IP주소를 알려준다.
  - `Root DNS 서버`: 만약 IP 주소를 못찾을 시 루트 DNS 서버에게 문의 후 루트 DNS 서버는 최상위 도메인이 .com인 것을 확인 후 ".com"이 등록된 네임 서버의 IP Address를 전달한다. 즉 com 도메인을 관리하는 DNS 서버에 문의해보라고 로컬 DNS 서버에게 .com DNS 서버의 IP주소를 알려주는 것이다.
  - `com DNS 서버`: 로컬 DNS 서버는 이제 com DNS 서버에게 해당 url(www.naver.com) 을 문의한다. 역시나 com DNS 서버에는 해당 url(www.naver.com)이 없으므로 "naver.com"을 관리하는 DNS 서버에게 문의하도록 로컬 DNS 서버에게 naver.com DNS 서버의 IP주소를 알려준다.
  - `naver.com DNS 서버`: 로컬 DNS 서버는 이제 naver.com DNS 서버에게 해당 url(www.naver.com)을 문의한다. "naver.com 도메인을 관리하는 DNS 서버"에는 "www.naver.com"에 대한 IP 주소가 있으므로 로컬 DNS 서버에게 해당 IP를 알려주는 것이다.
  - 이와 같이 로컬 DNS 서버가 열 DNS 서버를 차례대로(Local DNS 서버 -> Root DNS 서버 -> com DNS 서버 -> naver.com DNS 서버) 물어보며 답을 찾는 과정을 Recursive Query라고 부른다.

- `획득한 IP주소에 있는 서버와 TCP 3 Way Handshake를 진행한다`  
- `통신을 맺은 서버에 request를 보낸다`
   - HTTP 프로토콜을 사용하여 request 메시지 생성 
   - 클라이언트는 GET 요청을 통해 서버에게 www.google.com 웹페이지를 요구한다.
- `서버가 HTTP response를 보낸다.`
   - HTTP 프로토콜을 사용하여 HTTP 응답 메시지를 생성
   - TCP 프로토콜을 사용하여 인터넷을 거쳐 원래 컴퓨터로 전송된다.
- `도착한 HTTP 응답 메시지를 화면으로 그린다` 
   - 브라우저의 렌더링 엔진의 역할은 브라우저 구조 중 요청한 콘텐츠를 표시. 예를 들어 HTML을 요청하면 HTML과 CSS를 파싱하여 화면에 표시함
</details>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>웹브라우저에서 서버로 요청했을 때, 흐름을 설명해주세요.</strong></span></summary>
<hr>
   <p>웹 브라우저가 URL해석-&gt;URL이 문법맞으면 Punycode encoding을 url의 host부분에 적용-&gt; HSTS (HTTP Strict Transport Security 목록 로드해서 체크 -&gt;DNS 확인-&gt; ARP로 IP/MAC 확인 -&gt;TCP 통신을 통해 Socket을 열고 .HTTP 프로토콜로 요청 -&gt; HTTP 서버가 응답 -&gt;  웹 브라우저가 그린다.</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>CORS란 무엇인가요?</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>웹 서버와 웹 어플리케이션 서버(WAS)의 차이는 무엇인가요?</strong></span></summary>
<hr>
   <p><strong>웹 서버</strong></p>
   <ul>
      <li>항상 동일한 데이터를 주는 정적 콘텐츠를 제공</li>
   </ul>
   <ul>
      <li>동적 콘텐츠 제공을 위해 WAS에 클라이언트의 요청을 보내고 결과를 전달</li>
   </ul>
   <ul>
      <li>정적 콘텐츠만 처리해 서버 부담을 줄임</li>
   </ul>
   <p><strong>웹 어플리케이션 서버(WAS)</strong></p>
   <ul>
      <li>동적인 컨텐츠를 제공</li>
   </ul>
   <ul>
      <li>DB 접속/트랜잭션 관리/비즈니스 로직 수행</li>
   </ul>
   <ul>
      <li>요청에 맞는 콘텐츠를 제공하기 위해 필요함, 단순한 정적 콘텐츠는 웹 서버에 맡겨 부하를 줄임</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>REST API에 대해서 설명해 주세요.</strong></span></summary>
<hr>
   <p>HTTP를 통해 자원을 주고 받을 때 HTTP URI를 통해 자원을 명시하고 HTTP Method를 통해 자원의 CRUD를 수행하는 것을 말합니다.</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>REST ful</strong></span></summary>
<hr>
   <p>REST의 원리를 따르는 시스템을 말합니다. </p>
   <p>RESTful하지 못한 경우로는 (1) CRUD 기능을 POST로만 처리하는 경우나 (2) URI에 resource, id 외의 정보가 들어가는 경우입니다. </p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>API Gateway란 무엇인가요?</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>API Gateway가 다운되면 모든 API를 사용 못할지도 모르는데, 어떤 방안을 마련해야 할까요?</strong></span></summary>
<hr>

<hr>
</details>

<p></p>
<h2>기타</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>nagle 알고리즘에 대해 설명하세요.</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>TLS에 패킷 프토토콜의 대해 설명하세요</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>TLS</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>네트워크 Layer 라우팅 알고리즘</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>SNI 필드 차단</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>흐름제어 / 혼잡제어 / 오류제어</strong></span></summary>
<hr>
   <p><strong>흐름제어</strong>는 송신측과 수신측 사이의 데이터 처리 속도 차이를 해결하기 위한 기법입니다.</p>
   <p><strong>혼잡제어</strong>는 송신측의 데이터 전달과 처리 속도 차이를 해결하는 기법입니다.</p>
   <p><strong>오류제어</strong>는 패킷이 잘못 전달됐을 경우 패킷을 재전송하는 등 오류를 복구하는 기법입니다.</p>
   <p></p>
   <p><strong>흐름제어</strong></p>
   <ul>
      <li>송신측과 수신측 사이의 데이터 처리 속도 차이(흐름)를 해결하기 위한 기법</li>
   </ul>
   <ul>
      <li>송신측의 패킷 전송량 제어해서 수신측의 버퍼 오버플로우 방지</li>
   </ul>
   <p></p>
   <p><strong>오류제어</strong></p>
   <ul>
      <li>오류 검출과 재전송</li>
   </ul>
   <ul>
      <li>프레임이 손상되었거나 손실되면 재전송해서 오류 복구</li>
   </ul>
   <p></p>
   <p><strong>혼잡제어</strong></p>
   <ul>
      <li>송신측의 데이터 전달과 데이터 처리 속도를 해결하기 위한 기법</li>
   </ul>
   <ul>
      <li>네트워크 혼잡 제어를 피하기 위해 데이터의 전송 속도  제어</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>로드 밸런서 / 로드 밸런싱은 무엇인지 설명하세요.</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>WebRTC</strong></span></summary>
<hr>
   <p>어플리케이션(최근에는 Android 및 IOS도 지원) 및 사이트들이 별도의 소프트웨어 없이 음성, 영상 미디어 혹은 텍스트, 파일 같은 데이터를 브라우져끼리 주고 받을 수 있게 만든 기술</p>

<hr>
</details>

<p></p>
</div>
