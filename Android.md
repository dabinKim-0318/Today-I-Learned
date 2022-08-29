

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
   
- `정의`
  - Android 앱의 필수적인 기본 구성 요소(컴포넌트) 중 하나입니다 
  - Activity는 사용자와 상호작용하기 위한 진입점입니다. 
  - 사용자 인터페이스(UI) 화면을 구성하는 컴포넌트입니다 
  - 대부분의 앱은 한 개의 Activity가 아닌 여러 Activity로 이루어져 있습니다.  
 
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CActivity-LifeCycle%EC%88%98%EB%AA%85%EC%A3%BC%EA%B8%B0)
   
***
 </details>
 
 <details>
   <summary> Fragment란? </summary>
   
- `정의`
   - 프래그먼트는 앱의 전체 UI에서 어딘가에 반복적으로 재사용 가능한 부분을 말합니다.  
- `등장배경`
   - 1) Activity 안에 코드가 길어지게 되면 코드가 길어지니까 유지보수할 때 관리가 어려워짐
     2) 안드로이드 디바이스는 휴대폰,태블릿 등 다양하기 때문에 태블릿UI를 고려할 때 단순 Activity로 화면을 그리기에 한계가 있음
- `특징`
   - 1) 프래그먼트는 자체 레이아웃(xml파일을 정의할 수 있음)을 가질 수 있으며 자체 생명 주기를 보유
   - 2) 프래그먼트는 독립적으로 존재할 수 없고, 반드시 Activity나 다른 프래그먼트에 호스칭 되어야함
   - 3) 프래그먼트는 자체 UI를 개별적인 청크로써 사용할 수 있습니다. 개별 청크 단위로 다른 곳에서 재사용
- `사용법`
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
   
- `목적성`
   - Activity는 앱 전체적인 사용자 인터페이스(UI)에 포함될 요소들을 배치하는 곳입니다. Fragment는 단일 화면이나 화면 일부에 관한 사용자 인터페이스(UI)를 정의하는데 적합합니다.
 - `종속성`
    - 프래그먼트는 액티비티나 다른 프래그먼트에 종속되어야 합니다. 액티비티나 프래그먼트 내의 공간을 효율적으로 이용하기 위해 사용됩니다. 하나의 액티비티나 프래그먼트는 0개 또는 여러개의 프래그먼트를 포함할 수 있습니다. 액티비티는 다른 액티비티나 프래그먼트에 종속되지 않고 독립적으로 존재할 수 있습니다.
   - 따라서 액티비티는 AndroidMenifest파일에 Activity컴포넌트를 등록하면 안드로이드 시스템에서 관리되고, 프래그먼트는 독립적으로 존재할 수 없어 Menifest에 등록하지 않고 Activity나 상위 Fragment에 호스팅해야합니다.
 - `재사용성`
   - 프래그먼트는 여러개의 액티비티나 프래그먼트 안에서 재사용될 수 있어 재사용 가능한 컴포넌트처럼 동작할 수 있습니다.

   
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%ED%94%84%EB%9E%98%EA%B7%B8%EB%A8%BC%ED%8A%B81)
***
 </details>
 
   <details>
   <summary> Activity의 LifeCycle </summary>
<br />

- 액티비티는 크게 3가지 상태가 존재합니다.
   - running 실행 상태는 액티비티 스택의 최상위에 있으며 포커스를 가지고 있어 사용자에게 보이는 상태입니다. 
   - pasued 일시 중지 상태는 사용자에게 보이기는 하지만 다른 액티비티가 위에 있어 포커스를 받지 못하는 상태입니다.
   - stopped 중지 상태는 다른 액티비티에 의해 완전히 가려져 보이지 않는 상태를 말합니다.
   
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
   
 - [정의](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CRecycle-View)
   - 리사이클러뷰는 사용자가 관리하는 많은 수의 데이터 집합(Data Set)을 개별 아이템 단위로 구성하여 화면에 출력하는 뷰그룹(ViewGroup)이며, 한 화면에 표시되기 힘든 많은 수의 데이터를 스크롤 가능한 리스트로 표시해주는 위젯입니다
