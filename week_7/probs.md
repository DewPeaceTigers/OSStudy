1. Indexed Allocation의 동작 방법을 설명하시오

   index block에 주소가 있어서 특정 위치를 접근하려면 block에서 찾아서 접근한다. index block에 해당 파일 위치 정보가 열거 돼있다.

2. 빈 공간 관리하는 방법 4가지

   bit map, linked list, grouping, counting

3. Unified Buffer Cache의 장점은?

   - OS에 요청할 필요없이 직접 page cache에서 가져올 수 있다.
   - Buffer cache에 copy 할 필요없이 바로 page cache에 올려두어 올리는 경로가 더 단순해졌다.

4. Disk Access time의 구성 중 가장 긴 구성 요소는?

   seek time

5. FAT는 Linked Allocation의 어떤 문제를 해결한 것인가요?

   - reliability와 공간 효율성 문제를 해결했다.
   - FAT를 보면 직접 접근이 가능하다.

6. 디스크를 만들 때 sector들로 나누는 과정은?

   physical formatting

7. Disk Scheduling의 목표는?

   seek time 줄이기

8. indexed allocation의 장단점은?

   - 장점
     - 외부 조각 발생 안함
     - 직접 접근이 가능하다
   - 단점
     - 작은 파일이면 공간 낭비가 발생한다.
     - 아주 큰 파일이면 하나의 index block으로 모든 위치 정보 저장이 불가하다.

9. linked allocation의 단점을 보완하기 위한 방법은?

   FAT File Allocation Table
   아주 큰 파일일 경우에만 link scheme, muti-level index

10. 유닉스 파일시스템 구조에서 Inode list가 가지고 있는 정보

    메타데이터 위치 정보

11. SCAN 알고리즘과 LOOK 알고리즘의 차이점은?

    SCAN 알고리즘은 요청이 없어도 안쪽과 바깥쪽을 모두 이동하는데, LOOK 알고리즘은 요청이 없으면 방향을 바꾼다.

---

## 예리

1. Indexed Allocation의 동작 방법을 설명하시오
2. 빈 공간 관리하는 방법 4가지
3. Unified Buffer Cache의 장점은?
4. Disk Access time의 구성 중 가장 긴 구성 요소는?

**답**

1. index block을 이용하여 block의 한정된 공간 내에 위치 정보를 열거 해둠
2. bit map, linked list, grouping, counting
3. Buffer cache에 copy 할 필요없이 바로 page cache에 올려두어 올리는 경로가 더 단순해졌고, OS에 요청할 필요없이 직접 캐시에 접근하여 가져올 수 있어 효율적이다.
4. Seek time

---

## 지혜

1. 디스크의 비어있는 블록 관리 방법 4가지는?
2. FAT는 Linked Allocation의 어떤 문제를 해결한 것인가요?
3. 디스크를 만들 때 sector들로 나누는 과정은?
4. Disk Scheduling의 목표는?

**정답**

1. bitmap / linked list / grouping / counting
2. reliability(한 sector가 고장나 pointer 유실시 다음 데이터들의 주소 역시 망가지므로 많은 부분을 유실 가능)와 공간 효율성 문제(pointer를 위한 공간이 block의 일부가 되어 공간 효율성을 떨어뜨림)
3. physical formatting
4. access time중 seek time을 최소화한다.

---

## 정민

1. indexed allocation의 장단점은?
2. linked allocation의 단점을 보완하기 위한 방법은?
3. 유닉스 파일시스템 구조에서 Inode list가 가지고 있는 정보
4. SCAN 알고리즘과 LOOK 알고리즘의 차이점은?

**정답**

1. - 장점
     - 외부조각이 발생하지 않음
     - 직접 접근이 가능
   - 단점
     - 파일이 굉장히 작은 경우 공간 낭비
     - 파일이 굉장히 큰 경우 하나의 블록으로 Index를 저장하기에 부족함
2. FAT(File Allocation Table), 포인터를 별도의 위치에 보관하여 reliability와 공간효율성 문제 해결
3. 파일 이름을 제외한 파일의 모든 메타 데이터를 저장
4. LOOK 알고리즘은 끝에 요청이 없으면 바로 방향을 바꾸고, SCAN은 무조건 끝까지 확인을 하고 방향을 바꾼다.
