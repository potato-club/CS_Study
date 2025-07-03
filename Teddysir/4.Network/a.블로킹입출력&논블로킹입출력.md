# 💻 Blocking I/O & Non-Blocking I/O

> I/O 작업은 커널레벨? 에서만 수행 가능, 따라서 프로세스, 스레드는 커널에게 I/O를 요청해야한다.


---


## 1. ✅ Blocking I/O

- I/O 블로킹 형태의 작업은
    - Process(Thread)가 Kernel에게 I/O를 요청하는 함수를 호출
    - Kernel이 작업을 완료하면 작업 결과를 반환 받음.
- 특징
  - I/O 작업이 진행되는 동안 user Process(Thread)는 자신의 작업을 중단한 채 대기
  - Resource 낭비가 심하다. -> I/O 작업이 CPU 자원을 거의 쓰지 않으므로

> 여러 Client가 접속하는 서버를 블로킹 방식으로 구현하는 경우
- I/O 작업을 진행하는 작업을 중지 -> 다른 Client가 진행죽인 작업을 중지하면 안되므로, client 별로 별도의 Thread를 생성해야함 -> 접속자 수 매우 많아짐
- 이로 인해 많아진 스레드로 컨텍스트 스위칭 횟수 증가 -> 비효율적



## 2. ✅  Non-Blocking I/O
> I/O 작업이 진행되는 동안 User Process의 작업을 중단하지 않음.
- 진행 순서
  - User Process가 recvfrom 함수 호출
  - Kernel은 이 요청에 대해 곧바로 recvBuffer를 채워서 보내지 못하므로  -?
  - Blocking 방식과 달리, User Process는 다른 작업을 진행할 수 있다.
  - recvBuffer에 user가 받을 수 있는 데이터가 있는 경우, Buffer로부터 데이터를 복사하여 받아옴
    - 이때, recvBuffer는 Kenrnel이 가지고 있는 메모리에 적재되어 있으므로, 메모리간 복사로 인해, I/O 보다 훨씬 빠른 속도로 data를받아올 수 있음
  - recvfrom 함수는 빠른 속도로 data를 복사한 후, 복사한 data의 길이와 함께 반환함



---

# 🤔 중요 내용 요약 복습

### 1. 블로킹 I/O는 Spring 의 MVC 방식, 논블로킹 I/O는 Webflux 방식

