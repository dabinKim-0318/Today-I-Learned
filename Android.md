

# 🐳안드로이드 기초 <a name = "reason"></a>
<details>
<summary><span style="border-bottom:0.05em solid"><strong>안드로이드 4대 컴포넌트에 대해 설명하시오</strong></span></summary>
<br />


![ㅁㄴㅇ](https://user-images.githubusercontent.com/84564695/187105028-837f6503-2830-4f8b-9ee1-67f187b9194e.jpg)
👉[click](https://www.notion.so/4-Activity-Service-BroadCast-Receiver-Content-Provider-6e2dcace26b443f488fc4b27489c8254)

   ***
 </details>

<details>
<summary><span style="border-bottom:0.05em solid"><strong>📌안드로이드 실행환경</strong></span></summary>
<br />
   
- 안드로이드는 크게 4가지로 구성되어있습니다.
  - `리눅스 커널`: OS로 스마트폰의 메모리나 프로세스 등을 관리합니다.
  - `라이브러리`: 안드로이드에 있는 다양한 기능을 라이브러리를 제공하며 안드로이드 앱을 구동해주는 dalvik 가상머신을 포함합니다.
  - `어플리케이션 프레임워크`: 사용자의 이벤트에 따라 출력을 담당하는 환경을 제공합니다. 생명주기도 여기서 관리. 
  - `어플리케이션`: 실제로 동작하는 앱을 말합니다.
  
  안드로이드는 기본적으로 리눅스 커널 위에 탑재된 안드로이드 런타임인 DVM(Dalvik Virtual Machine, 달빅 가상 머신)에서 동작

 
   ***
   
 </details>
 
 <details>
<summary><span style="border-bottom:0.05em solid"><strong>안드로이드는 다른 플랫폼에 비해 어떠한 장점이 있는가</strong></span></summary>
<br />
   
- `오픈소스`
   - 비용부담x
   - 전세계 개발자 피드백 ->안전성 높고 버그x

- `리눅스 커널을 OS로` 
   - 다양한 하드웨어에 대한 드라이버 소스가 풍부함 
***
 </details>
 
   <details>
  <summary><span style="border-bottom:0.05em solid"><strong>📌안드로이드의 메모리 관리 방식? </strong></span></summary>    
<br />
   
- 안드로이드는 액티비티, 서비스리시버, 콘텐츠프로바이더를 실행하기 위해 앱이 실행되는 과정에서 프로세스 생성
  - 실행중인 모든 앱은 컴포넌트가 모두 종료되어도 다음에 이앱을 다시 실행할 가능성이 높음->프로세스 바로 제거X
  - 사용자에 의해 다시 앱이 실행되면 남아있던 프로세스가 존재하는 경우 바로 실행됨
  
- 이 과정에서 쌓여있던 많은 프로세스로 인해 메모리가 부족해지면
  - 프로세스 우선순위=사용빈도에 따라 프로세스를 종료하여 메모리 확보
   
***
 </details>
 
 ***
 
   <details>
<summary><span style="border-bottom:0.05em solid"><strong>Activity란? </strong></span></summary>   
<br />
  
- `정의`
  - Android 앱의 필수적인 기본 구성 요소(컴포넌트) 중 하나입니다 
  - Activity는 사용자와 상호작용하기 위한 진입점입니다. 
  - 사용자 인터페이스(UI) 화면을 구성하는 컴포넌트입니다 
  - 대부분의 앱은 한 개의 Activity가 아닌 여러 Activity로 이루어져 있습니다.  
- `구조`  
  - Activity는 ContextThemewrapper클래스를 상속, 이외 여러 인터페이스를 구현하고 있음
  - 실제 Activity컴포넌트를 사용하기 위해선  Android의 다양한 API Level을 지원하기 위해 만들어진 Activity class의 하위 클래스인 AppCompatActivity를 상속받은 class를 생성
- `사용방법`
  - AppCompatActivity를 상속받는 하위 클래스 생성
  - manifest에 등록: 필수속성인 activity class name지정, intent filter를 사용해 launcher로 지정가능
  - 수명주기: Activity 클래스가 생성되거나, 중단 또는 다시 시작하거나, 종료되는 등의 'Activity의 상태'인 수명주기 콜백을 활용해 상태변화에 따라 수행될 코드 작성
  
- `유사기술` = Fragment
  - 안드로이드 4대 컴포넌트는 아님
  - Activity의 한계 
    - 1) Activity 안에 코드가 길어지게 되면 코드가 길어지니까 유지보수할 때 관리가 어려워짐
    - 2) 안드로이드 디바이스는 휴대폰,태블릿 등 다양하기 때문에 태블릿UI를 고려할 때 단순 Activity로 화면을 그리기에 한계가 있음
 
  <br>
  
  (장단점)
  
- 💡Activity간 정보를 교환하려면 어떻게 해야하나요?
- 💡Activity 수명주기
- 💡Activity 3가지 상태
    <br>
  
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CActivity-LifeCycle%EC%88%98%EB%AA%85%EC%A3%BC%EA%B8%B0)
   
***
 </details>
 
 <details>
  <summary><span style="border-bottom:0.05em solid"><strong> Fragment란?  </strong></span></summary>    
   
