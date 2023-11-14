## Observer Pattern
옵저버 패턴은 객체의 상태 변화를 관찰하는 관찰자들(옵저버)의 목록을 객체에 등록하여 상태 변화가 있을때 마다 메소드 등을 통해 객체가 직접 목록의 각 옵저버에게 통지하도록 하는 디자인 패턴이다.
주로 분산 이벤트 핸들링 시스템을 구현하는 데 사용한다. 

### 어떤 객체 상태의 상태가 변화할시 그와 연관된 객체들에게 알림을 보내는 디자인 패턴

![image](https://github.com/showhohxc/LearningStudy/assets/98040028/5c920923-c8ce-4828-826f-16962ce2eb6c)
베디라는 객체는 코치이다. (코치 인터페이스를 구현해야 한다)
코치(코치 인터페이스)의 기능은 크루들을 등록한다, 크루들을 등록 해제한다, 크루들에게 행동을 알린다. 아주 간단하게 이 세가지의 기능을 가지고 있다.
### 코치는 모든 크루들에게 정보를 알려야 한다.
### 크루 인터페이스의 기능은 자신의 상태를 업데이트하는 기능을 가진다.

## Coach Interface
![image](https://github.com/showhohxc/LearningStudy/assets/98040028/c7ada712-26ce-4372-aff2-f2f7face4dce)
## Crew Interface
![image](https://github.com/showhohxc/LearningStudy/assets/98040028/4b3d6a33-9aa9-4386-b95b-8ea574fa2923)

## Baedi(Coach) Class
![image](https://github.com/showhohxc/LearningStudy/assets/98040028/43f07494-0141-4837-abab-61a8a94c19f1)
