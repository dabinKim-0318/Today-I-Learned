

# 안드로이드 기초 <a name = "reason"></a>
<details>
   <summary> 안드로이드 4대 컴포넌트에 대해 설명하시오</summary>
<br />


![ㅁㄴㅇ](https://user-images.githubusercontent.com/84564695/187105028-837f6503-2830-4f8b-9ee1-67f187b9194e.jpg)
👉[click](https://www.notion.so/4-Activity-Service-BroadCast-Receiver-Content-Provider-6e2dcace26b443f488fc4b27489c8254)

   ***
 </details>

<details>
   <summary> 📌안드로이드 실행환경 </summary>
<br />
- 안드로이드는 크게 4가지로 구성되어있습니다.
- 리눅스 커널, 라이브러리, 어플리케이션 프레임워크, 어플리케이션입니다.
- 리눅스 커널은 OS로 스마트폰의 메모리나 프로세스 등을 관리합니다.
- 라이브러리는 안드로이드에 있는 다양한 기능을 라이브러리를 제공하며 안드로이드 앱을 구동해주는 dalvik 가상머신을 포함합니다.
- 어플리케이션 프레임워크는 사용자의 이벤트에 따라 출력을 담당하는 환경을 제공합니다. 생명주기도 여기서 관리. 
 - 어플리케이션은 실제로 동작하는 앱을 말합니다.
   ***
 </details>
 
 <details>
   <summary> 안드로이드는 다른 플랫폼에 비해 어떠한 장점이 있는가 </summary>
<br />
   
- 오픈소스이므로 안정성과 버그 수정이 빠르다  
- 자바를 주 언어로 사용하여 자바 개발자들이 쉽게 개발할 수 있음
- 리눅스 커널을 OS로 사용하여 하드웨어에 대한 드라이버 소스가 풍부함 
***
 </details>
 
   <details>
   <summary> Activity란? </summary>
   
<br />
- Android 앱의 필수적인 기본 구성 요소(컴포넌트) 중 하나입니다
- Activity는 사용자와 상호작용하기 위한 진입점입니다.
- 사용자 인터페이스(UI) 화면을 구성하는 컴포넌트입니다
- 대부분의 앱은 한 개의 Activity가 아닌 여러 Activity로 이루어져 있습니다. 
 
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CActivity-LifeCycle%EC%88%98%EB%AA%85%EC%A3%BC%EA%B8%B0)
   
***
 </details>
 
 <details>
   <summary> Fragment란? </summary>
- 정의
   - 프래그먼트는 앱의 전체 UI에서 어딘가에 반복적으로 재사용 가능한 부분을 말합니다.  
- 등장배경
   - 1) Activity 안에 코드가 길어지게 되면 코드가 길어지니까 유지보수할 때 관리가 어려워짐
     2) 안드로이드 디바이스는 휴대폰,태블릿 등 다양하기 때문에 태블릿UI를 고려할 때 단순 Activity로 화면을 그리기에 한계가 있음
- 특징
   - 1) 프래그먼트는 자체 레이아웃(xml파일을 정의할 수 있음)을 가질 수 있으며 자체 생명 주기를 보유
   - 2) 프래그먼트는 독립적으로 존재할 수 없고, 반드시 Activity나 다른 프래그먼트에 호스칭 되어야함
   - 3) 프래그먼트는 자체 UI를 개별적인 청크로써 사용할 수 있습니다. 개별 청크 단위로 다른 곳에서 재사용
- 사용법
   - 1) Activity UI 레이아웃 안에 프래그먼트 존재를 정의하여 Activity UI가 Activity 클래스에 inflate될 때 프래그먼트 자체 UI도 자동으로 프래그먼트 클래스에 inflate 시키는 방법
   - 2) Activity UI 레이아웃 안에 프래그먼트 컨테이너(=이 위치에 프래그먼트 자체 UI가 배치될 것입니다~ 라고 위치를 지정해두는 것)를 정의하고 프로그래밍적으로 해당 컨테이너 안에 프래그먼트를 추가(Add)하는 방법
  * 주의할 점은 두 방법 모두 Activity UI 레이아웃 안에 FragmentContainerView 를 정의함으로써 해당 프래그먼트가 배치될 위치를 정의해야 한다는 점입니다.
   
 👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%ED%94%84%EB%9E%98%EA%B7%B8%EB%A8%BC%ED%8A%B81)
