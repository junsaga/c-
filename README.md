# c-

# 주소 형변환 후 메모리 접근 실습

##  코드 설명

정수형 변수 `n`을 메모리에서 **바이트 단위로 접근**하여 출력하는 코드입니다.  
**리틀 엔디안** 메모리 구조를 확인하기 위한 실습용 예제입니다.

## 📄 코드

```c
#include <stdio.h>

void main() {
    int n = 0x44434241;

    printf("%d %d\n", (char)&n, (char)&n);

    printf("%d %c\n", ((char)&n + 1), ((char)&n + 1));
    printf("%d %c\n", ((char)&n + 2), ((char)&n + 2));
    printf("%d %c\n", ((char)&n + 3), ((char)&n + 3));
}

'''

'''
# 실행결과
65 A
66 B
67 C
68 D
