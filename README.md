# 주소 형변환 후 메모리 접근 실습

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
✅ 실행 결과
css
코드 복사
65 A
66 B
67 C
68 D
📊 메모리 해석
메모리 주소	접근 코드	출력 값
12ff7c	(char)&n	65 A
12ff7d	(char)&n + 1	66 B
12ff7e	(char)&n + 2	67 C
12ff7f	(char)&n + 3	68 D
