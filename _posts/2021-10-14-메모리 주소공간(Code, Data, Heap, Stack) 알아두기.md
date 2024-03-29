---
title:  "메모리 주소공간(Code, Data, Heap, Stack) 알아두기"
date:   2021-10-14 23:30:51 -0700
---



값 타입과 참조 타입을 공부하다 흘러흘러 메모리 주소공간에 대해 복습하고자 글을 쓰게 되었습니다. 이번 글에서는 메모리 주소공간이 무엇인지, 세부 영역은 무엇이 있는지, 그리고 세부영역인 stack, heap이 차이가 무엇인지 간단히 적어보았습니다. 

## 메모리 주소공간은 무엇인가?

주소란 **메모리의 특정 위치**를 말합니다. 

프로그램이 실행되면 운영체제는 프로세스 주소 공간(Process Address Space)을 메모리에 할당해주게 됩니다. 이때 할당해주는 메모리공간은 **Code, Data, Stack, Heap** 으로 나뉩니다. 

![memory_structure](http://www.tcpschool.com/lectures/img_c_memory_structure.png)



## Code, Data, Stack, Heap

그럼 영역별로 하나씩 살펴보겠습니다. 

### Code

해당 프로세스의 기계어 코드를 담고 있습니다. **컴파일 시**에 영역의 크기가 결정됩니다. 

### Data

전역변수, static 변수, 정적 배열, 정적 구조체 등 프로그램이 사용하는 자료구조를 담고 있습니다. 마찬가지로 **컴파일 시** 크기가 결정됩니다. 

### Stack

지역변수, 매개변수, 리턴값과 같은 값이 담기는 영역입니다. 함수가 호출될 때 호출된 함수의 수행을 마치고 복귀할 주소 및 데이터를 임시로 저장할 때 사용되는 공간입니다. 마찬가지로 **컴파일 시** 크기가 결정됩니다.

### Heap

New, malloc 등을 활용한 동적할당객체에 대한 영역입니다. code, data, stack과 달리 **런타임 시** 크기가 결정됩니다. 사용한 후에는 메모리 해제를 반드시 해주어야 합니다. 그렇지 않으면 메모리 누수가 발생하게 됩니다. Code, Data, Stack 중 유일하게 **런타임 시에 결정**되기 때문에 데이터의 크기가 확실하지 않을 때 사용합니다. 



> **Stack, Heap 비교**
>
> 스택과 힙은 사실 같은 메모리 영역을 공유하고 있습니다. 그러나 **힙은 낮은 메모리 주소부터 할당**받고, **스택 영역은 높은 메모리 주소부터 할당** 받게 된다는 특징이 있습니다. 위에 올렸던 그림이 이를 잘 나타내주어 가지고 왔습니다.  

