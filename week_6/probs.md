**1. Empty Page가 없을 때 비울 Page를 선정하는 알고리즘 중 가장 오래 전에 사용된 것을 고르는 것은?**
- LRU (Least Recently Used)

**2. Clock Algorithm의 방법을 설명하시오.**
- Circular List 와 Pointer를 사용한다. Pointer가 한바퀴 돌면서 reference bit이 0인 것을 찾는다. 0이면 교체대상으로 선정한다. Reference bit이 1인 것을 0으로 바꾼다. modified bit이 있다면 1인 경우에는 디스크에 새로 올려둔 뒤 비워야 하므로 0인 것부터 우선적으로 쫓아낸다.

**3. 프로세스가 원활한 수행에 필요한 최소한의 page frame 수를 할당 받지 못한 경우를 부르는 말은?**
- Thrashing

**4. File 관리 중 Open()시 메모리 영역에 올려두게 되는 것은?**
- file의 metadata

**5. page fault가 발생하는 경우는?**
- 요청한 페이지가 메모리에 없는 경우

**6. Paging System에서 LRU, LFU 알고리즘이 가능한가?**
- 불가능하다. os가 페이지에 대한 정보를 모두 알지 못하기 때문이다.

**7. 빈칸 채우기**

```
Clock 알고리즘은 (1) 알고리즘의 근사 알고리즘이다. 
개선된 Clock 알고리즘은 (2),(3) 비트를 사용한다.
```
- (1) LRU
- (2) reference bit
- (3) modified bit

**8. Thrashing을 방지하는 방법**
- working-set : window만큼의 시간만 페이지를 메모리에 유지
- PFF : page frame rate를 넘으면 frame을 더 할당하고 작으면 할당 frame 수를 줄임

**9. invalid bit이 1인 것의 의미는?**
- 해당 페이지(?)가 물리메모리에 없다.

**10. Thrashing은 언제 발생하고 해결을 위해 무엇을 조절해야 하는가?**
- 프로세스가 원활한 수행에 필요한 최소한의 page frame 수를 할당 받지 못한 경우 발생하고 MPD (Multiprogramming Degree)를 조절해야한다.

**11. File system의 접근권한 조절 방법 중 일반적으로 사용되는 것은?**
- grouping

<br>
<br>
<br>
<br>
<br>
<br>

---
## 예리
1. Empty Page가 없을 때 비울 Page를 선정하는 알고리즘 중 가장 오래 전에 사용된 것을 고르는 것은?
- LRU

2. Clock Algorithm의 방법을 설명하시오.
- Circular list와 포인터를 통해 이루어진다. 포인터가 한 바퀴를 돌면서 Reference bit을 확인해 해당 비트가 1이면 0으로 바꾸고, 0이면 교체 대상으로 선정. modified bit이 있다면 1인 경우에는 디스크에 새로 올려둔 뒤 비워야 하므로 0인 것부터 우선적으로 쫓아낸다.

3. 프로세스가 원활한 수행에 필요한 최소한의 page frame 수를 할당 받지 못한 경우를 부르는 말은?
- Thrashing

4. File 관리 중 Open()시 메모리 영역에 올려두게 되는 것은?
- 파일 메타데이터

## 정민
1. page fault가 발생하는 경우는?

- 요청한 페이지가 메모리에 없는 경우이다.
( address translation 시에 invalid bit이 set 되어 있는 경우)

2. Paging System에서 LRU, LFU 알고리즘이 가능한가?

- 불가능하다.
- page fault인 경우에만 OS가 관여함
- 페이지가 이미 메모리에 존재하는 경우 참조시각 등의 정보를 OS가 알 수 없음
- O(1)인 LRU의 list 조작조차 불가능

3. 빈칸 채우기
```
Clock 알고리즘은 (1) 알고리즘의 근사 알고리즘이다. 
개선된 Clock 알고리즘은 (2),(3) 비트를 사용한다.
```
- (1) LRU, (2) 참조 reference, (3) 변경 modified

4. Thrashing을 방지하는 방법

- Working-set Model

  - process의 working set 전체가 메모리에 올라와 있어야 수행되고 그렇지 않을 경우 모든 frame을 반납한 후 swap out(suspend)

- PFF(Page Fault Frequency)

  - Page-fault rate의 상한값과 하한값을 두고, Page fault rate 상한값을 넘으면 frame을 더 할당, Page fault rate 하한값 이하면 할당 frame 수를 줄인다

## 지혜
1. invalid bit이 1인 것의 의미는?
2. Paging System 에서 LRU,LFU가 불가능한 이유는?
3. Thrashing은 언제 발생하고 해결을 위해 무엇을 조절해야 하는가?
4. File system의 접근권한 조절 방법 중 일반적으로 사용되는 것은?