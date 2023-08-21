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