- `등장배경`
   - 리사이클러뷰 전에 스크롤 가능한 리스트로 표현하기 위해서 ListView를 사용했었습ㄴ,ㅣ다. ListView는 한번에 ItemView를 그리기 어려웠음->속임수1)눈에 보이는 ItemView만 생성->속임수2)맨위에 있던 ItemView를 그려져야할 위치에 재사용->문제1)개발자들 요구사항 증가->문제2)다른 뷰에서 제공하는 비슷한 기능이 ListView에 추가되며 혼란->문제3)애니메이션 처리 문제->문제3)재사용될 ItemView인지 분기처리 필요->문제4)Adapter는 변경된 Item Data의 Position알 수 없음===>저 구글인데요 미안합니다 RecyclerView만들게요 ㅠㅠ ㅎㅎ
   
 - [특징](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CRecycle-View)
   -  RecyclerView의 내부 아키텍쳐는 컴포넌트(Component)기반 아키텍쳐입니다.
   - 그 중 Layout Manager, Item Animator, Adapter 라는 3가지 컴포넌트가 가장 중요합니다
    - **Layout Manager** :RecyclerView의 모양 책임. ItemView를 올바른 위치에 배치해주는 컴포넌트 
      - 선형/격자형/엇갈린 격자형
      - 때문에 RecyclerView 본인은 자기 자신이 선형 모양이 될지, 격자형 모양이 될지, 엇갈린 격자형 모양이 될지에 관해 알고 있지 않고, 각 ItemView가 어느 위치에 놓여야 하는지에 관해서도 관여하지 않습니다.
    - **ItemAnimator** :ItemView의 애니메이션을 담당하는 컴포넌트
    - **Adapter** :RecyclerView에 ItemView를 생성/제공/data set이 변경되었을 때 리사이클러뷰에게 알리는 컴포넌트
      - ItemView외에도 ListView와 다르게 ViewHolder 생성 강제
   
 - [동작원리](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-RecyclerView%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83-2%ED%83%84ViewHolder%EC%88%98%EB%AA%85%EC%A3%BC%EA%B8%B0)
   ![image](https://user-images.githubusercontent.com/84564695/187114067-896686a6-c52b-40f3-9782-8fa09f5fa7a6.jpg)
1) 사용자 스크롤이 일어나면 레이아웃 매니저가 RecyclerView에게 view를 요청
2) RecyclcerView는 원하는 ViewHoler가 있는지 ViewHolder로 이루어진 리스트 Cache를 먼저 방문한다고 했습니다.
3) 캐시에 없으면 adapter에게 배치되어야할 ItemView의 ViewHoler type이 뭔지 물어보고 Recycled Pool에 요청
   Recycled Pool은 getRecycledView의 파라미터로 ViewType을 전달하면, ViewType에 맞는 ViewHolder를 return해줍니다. ViewType마다 ViewHolder Pool을 가지고 있습니다
4) Pool에 있으면 반환, 없으면 adapter에게 createViewHolder로 아이템 생성.
5) pool에서 viewholder를 찾으면 adapter에서 bindview를 하고 LayoutManager에게 리턴.
6) LayoutManager는 addView를 수행하고 adapter의 onViewAttachedToWindow가 호출됨.

   *캐시와 Recycled Pool은 RecyclerView안에 이미 선언되어있음.
   *캐시 사이즈 변경 가능 기본용량 2개
   *pool 사이즈 변경 가능 기본용량 5개
   
  
   
***
 </details>
 
 <details>
   <summary> RecyclerView와 ListView의 차이? </summary>
   