- `정의`
   - 프래그먼트는 앱의 전체 UI에서 어딘가에 반복적으로 재사용 가능한 부분을 말합니다.  
   - `등장배경`
     - 1) Activity 안에 코드가 길어지게 되면 코드가 길어지니까 유지보수할 때 관리가 어려워짐
     - 2) 안드로이드 디바이스는 휴대폰,태블릿 등 다양하기 때문에 태블릿UI를 고려할 때 단순 Activity로 화면을 그리기에 한계가 있음
  
- `구조`
   - Object클래스 상속, 그외 다양한 인터페이스 구현
  
- `사용법`
   - Fragment클래스 의 하위 클래스 생성
   - Activity / Fragment에 호스팅
     - 이때 Activity는  FragmentActivity 를 상속하는 Activity여야함 (AppCompactActivity가 상속중)
     - 1) Activity UI 레이아웃 안에 프래그먼트 존재를 정의하여 Activity UI가 Activity 클래스에 inflate될 때 프래그먼트 자체 UI도 자동으로 프래그먼트 클래스에 inflate 시키는 방법
     - 2) Activity UI 레이아웃 안에 프래그먼트 컨테이너(=이 위치에 프래그먼트 자체 UI가 배치될 것입니다~ 라고 위치를 지정해두는 것)를 정의하고 프로그래밍적으로 해당 컨테이너 안에 프래그먼트를 추가(Add)하는 방법
  * 주의할 점은 두 방법 모두 Activity UI 레이아웃 안에 FragmentContainerView 를 정의함으로써 해당 프래그먼트가 배치될 위치를 정의해야 한다는 점입니다.
    - 프래그먼트를 추가/교체/삭제
      - 백 스택(Back Stack) 에 프래그먼트 작업에 의한 변경 사항을 push 및 pop 하는 작업을 담당하는 클래스인 FragmentManager필요
      - 프래그먼트 추가/교체/삭제 작업을 제공하는 메서드는 추상클래스인 FragmentTransaction이 정의       - FragmentTransaction 하위클래스인 FragmentManager클래스 인스턴스화한후 beginTransaction호출해서 FragmentTransactioin인스턴스 얻음
      - 트랜잭션을 생성 후 프래그먼트 작업 명시한 후 commit()
      - commit함수를 호출해야만 FramgmentManager가 해당 FramgmentTransaction 수행을 예약 합니다
  
- `유사기술` = Activity
   
- `특징`
   - 1) 프래그먼트는 자체 레이아웃(xml파일을 정의할 수 있음)을 가질 수 있으며 **자체 생명 주기**를 보유
   - 2) 프래그먼트는 독립적으로 존재할 수 없고, 반드시 Activity나 다른 프래그먼트에 **호스팅** 되어야함
   - 3) 프래그먼트는 자체 UI를 **개별적인 청크**로써 사용할 수 있습니다. 개별 청크 단위로 다른 곳에서 재사용  

- 💡commi(), commitNow() 차이
- 💡fragmentTransaction에서 제공하는 프래그먼트 조작 함수 
- 💡백스택에 프래그먼트 트랜잭션 기록하는법? 
  
  <br>
  
 👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%ED%94%84%EB%9E%98%EA%B7%B8%EB%A8%BC%ED%8A%B81)
***
 </details>
 
 <details>
     <summary><span style="border-bottom:0.05em solid"><strong> Activity와 Fragment의 차이  </strong></span></summary>    
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
      <summary><span style="border-bottom:0.05em solid"><strong>  Activity의 LifeCycle </strong></span></summary>    
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
       <summary><span style="border-bottom:0.05em solid"><strong>  Fragment의 LifeCycle  </strong></span></summary>    
<br />
   
