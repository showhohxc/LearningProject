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

베디(코치)는 Crew들의 리스트를 가지고 있고, 세가지의 기능을 가지고 있다. eatFood / RunWay / Upgrade 그리고 인터페이스에 정의된 대로 3개의 함수를 구현한다.
주목할 것은 NotifyCrew 메소드를 각 기능에서 호출하는 것이다. 그리고 Crew들에게 한 명씩 업데이트 메소드를 호출한다.

### 티버(크루)는 베디(코치)의 알림을 받고 싶어서 구독을 하고 싶어한다.
![image](https://github.com/showhohxc/LearningStudy/assets/98040028/8521348f-d56d-491f-ac9d-28f6098ed204)

### 다른 Crew의 멤버 르윈 / 제이도 마찬가지이다. 
![image](https://github.com/showhohxc/LearningStudy/assets/98040028/053edc05-9b61-40e9-98ab-4a1963ace50b)

## For Example

## Main Method
![image](https://github.com/showhohxc/LearningStudy/assets/98040028/1017f2a4-7b9f-415c-ba5e-d1a647b86359)

Coach인 베디에게 3명의 Crew들이 구독을 하였다. 그리고 Upgrade() 메소드를 호출한다. 그렇게 되면 구독한 3명의 크루객체들에게 메시지가 전달된다.
```
베디코치가 귀여움을 강화했다
Lewin 수신 : 나 더 귀여워 졌따
Tiber 수신 : 나 더 귀여워 졌따
Jay 수신 : 나 더 귀여워 졌따
```

이에 Lewin은 구독을 해지한다.

```
baedi.unsubscribe(lewin);
baedi.eatFood();

베디코치가 밥을 먹는다
Tiber 수신 : 나 밥 먹었따
Jay 수신 : 나 밥 먹었따
```

Lewin은 알림 대상에서 제외되고
이로써 객체의 상태가 변화할때 연관된 객체들에게 알림을 보낼수 있게 된다. 이것이 Observer Pattern 이다.
Crew Interface == Observer Interface
Coach Interface == Observable Interface
Observable은 발행자가 되고 Observer는 구독자가 된다.

![image](https://github.com/showhohxc/LearningStudy/assets/98040028/dab3306e-f828-48bf-b7bc-c325a1acdf1f)

