## Heap Stack 에 대한 기본 메모리 구조
어떠한 프로그램 구동시 운영체제는 실행한 프로그램을 위한 메모리 공간을 할당 하게 된다. 
이때 할당되는 메모리 공간은 Stack / Heap / Data 의 영역으로 나누어지게 된다.
할당되는 장소는 RAM 에 해당하며, 할당되는 용도는 프로그램 실행시 필요한 메모리 공간을 지정하기 위해 할당된다.

![img1 daumcdn](https://img1.daumcdn.net/thumb/R1280x0/?code=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FbdhYIH%2FbtrE7wTmnC5%2FgTJ1JohuTRklTJHdMdeqLk%2Fimg.png).

### Data Area
int 형 변수 m_nData_1, m_nData_2는 프로그램 구동시 int형 함수 main에 호출되기 전에 데이터 영역에 할당되게 된다.
프로그램 종료 될때 까지 메모리 상에 존재하게 된다. 이것이 전역 변수가 프로그램이 종료될때까지 존재하는 이유이다.
ex)
int m_nData_1 = 0;  // 데이터 영역에 할당
int m_nData_2 = 1;  // 데이터 영역에 할당

![img1 daumcdn](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2Flcew1%2FbtrFdGBx4JL%2FKHb1rB2FUkkRxD3tceqgIK%2Fimg.png)

### Stack Area
스택 영역에 저장되는 변수는 함수 호출시에 생성이 되며, 함수 호출이 완료되면 사라지게 됩니다. 변수 m_nData_1, m_nData_2는 데이터 영역에 저장되며 
main 메서드안에 존재하는 int nNum, void ProcMethod_1 메서드 안에 있는변수nIndex_1, nNum1 그리고 void ProcMethod_2 메서드 안에 존재하는 변수 nIndex_2, nNum2가 
스택영역에 저장된다. 스택이라는 이름과 같이 데이터를 건초더미처럼 쌓아 올려놓는 역할을 하게 됩니다.

ex)
```
int m_nData_1 = 0;  // 데이터 영역에 할당
int m_nData_2 = 1;  // 데이터 영역에 할당

int main() 
{
    int nNum = 3;    // 지역변수 nNum이 스택 영역에 할당
    
    ProcMethod_1(nNum);
    ProcMethod_2(nNum);
}

void ProcMethod_1(int nIndex_1)
{
    int nNum1 = 4;    // 매개변수 nIndex_1과 지역변수 nNum1가 스택영역에 할당
}

void ProcMethod_2(int nIndex_2)
{
    int nNum2 = 5;    // 매개변수 nIndex_2과 지역변수 nNum2가 스택영역에 할당
}
```

![img1 daumcdn](https://img1.daumcdn.net/thumb/R1280x0/?scode=mtistory2&fname=https%3A%2F%2Fblog.kakaocdn.net%2Fdn%2FJPav8%2FbtrFe3DehqQ%2FW9aJ0OsOkSYI7VArJkZRgK%2Fimg.png)

### Heap Area
*힙 영역은 프로그래머가 할당
보통 배열을 선언시 상수로 선언을 하는데, 스택 영역에 할당될 메모리의 크기는 컴파일 타임에 결정된다.
정상적인 배열 선언이라면 nArr배열의 크기가 40 byte 라는것을 확인할수 있는데, 배열의 값을 동적으로 처리시 메모리의 값을 알수없다.
JAVA에서는 가비지 컬렉터를 통해서 자동으로 관리되는 영역인데, 
가비지 컬렉터가 없으면 프로그래머가 직접 관리(할당/해제)해줘야 합니다. 보통 스택보다 큰 메모리를 할당받기 위해서 사용합니다.
```
int main()
{
    int nArr[10]       // 정상 배열선언

    // 비정상 배열선언
    int nNum = 0;
    scanf("%d", &nNum);
    int nArr[nNum];
}
```

## 정리
```
-Data Area
 - 프로그램이 종료될 때까지 지워지지 않을 데이터 저장.
 - 대표적으로 전역 변수와 static 변수
 - 상수도 저장

-Stack Area
 - 잠깐 사용하고 삭제하는 데이터 저장(지역변수, 매개변수) 
 - 해당 객체가 정의된 블록(스코프)을 벗어날 때 소멸
 - 함수의 호출하는 위치도 저장.
 - 힙보다 빠름
-Heap Area
 - 가비지 컬렉터가 없으면 프로그래머가 직접 관리(할당/해제)해줘야 함.
 - 스택보다 큰 메모리를 할당받기 위해 사용
 - 동적 메모리 할당 ( new /포인터 )
 - delete를 사용하여 해당 객체 메모리 반환
 - 스택보다 느림
```
    