***
 </details>
   
 </details>
 
 <details>
   <summary> Activity와 Fragment의 차이 </summary>
<br />
- 목적성
   - Activity는 앱 전체적인 사용자 인터페이스(UI)에 포함될 요소들을 배치하는 곳입니다. Fragment는 단일 화면이나 화면 일부에 관한 사용자 인터페이스(UI)를 정의하는데 적합합니다.
 - 종속성
    - 프래그먼트는 액티비티나 다른 프래그먼트에 종속되어야 합니다. 액티비티나 프래그먼트 내의 공간을 효율적으로 이용하기 위해 사용됩니다. 하나의 액티비티나 프래그먼트는 0개 또는 여러개의 프래그먼트를 포함할 수 있습니다. 액티비티는 다른 액티비티나 프래그먼트에 종속되지 않고 독립적으로 존재할 수 있습니다.
   - 따라서 액티비티는 AndroidMenifest파일에 Activity컴포넌트를 등록하면 안드로이드 시스템에서 관리되고, 프래그먼트는 독립적으로 존재할 수 없어 Menifest에 등록하지 않고 Activity나 상위 Fragment에 호스팅해야합니다.
 - 재사용성
   - 프래그먼트는 여러개의 액티비티나 프래그먼트 안에서 재사용될 수 있어 재사용 가능한 컴포넌트처럼 동작할 수 있습니다.

   
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%ED%94%84%EB%9E%98%EA%B7%B8%EB%A8%BC%ED%8A%B81)
***
 </details>
 
   <details>
   <summary> Activity의 LifeCycle </summary>
<br />
 액티비티는 크게 3가지 상태가 존재합니다.먼저 running 실행 상태는 액티비티 스택의 최상위에 있으며 포커스를 가지고 있어 사용자에게 보이는 상태입니다. pasued 일시 중지 상태는 사용자에게 보이기는 하지만 다른 액티비티가 위에 있어 포커스를 받지 못하는 상태입니다.
