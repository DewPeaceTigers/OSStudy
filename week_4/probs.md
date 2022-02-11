1. Producer-consumer Problem에서 Producer의 역할에 대한 수도 코드이다. 빈칸을 채워라
   ```
   Producer
   1. ____ buffer 기다리기 P(___)
   2. Shared data에 lock을 건다. __(mutex)
   3. ____ buffer에 데이터 입력
   4. Lock 풀기 __(mutex)
   5. ____ buffer++ V(___)
   ```
   empty, P, empty, V, full
2. Dining Philosopher 문제 해결 방법은?

   젓가락을 들 때 동시에 두 개를 들게 한다. 두 개를 들 수 있을 때만 권한을 준다.

3. "Monitor이 사용하는 변수는 조건 변수이다." O/X로 답하고, Monitor의 특징을 3가지 적으세요

   O

   - lock을 걸지 않아도 된다.
   - 공유 데이터를 직접 접근하지 않고 프로시저를 통해서만 접근한다.
   - 하나의 프로세스만 접근이 가능하다.

4. Deadlock의 4가지 조건 중 강제로 빼앗기지 않으려는 조건은?

   비선점 No preemption

5. Baneker's Algorithm은 Deadlock Avoidance와 Detect and Recovery 각 방법에서 어떤 관점의 차이를 가지고 이용되나

   Avoidance는 앞 프로세스에 대해 최악의 상황을 가정해서 최대 사용량을 요청했다고 가정, Detect and Recovery는 앞 프로세스에 대해 낙관적으로 보아 모두 반납했다고 가정

6. 프로세스 동기화 상황에서 발생할 수 있는 고전적인 문제 3가지

   - Producer-consumer Problem
   - Readers-Writers Problem
   - Dining-Philosophers Problem

7. 다음 그림에서 starvation이 발생하는 경우와 해결방안

   <img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/86f81446-9def-41fe-867d-7b474f6ee5e7/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220210%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220210T154026Z&X-Amz-Expires=86400&X-Amz-Signature=0b0a8608f3a28570815e44f0ba53af5da608039314d9f2d4f31cb2985ee3c84c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject"
     height="300" />

   Reader가 계속 DB에 접근할 경우, Writer가 접근하지 못함

   - Queue에 우선순위를 부여하여 Writer가 오래 기다리지 않게 한다.

8. Deadlock의 의미, Deadlock 발생의 4가지 조건

   프로세스들이 서로가 가진 자원을 기다리며 block된 상태

   - 상호 배제 : 독점적. 한번에 하나의 프로세스만 자원 이용 가능
   - 비선점 : 가진 자원을 빼앗기지 않는다.
   - 보유 대기 : 프로세스가 다른 자원을 기다릴 때 가진 자원을 놓지않고 갖고 있다.
   - 순환 대기 : 자원을 기다리는 프로세스 간에 사이클이 형성되어야 함.자원 요청이 cycle을 이루고 있다.

9. Deadlock 회피 기법인 Banker's Algorithm 에 대하여 설명하세요

   - 자원 당 여러 개의 인스턴스가 있을 때 사용
   - 미리 최대 요청을 받아놓음
   - 자원을 요청할 때 최대로 필요한 자원을 충족할 수 없을 때는 deadlock이 발생할 가능성이 있으므로 요청을 받아들이지 않아 데드락을 방지한다.

10. monitor의 프로세스 동기화 방법은?

    프로세스가 공유데이터에 접근하기 위해서는 monitor 내부의 어떠한 절차를 통해서만 공유 데이터에 접근할 수 있게 한다. 모니터의 경우 기본적으로 여러 프로세스가 모니터에 대한 동시접근을 제한한다. 그렇기 때문에 한 순간에 하나의 프로세스만 모니터에 접근하여 공유데이터를 사용할 수 있다. 다른 프로세스가 접근하면 queue에서 기다리게 된다.

11. monitor와 semaphore의 차이는?

- semaphore : 자원을 획득하기 위해서 프로그래머가 알아서 P연산, V연산을 해줘야 함.
- monitor : 동시 접근을 막는 것을 모니터 차원에서 지원해줌

* monitor는 조건 변수, semaphore는 값이 있는 변수

12. Deadlock이 발생하지 않도록 미리 관리하는 방법은?

- Prevention, Avoidance

## 예리

1. Producer-consumer Problem에서 Producer의 역할에 대한 수도 코드이다. 빈칸을 채워라
   ```
   Producer
   1. ____ buffer 기다리기 P(___)
   2. Shared data에 lock을 건다. __(mutex)
   3. ____ buffer에 데이터 입력
   4. Lock 풀기 __(mutex)
   5. ____ buffer++ V(___)
   ```
2. Dining Philosopher 문제 해결 방법은?

3. Monitor이 사용하는 변수는 조건 변수이다. O/X로 답하고, Monitor의 특징을 3가지 적으세요

4. Deadlock의 4가지 조건 중 강제로 빼앗기지 않으려는 조건은?

5. Baneker's Algorithm은 Deadlock Avoidance와 Detect and Recovery 각 방법에서 어떤 관점의 차이를 가지고 이용되나

## 정민

1. 프로세스 동기화 상황에서 발생할 수 있는 고전적인 문제 3가지
2. 다음 그림에서 starvation이 발생하는 경우와 해결방안

   <img src="https://s3.us-west-2.amazonaws.com/secure.notion-static.com/86f81446-9def-41fe-867d-7b474f6ee5e7/Untitled.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45EIPT3X45%2F20220210%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20220210T154026Z&X-Amz-Expires=86400&X-Amz-Signature=0b0a8608f3a28570815e44f0ba53af5da608039314d9f2d4f31cb2985ee3c84c&X-Amz-SignedHeaders=host&response-content-disposition=filename%20%3D%22Untitled.png%22&x-id=GetObject"
    height="300" />

3. Deadlock의 의미, Deadlock 발생의 4가지 조건
4. Deadlock 회피 기법인 Banker's Algorithm 에 대하여 설명하세요

## 지혜

1. monitor의 프로세스 동기화 방법은?
   1. 프로세스가 공유데이터에 접근하기 위해서는 monitor 내부의 어떠한 절차를 통해서만 공유 데이터에 접근할 수 있게 한다. 모니터의 경우 기본적으로 여러 프로세스가 모니터에 대한 동시접근을 제한한다. 그렇기 때문에 한 순간에 하나의 프로세스만 모니터에 접근하여 공유데이터를 사용할 수 있다. 다른 프로세스가 접근하면 queue에서 기다리게 된다.
2. monitor와 semaphore의 차이는?
   - semaphore : 자원을 획득하기 위해서 프로그래머가 알아서 P연산, V연산을 해줘야 함.
   - monitor : 동시 접근을 막는 것을 모니터 차원에서 지원해줌
3. Deadlock의 발생조건 4가지는? 1. Mutual Exclusion
   상호배제 : 매 순간 하나의 프로세스만이 자원을 사용할 수 있음 2. No Preemption
   비선점 : 프로세스는 자원을 스스로 내어놓을 뿐 강제로 빼앗기지 않음 3. Hold and wait
   보유대기 : 자원을 가진 프로세스가 다른 자원을 기다릴 때 보유한 자원을 놓지 않고 계속 가지고 있음 4. Circular wait
   순환대기 : 자원을 기다리는 프로세스 간에 사이클이 형성되어야 함
4. Deadlock이 발생하지 않도록 미리 관리하는 방법은?
   1. Prevention & Avoidance
