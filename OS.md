

# 프로세스와 스레드 <a name = "outline"></a>
</details>


<details>
   <summary> Click 🙋‍♀️</summary>
<br />
 

### 📌프로세스  
- **프로세스는 컴퓨터 시스템의 작업 단위**로 태스크라고도 부름
  - 저장장치에 저장되어 있는 정적인 상태인 **프로그램이 운영체제로부터 프로세스 제어블록을 받아 메모리상에 올라오면 "프로세스"** 
  - 프로세스 제어 블록이 없으면 프로그램이 프로세스로 전환되지 못하며, 어떤 프로그램이 프로세스가 되었다는 것은 운영체제로부터 프로세스 제어 블록을 받았다는 의미
  - 프로그램 실행->프로세스
  - 자신만의 고유 공간과 자원을 할당받아 사용(코드/데이터/힙/스택)
  
  
### 📌스레드
- **CPU 스케줄러가 CPU에 작업을 요청하는 실행단위=프로세스 안에서 실행되는 흐름단위**
  - 운영체제가 프로세스 제어블록을 생성하고 작업에 필요한 메모리 영역을 확보한 후 준비된 프로세스를 준비큐에 삽입  
  ->프로세스가 생성되면 CPU스케줄러는 프로세스가 해야하는 일을 CPU에 전달하고 실제 작업은 CPU가 수행  
  ->이때 CPU스케줄러가 CPU에 전달하는 일 하나는 "스레드"  
  - 스레드는 스택영역만 따로 할당받고 나머지 영역은 스레드끼리 서로 공유

  
### 📌스레드 vs 프로세스
-  프로세스는 운영체제의 **작업단위**, 스레드는 CPU 스케줄러가 CPU에 작업을 요청하는 **실행단위** 
-  프로세스는 **자신만의 고유 공간과 자원 할당** 받음 / 스레드는 **다른 스레드와 자원 공유**
  
### 📌멀티스레드
- 예전엔 여러 작업을 동시에 처리하기 위해 fork() 시스템 호출로 프로세스를 전환하는 방법을 이용했음 = 멀티태스크 ex) 워드랑 프린트 스풀러는 독립적으로 작동하다가 필요할 때 출력할 데이터를 프로세스간 통신을 이용해 주고받음     
  ->프로세스의 정적영역(코드/데이터) 영역 메모리 중복 
  ->비슷한 일을 하는 여러 프로세스를 만들지 말자   
  ->정적영역 공유면서 여러개의 일을 하나의 프로세스 내에서 하자   
  ->CPU가 여러 스레드 조금씩 돌면서 병렬적으로 작업  
  ->코드 영역등을 함께 공유해서 자원 낭비 막고 효율성 향상!!! 

- 멀티스레드 장점
    - **자원공유**: 프로세스가 가진 자원을 모든 스레드가 공유->작업 원활   
    - **응답성 향상**: 다른 스레드가 작업을 계속하여 사용자의 작업 요구에 빨리 응답 가능   
   ex) 채팅+파일 주고받기 / 워드 작성+틀린글자 찾아줌 / 비디오 플레이어 입출력(재생파일 저장장치로부터 가져옴)+영상재생   
  
 - 멀티스레드 단점
    - **독립X**: 모든 스레드가 자원공유하니까 한 스레드에 문제 발생하면 전체 프로세스에 영향  
  EX)익스플로러:프로세스1+멀티스레드 / 크롬:멀티태스크 -> 다른 화면 종료되어도 전체종료X
    - **동기화**:자원 공유로 인한 일치 문제 등
    - **오버헤드**: 싱글 코어 멀티 스레딩은 스레드 생성 시간이 오히려 오버헤드로 작용해 단일 스레드보다 느리다.
 
 - 안전성 Critical Section 대비함
   - 하나의 스레드가 공유 데이터 값을 변경하는 시점에 다른 스레드가 그 값을 읽으려할 때 발생하는 문제를 해결하기 위한 동기화 과정