stopped 중지 상태는 다른 액티비티에 의해 완전히 가려져 보이지 않는 상태를 말합니다.
   
   ![image (1)](https://user-images.githubusercontent.com/84564695/187110702-3f13eb5c-d5bb-4ead-a403-ba0e27f84d31.png)

   👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CActivity-LifeCycle%EC%88%98%EB%AA%85%EC%A3%BC%EA%B8%B0#%EC%88%98%EB%AA%85%EC%A3%BC%EA%B8%B0%EB%9E%80)
    
***
 </details>

   <details>
   <summary> Fragment의 LifeCycle </summary>
<br />
   
     ![ㅁㅁ](https://user-images.githubusercontent.com/84564695/187110664-a727c532-9afe-427f-a2be-104b74c1e6cf.jpg)

   👉[click](https://abundant-playground-8c8.notion.site/LifeCycle-Activity-Fragment-89e3dd9483c04ef68151187fe04b0a84)
 
***
 </details>
 
<details>
   <summary> RecyclerView란? </summary>
<br />
   
***
 </details>
 
 <details>
   <summary> RecyclerView와 ListView의 차이? </summary>
<br />
   
***
 </details>
 
  <details>
   <summary> View가 그려지는 과정 </summary>
<br />
   
***
 </details>
 
  <details>
   <summary>Intent와 IntentFilter란? </summary>
<br />
   
***
 </details>
 
   <details>
   <summary>ANT이란? </summary>
<br />
   
***
 </details>
 
<details>
 <summary>인플레이션이란? </summary>
<br />
   
***
 </details>
 
 <details>
 <summary>Context란? </summary>
<br />
   
***
 </details>
 
 <details>
 <summary>안드로이드 매니페스트 파일이란? </summary>
<br />
   
***
 </details>
 
  <details>
 <summary> Thread, Looper, Handler에 대해 설명하라 </summary>
<br />
   
***
 </details>
 
   <details>
 <summary>디스플레이(display), 윈도우(window), 서피스(surface), 뷰(view), 뷰 그룹(view group), 뷰 컨테이너(view container), 레이아웃(layout)에 대해 설명하라</summary>
<br />
   
***
 </details>
 
<details>
 <summary>노티피케이션이란?</summary>
<br />
   
***
 </details>
 
 <details>
 <summary>Task란?</summary>
<br />
   
***
 </details>
 
  <details>
 <summary>안드로이드의 메모리 관리 방식?</summary>
<br />
   
***
 </details>
 
<details>
 <summary>어노테이션이란?</summary>
<br />
   
***
</details>
 
 
<details>
 <summary>ViewPager?</summary>
<br />
   
***
 </details>
 
 

<p></p>
<h2>안드로이드 심화</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>액티비티간 데이터 전달에서 임의의 클래스 객체를 바로 전달하지 못하는 이유는 무엇이고 전달하기 위해서는 어떤 처리가 필요한가?</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>부모 액티비티에서 자식 액티비티의 결과 값을 받아오기 위해 어떻게 해야하는가?</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>안드로이드가 리소스(resource)를 접근하는 방식에 대해서 설명하시오.</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>디바이스를 회전할 때 Activity에서 일어나는 과정에 대해 설명하시오</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Singleton Pattern에 대해 설명하시오</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Viewholder Pattern이란 무엇인가?</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>MVC, MVP, MVVM에 대해서 설명하시오</strong></span></summary>
<hr>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>액티비티 스택에 대해 설명하시오</strong></span></summary>
<hr>

<hr>
</details>

<p></p>
<h2>안드로이드 응용</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Dependency Injection이란?</strong></span></summary>
<hr>
   <p>의존성 주입이란 외부에서 의존 객체를 주입해줘서 결합도를 줄여주는 것을 말합니다.</p>
   <p>생성자에서 주입하는 방식과 setter를 사용하는 방법이 있습니다.</p>
   <p>장점은 (1) 종속성이 감소해 변경에 대한 여파가 줄어들고, (2)재사용성이 증가하고, (3) 테스트가 용이합니다.</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Koin과 Dagger의 차이점은?</strong></span></summary>
<hr>
   <p><strong>Koin</strong></p>
   <ul>
      <li>런타임과정에 DI 주입</li>
   </ul>
   <ul>
      <li>컴파일이 빠름</li>
   </ul>
   <ul>
      <li>런타임 에러 가능</li>
   </ul>
   <ul>
      <li>Module에서 선언한 DI를 캐시에 저장하고 by inject로 캐시를 조회해서 객체를 가져옴</li>
   </ul>
   <p><strong>Dagger</strong></p>
   <ul>
      <li>Annotation을 통해 컴파일과정에 DI 주입</li>
   </ul>
   <ul>
      <li>컴파일은 느리지만 런타임에서 에러 발생하지 않음</li>
   </ul>
   <ul>
      <li>컴파일 시 오버헤드 발생</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>SharedPreferences란?</strong></span></summary>
<hr>
   <ul>
      <li>키-값 쌍이 포함된 파일을 가리킴</li>
   </ul>
   <ul>
      <li>데이터를 파일로 저장하므로 앱을 삭제하면 데이터도 삭제됨</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>DiffUtil이란?</strong></span></summary>
<hr>
   <p>두 목록 간의 차이점을 찾고 업데이트되어야 할 목록을 반환함</p>
   <p>추가 및 제거 작업할 아이템을 찾기위해 O(n) 소요</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>직렬화와 역직렬화란?</strong></span></summary>
<hr>
   <p><strong>직렬화</strong></p>
   <ul>
      <li>객체를 연속적인 데이터로 변형해 전송 가능한 형태로 만드는것</li>
   </ul>
   <ul>
      <li>JVM 메모리에 상주되어있는 객체를 바이트 형태로 변환</li>
   </ul>
   <p><strong>역직렬화</strong></p>
   <ul>
      <li>직렬화된 파일을 다시 객체의 형태로 만드는것</li>
   </ul>
   <ul>
      <li>직렬화된 바이트 형태의 데이터를 객체로 변환해 JVM으로 상주시킴</li>
   </ul>
   <p><strong>직렬화해야하는 이유</strong></p>
   <ul>
      <li>디스크에 저장하거나 통신에는 value type만 가능하고 reference타입은 불가능</li>
   </ul>
   <ul>
      <li>PC마다 사용하고 있는 메모리 주소는 다르다.</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Immutable이란?</strong></span></summary>
<hr>
   <p>값을 변경할 수 없는 것</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Image Loading 라이브러리에는 어떤 것이 있는가?</strong></span></summary>
<hr>
   <p><strong>Glide</strong></p>
   <ul>
      <li>화질이 더 안좋음</li>
   </ul>
   <ul>
      <li>메모리 덜 씀</li>
   </ul>
   <p><strong>Picasso</strong></p>
   <ul>
      <li>화질 좋음</li>
   </ul>
   <ul>
      <li>메모리 더 씀</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Android Ktx이란?</strong></span></summary>
<hr>
   <ul>
      <li>코틀린 개발용 확장 라이브러리</li>
   </ul>
   <ul>
      <li>확장함수, 람다, 이름이 지정된 매개변수, 코루틴 등 지원</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>데이터바인딩이란?</strong></span></summary>
<hr>
   <p><strong>데이터바인딩</strong></p>
   <ul>
      <li>데이터를 결합시켜 동기화하는 방식</li>
   </ul>
   <p><strong>안드로이드 데이터바인딩 라이브러리</strong></p>
   <ul>
      <li>UI 컴포넌트와 데이터를 programmatic하게 연결하지 않고, 선언형으로 결합하도록 도와줌</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>GSON이란?</strong></span></summary>
<hr>
   <p>JSON과 JAVA 사이의 직렬화와 역직렬화를 도와주는 라이브러리</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Retrofit과 Okhttp란?</strong></span></summary>
<hr>
   <p><strong>Retrofit</strong></p>
   <ul>
      <li>Type-safe한 HttpClient 라이브러리</li>
   </ul>
   <ul>
      <li>Type-safe : 네트워크로부터 전달된 데이터를 우리 프로그램에서 필요한 형태의 객체로 받을 수 있음</li>
   </ul>
   <ul>
      <li>보통 Http 요청을 위해서는 <strong>연결, 캐싱, 재시도, 스레딩, 응답 분석, 오류 처리</strong> 등을 해야하는데, 라이브러리는 이것들을 알아서 해줌</li>
   </ul>
   <p><strong>OkHttp</strong></p>
   <ul>
      <li>REST API와 HTTP통신을 간편하게 구현할 수 있도록 도와주는 라이브러리</li>
   </ul>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Volley와 Retrofit의 차이는?</strong></span></summary>
<hr>
   <p><strong>Volley</strong></p>
   <ul>
      <li>용량이 작고 빠른 실행 속도</li>
   </ul>
   <ul>
      <li>동시 네트워크 연결</li>
   </ul>
   <ul>
      <li>요청 우선순위 지원</li>
   </ul>
   <ul>
      <li>JSON Object나 Array 반환</li>
   </ul>
   <p><strong>Retrofit</strong></p>
   <ul>
      <li>속도가 빠르다</li>
   </ul>
   <p></p>
   <figure/></a></figure>

<hr>
</details>
