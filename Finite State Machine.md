# Finite State Machine (유한 상태 머신)
## Whate is FSM ???

기계들은 한 번에 한 개의 상태만을 가지게 되며, 현재 상태 (Current State)란 임의의 주어진 시간의 상태를 칭한다. 
이러한 기계는 EVENT 에 의해 한 상태에서 다른 상태로 변화 할수 있으며 이를 Transition 라 칭한다. 사용하는 이유? '안전성' 협업시 멀티스레딩 / 멀티프로세싱 환경일 때에는 변소 오염의 문제가 더욱 심각한것을 방지하고 결함일 일어날 경우의 수를 낮춘다.

![fsm](https://github.com/showhohxc/LearningStudy/assets/98040028/116503b7-1478-4202-afaa-3677316e5584)

- 초기상태 가르키기(Target)은 어떤 상태로 처음에 Target에 가야함을 나타낸다.
- Transition은 내가 Targeting 이 끝나면 다음 상태 행동으로 넘어가는것

어려운 로직을 좀 더 편하게 직관적으로 표현하는 도구 이정표
