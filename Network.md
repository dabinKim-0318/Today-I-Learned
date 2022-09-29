
# Network

<h2>전산 기본</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘TCP/IP</strong></span></summary>
   
- TCP/IP는 **패킷 통신**을 위한 통신 규약이다.
- **현재의 인터넷에서 컴퓨터들이 서로 정보를 주고받는데 쓰이는 프로토콜의 모음**
- TCP/IP는 **인터넷 프로토콜인 IP**와 **전송 조절 프로토콜인 TCP**로 이루어져 있다.
- SMTP, HTTP, HTTPS, FPS 등 우리에게 친숙한 인터넷 서비스 대부분이 TCP/IP 기반으로 이루어져 있다.
- IP는 복잡한 네트워크 망에서 빠른 길을 찾는 역할을 한다.
  - **데이터의 순서, 손실에 대해 고려하지 않는다**
  - 단순 데이터 전달만을 담당.
  - **IP는 신뢰도가 낮다**

- TCP는 데이터를 잘게 잘라 보내면서, 패킷에 **일련의 번호를 붙여 순서를 재조합**하고 **손실을 찾아내 교정**한다.
  - **TCP는 복잡한 만큼 신뢰도가 높다**

**(데이터의 정확성 확인은 TCP가, 패킷을 목적지까지의 전송은 IP가 담당**
   
</details>   

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>OSI 7계층</strong></span></summary>
   
- `정의` : 네트워크에서 통신이 일어나는 과정을 7단계로 나눈 것
- `나눈 이유`
     - 한눈에 보기 쉽고 이해하기 쉽다
     - 네트워크에 이상이 생기면 어디에서 생긴 문제인지 파악하고 해당 계층만 고치면 됨
     - OSI 7계층 생기기 이전엔 표준이 없으니까 데이터 전송이 어려웠음
      
<img width="500" alt="01" src="https://user-images.githubusercontent.com/84564695/187700599-9ace277b-44ad-427e-9a65-01e1fe748fd4.png">
   
- `7-애플리케이션 계층` => 메세지
      - 응용 프로그램과 연관하여 사용자가 이용할 수 있는 통신서비스 형태로 만든다
      - HTTP, FTP프로토콜

- `6-프레젠테이션 계층` => 메세지
      - 어플리케이션 계층(7계층)이 **다양한 데이터 타입을 다루는 부담을 덜어준다.**
      - **인코딩/ 암호화** 등을 담당
      - ex) 해당 데이터가 TEXT인지 그림인지 GIF인지 등을 구분
   
 - `5-세션 계층` => 메세지
      - 데이터가 통신하기 위한 논리적인 연결을 말한다. 통신을 하기위한 대문이라고 보면 된다.
      - 세션 설정, 유지 등 TCP/IP 세션을 만들고 없애는 책임
    
 - `4-트랜스포트 계층` => TCP(세그멘테이션) / UDP(데이터그램)
      - 신뢰성 있는 데이터를 주고받을 수 있게 함 
      - 포트 번호를 통해 애플리케이션 프로토콜 식별
      - TCP / UDP 프로토콜 
      
 - `3-네트워크 계층` => 통신 단위 **패킷**
      - **IP주소**를 부여
      - 목적지까지 가기위한 경로를 설정하는 역할 (길을 찾는 역할)→ **Routing(라우팅)**
      - 라우터의 입력 포트에서 출력 포트로 패킷을 이동시키는 역할 → **Forwarding(포워딩)**
      - 대표적인 장비로는 **Router**: IP헤더에 기록된 목적지의 IP주소를 보고 다음 전송처 결정
   
- `2-데이터링크 계층` => 통신 단위 **프레임**
      - 인접한 네트워크 노드들끼리 데이터를 전송하는 기능과 절차 제공
      - 네트워크 인터페이스 카드에 적혀있는 MAC주소를 가지고 통신한다
      - 물리계층에서 생길 수 있는 오류 감지하고 수정
      - 이더넷(Ethernet)
  
 - `1-물리 계층` => 통신 단위 **비트**
      - 데이터<->신호
      - 변환방법은 통신매체에 의존하기 때문에 프로토콜이 정해져 있지 않다
      - 케이블, 허브 장비 사용
 
   
