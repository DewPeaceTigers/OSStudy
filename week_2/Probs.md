## 2주차 문제 정리
1. 문맥 교환시 OS가 하는 일은?
    - PCB에 현재 실행중인 프로세스 문맥을 저장하고, 새로 점유할 프로세스의 문맥을 PCB에서 읽어온다.

2. Ligthweight Process가 Heavyweight Process보다 좋은 효율을 갖는 이유가 무엇일까?
    - 메모리를 공유하는 부분이 있어 효율적이다. blocked 되었을 때 다른 스레드로 바꿀 때 빠른 응답성을 갖고 오버헤드가 적다.

3. 프로세스가 종료될 때 지켜야하는 원칙은?
    - 자식 프로세스가 부모 프로세스보다 먼저 종료되어야한다.

4. Process의 문맥이란
    - 프로세스가 어디까지 실행 되었는지를 나타냄 - CPU 관련 정보(Program Counter, Register)

5. Suspended 상태란?
    - 외부적인 이유로 프로세스가 종료됨
    - Medium-Term scheduler에 의해 메모리에서 swap out된 상태
    
6. 프로세스 생성 원리는? 
    - 복제 생성. 
    - OS가 부모 프로세스 문맥을 자식 프로세스에게 복사한다.

7. IPC의 방법 2가지를 비교하기
    - Message Passing
        - 커널을 통해서 메시지를 전달
    - Shared Memory
        - 프로세스 간의 물리적 메모리를 공유

8. 프로세스의 문맥이 필요한 이유
    - CPU 제어권이 돌아왔을 때 완료한 시점 이후부터 실행하기 위해서

9. 프로젝트의 상태 **blocked** 와 **suspended**의 차이
    - blocked
        - 요청한 event가 끝나면 ready 상태가 됨
        - 자발적 정지
    - suspended
        - 외부적인 이유로 프로세스가 정지됨 
        - 비자발적 정지

10. Thread 가 별도로 갖는 값과 공유하는 값은 각각 무엇인가? (3가지씩)
    - 별도로 갖는 값
        - Program counter
        - register
        - stack
    - 공유하는 값
        - code
        - data
        - 나머지,, (OS 자원)

11. Long-Term Scheduler 과 Medium-Term Scheduler의 차이는?
    - Long-Term Scheduler는 어떤 프로세스를 메모리에 올릴지 결정하는 부분.
    - Medium-Term Scheduler는 메모리에 올라와 있는 프로세스들 중에 어떤 것을 쫓아낼지 결정하는 부분

---
#### 예리

1. 문맥 교환시 OS가 하는 일은?

   현 프로세스의 상태를 해당 PCB에 저장하고 새로 온 프로세스의 상태를 알기 위해 해당 PCB를 읽는다.

2. Ligthweight Process가 Heavyweight Process보다 좋은 효율을 갖는 이유가 무엇일까?

   Lightweight Process는 한 프로세스에 여러 Thread를 두는 방식으로 한 주소 공간을 공유 하는 등 최대한 공유를 하기 때문이다. 이를 통해 하나가 blocked 되어도 빠르게 다른 것이 run되는 빠른 응답성을 갖고, 전환되는 과정도 프로세스가 전환되는 것보다 오버헤드가 적기 때문에 효율이 좋다.

3. 프로세스가 종료될 때 지켜야하는 원칙은?

   자식 프로세스는 부모 프로세스보다 일찍 죽으면 안된다. 그래서 부모가 갑작스레 종료되면 그 아래 모든 자식들이 종료된 후에 처리 된다.

4. Long-Term Scheduler 과 Medium-Term Scheduler의 차이는?
    - Long-Term Scheduler는 어떤 프로세스를 메모리에 올릴지 결정하는 부분.
    - Medium-Term Scheduler는 메모리에 올라와 있는 프로세스들 중에 어떤 것을 쫓아낼지 결정하는 부분


#### 지혜

1. Process의 문맥이란
프로세스의 현재 상태를 나타내기 위한 모든 요소이다.
PC, register과 같이 cpu 수행 상태를 나타내는 하드웨어적 문맥,
code, stack, data 같이 메모리 상의 프로세스 주소 공간적 문맥,
pcb, kernel stack 같이 커널 자료구조적 문맥이 있다.

2. Suspended 상태란?
외부적인 이유로 프로세스의 수행이 정지된 상태
Medium-Term Schedular에 의해 프로세스가 메모리를 모두 빼았기고 disk로 swap out

3. 프로세스 생성 원리는? 
복제

4. IPC의 방법 2가지를 비교하기
    1. messaging passing : 커널을 통해 메시지 전달
    2. shared memory : 프로세스간의 물리적 메모리 공간 일부 공유


#### 정민
1. 프로세스의 문맥이 필요한 이유
    - Time sharing, Multi tasking 등 프로세스들이 번갈아 가면서 실행되기 때문에 하나의 프로세스가 CPU를 잡고 실행을 하다가 다른 프로세스에게 CPU가 넘어간다. 프로세스의 현재 문맥을 모르면 다음 CPU를 잡았을 때 처음부터 다시 실행해야 되는 문제 발생하므로 **문맥을 파악하고 있어야 완료된 부분 다음 시점부터 instruction을 실행**할 수 있다
2. 프로젝트의 상태 **blocked** 와 **suspended**의 차이
    - blocked: I/O 등의 event를 **스스로** 기다리는 상태
    - suspended: **외부적인 이유**로 프로세스의 수행이 정지된 상태
3. Thread 가 별도로 갖는 값과 공유하는 값은 각각 무엇인가? (3가지씩)
    - 별도로 갖는 값 - cpu 수행과 관련된 정보
        - Program Counter
        - Register Set
        - Stack space
    - 공유하는 값
        - Code section
        - Data section
        - OS resources
4. 프로세스가 생성되는 방법 : 부모 프로세스가 자식 프로세스를 _ _ 생성한다.
    - 복제 생성
    - 부모프로세스의 주소공간 내용을 그대로 자식 프로세스의 주소공간으로 복사한다.
    - 부모 프로세스와는 다른 자식프로세스의 프로그램을 실행해야할 경우 복제된 주소공간 위에 새로운 프로그램의 주소공간을 덮어씌어 실행한다.