### 📌싱글스레드
- 하나의 프로세스에서 오직 하나의 스레드로만 실행
- 장점
  - **문맥 교환X**: 문맥 교환은 여러 개의 프로세스가 하나의 프로세서를 공유할 때 발생하는 작업으로 많은 비용을 필요로 한다.

  - **동기화X**: 여러 개의 스레드가 프로세스의 자원을 공유할 경우, 각 스레드가 원하는 결과를 얻게 하려면 공용 자원에 대한 접근을 제어해야 한다. 쉽게 말해서, 모든 스레드가 일정 자원에 동시에 접근하거나, 똑같은 작업을 실행하려는 경우, 에러가 발생하거나 원하는 값이 나오지 않는다. 그래서, 스레드들이 동시에 같은 자원에 접근하지 못하도록 제어해줘야만 한다. 이 작업은 프로그래머에게 많은 노력을 요구하고 비용을 발생시킨다.

- 단점
  - **연산량이 많은 작업을 하는 경우, 그 작업이 완료되어야 다른 작업을 수행**할 수 있다
  EX)서버 통신 완료 되어야 UI클릭 가능

  - **에러 처리를 못하는 경우 멈춘다.**
멀티 스레드 모델은 에러 발생 시 새로운 스레드를 생성하여 극복한다. 다만, 새로운 스레드 생성이나 놀고 있는 스레드 처리에 비용이 발생한다.
### 📌멀티스레드 vs 싱글스레드

- **단순히 CPU만을 사용하는 계산작업이라면, 오히려 멀티스레드보다 싱글스레드로 프로그래밍하는 것이 더 효율적**이다.
=> a) 두 개의 작업을 하나의 스레드로 처리하는 경우 VS b) 두 개의 스레드로 처리하는 경우
b의 경우는 짧은 시간 동안 2개의 스레드가 번갈아가면서 작업을 수행한다. 그래서 동시에 두 작업이 처리되는 것과 같이 느끼게 된다.
하지만, 오히여 두 개의 스레드로 작업한 시간이 싱글스레드로 작업한 시간보다 더 걸릴 수도 있는데, 그 이유는 **스레드 간의 작업전환(context switching)에 시간이 걸리기 때문**이다.
다시 말해서, 단순히 CPU만을 사용하는 작업은 싱글 스레드가 멀티 스레드보다 빠르다.

### 📌멀티프로세스  
- 두개 이상 다수의 프로세서(CPU)가 협력적으로 하나 이상의 작업(Task)을 동시에 처리하는 것이다. (병렬처리)

- 장점
  - 프로세스 중 하나에 문제가 생겨도 다른 프로세스에 영향을 주지 않아, 작업속도가 느려지는 손해정도는 생기지만 정지되거나 하는 문제는 발생하지 않는다.

- 단점
  - **각각 독립된 메모리 영역**을 가지고 있어, **작업량이 많을수록 Context Switching이 자주** 일어나서 **주소 공간의 공유가 잦을 경우 캐시 메모리 초기화 등 무거운 작업**이 자주 진행되면 **오버헤드**가 발생한다.
  
### 📌오버헤드
- 오버 헤드는 특정 기능을 수행하는데 드는 간접적인 시간, 메모리 등 자원
- 10초 걸리는 기능이 간접적인 원인으로 20초걸린다면 오버헤드는 10
### 📌Context Switching
- 두 프로세스가 프로세스 제어블록을 교환하는 작업(타임아웃/인터럽트)
  - CPU는 한번에 하나의 프로세스만 실행 가능
  - CPU를 차지하던 프로세스가 나가고 새로운 프로세스를 받아들이는 작업. 이때 프로세스 제어 블록의 내용이 변경되는데 실행상태에서 나가는 프로세스 제어블록에는 지금까지의 작업 내용을 저장하고 반대로 실행 상태로 들어오는 프로세스 제어 블록의 내용으로 CPU가 다시 세팅.
  
- **교환과정**: A타임아웃->A준비상태로감->CPU 레지스터가 B의프로세스 제어블록값으로 채워져 다음 작업 실행
    

### 👉응용사례) 이런 상태일때는 무슨 스레드 쓰니??
  