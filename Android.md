

# 안드로이드 기초 <a name = "reason"></a>
<details>
   <summary> 안드로이드 4대 컴포넌트에 대해 설명하시오 🙋‍♀️</summary>
<br />
# 4대 컴포넌트 → 구성요소/진입점/수명주기 Activity,Service,BroadCast Receiver, Content Provider

## 💘One Pager 요약

![ㅁㄴㅇ](https://user-images.githubusercontent.com/84564695/187105028-837f6503-2830-4f8b-9ee1-67f187b9194e.jpg)


## ✅질문

### 질문) **Content Provider와 Content Resolver 차이**

**Content Provider** : 어플리케이션 내에서 사용할 수 있는 데이터를 ‘공유’하기 위한 컴포넌트

Ex) 연락처,이미지 등 (카카오톡)

**Content Resolver** : 앱이 ContentProvider를 접근할 때에는, Content Resolver를 통해 접근하게 됨.

기본적으로 CRUD 함수들 제공 -> 다른 앱의 데이터베이스를 조작할 수 있음.

Ex) contentResolver.query()

### 질문) **Broadcast Receiver 를 사용할 때, Broadcast를 수신하는 기능 말고 Broadcast 를 송신할 수는 없을까요?**

Broadcast Receiver를 이용하여 앱간의 데이터 전달이나 Broadcast 를 송신할 수 있습니다.

상호작용할 앱 모두에 Broadcast Receiver를 등록하고, sendBroadcast() 를 이용하여 Intent 를 주고 받는 방식으로 동작시켜줍니다.

### 질문)  **Content Provider를 이용해 구현해 본 앱이나 기능이 있으신가요?**

**Content Provider**는 앱간의 정보공유를 가능해게 해주는 컴포넌트입니다.

무엇인지는 알고 있었지만 실제로 사용해 본 적은 없어, 없다고 답했습니다.

이후 찾아본 정보에 의하면 **Content Provider**를 구현하기 위해서는 우선 Content Uri 를 디자인 해야합니다. 이후 **query , insert , update , delete** 를 구현한 뒤 **intent**를 교환하여 앱간의 정보교환이 이루어지게 됩니다.

## ✅4대 컴포넌트

`Activity, Service, Broadcast Receiver, Content Provider`

- 앱 구성 요소는 Android **앱의 필수적인 기본 구성 요소**
- 각 구성 요소는 **시스템이나 사용자가 앱에 들어올 수 있는 진입점**
- 다른 구성 요소에 **종속되는 구성** 요소도 존재
- 각 유형은 뚜렷한 목적을 수행하고 **각자 나름의 수명 주기**가 있어 구성 요소의 생성 및 소멸 방식을 정의

## ✅Activity, Service, BroadCast Receiver, Content Provider

- `Activity`
    - 사용자와 **상호작용하는 interface / 진입점**
    - 안드로이드 시스템과 안드로이드 앱의 주요 상호작용을 도움

![ee JPG](https://user-images.githubusercontent.com/84564695/187105045-2368d1e7-50e7-43b2-9fb5-7ee40a8a9682.jpg)


- `Service`
    - **백그라운드에서 앱을 실행하기 위함**
    - Activity와 다르게 사용자 인터페이스, **UI를 제공하지 않음**
    - 앱이 백그라운드 상태에 있을때도 계속 실행할 수 있기 때문에 사용자가 다른 앱에 있는 동안 백그라운드에서 음악을 재생하거나 네트워크를 통해 다운로드하거나 가능
    - **Service**라는 클래스를 상속한 SubClass를 작성함으로서 구현 가능
    
![캡처 JPG](https://user-images.githubusercontent.com/84564695/187105048-bf2c1b29-b3ba-4409-94ef-0ef6334c213a.jpg)

    
- `Broadcast Receivr`
    - BroadCast Receiver는 안**드로이드 시스템이 앱에 알려야하는 BroadCast(방송/사건)이 생길때 이벤트를 앱에 전달해서 앱에 진입할 수 있는 진입점 역할**을 함
        - ex)앱이 사용자에게 예정된 이벤트에 대해 알리는 알림을 게시하기 위한 알람을 예약할 경우, 그 **알람을 앱의 Broadcast Receiver에 전달하면 알람이 울릴 때까지 앱을 실행하고 있을 필요가 없음**
        - **현재 실행되고 있지 않은 앱에도** Android 시스템에서 Broadcast를 전달할 수 있다.
        - 대다수의 브로드캐스트는 안드로이드 시스템에서 발생
            - ex)화면이 꺼졌거나 배터리가 부족하거나 사진을 캡처했다고 알리는 브로드캐스트가 대표적앱도 브로드캐스트를 발생 할 수 있음
            - 다른 앱에 일부 데이터가 기기에 다운로드되었고 이를 사용할 수 있다는 것을 알리는 데 사용
    - **BroadCast Receive**라는 클래스를 상속해서 구현 가능
- `Content Provider`
    - Content Provoder는 **안드로이드 앱 간에 파일시스템, SQLite 데이터베이스 등 앱이 엑세스 할 수 있는 앱 데이터를 공유**할 수 있게 함
        - 다른 앱은 콘텐츠 제공자를 통해 해당 데이터를 쿼리하거나, 콘텐츠 제공자가 허용할 경우에는 수정도 가능
        - ex) Android 시스템은 사용자의 연락처 정보를 관리하는 콘텐츠 제공자를 제공. 적절한 권한을 가진 앱이라면 콘텐츠 제공자(예: ContactsContract.Data)를 쿼리하여 특정한 인물에 대한 정보를 읽고 쓸 수 있음
    - **Content Provider**라는 클래스를 상속해서 구현 가능
   
 </details>

<br>
 