- `AdapterView`
   - AdapterView는 많은 양의 data를 효율적으로 표시하고 Adapter가 관리하는 데이터를 출력(data set의 형태로 눈에 보이도록)할 수 있게 해주는 View이다.
   
 - `ListView`
   - ListView는 수직 스크롤 가능하도록 만드는 뷰이고 AdapterView중 가장 많이 사용되기도 합니다
   - ListView는 AdapterView이기 때문에 Adapter을 사용해야하며 ArrayAdapter, BaseAdapter를 통해 구현할 수 있습니다
   - View를 재활용하지 않거나 ViewHolder를 사용하지 않으면 매번 같은 view를 inflate하고 findViewById를 호출해서 비효율적입니다
   - `성능개선`
     - **1) View재활용: inflate줄이기**
       - 사용자의 눈에 보이는 View만 생성해두고 스크롤이 발생하면 맨 위에 있던 View를 가장 아래로 가져오고 그 안에 들어간 data만 바꾸는 방법 
       - 실제 화면에 그려지는 아이템을 convertView라는 배열로 관리합니다. 화면에 보여지는 만큼 convertView를 생성하고 스크롤하면 이 View를 재활용합니다. 즉 convertView는 ListView의 재활용 View입니다
     - **2) ViewHolder사용하기: findViewById줄이기( ViewGroup 밑에 있는 모든 뷰들을 전부 한 번씩 순회하며 id값을 비교하는 과정을 거치기 때문에 자원이 많이 듭니다)**
       - view는 재활용하는데, 정작 데이터 셋팅할 때 convertView의 자식뷰(textView 등) 정보를 매번 findViewById()를 통해 다시 가져와 재연결하기 때문에 비효율적입니다. 문제는 ViewHolder패턴을 이용하면 해결가능합니다
       - ViewHolder는 ItemView의 각 요소를 바로 엑세스 할 수 있도록 저장해두고 사용하기 위한 객체입니다
       -  converView의 tag에 viewHolder를 넣어주면 view를 재활용할때 viewHolder의 정보도 함께 불러올 수 있습니다
   
- `장점`
   - ListView는 간단하게 리스트를 만드는 부분에 있어서는 장점을 가지고 있다. [ex) 텍스트만 있는 리스트]
   - 간단한 아이템 형태를 만드는 경우에는 빠르게 적용이 가능한 ArrayAdapter를 제공한다.
- `차이`
   - 수직 스크롤밖에 안됨 
   - 애니메이션 처리 문제
   - ViewHolder강제 유뮤 -> 고비용의 findViewById
   - item배치만 담당하는 layoutManager유무
   
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-Adapter-AdapterView%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83)
   
   
<br />
   
***
 </details>
 
  <details>
   <summary> 📌View가 그려지는 과정 </summary>
<br />
   
- 액티비티가 포커스를 얻으면 자신의 레이아웃을 그리도록 한다
- 액티비티에 레이아웃의 계층구조 중 루트 노드를 제공해야함
- 레이아웃의 루트노드에서 시작해 레이아웃 트리를 따라 이동
- 부모 뷰는 자식 뷰 이전에 그려짐
- 자식 뷰는 전위순회 방식으로 그려짐
- measure, layout 단계가 있음
   
***
 </details>
 
  <details>
   <summary>Intent와 IntentFilter란? </summary>
