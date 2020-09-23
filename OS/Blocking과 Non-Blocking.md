## Blocking과 Non-blocking

> Blocking/Non-Blocking의 관심사는 "호출된 함수가 바로 제어권을 넘겨 주느냐"이다.

#### Blocking I/O

- 호출된 함수가 자신의 작업을 모두 끝낼때까지 제어권을 가지고 있어 호출한 함수가 대기하도록 만든다.



#### NonBlocking I/O

- 호출된 함수가 바로 return 해서 호출한 함수에게 제어권을 주어 다른 일을 할 수 있게 한다.
- 호출되는 함수가 바로 리턴하느냐 마느냐가 중점이다.



NonBlocking & Sync와 Blocking & Async에 대해 알아보도록 하자.

- NonBlocking & Sync
  - NonBlocking은 바로 return을 해서 **제어권을 준다**고 했고, Sync 작업 완료 여부를 **호출한** 쪽에서 신경 쓴다. 그림을 보면 호출하고 바로 반환이 되어 다른 일을 수행한다.
  - 이후에 작업이 완료되었는지 계속 물어보는 일을 추가로 수행하는 것이 NonBlocking & Sync이다.
  - 즉, NonBlocking이 제어권을 바로 return 해주면 Sync는 제어권을 받아서 작업 완료 여부를 호출한 쪽에서 계속 물어보며 추가로 일을 수행하게 되는 것이다.
- Blocking & Async
  - Blocking은 작업이 완료될 때까지 제어권을 호출된 쪽에서 가지고 있고, Async는 작업의 완료 여부를 호출된 쪽에서 신경 쓴다. 
  - 어차피 제어권이 없는 상태에서 결과만 기다리는 Blocking & Sync와 차이가 없다. 이 방식은 특별한 장점이 없어서 일부로 사용할 필요는 없다.
  - 보통 NonBlocking & Async 방식을 쓰는 데 그 과정 중 하나라도 Blocking이 포함되면 의도치 않게 Blocking & Async로 작동한다고 한다. 
