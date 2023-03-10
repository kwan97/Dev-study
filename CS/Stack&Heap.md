# [CS] 메모리 구조별 파악

## <strong># 메모리 구조</strong>

    프로그램이 실행되기 위해서는 먼저 프로그램이 메모리에 로드(load)되어야 한다.
    또한, 프로그램에서 사용되는 변수들을 저장할 메모리도 필요하다.

- ### <strong> 프로그램이 운영체제로부터 할당받는 대표적인 4가지 메모리 공간</strong>

  - 코드(code) 영역

  - 데이터(data) 영역

  - 스택(stack) 영역

  - 힙(heap) 영역

<br>

> <strong><필요한 사전 지식></strong>
> <br>  
> <strong>*컴파일 타임:</strong> 프로그램을 생성하기 위해 개발자가 소스코드를 작성하고 컴파일이라는 과정을 통해 기계어코드로 변환 되어 실행 가능한 프로그램이 되며, 이러한 편집 과정을 컴파일타임(Compiletime)이라 한다.  
> <br>
> <strong>*런타임: </strong>컴파일과정을 마친 프로그램은 사용자에 의해 실행되어 지며, 이러한 응용프로그램이 동작되어지는 때를 런타임(Runtime)이라 한다.

<br>

### <strong>\*코드 영역(텍스트 영역)</strong>

    - 실행할 프로그램의 코드가 저장되는 영역이다.

    - CPU는 코드 영역에 저장된 명령어를 하나씩 가져가서 처리해준다.

    - 프로그램이 시작하고 종료될 때 까지 메모리에 계속 남아있는다.

<br>

### <strong>\*데이터 영역(정적메모리)</strong>

    - 프로그램의 전역변수와 정적(static)변수가 저장되는 영역이다.

    - 프로그램 시작과 동시에 메모리를 할당 받게 되고, 프로그램이 종료되면 소멸된다.

<br>

### <strong>\*스택 영역(자동 메모리)</strong>

    - 프로그램이 자동으로 사용하는 임시 메모리 영역이다.

    - 스택 영역은 함수의 호출과 관계되는 지역 변수/ 매개 변수가 저장되는 영역이다.

    - 함수의 호출과 함께 메모리가 할당되며, 해당 객체가 정의된 스코프를 벗어날 때 소멸한다.

    - 힙보다 빠르다.

    - 함수의 호출하는 위치도 저장한다.(스택 프레임)

```java
void fct1(int);
void fct2(int);

int a = 10; //데이터 영역에 할당
int b = 20; //데이터 영역에 할당

int main() {
    int i = 100; //지역 변수 i가 스택영역에 할당

}
void fct1(int c) {
    int d = 30; //매개변수 c와 지역변수 d가 스택영역에 할당
}
```

<br>

### <strong>\*힙 영역(자유 저장소)</strong>

    - 힙 영역은 프로그래머가 직접 공간을 할당, 해제하는 메모리 영역이다.

    - 선입선출(FIFO)의 방식으로, 가장 먼저 들어온 데이터가 가장 먼저 인출된다.

    - 힙 영역은 메모리의 낮은 주소에서 높은 주소의 방향으로 할당된다.

<br>

## <strong># 오버플로우(OVERFLOW)</strong>

    한정된 메모리 공간이 부족하여 메모리 안에 있는 데이터가 넘쳐 흐르는 현상

- ### 힙 오버플로우: 힙이 스택 영역에 침범하는 경우
- ### 스택 오버플로우: 스택이 힙 영역에 침범하는 경우