![ㅁㅁ](https://user-images.githubusercontent.com/84564695/187110664-a727c532-9afe-427f-a2be-104b74c1e6cf.jpg)

👉[click](https://abundant-playground-8c8.notion.site/LifeCycle-Activity-Fragment-89e3dd9483c04ef68151187fe04b0a84)
 
***
 </details>
 
 <details>
       <summary><span style="border-bottom:0.05em solid"><strong>  ☘FragmentTransaction</strong></span></summary>    
<br />
   
- FragmentTransaction 클래스는 abstract 클래스(추상 클래스)입니다. 
  - FragmentManager 클래스에 구현되어 있기 때문에 FragmentTransaction 클래스를 사용하기 위해 FragmentManager 클래스가 제공하는 beginTransaction함수 호출을 통해 FragmentTransaction 인스턴스를 생성해야합니다
  - FragmentManager가 수행할 단일 단위
  - 따라서 하나의 FramgmentTransaction 단위 내에 FramgmentTransaction 클래스가 제공하는 프래그먼트 추가/삭제/교체 작업 등을 명시하면 됩니다
  
- FragmentTransaction가 제공하는 함수  
  - `add`: 프래그먼트를 추가. 호스트 Activity의 수명 주기에 프래그먼트 수명 주기를 추가하는 것
  - `remove`: 생성되어 있는 프래그먼트 중 remove() 함수 인자로 전달한 프래그먼트를 제거
    - onDestroyView->onDestroy->onDetach까지 호출되며 메모리에서 "제거"
  - `replace`: 생성되어 있는 프래그먼트 중 replace() 함수 인자로 지정된 프래그먼트를 제외한 나머지 모든 프래그먼트가 제거(remove)됩니다. 
    - 프래그먼트 컨테이너에 남아있는 프래그먼트 자체 UI레이아웃은 replace()함수의 인자로 지정된 프래그먼트 뿐이기 때문에 사용자의 눈에는 해당 프래그먼트만 보이게 됩니다.  
    - 결과만 보면 replace()를 호출하는건 호스트 Activity에 생성되어 있는 모든 프래그먼트를 remove() 한 후 replace()함수의 인자로 전달한 프래그먼트를 add()하는 것과 같습니다
  - `attach`: 프래그먼트가 deflate되어있던 자신의 자체 UI와 다시 inflate됩니다 
    - UI 뷰 계층은 다시 재생성되어 프래그먼트 컨테이너에 다시 쌓여 사용자 눈에 보이게 됩니다
  - `detach`: 프래그먼트가 자신의 자체 UI로부터 떼지고(=inflate되어 있던 프래그먼트 클래스와 자체 UI가 deflate된다는 의미) 자체 UI 뷰 계층은 파괴(destroying)됩니다. 
    - detach는 해당 프래그먼트가 자신의 자체 UI로부터 떼지고(=inflate되어 있던 프래그먼트 클래스와 자체 UI가 deflate된다는 의미) 자체 UI 뷰 계층은 파괴되는 것입니다. 
    - 따라서 fragment객체는 메모리에 남아있고 onDestroyView까지만 호출되는 것을 확인할 수 있습니다.
  - `show()/hide()`: 프래그먼트 컨테이너에 쌓인 자체 UI 순서에 영향을 주지 않고 자신이 쌓여있는 위치에서 사용자 눈에서 보이기/안보이기 설정만 바뀌는 겁니다  
  
  
👉[click](https://abundant-playground-8c8.notion.site/LifeCycle-Activity-Fragment-89e3dd9483c04ef68151187fe04b0a84)
 
***
 </details>
 
***
 
<details>
    <summary><span style="border-bottom:0.05em solid"><strong>  ☘RecyclerView란?  </strong></span></summary>    
<br />
   
 - [정의](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CRecycle-View)
   - 리사이클러뷰는 사용자가 관리하는 많은 수의 데이터 집합(Data Set)을 개별 아이템 단위로 구성하여 화면에 출력하는 뷰그룹(ViewGroup)이며, 한 화면에 표시되기 힘든 많은 수의 데이터를 스크롤 가능한 리스트로 표시해주는 위젯입니다
 - `등장배경`
    - 리사이클러뷰 전에 스크롤 가능한 리스트로 표현하기 위해서 ListView를 사용했었습ㄴ,ㅣ다. ListView는 한번에 ItemView를 그리기 어려웠음->속임수1)눈에 보이는 ItemView만 생성->속임수2)맨위에 있던 ItemView를 그려져야할 위치에 재사용->문제1)개발자들 요구사항 증가->문제2)다른 뷰에서 제공하는 비슷한 기능이 ListView에 추가되며 혼란->문제3)애니메이션 처리 문제->문제3)재사용될 ItemView인지 분기처리 필요->문제4)Adapter는 변경된 Item Data의 Position알 수 없음===>저 구글인데요 미안합니다 RecyclerView만들게요 ㅠㅠ ㅎㅎ
   
- 구조  
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
 
- `유사기술` = ListView
  
   
  
   
***
 </details>
 
 <details>
 <summary><span style="border-bottom:0.05em solid"><strong>  ☘RecyclerView와 ListView의 차이?   </strong></span></summary>  
  
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
 
 ***
 
 
<details>
      <summary><span style="border-bottom:0.05em solid"><strong>☘ViewPager?</strong></span></summary>    
  
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
    <summary><span style="border-bottom:0.05em solid"><strong>☘ViewPager2?</strong></span></summary>    
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
  
  ***
 
  <details>
    <summary><span style="border-bottom:0.05em solid"><strong> 📌☘View가 그려지는 과정  </strong></span></summary>    
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
    <summary><span style="border-bottom:0.05em solid"><strong> ☘LiveData </strong></span></summary>    
<br />
   
  
- `LiveData`: 관찰자 패턴을 따르는 데이터 홀더 클래스
  
- `Observer`: 인터페이스
   - LiveData의 업데이트 알림을 받아 처리되는 로직인 onChange() 메서드가 정의되어 있음
   - LiveData는 데이터가 변경될 때 Observer 객체에 알림
   
- observe(..) 함수: LiveData 클래스에 정의된 함수
  - LiveData 객체에 Observer 객체를 **연결**합니다. 
  - observe() 메서드는 LifecycleOwner 객체를 사용합니다. 
  - 이렇게 하면 Observer 객체가 LiveData 객체를 **구독**하여 변경사항에 관한 알림을 받습니다. 
  - UI 컨트롤러에 Observer 객체를 연결합니다.
  
```
- 뷰모델.LiveData.observe(라이프사이클,Observer객체)
  
- UI Controller(Activity,Fragment)에서 LiveData에 observer()를 호출한다 
  =강아지 고양이보고 event 발생 관찰하라고 관찰자를 등록한다(LiveData 객체에 Observer 객체를 연결해서 Observer가 구독)
- 이때 첫번째 인자로 라이프사이클을 전달하니까 UI Controller가 resume()이거나 start() 상태일때만 
  관찰자가 활성상태라고 간주해서 onChange() 되었다고 알리기 위해서다
- 두번째 인자로 Observer객체를 전달하는건, Observer 객체인 관찰자가 LiveData 객체를 구독하여 변경사항에 관한 알림을 받아 해야할 작업을 정의하기 위함이다(UI를 업데이트 하는 작업을 작성)
```
  
