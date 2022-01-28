## 3주차 문제 정리
1. 스케줄링 기준 중 프로그램 입장에서의 성능 척도를 나타내는 세가지 단어를 차이점과 함께 적어주세요.
  - Turnaround time : cpu를 사용하기 위해 큐에 들어간 시간부터 다 처리하고 완전히 나간 시간
  - Waiting time : Ready 큐에서 기다린 총 시간
  - Response time : Ready 큐에 들어와서 처음으로 cpu를 얻는데 걸린 시간

2. Round Robin에 대해서 설명해주세요.
- 동일한 크기의 할당 시간을 갖는 선점형 스케줄링 알고리즘. cpu를 기다리는 시간과 사용하는 시간이 비례한다. 시간 할당이 되어있어서 응답시간이 빨라진다.

3. Critical Section에 대해 설명하세요.
- 같은 데이터에 접근할 수 있는 코드 부분. 한 프로세스가 접근 중이라면 다른 프로세스가 접근할 수 없는 부분.

4. Semaphore의 두가지 방식을 말하면서 각 방식의 lock 방법과 변수 이용의 차이점을 설명해주세요.
- Busy-Wait : spin lock / 자원의 개수를 세는 정도로 사용한다.
- Block-WakeUp : sleep lock / 변수는 상황을 나타내는 정보로 사용된다.

5. Priority Schedule의 문제점과 해결책은?
- 문제점 : Starvation | 우선 순위가 낮은 프로세스들이 계속 기다리게 된다.
- 해결 : Aging | 기다린 시간에 따라서 우선순위를 높여준다.

6. RR 스케줄링의 할당 시간(time quantum) 이 큰 경우와 작은 경우 performance 가 어떻게 되는가
- 큰 경우 : FCFS 와 비슷해진다.
- 작은 경우 : context switch 오버헤드가 커진다.

7. Semaphore의 연산 두 가지와 하는 역할
- P 연산 : 자원을 획득하는 연산. lock을 거는 과정
- V 연산 : 자원을 반납하는 연산. lock을 푸는 과정

8. 라운드 로빈 스케쥴링 방식이 응답시간이 빨라지는 이유에 대해 설명하세요.
- cpu 사용 시간을 공평하게 할당했기 때문이다.

9. MultiLevel Feedback Queue 의 동작방식을 간단하게 설명하세요.
* Q의 우선 순위 : Q0 (RR : time quantum=8) > Q1 (RR : time quantum=16) > Q2 (FCFS)
    * new job이 Q0로 들어감
    * cpu를 잡아서 할당 시간 8ms동안 수행됨
    * if (할당 시간내에 다 끝내면) out / else Q1으로 내려감
        * Q1에서 줄서서 기다렸다가 cpu를 잡아서 16ms동안 수행됨
        * if (할당 시간내에 다 끝내면) out / else Q2로 내려감
            * Q2는 FCFS 방식으로 작동하는 큐이므로 순서를 기다림

10. Race Condition의 발생 이유에 대해 설명하세요.
- 프로세스들이 공유 데이터를 사용하기 때문이다.


<br>
<br>
<br>

---

### 예리
1. 스케줄링 기준 중 프로그램 입장에서의 성능 척도를 나타내는 세가지 단어를 차이점과 함께 적어주세요.
2. Round Robin에 대해서 설명해주세요
3. Critical Section에 대해 설명하세요.
4. Semaphore의 두가지 방식을 말하면서 각 방식의 lock 방법과 변수 이용의 차이점을 설명해주세요.

### 정민
1. 프로그램 입장에서의 Scheduling Criteria(성능척도) 는?
2. Priority Schedule의 문제점과 해결책은?
3. RR 스케줄링의 할당 시간(time quantum) 이 큰 경우와 작은 경우 performance 가 어떻게 되는가
4. Semaphore의 연산 두 가지와 하는 역할

### 지혜
1. 라운드 로빈 스케쥴링 방식이 응답시간이 빨라지는 이유에 대해 설명하세요.
* 각 프로세스는 동일한 크기의 할당 시간 (Time Quantum) 을 가지기 때문

2. MultiLevel Feedback Queue 의 동작방식을 간단하게 설명하세요.
* Q의 우선 순위 : Q0 (RR : time quantum=8) > Q1 (RR : time quantum=16) > Q2 (FCFS)
    * new job이 Q0로 들어감
    * cpu를 잡아서 할당 시간 8ms동안 수행됨
    * if (할당 시간내에 다 끝내면) out / else Q1으로 내려감
        * Q1에서 줄서서 기다렸다가 cpu를 잡아서 16ms동안 수행됨
        * if (할당 시간내에 다 끝내면) out / else Q2로 내려감
            * Q2는 FCFS 방식으로 작동하는 큐이므로 순서를 기다림

3. Race Condition의 발생 이유에 대해 설명하세요.
* 여러 프로세스들이 동시에 같은 데이터에 접근하는 상황

4. Critical Section은 무엇인가요.
* 코드 상에서 공유 데이터에 접근하여 Race condition이 발생할 수 있는 부분