- `TCP / IP 계층과 OSI 7 계층의 차이`
  - TCP / IP 계층이 OSI 7계층 보다 먼저 개발되었음
  - OSI 7계층은 장비, 개발, 통신, 설계를 위한 표준으로 사용되지만, **실제 통신에서는 TCP / IP**를 사용한다
  - TCP / IP는 **지속적인 표준화로 신뢰성이 높지만**, OSI 7계층은 적은 구현으로 인해 신뢰성이 다소 낮다  
   
</details>



<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘DNS가 무엇인가요?</strong></span></summary>

 - **IP주소를 문자로 표현한 주소로 바꾸는 시스템 혹은 서버**

        ex) [naver.com](http://naver.com) 은 도메인이고 dns에서는 이것을 34.32.222와 같은 ip주소로 바꿔준다.

- DNS는 **분산계층 데이터 베이스**이다

     → DNS를 여러 서버로 나누고, 이들을 계층 형태로 구성해 전세계로 분산시켜두었다.  
   
- DNS 서버에서  IP 주소를 찾는 과정
   
   <img width="500" alt="01" src="https://user-images.githubusercontent.com/84564695/187702819-41df8a9e-d53b-4cb0-b539-217aa7f49884.png">


(1) 브라우저가 설치된 컴퓨터는 www.naver.com IP를 알아내기 위해서 ***Local DNS 서버*** naver.com의 IP를 문의 

(2) ***Local DNS 서버***가 IP를 알고 있다면 즉시 IP 주소 줌 하지만 IP 주소를 모르면 ***Root DNS서버***에게 문의

(3) ***Root DNS서버***는 도메인의 최상위 도메인 .com인 것을 보고 ***.com 관리하는 네임서버***의 IP를 전달 =  "나는 IP 주소를 가지고 있지 않지만, .com 네임서버에게 물어보면 도와줄꺼야" 

(4) ***Local DNS 서버*** 는 ***.com 관리하는 네임서버***을 관리하는 네임서버에게 문의한다. 

(5) ***.com 관리하는 네임서버***는 ***naver 네임서버*** IP 주소를 알려준다. 

(6) ***Local DNS 서버***는 ***naver 네임서버***에게 문의하고, 

(7) ***www 의 네임서버***를 알려준다. 

(8) 최종적으로 ***www 네임서버***에게 문의 후 

(9) www.naver.com의 IP 주소를 얻는다. 

(10) ***Local DNS 서버***는 이 IP 주소를 클라이언트에게 알려준다. 클라이언트 컴퓨터는 이 IP를 브라우저에게 알려주면 브라우저는 이 IP에 해당하는 컴퓨터에 접속 할 수 있게 된다.
   
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
   <summary><span style="border-bottom:0.05em solid"><strong>☘TCP와 UDP의 차이에 대해서 설명해 주세요.</strong></span></summary>

- `ICMP`
 - IP 계층에서 생긴 **오류**를 보고하는 역할
 - 위험한 상황에 대한 경보
 - **오류에 대한 해결은 못함**  - IP 프로토콜과 함께 쓰임
   
- `TCP와 UDP가 등장하게 된 배경은?`
  - IP 프로토콜로 송신자를 찾아갈 수 있지만, 그 안에서 여러 프로세스가 동작하고 있을 경우 어떤 프로세스에게 메세지를 전달해야 할지 알지 못하기 때문
  - IP 계층에서 오류가 발생했을 때, 해결이 필요함 → IP 계층의 ICMP 프로토콜은 **오류 보고**만 가능, **해결은 불가능**
   
   <img width="500" alt="01" src="https://user-images.githubusercontent.com/84564695/187839359-a567046b-540d-4099-ad25-954b1e8c35a5.png">
   
- 신뢰성: 순서 / 재전송 / 흐름제어, 혼잡제어
- 속도
- 데이터 스트림(경계X) / 데이터그램(경계O)
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>🦑TCP 헤더에 대해서 설명해 주세요.</strong></span></summary>

   https://www.notion.so/TCP-UDP-676ca61cb16f4b7796d4ff1b7f780eb1
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>MTU가 무엇인가요?</strong></span></summary>

- `MTU(maximum transmission unit)`:데이터 링크 계층 프레임이 전달할 수 있는 최대 데이터 양
   - 모든 데이터 링크계층 프로토콜이 같은 크기의 데이터를 전달할 수 없다 프로토콜마다 다름  
- `단편화`: MTU 보다 큰 데이터그램은 전송이 불가능 하기 때문에 MTU 보다 작은 크기로 만들어 주는 과정


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

   <h3>4 way handshake</h3>
   <ul>
      <li>연결 설정 해제함</li>
   </ul>
   <ol>
      <li><strong><mark class="highlight-yellow_background">클라이언트</mark></strong>→ <strong><mark class="highlight-purple_background">서버</mark></strong> : <mark class="highlight-red">연결 해제하겠다는 </mark><strong><mark class="highlight-red">FIN 패킷</mark></strong> 보냄</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-purple_background">서버</mark></strong> → <strong><mark class="highlight-yellow_background">클라이언트</mark></strong> : <mark class="highlight-orange">응답으로</mark><strong><mark class="highlight-orange"> ACK 패킷</mark></strong> 보냄(서버는 본인이 전송할 데이터 남았으면 마저 다 전송 필요)</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-purple_background">서버</mark></strong> → <strong><mark class="highlight-yellow_background">클라이언트</mark></strong>: 처리해야할 모든 통신 끝내고 <mark class="highlight-teal">연결 종료하겠다는 </mark><strong><mark class="highlight-teal">FIN 패킷</mark></strong> 보냄</li>
   </ol>
   <ol>
      <li><strong><mark class="highlight-yellow_background">클라이언트</mark></strong>→ <strong><mark class="highlight-purple_background">서버</mark></strong> : <mark class="highlight-blue">확인 응답으로 </mark><strong><mark class="highlight-blue">ACK 패킷</mark></strong> 보냄</li>
   </ol>
 

<hr>

- TCP의 연결 설정 과정(3단계)과 연결 종료 과정(4단계)이 단계가 차이나는 이유?
 - 클라이언트가 데이터 전송을 마쳤다고 하더라도 서버는 아직 보낼 데이터가 남아있을 수 있기 때문에,곧바로 클라이언트에게 FIN 메세지를 보내지 않고,  FIN에 대한 ACK만 먼저 보내고, 남은 데이터를 모두 전송하는 단계 필요

- **만약 Server에서 FIN 플래그를 전송하기 전에 전송한 패킷이 Routing 지연이나 패킷 유실로 인한 재전송 등으로 인해 FIN 패킷보다 늦게 도착하는 상황이 발생하면 어떻게 될까?**
  - 해당 패킷이 도착하기 전에 연결이 close된 상태라면, 해당 패킷은 유실되고 drop 될 것이다. 이를 방지하기 위해, client에서는 FIN응답을 받은 이후, 바로 연결을 close하지 않고 일정시간 동안 time-wait 상태로 패킷을 기다리며 세션을 유지하고 있는다.

</details>

<p></p>
<h2>HTTP</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘HTTP 프로토콜에 대해서 아는대로 말해주세요.</strong></span></summary>
<hr>

- HTTP(HyperText Transfer Protocol =하이퍼텍스트 트랜스펄 프로토콜=웹페이지 교환 프로토콜)
  - TCP/IP 5계층 중 애플리케이션 계층에 있는 프로토콜 중 하나
  - 애플리케이션 계층의 역할이통신 서비스의 실현인데, HTTP는웹 서비스를 실현하기 위한프로토콜임
  - Web browser, Web server가 통신할때 사용하는규칙
  - 요청,응답이라는 두 종류의패킷을 사용해텍스트 형식으로 주고받기 수행
  - 암호화 되지 않은 평문 데이터를 전송하는 프로토콜 → 기밀한 정보를 주고받기에 적절 x
    - 위장 가능
      - 악의를 가진 누군가가 자신이 클라이언트인것처럼, 혹은 서버인 것처럼 위장을 할 수 있다
    - 변조 가능
      - 지금 내가 받고 있는 데이터가 진짜 서버(클라이언트)가 보낸 것 과 같은지 확인을 하지 않기 때문에 중간에 누군가가 개입해 정보를 바꾸더라도 알지 못한다
  
- Connectionless (비연결성)
    - 클라이언트와 서버가 한번 연결을 맺은 후, 클라이언트의 요청에 서버가 응답을 마치면 맺었던 연결을 끊어버리는 성질
    - 장점
        - **리소스 감소를 통한 더 많은 연결(연결 유지에 대한 리소스가 필요 없음)**
    - 단점
        - 동일한 클라이언트의 요청에 대해 **매번 새로운 연결/연결해제 를 진행하는 오버헤드**가 발생
- Stateless (무상태)
    - 이전 요청에 대한 결과를 기억하고 있지 않음
    - 장점
        - 이전 통신 정보를 저장하고 있을 필요가 없어서 서버 설계가 간단하다
        - 서버를 쉽게 **증설 가능 어떤 서버가 처리해도 상관 없기 때문**
        - 각각의 독립적 요청에 대해 응답만 해주면  OK
    - 단점
        - HTTP 요청을 보낼 때 마다 **해당 요청을 처리하기 위한 모든 데이터를 매번 보내야 한다(클라이언트가 추가 정보 전달)**
        - ex) 회원 정보를 조회하는 요청을 처리하기 위해선, 로그인이 되어 있는지 여부를 매번 파악해야 함   
   