<br />
   
   ![KakaoTalk_20220711_214321306](https://user-images.githubusercontent.com/84564695/187116433-7aa6c027-efae-4969-9055-73116e342793.jpg)
👉[click](https://www.notion.so/Intent-pending-intent-sticky-intent-4cf97968d28a4a18b4403118c1793a5a)
   
***
 </details>
 
   <details>
   <summary>ANR이란? </summary>
<br />
   
   ![KakaoTalk_20220713_205339727](https://user-images.githubusercontent.com/84564695/187116773-21dcca73-785b-4770-ba89-a8d7369f5af1.jpg)

 - `정의`
   - 앱의 UI 스레드가 너무 오랫동안 차단되면 나타나는 오류 
 
 - `원인`
   - 메인스레드인 UI스레드는 제약사항이 있는데요. 반드시 화면 UI그리기를 담당하는 것입니다
   - UI를 순차적으로 그려내기 위해 메인 스레드 하나에서만 UI작업을 합니다
   - 만약 UI이벤트 작업에 5초 안에 응답하지 않으면 
   - 안드로이드 시스템은 ANR(Android Not Responsing)이라는 팝업창을 띄웁니다
 
 - `해결방안`
   - 이러한 문제점을 막기위해 불안정한 UI관련 작업이나 비동기 작업(애니메이션 등) , High Cost의 연산작업 (Database 처리등) 등은 Worker Thread를 따로 만들어 처리하도록 합니다.

👉[click](https://www.notion.so/ANR-Thread-Looper-UI-486f771483564e67883aeac814fae8ef)
   
***
 </details>
 
<details>
 <summary>📌인플레이션이란? </summary>
<br />
   
자바 소스코드에서 xml의 구성요소들을 사용할 수 있게 객체로 만들어주는것

메모리상에 실제로 객체화되어 앱에 보여지는 것
   
***
 </details>
 
 <details>
 <summary>Context란? </summary>
<br />
   
- Context는 Android 시스템에서 구현체를 제공하는 추상클래스이다
- gc에 의해 수집되지 않는다
   
  ![KakaoTalk_20220711_214307895](https://user-images.githubusercontent.com/84564695/187117252-d356bea3-e488-4f39-a50d-a2a2444bcac8.jpg)
 
 👉[click](https://www.notion.so/Context-Application-Activity-2e40351127744b188cb72f6d9222b571)
***
 </details>
 
 <details>
 <summary>안드로이드 매니페스트 파일이란? </summary>
<br />
   
- 매니페스트는 앱의 이름, 버전, 구성요소, 권한 등 앱의 실행에 있어 필요한 각종 정보들이 저장되어있는 파일이다.
- 안드로이드 프로젝트의 최상위에 위치하고 있다.

***
 </details>
 
  <details>
 <summary> Thread, Looper, Handler에 대해 설명하라 </summary>
<br />

- 안드로이드는 메인스레드와 백그라운드 스레드 및 스레드간 통신을 위해 핸들러(Handler)와 루퍼(Looper)을 제공함
- `루퍼`
   - Main 스레드는 Looper를 가지지만, 기본적으로는 Looper를 가지지않음 스레드당 하나만 가질 수 있음
   - 루프(Loop)를 실행하고 그 루프(Loop) 안에서 메시지 큐(Message Queue)로 전달되는 메시지가 존재하는지 검사
   - 메시지 들어오면 꺼내서 핸들러에게 전달함

- `핸들러`
   - 루퍼에 의해 새로운 메시지가 포착되면 해당 메시지를 처리할 핸들러(Handler) 메서드를 실행
   - 새로 생성된 스레드들과 메인 스레드와의 통신을 담당함.
   - 루퍼를 통해 전달되는 메시지를 받아서 처리하는 일종의 명령어 처리기
   - 루퍼는 앱이 실행되면 자동으로 하나 생성되어 무한루프를 돌지만 핸들러는 개발자가 직접 생성
   
 
 👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%EC%8A%A4%EB%A0%88%EB%93%9CThread%EC%99%80-%EC%BD%94%EB%A3%A8%ED%8B%B4)
***
 </details>
 
   <details>
 <summary>디스플레이(display), 윈도우(window), 서피스(surface), 뷰(view), 뷰 그룹(view group), 뷰 컨테이너(view container), 레이아웃(layout)에 대해 설명하라</summary>
<br />
   
- `디스플레이` : 안드로이드 단말기가 가지는 하드웨어 화면
- `윈도우` : 화면에서 눈에 보이는 것을 담는 가장 기본적인 "공간"이자, 뭔가를 그릴 수 있는 "창"
- `서피스` : 윈도우에 그림을 그릴 때 화면에 합성되는 픽셀을 저장.  화면에 표시되는 모든 Window는 자신만의 Surface가 포함되어 있습니다
- `뷰 = 위젯`: 사용자가 보고 상호작용 할 수 있는 모든 것입니다. View객체는 "위젯"이라고도 하고, Button, TextView와 같은 클래스는 View class를 상속한 서브클래스 입니다 이처럼 View는 Button, TestView 등 어떤 기능을 하는 컴포넌트 입니다.
- `뷰 그룹 = 레이아웃`: View를 상속받고 있고, 하위에 여러 ViewGroup, View들을 포함하고 있습니다.(ViewGroup 안에 ViewGroup을 포함할 수 있음) ViewGroup은 자신이 포함한 ViewGroup, View 객체들의 위치를 결정합니다 ViewGroup은 "레이아웃"이라고도 하며 LinearLayout 또는 ConstraintLayout은 ViewGroup을 상속한 서브 클래스 입니다
- `뷰 컨테이너` : 다른 뷰를 포함하고 있는 뷰

   

***
 </details>
 
<details>
 <summary>노티피케이션이란?</summary>
<br />
   
 - 앱이 forground에서 실행 상태가 아니여도 사용자에게 정보를 제공할 수 있는 UI형태입니다.
   
 👉[click]([https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%EC%8A%A4%EB%A0%88%EB%93%9CThread%EC%99%80-%EC%BD%94%EB%A3%A8%ED%8B%B4](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CNotification))   
***
 </details>
 
 <details>
 <summary>Task란?</summary>
<br />
   
![KakaoTalk_20220712_204050466](https://user-images.githubusercontent.com/84564695/187118833-5c18a7b8-bac4-4afa-a654-982969f36f02.jpg)

 - `정의`  
  - 안드로이드 task는 stack 형식으로 쌓이는 activity들의 집합입니다 가장 아래에 있는 activity는 roomActivity라고 부르고 어플리케이션 런쳐로부터 시작됩니다. 가장 최근에 쌓인 activity는 topActivity라고 합니다.
 - `Intent Flag`  
   - Intent Flag는 안드로이드에서 Activity를 호출하다 보면 발생하는 Activity중복문제나 흐름을 제어하고 싶을 때 사용합니다
 - `Frag 사용 2가지 방법`  
   - 매니페스트 속성으로 지정
   - 소스코드로 제어
 
 👉[click](https://www.notion.so/Task-Activity-Root-Top-intent-Flag-7d1c0158dec64864b43f6014801572ea)
   
***
 </details>
 
  <details>
 <summary>📌안드로이드의 메모리 관리 방식?</summary>
<br />
   
 - 안드로이드 런타임(ART)와 Dalvik 가상 머신은 페이징과 메모리 매핑을 통해 메모리를 관리함
   
***
 </details>
 
<details>
 <summary>📌어노테이션이란?</summary>
   
- 일종의 메타데이터
- 컴파일/런타임 과정에서 코드를 어떻게 처리할 지 알려주는 정보
  - 컴파일러에게 코드 문법 에러를 체크하도록 정보 제공
  - 런타임시 특정 기능 실행하도록 정보 제공
  - 소프트웨어 개발 툴이 빌드나 배치 시 코드를 자동으로 생성할 수 있도록 정보를 제공
   
<br />
   
***
</details>
 
 </details>
 
 <details>
 <summary>ViewPager?</summary>
<br />
  
- `정의`
   - 데이터를 페이지 단위로 표시하고, 뷰를 스와이프해서 페이지를 전환할 수 있도록 만들어주는 컨테이너
   
- `사용방법`
   - 추상클래스인 PagerAdapter의 하위클래스인 Fragment/Pager/Adater, Fragment/State/Pager/Adapter 중 하나를 상속받아 만들 수 있음
   - **`FragmentPagerAdapter`** => attach / detach
     - PagerAdapter를 상속하고 있는 추상 클래스입니다
     - 모든 프래그먼트를 메모리에 저장해두기 때문에 빠르게 스와이핑해도 메모리에 로드된 프래그먼트를 가져다 쓰므로 버벅이지 않고 화면이 잘 넘어갑니다.
     - 하지만 많은 개수의 프래그먼트를 가지고 있다면 저장해야할 프래그먼트도 많아지므로 메모리 측면에서 부담이 될 수 있습니다
     -  fragment의 인스턴스는 메모리에 모두 저장해두고 화면에 보이거나 사라지는 fragment의 View만 붙였다가(attach) 떼면서(datach) ViewPager를 구현
   - **`FragmentStatePagerAdapter`** => add / remove
     - PagerAdapter를 상속하고 있는 추상 클래스입니다
     - 필요에 따라 메모리에서 Fragment를 제거하고 다시 생성하며 상태를 유지합니다.
     - 메모리에는 각 프래그먼트의 상태값만 계속 저장하기 때문에 메모리 입장에서는 부담이 덜합니다.
     - 상태(프래그먼트 로벌변수값/프래그먼트 뷰의 상태)를 저장해두고 인스턴스를 add()메소드 호출로 다시 생성 후 저장해둔 상태값으로 세팅하기 때문에 인스턴스가 재생성되어도 페이지를 보여주는데 필요한 데이터들이 초기화되지 않는 것

   
- `둘의 차이`
   - FragmentPagerAdapter는 프래그먼트를 제거하지 않고 View만 붙였다 떼었다했지만, FragmentStatePagerAdapter는 프래그먼트는 제거하고 상태만 저장한다

- `attach/detach  add/remove 시점`
   - 사용자가 보고있는 position의 "다음" position의 view를 미리 attach/add한다는 것과 동시에 position의 2번째 이전 position의 view를 detach/remove한다는 것입니다.
   - viewPager를 사용할 때 양 사이드의 화면을 조금 보여줘야 하는 상황이 있을 수 있기때문
   
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-ViewPager%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83)
 </details>
 
 
<details>
 <summary>ViewPager2?</summary>
<br />
  
- `등장배경`
   - 2019년 ViewPager2가 등장했습니다. 
   - PagerAdapter.notifyDataSetChanged()를 호출하면 메모리에 저장되어 있는 모든 페이지의 인스턴스에 대해 갱신처리가 이루어지는 로직입니다 
   - 이때 내부적으로 PagerAdapter.getItemPosition() 메소드를 호출해 새로운 포지션을 가져오게끔 되어있는데, getItemPosition()이 리턴하는 값이 POSITION_UNCHANGED(포지션에 변경이 없음)으로 고정되어 있던 것입니다.
   - 따라서 notifyDataSetChanged()를 호출해 페이지 갱신 로직을 요청해도 페이지에 변경이 없다는 상태로 고정되어있어 갱신이 이루어지지 않은 것입니다.이러한 문제점으로 인해 구글은 ViewPager2를 새롭게 등장시켰습니다!
   
- `변경점`
  - **Vertical Scrolling 지원**: ViewPager는 좌우 슬와이핑만 가능했지만 ViewPager2는 위아래 스와이핑도 지원합니다
  - **Right to Left Scrolling**: 오른쪽에서 왼쪽으로 읽는 문화권의 나라를 위해 오른쪽->왼쪽 방향의 스와이핑을 지원합니다

- `개선된 기능`
  - **데이터 갱신 이슈**: ViewPager의 문제였던 notifyDataSetChanged의 문제를 해결했습니다
  - **View 재활용 가능**: ViewPager의 PagerAdapter를 이용해 View를 item으로 할때는 View 재활용이 불가능했지만 ViewPager2에서는 RecyclerView.Adapter를 이용하기 때문에 DiffUtil 통한 View 재활용이 가능합니다
   
- `마이그레이션`
  - FragmentPagerAdapter, FragmentStatePagerAdapter->FragmentStateAdapter
  - PagerAdapter->RecyclerView.Adapter
  - getCount()->getItemCount()
  - getItem()->getCreateItem()

- `구현방법`
 - **page를 view로 구현: RecyclerView.Adapter**
    - RecyclerView.Adapter를 상속하므로->ViewHodler를 재활용(FrameLayout)
 - **page를 Fragment로 구현: FragmentStateAdapter**
    - fragment 인스턴스를 페이지 수만큼 생성해 메모리에 올려두는게 아니라 position에 가까워지면 생성(add)하고 멀어지면 remove
    - 추상클래스
    - 내부적으로 RecyclerView.Adapter상속
    - 추상메서드인 createFragment, getItemCount 오버라이딩
    - 이외 다른 RecyclerView.Adapter의 콜백메소드는 FragmentStateAdaper가 오버라이딩하고있음
   
- `생성자 함수`
  - **1. fragmentManager, lifecycle** ->2,3이 내부적으로 호출하는 찐 생성자 함수
  - **2. fragmentActivity** ->Fragment가 호스팅되어있는 Activity인 인스턴스 / ViewPager2를 Activity에 배치할때 사용
  - **3. fragment** ->fragment 인스턴스 / ViewPager2를 Fragment에 배치할때 사용
   
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-ViewPager2%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83)
 
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

- `정의`
  - 의존성 주입이란 외부에서 의존 객체를 주입해줘서 넘겨주는 것

- `DI Framework`
  - 의존성 주입을 위해서 넘겨주는 무언가가 필요한게 이 역할을 하는게 DI Framework
  - Dagger2, Hilt
 
 - `Dagger2`
   - UI가 있는 프로그램인 안드로이드 프로그램같은 경우 객체 별 생명주기 관리가 매우 중요하다. 
   - 근데 프로젝트가 커질수록 의존성 인스턴스들을 생명주기까지 고려하면서 잘 관리하는게 여간 쉽지 않다. 
   - 의존성 인스턴스 관리좀 해주는 거 뭐 없나? 해서 등장한게 대표적인 DI Framework인 Dagger2이다.
   - Annotation을 통해 컴파일과정에 DI 주입
   - 컴파일은 느리지만 런타임에서 에러 발생하지 않음
   - 컴파일 시 오버헤드 발생
   
 - `Hilt`
   - Dagger2를 기반으로하여 만들어진 라이브러리
   - Hilt는 안드로이드 JetPack에서 제공하는 전용 DI Framework(JetPack의 ViewModel에 대한 의존성 주입 구현하기 좋다.)
   - Component(의존성 객체 생성해서 주입하는 역할), Scope(각 컴포넌트 수명주기) 기본 제공
   - 컴포넌트의 라이프 사이클을 자동관리->DI 환경 구축 비용 감소

   
 - `Koin`
   - 엄밀히 DI는 아님
   - 런타임과정에 DI 주입
   - 컴파일이 빠름
   - 런타임 에러 가능
   
[👉clike](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-HiltRepository%ED%8C%A8%ED%84%B4)
   
 ***
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>SharedPreferences란?</strong></span></summary>

- 키-값 쌍이 포함된 파일을 가리킴
- 데이터를 파일로 저장하므로 앱을 삭제하면 데이터도 삭제됨
   
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>DiffUtil이란?</strong></span></summary>

 - `정의`
    - RecyclerView에서 item의 difference를 찾기 위한 Util클래스
    - 차이알고리즘을 사용하여 최소 업데이트 수를 계산하는 원리
   
 - `등장배경`
    - 리사이클러뷰에 등록된 관찰자에게 데이터 집합이 변경되었음을 알리는 메서드로 notifyDataSetChanged를 많이 사용
    - 하지만, 몇개의 itemview의 항목이나 구조가 변경되었든 상관없이 초기의 뷰홀더 개수만큼 뷰홀더를 "다시" 생성하고 bind하니, 아이템의 수가 많은 경우 모든 아이템을 한번에 변경하느라 깜빡이는 현상도 발생
    - 이외 RecyclerView.Adapter가 가진 데이터 변경 이벤트 메서드는 notifyDataSetChanged를 포함해서 총 5가지 but 포지션 계산 번거러움
   
 - `사용방법`
   - DiffUtil의 내부 클래스이자 abstract static class인 ItemCallback 클래스의 인스턴스를 생성
   - 추상메서드인 areItemsTheSame, areContentsTheSame을 반드시 오버라이딩
   - item의 id같은 고유 항목을 비교해서 newItem과 oldItem이 동일 항목인지 계산
   
[👉clike](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-DiffUtil-ListAdapter-notifyDataSetChanged%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83)

 ***
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>📌직렬화와 역직렬화란?</strong></span></summary>

- `직렬화`
  - 객체를 연속적인 데이터로 변형해 전송 가능한 형태로 만드는것
  - JVM 메모리에 상주되어있는 객체를 바이트 형태로 변환

- `역직렬화`
  - 직렬화된 파일을 다시 객체의 형태로 만드는것
  - 직렬화된 바이트 형태의 데이터를 객체로 변환해 JVM으로 상주시킴

- `직렬화해야하는 이유`
  - 디스크에 저장하거나 통신에는 value type만 가능하고 reference타입은 불가능
  - PC마다 사용하고 있는 메모리 주소는 다르다.  
 
***
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>📌Immutable이란?</strong></span></summary>
<hr>
   <p>값을 변경할 수 없는 것</p>

***   
   
<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>📌Image Loading 라이브러리에는 어떤 것이 있는가?</strong></span></summary>
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
   <summary><span style="border-bottom:0.05em solid"><strong>📌Android Ktx이란?</strong></span></summary>
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
   
![ㅁㄴㅇ2](https://user-images.githubusercontent.com/84564695/187128272-fddd333a-4695-4661-bd9a-4f1d9d95dbb3.jpg)

- `ViewBinding`
  - 등장배경: 기존의 findViewById를 호출해서 특정 뷰 객체의 참조값을 사용하는 반복적인 코드를 해결하기 위해View Binding 등장
  - 목적: Fragment나 Activity에서 원하는 뷰 객체의 참조를 간편하게 바로 가져다 쓸 수 있도록 함
  - 특징: 빌드과정에서 생성 / 끝에 Binding / 카멜표기 / getRoot()메서드 자동 포함
  - binding class: ID가 존재하는 모든 뷰의 참조값이 멤버변수로 / rootView(모든 뷰들 중 가장 top에 존재하는 뷰 객체의 참조) / getRoot(root view 객체의 참조값을 반환)
  - findViewById와의 차이
    - null safety - 뷰 직접 참조로 없는 아이디로 널포인트 익셉션 발생 안함.
    - type safety - 뷰 타입이 일치함으로 Class Cast Exception 발생 안하지.
 
- `DataBinding`
  - 등장배경: viewbinding의 역할을 하면서 레이아웃에서 데이터와 뷰 연결작업을 하고 싶어 Databinding등장
  - 특징
     - 장점: databinding은 null안전성을 가지며 뷰를 참조할 수 있는 viewBinding역할을 함
동시에 activity, fragment에서 데이터 연결 작업을 하지 않아도 되어서 역할 분리 확실해짐
     - 단점:  뷰 바인딩이 상대적으로 간단하며 퍼포먼스 효율이 좋고 용량이 절약된다는 장점이 있다.실제로 구글 공식문서에서는 단순히 findViewById를 대체하기 위한 거라면, 뷰 바인딩을 사용할 것을 권장
   
- `사용법`
   - 레이아웃의 루트태그를 < layout >으로 감싸주고 그 안에 < data >태그를 추가
   - 각 xml파일마다 binding class가 자동으로 생성됨
   -  binding class를 인스턴스화를 위해 DataBindingUtil 이라는 클래스 안의 setContentView() 메소드를 통해 활성 뷰를 해당 레이아웃으로 설정
   
[👉clike](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CDataBinding)
   
 ***
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>GSON이란?</strong></span></summary>
<hr>
   <p>JSON과 JAVA 사이의 직렬화와 역직렬화를 도와주는 라이브러리</p>

<hr>
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Retrofit과 Okhttp란?</strong></span></summary>
   
2007/11/05 : Android가 발표
2011/09/29 : HttpURLConnection을 권장하는 블로그가 나옴
2013/05/06 : OkHttp 1.0.0이 릴리즈 됨
2013/05/14 : Retrofit 1.0.0이 릴리즈 됨
2013/05/21 : Volley가 릴리즈 됨
2016 : Android6.0에서 HttpClient가 삭제 됨
2016/03/12 : Retrofit2가 릴리즈 됨
   
   - 둘 다 같은 회사(Square)에서 만든 HTTP 통신 라이브러리입니다. 
   
 - `OkHttp`
   - 통신을 동기화로할지 비동기 처리로할지 선택가능(Volley는 불가)
   
- `Retrofit`
   - OkHttp를 래핑하여 더 Type-safe하고, 더 직관적으로 사용할 수 있도록 인터페이스로 만들어진 게 Retrofit입니다. 
   
- `Retrofit이 OkHttp보다 좋은점`
  - 1. 어노테이션(Annotation) 사용으로 코드의 가독성이 좋고, 직관적인 설계가능.
  - 2. 통신 결과값을 JSON으로 변환해줄 필요가 없음
  - 3. 결과값을 메인스레드에서 바로 사용할 수 있음
  - 하지만 이 둘을 같이 쓰는 이유는, OkHttp가 제공하는 Intercepter를 통해 API가 통신되는 모든 활동을 모니터링 할 수 있으며 서버 통신 시간 조절이 가능하다는 장점!
  - 결과적으로, 최고의 성능을 내기 위해서 둘 다 사용하는 게 보편적
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Volley와 Retrofit의 차이는?</strong></span></summary>
- 1. 높은 성능
- 2. 뛰어난 가독성
- 3. 쉬운 유지보수
   
[👉clike](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-Android-%ED%86%B5%EC%8B%A0-%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC%EC%9D%98-%EC%97%AD%EC%82%AC)   
   
</details>
