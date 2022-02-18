1. MMU의 역할과 사용하는 register에 대해 설명하시오
- 가상 주소를 물리 주소로 변환해주는 H/W, 
- base(relocation) register : 물리 메모리 상에 올라갈 시작 위치
- limit register : 논리적 주소의 범위

2. 내부 조각과 외부 조각에 대해 설명하시오
- 내부 조각
    - 프로세스보다 페이지가 커서 남는 공간이 생김
- 외부 조각
    -  프로그램 크기보다 분할 크기가 작아서 할당되지 못하는 공간이다.
    메모리가 할당 되었다가 해제되어서 중간중간 사용하지 않는 공간이 생기게 되는데 총 메모리 공간이 충분하지만 메모리 조각의 크기가 작아서 프로세스를 할당할 수 없다.

3. Muti-level page table을 사용하게 되는 이유는?
- page table 의 메모리 낭비를 줄이기 위해서

4. Paging과 Segment의 차이점을 설명하시오
- Paging은 가상 메모리를 동일한 크기로 나눈다. Segment는 의미 단위로 나뉜다.
- segment는 의미 단위로 나누기에 protection과 sharing에 효과적이지만, 그 크기가 다르기에 외부조각이 발생한다. 반면, paging은 protection과 sharing에 대응하기 어렵지만, 외부 조각은 발생하지 않는다.
- paging은 entry 개수가 매우 많지만, segment는 적다. 

5. 사용자 프로세스 영역의 할당 방법은? (Contiguous 2가지, NonContiguous 3가지)
- Contiguous
    - Fixed Partition Allocation : 고정 분할 방식
    - Variable Partition Allocaion : 가변 분할 방식

- NonContiguous
    - Paging 
    - Segmentation 
    - Paged Segmentation : 요즘 사용, 세그먼트 + 페이징 혼합    

6. 페이징 기법을 사용하면 메모리에 _번 접근하여야 한다. 속도를 향상 시키기 위한 방법은?
- 2번, page table 접근 1번 + 메모리 접근 1번
- TLB를 사용한다. 주소 변환을 위한 캐시메모리(메인메모리와 CPU 사이에 존재), 메인메모리보다 접근 속도가 빠른 하드웨어로 구성

7. Shared Code 조건 2가지
- read-only
- shared code는 logical address space에서 동일한 위치에 있어야 한다.

8. Segmentation 기법의 장단점
- segment는 의미 단위로 나누기에 protection과 sharing에 효과적이지만, 그 크기가 다르기에 외부조각이 발생한다.

9. 주소 변환의 순서는??
- symbolic address -> logical address -> physical address

10. segmentation 기법은 어떤 단위로 데이터를 쪼개나요?
- 의미 단위로 쪼갭니다. 
- 의미 단위에는 함수, 스택, global 변수, symbol table & array 등이 있다.

----
## 지혜
1. 주소 변환의 순서는??

2. 내부 조각과 외부 조각을 설명하세요

3. Muti-level page table 사용 이유는?

4. segmentation 기법은 어떤 단위로 데이터를 쪼개나요?


## 정민
1. 사용자 프로세스 영역의 할당 방법은? 
    (Contiguous 2가지, NonContiguous 3가지)
    
    - Contiguous Allocation 
    : Fixed partition allocation, Variable partition allocation
    - Noncontiguous Allocation 
    : Paging, Segmentation, Paged Segmentation

2. 페이징 기법을 사용하면 메모리에 _번 접근하여야 한다. 속도를 향상 시키기 위한 방법은?  
    2번, TLB를 사용한다.
    - TLB : 주소 변환을 위한 캐시메모리(메인메모리와 CPU 사이에 존재), 메인메모리보다 접근 속도가 빠른 하드웨어로 구성

3. Shared Code 조건 2가지
    
    1) **read-only**로 세팅
    
    2. 동일한 **logical addess space**에 위치해야 함
    
4. Segmentation 기법의 장단점
    - 장점 : segment는 의미 단위이기 때문에 공유(sharing)와 보안(protection)에 있어 paging보다 훨씬 효과적임
    - 단점 : external fragmentation 발생, segment의 길이가 균일하지 않기 때문에 가변분할 방식에서와 동일한 문제점이 발생

## 예리
1. MMU의 역할과 사용하는 register에 대해 설명하시오
logical address를 physical address로 변환해주는 H/W
올라갈 메모리 시작 위치를 갖는 Relocation register와 논리적 주소의 범위인 Limit register가 있다.
이 두 register로 주소 변환을 한다.

2. 내부 조각과 외부 조각에 대해 설명하시오
내부 조각은 프로그램 크기보다 분할 크기가 커 남는 공간이고, 외부 조각은 프로그램 크기보다 분할 크기가 작아서 할당되지 못하는 공간이다.

3. Muti-level page table을 사용하게 되는 이유는?
프로그램의 주소 공간만큼 entry 생성시 낭비여서 여러 table을 두어 사용하지 않는 공간을 줄이는 것.

4. Paging과 Segment의 차이점을 설명하시오
- paging은 분할 크기가 고정돼있지만, segment는 의미 단위로 분할하기에 그 크기가 매번 다르다.
- segment는 의미 단위로 나누기에 protection과 sharing에 효과적이지만, 그 크기가 다르기에 외부조각이 발생한다. 반면, paging은 protection과 sharing에 대응하기 어렵지만, 외부 조각은 발생하지 않는다.
- paging은 entry 개수가 매우 많지만, segment는 적다. 