<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘HTTP와 HTTPS 의 차이는 무엇인가요?</strong></span></summary>
<hr>

- HTTPS(Hyper Text Transfer Protocol over Secure Socket Layer)
  - http에 **암호화가 추가**된 프로토콜
  - 이름에서 알 수 있듯이, **SSL 프로토콜 위에서 동작**
  - 모든 HTTP 요청과 응답 데이터는 **네트워크로 보내지기 전에 암호화**된다.


   
<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘HTTPS가 동작하는 방식에 대해서 설명해 주세요.</strong></span></summary>
<hr>
## **HTTPS의 동작 과정**

- HTTP의 기본 동작에 아래의 내용이 추가된다.

: HandShake → 전송 → 세션 종료

<HandShake의 과정> 

1. 유저가 서버(사이트)에 접속하면, **서버는 자신의 인증서(암호화된 상태)를 웹브라우저에 제공**한다
2. 웹 브라우저는 미리 가지고 있던 **CA의 공개키**로 인증서를 **복호화**한다.
3. 웹브라우저는 인증서에 포함되어 있는 **사이트의 공개키**로 **대칭키를 암호화**해서 서버에 전달한다
4. 서버는 **자신의 개인키**로 암호문을 해독해, 대칭키를 얻게 되고, 이 **대칭키**로 데이터를 주고받게 된다

      → ssl에서는 암호화된 데이터를 전송하기 위해 공개키와 대칭키를 모두 사용한다.