- 장점
  - 1. UI와 데이터 상태의 일치 보장 / 최신 데이터 유지
    - = Observer패턴을 따른다->강아지가 알아서 onChange()된다->데이터 변경시 UI알아서 업데이트 된다
  - 2. 메모리 누수 없음 / 수명 주기를 더 이상 수동으로 처리하지 않음
    - 관찰자는 Lifecycle 객체에 결합되어 있으며 연결된 수명 주기가 끝나면 자동으로 삭제됩니다.
    - LiveData는 관찰하는 동안 관련 수명 주기 상태의 변경을 인식하므로 이 모든 것을 자동으로 관리합니다.
  - 3. 중지된 Activity로 인한 비정상 종료 없음
    - 활동이 백 스택에 있을 때를 비롯하여 관찰자의 수명 주기가 비활성 상태에 있으면 관찰자는 어떤 LiveData 이벤트도 받지 않습니다.
  
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-LiveData%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83#%EA%B3%B5%EB%B6%80%EB%B0%B0%EA%B2%BD)
     
  
***
 </details>
 
 
 
  <details>
     <summary><span style="border-bottom:0.05em solid"><strong>Intent와 IntentFilter란? </strong></span></summary>    
<br />
   
   ![KakaoTalk_20220711_214321306](https://user-images.githubusercontent.com/84564695/187116433-7aa6c027-efae-4969-9055-73116e342793.jpg)
👉[click](https://www.notion.so/Intent-pending-intent-sticky-intent-4cf97968d28a4a18b4403118c1793a5a)
   
***
 </details>
 
   <details>
    <summary><span style="border-bottom:0.05em solid"><strong> ANR이란?  </strong></span></summary>    
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
    <summary><span style="border-bottom:0.05em solid"><strong>📌인플레이션이란? </strong></span></summary>    
<br />
   
자바 소스코드에서 xml의 구성요소들을 사용할 수 있게 객체로 만들어주는것

메모리상에 실제로 객체화되어 앱에 보여지는 것
   
***
 </details>
 
 <details>
       <summary><span style="border-bottom:0.05em solid"><strong>Context란? </strong></span></summary>    
<br />
   
- Context는 Android 시스템에서 구현체를 제공하는 추상클래스이다
- gc에 의해 수집되지 않는다
   
  ![KakaoTalk_20220711_214307895](https://user-images.githubusercontent.com/84564695/187117252-d356bea3-e488-4f39-a50d-a2a2444bcac8.jpg)
 
 👉[click](https://www.notion.so/Context-Application-Activity-2e40351127744b188cb72f6d9222b571)
***
 </details>
 
 <details>
       <summary><span style="border-bottom:0.05em solid"><strong> manifest파일</strong></span></summary>    
<br />
   
- 매니페스트는 앱의 이름, 버전, 구성요소, 권한 등 앱의 실행에 있어 필요한 각종 정보들이 저장되어있는 파일이다.
- 안드로이드 프로젝트의 최상위에 위치하고 있다.

- `manifest태그`
    - 최상위에 위치
    - 패키지명, 앱버전코드, 앱버전 이름 정의
   
 - `application태그`
    - 앱 아이콘, 앱 이름
   
- `activity`
    -   클래스명, 액티비티 이름, intent filter태그
   
- `service, receiver, provider`
    -   각 내용 정의

- `permission`
    -   앱에 필요한 권한 정의
   
- `use-sdk`
    -   최소 안드로이드 SDK
   
***
   
 </details>
 
 <details>
   <summary><span style="border-bottom:0.05em solid"><strong> Thread, Looper, Handler에 대해 설명하라 </strong></span></summary>    
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
  <summary><span style="border-bottom:0.05em solid"><strong> 디스플레이(display), 윈도우(window), 서피스(surface), 뷰(view), 뷰 그룹(view group), 뷰 컨테이너(view container), 레이아웃(layout)에 대해 설명하라 </strong></span></summary>    
<br />
   
- `디스플레이` : 안드로이드 단말기가 가지는 하드웨어 화면
- `윈도우` : 화면에서 눈에 보이는 것을 담는 가장 기본적인 "공간"이자, 뭔가를 그릴 수 있는 "창" . 사용자로부터 입력받아 앱에 전달
- `서피스` : 윈도우에 그림을 그릴 때 화면에 합성되는 픽셀을 저장.  화면에 표시되는 모든 Window는 자신만의 Surface가 포함되어 있습니다
- `뷰 = 위젯`: 사용자가 보고 상호작용 할 수 있는 모든 것입니다. View객체는 "위젯"이라고도 하고, Button, TextView와 같은 클래스는 View class를 상속한 서브클래스 입니다 이처럼 View는 Button, TestView 등 어떤 기능을 하는 컴포넌트 입니다.
- `뷰 그룹 = 레이아웃`: View를 상속받고 있고, 하위에 여러 ViewGroup, View들을 포함하고 있습니다.(ViewGroup 안에 ViewGroup을 포함할 수 있음) ViewGroup은 자신이 포함한 ViewGroup, View 객체들의 위치를 결정합니다 ViewGroup은 "레이아웃"이라고도 하며 LinearLayout 또는 ConstraintLayout은 ViewGroup을 상속한 서브 클래스 입니다
- `뷰 컨테이너` : 다른 뷰를 포함하고 있는 뷰

   

***
 </details>
 
<details>
     <summary><span style="border-bottom:0.05em solid"><strong>노티피케이션이란? </strong></span></summary>    
<br />
   
 - 앱이 forground에서 실행 상태가 아니여도 사용자에게 정보를 제공할 수 있는 UI형태입니다.
   
 👉[click]([https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C%EC%8A%A4%EB%A0%88%EB%93%9CThread%EC%99%80-%EC%BD%94%EB%A3%A8%ED%8B%B4](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CNotification))   
***
 </details>
 
 <details>
        <summary><span style="border-bottom:0.05em solid"><strong>Task란? </strong></span></summary>    
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
    <summary><span style="border-bottom:0.05em solid"><strong>🦑Memory leak에 대한 경험 및 처리하고 개선한 방안</strong></span></summary>    


<br />
   
***
</details>

<details>
    <summary><span style="border-bottom:0.05em solid"><strong>📌어노테이션이란?</strong></span></summary>    

 <br/>
  
- 일종의 메타데이터
- 컴파일/런타임 과정에서 코드를 어떻게 처리할 지 알려주는 정보
  - 컴파일러에게 코드 문법 에러를 체크하도록 정보 제공
  - 런타임시 특정 기능 실행하도록 정보 제공
  - 소프트웨어 개발 툴이 빌드나 배치 시 코드를 자동으로 생성할 수 있도록 정보를 제공
   
<br />
   
***
</details>


<p></p>
<h2>🐋안드로이드 심화</h2>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>액티비티간 데이터 전달에서 임의의 클래스 객체를 바로 전달하지 못하는 이유는 무엇이고 전달하기 위해서는 어떤 처리가 필요한가?</strong></span></summary>

- `이유`
   - 액티비티간 전달할 수 있는 데이터의 타입은 보통 기본형
   - 그 이유는, intent를 이용해서 액티비티의 데이터를 전달하는 과정에서 현재 실행중인 앱 프로세스가 시스템 프로세스로 실행중인 액티비티 매니저 서비스 프로세스에게 전달되는데, 이 경우 프로세스간 통신이기 때문에 intent에 있는 값들을 복사해 넘기는 방식으로 처리되기 때문에 객체 주소를 바로 넘기지 못하는 문제 발생
- `해결법`
   - 자신이 임의로 만든 클래스 객체를 전달하기 위해선 Serializable, Parceable 인터페이스를 상속받아 객체를 직렬화하여 넘기는 방식 사용
   
***
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>부모 액티비티에서 자식 액티비티의 결과 값을 받아오기 위해 어떻게 해야하는가?</strong></span></summary>

- 부모 액티비티에서 `startActivityForResult`메소드에 intent, request코드 파라미터로 넘김
- 자식 액티비에서 `setResult`메소드에 결과 코드, 데이터를 파라미터로 넘김
- 다시 부모 액티비티에서 `onActivityRexult`메서드를 오버라이딩하여 자식 액티비티에서 보낸 결과코드와 데이터를 받아 처리하는 코드 작성
- 이후 자식 액티비티 finish->부모 액티비티 resume
- 이때 `onActivityResult`메서드 작동
  
***  
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>안드로이드가 리소스(resource)를 접근하는 방식에 대해서 설명하시오.</strong></span></summary>

- `소스 파일`
  -  R 클래스를 사용한다.
  - 자동으로 생성되는 클래스로서 resource의 id가 배정되는 클래스
  - R클래스에 접근하는 문법 : R.resourceType.resourceName : R.string.app_name
  - R 클래스로 접근하여 얻는 데이터는 int형으로 이를 원하는 객체로 바꾸려면 변환해주는 메소드를 사용 : getResource.getString(R.string.app_name);
- `XML파일`
  - R 클래스의 역할을 @가 대신한다. 
 
***  
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>디바이스를 회전할 때 Activity에서 일어나는 과정에 대해 설명하시오</strong></span></summary>

- `과정`
  - Activity lifecycle 에서 onDestroy()가 호출되고 onCreate()가 호출
  -  onCreate()를 다시 하기 때문에 Activity 안에 데이터는 다시 초기화=
  - 만약 사용자가 화면에 중요한 내용을 작성중에 있었고 구성변경이 일어난다면 화면의 데이터는 날아감아감

- `데이터 보존법`
  - `AAC Viewmodel`
  - `onSaveInstanceState()`
    - 데이터=instanceState=Bundle 객체에 저장된 키-값 쌍의 컬렉션
    - onStop다음에 호출
    - onCreate: Bundle이 null인지 확인 필요
    - onRestoreInstanceState: null확인 필요 없음
  - `매니페스트에 android:configChanges 설정`
    - android:configChanges="keyboardHidden|orientation|screenSize"
    - onDestroy() -> onCreate() 대신에 onConfigurationChanged() 
    - 만약 화면 전환에 따라 layout을 다르게 바꿔 주고 싶다면 이 메서드를 오버라이딩

***
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Singleton Pattern에 대해 설명하시오</strong></span></summary>

 - 디자인 패턴 중 하나로, 클래스의 객체화를 "single" 객체로 만드는 것
 - 불필요한 메모리 사용 막을 수 있음
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Viewholder Pattern이란 무엇인가?</strong></span></summary>

 - `정의`
  - 각 뷰 객체를 뷰 홀더에 보관함으로써 findViewById()와 같은 반복적 호출 메서드를 줄여 효과적으로 속도 개선을 할 수 있는 패턴
 
- 'ViewHolder'
  - 각 뷰를 보관하는 Holder 객체
  - 예를들어 ListView의 각 아이템 data를 업데이트 할때마다 findViewById호출하면 성능저하(ViewGroup 밑에 있는 모든 뷰들을 전부 한 번씩 순회하며 id값을 비교하는 과정을 거치기 때문에 자원이 많이 듭니다)
  - 따라서, ItemView의 id같은 요소를 바로 엑세스 할 수 있도록 저장해두고 사용하기 위한 객체
  
- `사용법`
  - ViewHolder생성
  - view의 setTag호출해서 view의 tag에 생성된 ViewHoler 저장
  - viewHolder가 최초 1회만 생성되고 이후 else문을 통해서 view에서 getTag를 호출해 ViewHolder를 꺼내와서 ViewHolder에 접근이 가능한 형태가 만들어지는 것

***  
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘MVC, MVP, MVVM에 대해서 설명하시오</strong></span></summary>

- `아키텍쳐`
  - 시스템 구성과 동작 원리 등 최상의 소프트웨어를 구성하는 설계도
- `디자인패턴`
  - 좋은 코드를 설계하기 위한 방법론
  
- `MVC`
  - VIEW: Activity, Fragment
  - Model: Room이나 서버에서 데이터 처리하는 로직(Call해서 데이터 가져오기 등)
  - Controller: 사용자의 이벤트를 처리하고 데이터를 xml에 꽂아주는 로직
   -  화면에 보이는 애는 VIEW가 데이터는 MODERL이 그 사이에서 controller가 컨트롤함
   - setOnClickListener같은 사용자의 Action이 Controller에 들어옵니다
   - Controller는 Model을 나타내줄 View를 선택합니다
   - View는 Model을 이용하여 화면을 나타냅니다
   - 단점
      - 하나의 파일에 이벤트 처리, 서버 통신처리 등의 컨트롤하는 로직이 전부 들어가니까 복잡합니다
      - 서버랑 통신할때의 call하는 로직을 activity,fragment에서 처리했었음 근데 서버 통신은 '데이터 처리' 작업의 일종인데 이걸 view에서 처리하고 있던 것입니다 
      - 즉, Model이 해야하는 일을 View에서 하면서 Model과 View사이 의존성이 생깁니다. 이는 객체지향 관점에서도 좋은 현상이 아닙니다
      - Model에서 뭐 하나가 수정되면 View에서도 전부 수정해야하는 문제가 발생합니다
  
  
- `MVP`
  - MVC는 View내부에서 데이터 요청, 이벤트 모두 처리했는데
  - mvp는 데이터 요청 작업을 View가 Presenter에게 요청해서 Presenter가 하는 방식임
  - view로 이벤트 들어오면 presenter가 1:1로 담당하고 presenter을 거쳐서 모델에 요청하니까  view와 presenter사이 의존성이 높음
  - view하나 만들때마다 presenter도 같이 만듦

- `MVVM`
  - Model: 어플리케이션에서 사용되는 데이터와 그 데이터를 처리하는 부분(서버통신, 로컬db처리)
  - View: 사용자에게 보여지는 UI
  - ViewModel: View를 나타내 주기 위한 Model이자 View를 나타내기 위한 데이터 처리를 하는 부분
  - ViewModel은 View를 참조하지 않기 때문에 독립적
  
  - MVVM을 왜 쓸까?
    - 구글에서 공식적으로 MVVM을 사용하기 쉽도록 제공하는 AAC들이 있습니다. 그래서, 아키텍처를 쓸때 대표적인게 MVVM입니다
    - ✔동작  
      - 모든 입력(Input)들은 View로 전달됩니다.
      - View는 ViewModel한테 데이터를 요청하거나 ViewModel은 View가 입력 들어왔다고 알려주면 해당하는 Presentation Logic을 처리합니다
      - (Presentation Logic : 실제 눈에 보이는 GUI 화면을 구성하는 코드를 말하며 여기서는 실제로 화면에 보여지는 데이터를 처리하는 로직을 말합니다.)
      - View Model은 View에게 데이터 전달하는게 아니라 View가 View Model을 관찰할 뿐 View에게 관여안합니다(MVP는 Model에게 받아온 데이터 처리하고 View에게 전달까지 했다!)
    - ✔특징  
      - ViewModel은 View를 참조하지 않기 때문에 독립적입니다
      - (ViewModel과 View는 1:n 관계다.)
      - 따라서 View가 이용할 ViewModel을 선택해 바인딩하여 업데이트를 받게 됩니다.
      - (Command 패턴이나 Data Binding을 이용하여 V-VM간 의존성을 없앨 수 있다.)
      - Command 패턴:View에 입력이 들어오면 커맨드 패턴으로 ViewModel에 명령합니다
    - ✔장점  
      - View와 Model 사이의 의존성이 없습니다
      - View와 ViewModel 사이의 의존성 또한 크지 않습니다
      - 각 View, ViewModel, Model 부분은 독립적이어서 모듈화하여 개발 가능합니다
    - ✔단점  
      - ViewModel설계가 어려울 수 있습니다
  
👉[click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CMVVM)  
***  
  
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘안드로이드 권장 아키텍쳐</strong></span></summary>

-안드로이드에서 자주 사용되는 '아키텍쳐 패턴'에는 MVC패턴,MVP패턴,MVVM패턴이 있음

- 안드로이드 공식문서에서 설명하는 '권장하는 아키텍쳐란' MVVM과 같은 아키텍쳐 패턴을 사용하면서, 프로젝트에서 계층을 나눠 관심사를 분리시킨 '설계구조'라고 할 수 있습니다.

- 모바일 앱 사용자 환경
  - 사용자는 모바일 환경에서 다양한 앱을 시도때도 없이 바꾸기도 하고 전화나 알림 등의 작업도 동시에 하기 때문에 앱에서 이런 사용자 흐름이 중단되지 않고 자연스럽게 흘러가도록 올바르게 처리
  - 앱 구성요소에 앱 데이터나 상태를 저장 X =>  앱 구성요소가 저장하고 있는 데이터는 유실

- Android Clean Architecture 두 가지 원칙  
  - 1. "UI 기반 클래스를 가볍게 하라"
   - UI 기반 클래스는 UI를 핸들링하거나 수명주기에 따라 발생할 수 있는 상황에 대처하는 코드만 작성
  
  - 2. "UI와 Model(모델)을 분리하라"
    - UI 기반 클래스에 데이터나 상태를 저장하지 말라
  
- 안드로이드 권장 아키텍쳐
  - 안드로이드에서 권장하는 앱 아키텍쳐는 최소 2개 이상의 Layer로 구성되어야 합니다
  - `UI Layer`: 화면에 애플리케이션 데이터를 표시하는 UI 레이어
    - UI : UI element(버튼) + UI State를 결합한 것 ex)로그인 버튼 활성화 되어있는 화면
    - UI 컨트롤러(Fragment/Activity) : UI에 View를 그리거나 사용자 event를 trigger하는 등 UI관련 동작을 캡쳐함
    - UI 데이터 : 사용자 눈에 보여야 하는 데이터
    - stateHolders(ViewModel) : UI State를 생성하는 역할을 하며 생성 작업에 필요한 로직을 포함하는 클래스
    - UI element : 버튼같은 컴포넌트
  - `Data Layer`: 앱의 비즈니스 로직을 포함하고 애플리케이션 데이터를 노출
    - Domain Layer나 UI Layer는 데이터 소스에 직접 액세스 하면 안됩니다. 
    - 데이터 영역의 진입점은 항상 Repository클래스여야 합니다. 
    - 여러개의 DataSource로 추상화되어있는 Repository로 구성
    - local / remote / repository구현체
  - `Domain Layer`: UI와 데이터 레이어 간의 상호작용을 간소화하고 재사용하기 위함
    - UseCase
    - UI 레이어와 데이터 레이어 사이에 있는 선택적 레이어
    - 복잡한 비즈니스 로직이나 여러 ViewModel에서 재사용되는 간단한 비즈니스 로직의 캡슐화
    - UI Layer->Domain Layer->Data Layer 순대로 의존성이 높습니다
 
  
</details>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘Room</strong></span></summary>

- `SQLite`
  - 데이터베이스는 안드로이드에서 제공하는 관계형 데이터베이스이자 경량 데이터베이스다
  - 관계형 데이터 베이스는 테이블, 컬럼(속성), 레코드(로우,튜플)로 이루어져 있음
  - SQL: RDB가 데이터를 조작, 제어하는 용도로 사용하는 언어
  - SQL구문(쿼리): SQL언어로 쓴 명령어
  - SQLite을 사용하기 위해선 안드로이드의 컨텍스트가 가지고 있는 SQLiteOpenHelper 클래스를 상속받아 사용해야 한다
  
- `Room`
  - 개념
    - 안드로이드는 SQLite를 코드 관점에서 접근할 수 있도록 ORM 라이브러리인 Room을 제공함
    - SQLite보다 쉽고(쿼리를 직접 안짜도됨) 기기가 네트워크에 액세스할 수 없을 때 즉 서버 연동없이 오프라인 상태인 동안에도 사용 가능함
 - SQLite 단점
   - SQL 쿼리에 대한 컴파일 체크가 없다. 실제 DB에 없는 틀린 열 이름으로 쿼리를 작성하면 런타임 동안 예외가 발생하고 컴파일하는 동안 이 문제를 잡을 수 없다.
   - 스키마가 바뀌면 영향 받는 SQL 쿼리를 수동 업데이트해야 한다. 여기서 시간이 오래 걸리거나 다른 오류가 발생할 수도 있다.
   - SQL 쿼리와 자바 데이터 객체 간 변환 처리를 하려면 많은 상용구 코드를 작성해야 한다.
 - Room DB 장점
   - Room은 컴파일하는 시간에 SQL 유효성 검사를 수행한다.
   - 스키마가 바뀌었을 때 영향 받는 SQL 쿼리를 직접 바꾸지 않아도 된다.
   - 상용구 코드 없이 DB 객체를 자바 객체에 매핑한다.
  
 - Room사용
  ![images_dabin_post_0f7e62c8-ea78-4494-9d16-04f51b50fb49_image](https://user-images.githubusercontent.com/84564695/191971243-37b77f25-83dc-475e-9e95-efc3db1cd2df.png)

- 총 4개의 파일을 만들게 된다(리스트 형태로 사용하려면 어댑터 추가..)
- `Entities`: 데이터베이스의 테이블 역할을 하는 클래스라고 보면됨. Entities클래스 하나 당 테이블 하나를 만드는 것
  - Entity(개체)와 Object(객체)는 비슷해 보이지만 다른 의미를 가지고 있다.객체는 개체를 포함한 더 큰 개념이다.
대상에 대한 정보뿐만 아니라 동작, 기능, 절차 등을 포함하는 것이 객체이다.
 - `DAO`:Room은 데이터를 읽고 쓰는 메서드를 인터페이스 형태로 설계하고 사용함. 코드 없이 이름만 명시하는 형태로 인터페이스를 만들면 Room이 알아서 나머지 코드 작성해줌 즉 DAO는 데이터베이스에 접근해서 DML쿼리(CRUD수행하는 쿼리)를 실행하는 메서드의 모음
 - `Room Database`:Room 라이브러리가 제공하는 데이터베이스인 RoomDatabase는 RoomDatabase를 상속받아 클래스(RoomHelper)를 만들면 됨. 추상클래스로 만들어야함
- Rest of The App:나머지 부분 코드를 작성!
  
[👉click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CSQLite)
  
</details>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>☘sharedpreferences </strong></span></summary>

- `정의`
  - Key-Value 방식
  - 목적: 공유된 사용자의 기호 방식
  - 하드하게 데이터베이스 시스템 구축 불가
  
- `사용`
 ```kotlin
              val sharedPreference = getSharedPreferences("sp1", MODE_PRIVATE)
            val editor: SharedPreferences.Editor = sharedPreference.edit()
            editor.putString("hello", "안녕하세요")  //key-value값으로 저장
            val value2 = sharedPreference.getString("goodbye", "데이터 없음2") 
 ```
 
  [👉click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CSharedpreference%EC%8B%A4%EC%A0%84)
  
  
</details>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>액티비티 스택에 대해 설명하시오</strong></span></summary>

- `정의`
  - 여러 Activity 는 Stack 형태로 관리된다.  OneActivity에서 TwoActivity를 부르면 위에 쌓이고, TwoActivity에서 ThreeActivity를 부르면 위에 쌓이고  

- `관리`
  - `1. AndroidManifest의 LaunchMode의 옵션`
    - `standard`
     - 새 인스턴스를 생성하고 여러 번 인스턴스화 가능
    - `singleTop`
     -  기존에 생성된 것이 있다면 이 것을 재활용
    - `singletask`
     - 스택의 루트에만 존재가능
     - 무조건 새로운 루트 생성해서 거기부터 새 인스턴스 만들어서 스택 다시 쌓기
     - 다른 액티비티를 호출할경우 그 액티비티는 새로 생성된 Task 위에 쌓임 (singInstance와의 차ㅣ)
    - `singleInstance`
     - singleTask 는 새로운 태스크에 2~3~ 이상의 액티비티 스택을 쌓을수 있는 반면, singleInstance는 오직 하나의 태스크에 하나의 액티비티만 존재
  - `2. Intent Flag`
    - `NEW_TASK`
     - singletask랑 비슷
    - `SINGLE_TOP` 
      -  기존에 생성된 것이 있다면 이 것을 재활용
    - `CLEAR_TOP`  
     - 액티비티의 스택을 제거하고 새로운 액티비를 가장 top으로 만든다. 
</details>

<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Vector, 비트맵 차이</strong></span></summary>

- `벡터`: 리사이징 되어도 안꺠짐, 모든 해상도에서 자유자재로 활용할 수 있어서 특정 해상도에 제한되어 있지 않음
   - SVG
- `비트맵`: 픽셀로 구성, 자유자제로 바꾸거나 움직이기 불가
   - PNG,JPEG
</details>

<p></p>
<h2>🐬안드로이드 응용</h2>

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
   
[👉click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-HiltRepository%ED%8C%A8%ED%84%B4)
   
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
   
[👉click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-%EA%B3%B5%EC%8B%9D%EB%AC%B8%EC%84%9C-%ED%8C%8C%ED%97%A4%EC%B9%98%EA%B8%B0-DiffUtil-ListAdapter-notifyDataSetChanged%EC%9D%98-%EB%AA%A8%EB%93%A0-%EA%B2%83)

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
   <summary><span style="border-bottom:0.05em solid"><strong>☘데이터바인딩이란?</strong></span></summary>
   
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
   
[👉click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9CDataBinding)
   
 ***
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>GSON이란?</strong></span></summary>

   <p>JSON과 JAVA 사이의 직렬화와 역직렬화를 도와주는 라이브러리</p>

***
   
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

[👉click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-Android-%ED%86%B5%EC%8B%A0-%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC%EC%9D%98-%EC%97%AD%EC%82%AC)
   
***
   
</details>


<details>
   <summary><span style="border-bottom:0.05em solid"><strong>Volley와 Retrofit의 차이는?</strong></span></summary>
- 1. 빠르다
- 2. 뛰어난 가독성
   - Annotation으로 HTTP 메소드를 정의함으로서 코드의 구현이 쉬워지며 개발자들은 행위를 손쉽게 알아볼 수 있게 되어 직관적으로 코드를 설계
- 3. 쉬운 유지보수
   - XML을 자동을 파싱해주는 Converter 연동을 지원
   
[👉click](https://velog.io/@dabin/%EC%95%88%EB%93%9C%EB%A1%9C%EC%9D%B4%EB%93%9C-Android-%ED%86%B5%EC%8B%A0-%EB%9D%BC%EC%9D%B4%EB%B8%8C%EB%9F%AC%EB%A6%AC%EC%9D%98-%EC%97%AD%EC%82%AC)   
   
   
</details>
