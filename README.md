# c-

# 주소 형변환 후 메모리 접근 실습

##  코드 설명

정수형 변수 n을 메모리에서 **바이트 단위로 접근**하여 출력하는 코드입니다.  
**리틀 엔디안** 메모리 구조를 확인하기 위한 실습용 예제입니다.

## 📄 코드
```
c
#include <stdio.h>

void main() {
    int n = 0x44434241;

    printf("%d %d\n", (char)&n, (char)&n);

    printf("%d %c\n", ((char)&n + 1), ((char)&n + 1));
    printf("%d %c\n", ((char)&n + 2), ((char)&n + 2));
    printf("%d %c\n", ((char)&n + 3), ((char)&n + 3));
}
```
```
첫 줄: (char)&n → 0x41 → 65 ('A')

두 번째 줄: ((char)&n + 1) → 0x42 → 66 ('B')

세 번째 줄: ((char)&n + 2) → 0x43 → 67 ('C')

네 번째 줄: ((char)&n + 3) → 0x44 → 68 ('D')
```

```
결론
메모리 위치	코드 예시	출력 값
12ff7c	((char)&n)	65 A
12ff7d	((char)&n + 1)	66 B
12ff7e	((char)&n + 2)	67 C
12ff7f	((char)&n + 3)	68 D
```

```
# 실행결과
65 A
66 B
67 C