<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘HTTP Method 종류 및 역할</strong></span></summary>

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
   <summary><span style="border-bottom:0.05em solid"><strong>☘쿠키와 세션에 대해서 설명해 주세요.</strong></span></summary>

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
   <summary><span style="border-bottom:0.05em solid"><strong>☘www.naver.com에 접속할때 일어나는 일</strong></span></summary>
   
   https://hongjuzzang.github.io/web/web_browser2/
   [잘 정리된 벨로그](https://velog.io/@tnehd1998/%EC%A3%BC%EC%86%8C%EC%B0%BD%EC%97%90-www.google.com%EC%9D%84-%EC%9E%85%EB%A0%A5%ED%96%88%EC%9D%84-%EB%95%8C-%EC%9D%BC%EC%96%B4%EB%82%98%EB%8A%94-%EA%B3%BC%EC%A0%95)
   
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
   <summary><span style="border-bottom:0.05em solid"><strong>☘REST / REST원칙 / REST API에 대해서 설명해 주세요.</strong></span></summary>

- `REST= Representational State Transfer`
  -  HTTP를 잘 활용하기 위한 원칙이자 네트워크 아키텍쳐 스타일(청사진이  

- `REST원칙` = 행위+자원
   - URI로 자원을 표현하는 데에 집중하고, 자원의 상태(행위)에 대한 정의는 HTTP METHOD

   
-  `RESTful API`   
   - REST원칙을 잘 지킨 API
      - CRUD 기능을 POST로만 하는 경우
      - GET /members/delete/1 -> DELETE /members/1
        - URI는 자원을 표현하는데 중점을 두어야 한다. delete와 같은 행위에 대한 표현이 들어가서는 안된다.
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>API Gateway란 무엇인가요?</strong></span></summary>

 - 서비스로 전달되는 모든 api요청의 관문역할
 - 서버 시스템의 아키텍쳐를 내부로 숨기고 외부 요청에 대한 응답만을 적절한 형태로 전달
   - 클라이언트는 서버 내부 구조 상관없이 서로 약속된 형태의 api요청만 서버로 보내면됨
   
 - 장점
   - 클라이언트의 요청을 일괄적으로 처리
   - 시스템 내부에 아키텍쳐를 숨길 수 있음
   - 시스템상에 오고가는 요청과 응답에 대해 모니터링 가능
   
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>🦑API Gateway가 다운되면 모든 API를 사용 못할지도 모르는데, 어떤 방안을 마련해야 할까요?</strong></span></summary>
<hr>

<hr>
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
      <li>사용자가 웹브라우저에 어떤 페이지 요청하면 정적컨텐츠(단순HTML문서,CSS,javascript) 제공하는 서버</li>
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
   
  
 <h2>back</h2>
   
 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>Server에서 FIN 플래그를 전송하기 전에 전송한 패킷이 Routing 지연이나 패킷 유실로 인한 재전송 등으로 인해 FIN 패킷보다 늦게 도작한 상황이 발생하면?</strong></span></summary>

이러한 현상을 대비하여 Client는 Server로부터 FIN 플래그를 수신하더라도 일정기간 time wait동안 세션을 남겨 놓고 잉여 패킷을 기다리는 과정을 거친다.
   
</details>
   
 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>포트와 소켓</strong></span></summary>

- 포트
  - 네트워크를 통해 데이터를 주고받는 **프로세스를 식별하기 위해 호스트 내부적으로 프로세스가 할당받는 고유한 값**
  - 하나의 IP 주소 내에 개별적으로 부여된 통신 프로세스
    
- 소켓
  - 네트워크상에서 동작하는 프로그램 간 통신의 종착점(Endpoint)
  - **두 시스템 사이의 네트워크 연결을 나타내는 객체**
  - 소켓을 열기 위해선 호스트에 할당된 IP, 포트 번호, 프로토콜이 필요하다.
  - 위 세가지가 소켓을 정의할 수 있지만 유일하게 식별하지는 않는다.
  - 보내는 쪽과 받는 쪽 모두 소켓을 열어야 한다.
  - 하나의 프로세스가 같은 포트를 갖고 여러 개의 소켓을 열 수 있다.

   
</details>
   
<details>
   <summary><span style="border-bottom:0.05em solid"><strong>keep-alive 헤더</strong></span></summary>
HTTP는 매번 연결을 끊고 새로 생성한다.
특정 시간까지는 access가 없더라도 기다리고 연결상태를 유지하는 헤더이다.
HTTP 1.1부터는 defualt로 keep-alive를 지원한다.
   
</details>


 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>세션은 서버에 저장되고, 쿠키는 클라이언트에 저장된다고 하셨는데, 그럼 쿠키가 안되는 상황에서도 세션은 사용할 수 있나요?</strong></span></summary>

 쿠키를 사용할 수 없을 때는 url 뒤쪽에 파라미터 값으로 전달하는 경우가 있다.

  
</details>

 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>JWT</strong></span></summary>

- 보통 로그인 방식으로는 세션과 쿠기를 통해 구현한다.
세션에 저장된 정보는 고유 세션ID가 부여되는데 사용자가 로그인을 하면 서버는 쿠키에 세션ID를 실어서 보낸다. 
- 브라우저는 쿠키를 쿠키저장소에 갖고 있다가 다음 페이지를 요청할 때 해당 유저의 쿠키를 다시 요청헤더에 포함해서 전송한다. 
- 서버는 쿠키 내부의 세션ID를 통해 세션 내부에 일치하는 유저 정보를 가져와서 처음에 로그인한 유저가 맞는지 확인하는 작업이 반복되면서 로그인 상태가 유지된다.
- 세션은 서버의 메모리 내부에 저장되기 때문에 많아지는 만큼 메모리에 부하가 걸리게 되고, 확장 시 세션을 분산시키는 기술을 따로 설계해야 한다.
- JWT는 토큰을 만들어 발행하는 방식 으로 쿠키에 담거나 HTTP 헤더에 담아서 보낼 수 있다. 따로 서버에서 저장하지 않기 때문에 토큰이 유효한지 검증하는 과정만 있으면 된다.
- 하지만 탈취에 의해 악의적으로 사용될 가능성이 있기에 보통 유효시간을 짧게 가져가고 Refresh 토큰을 사용하는 방식으로 구현한다.
쿠키는 웹브라우저에서 사용할 수 있는 기능이므로 모바일 애플리케이션에서는 JWT를 사용한 인증방식이 최적이다.
   
</details>


 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>OAuth</strong></span></summary>
자신이 소유한 리소스에 소프트웨어 애플리케이션이 접근할 수 있도록 허용해 줌으로써 접근 권한을 위임해주는 개방형 표준 프로토콜

</details>
   

 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>URI</strong></span></summary>

</details>
 
- URI는 인터넷 자원을 식별하기 위한 문자열 이다.
- URI는 인터넷 주소 같은 것으로 정보 리소스를 유일하게 식별하고 위치를 지정할 수 있다.

```
http://test.com/company/location
http://test.com/member/jobhope
URI의 하위 개념으로 URL, URN이 있다.
```

 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>URL</strong></span></summary>

- 웹에서 자원의 위치를 나타낸다. 즉, 특정 서버의 한 리소스에 대해 구체적인 위치 를 표현한다.

```    
safefood.com 서버에서 food폴더 안의 salad.png를 요청하는 URL
>> http://safefood.com/food/salad.png

http://example.com/mypage.html - 실제 사이트 URL
http://img.naver.net/static/www/dl_qr_naver.png - 네이버 앱QR코드의 이미지에 대한 URL
```
    
</details>
   

 <details>
   <summary><span style="border-bottom:0.05em solid"><strong>중간자 공격</strong></span></summary>

두 사람이 서로 통신을 주고 받는데, 중간에 제 3의 인물이 끼여서 데이터를 중계한다면, 이 제3자는 그 내용을 모두 알 수 있고, 데이터를 위/변조할 경우 두 사람에게 서로 잘못된 정보를 전달하게 만들 수도 있다. 중간에서 데이터를 가로채는 것이 중간자 공격이다.
중간자 공격은 4가지가 있다.

- 스니핑
  - 시스템 및 네트워크에서 들어오고 나가는 데이터 패킷을 캡쳐한다.
- 패킷 주입
  - 공격자가 일반 데이터와 함께 악의적인 데이터를 주입한다.
- 세션 하이재킹
  - 세션 가로채기라고도 불리며 두 시스템 간 연결이 활성화된 상태를 가로채는 것
- 보안 소켓 계층 스트리핑
  - 공격자는 SSL/TLS 연결을 차단하여 프로토콜 보안성이 있는 HTTPS에서 안전하지 않은 HTTP로 전환한다.

    
 이 공격법을 방어하기 위한 목적으로 만들어진 것이 TLS 통신이다. TLS 통신은 클라이언트가 연결을 요청하면 서버에서 자신의 공개키가 포함된 인증서를 보내고, 클라이언트는 인증서의 내용을 연결 프로그램(웹 브라우저 등) 또는 운영체제에 내장된 루트 인증서 정보와 비교하여 무결성을 검증한 뒤, 인증서에 있는 공개키로 대칭형 암호화 키를 만들 수 있는 난수 정보를 공개키로 암호화해 서버로 보내며, 클라이언트와 서버가 각각 이 난수에서 암호화 키를 만들어내 암호화 연결이 개시된다.   
    
</details>
   

