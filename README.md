# 오픈 소스sw 과제 20223101 위영림 
![너무 예쁜 나](https://user-images.githubusercontent.com/106826654/171910374-c0f0a973-43c0-4367-a682-c19f08c1640e.jpg)
<img src=“https://user-images.githubusercontent.com/106826654/171910374-c0f0a973-43c0-4367-a682-c19f08c1640e.jpg” width=“25” height=“25”>

## 1. 리눅스 명령어 : top, ps, jobs, kill 명령어 조사하기
### 1) top
 : 실시간으로 프로세스 정보를 확인할 수 있는 명령어이다. q를 눌러 작동을 멈출 수 있다. ps와 달리 지속적인 모니터링 기능(작업관리자와 유사)
실행 상태에서 다양한 명령을 입력하여 프로세스 상태를 출력하거나 제어가 가능하다.
```c
root@LAPTOP-3VL7OQGV:~# top
top - 02:30:58 up  3:03,  0 users,  load average: 0.00, 0.00, 0.00
Tasks:  10 total,   1 running,   9 sleeping,   0 stopped,   0 zombie
%Cpu(s):  0.0 us,  0.0 sy,  0.0 ni,100.0 id,  0.0 wa,  0.0 hi,  0.0 si,  0.0 st
MiB Mem :   3830.5 total,   2172.6 free,    656.4 used,   1001.5 buff/cache
MiB Swap:   1024.0 total,   1024.0 free,      0.0 used.   2600.1 avail Mem

  PID USER      PR  NI    VIRT    RES    SHR S  %CPU  %MEM     TIME+ COMMAND
    1 root      20   0    1756   1080   1016 S   0.0   0.0   0:00.09 init
   23 root      20   0    1752     68      0 S   0.0   0.0   0:00.00 init
   24 root      20   0    1752     76      0 S   0.0   0.0   0:00.04 init
   25 root      20   0 1606428  32616  13368 S   0.0   0.8   0:00.99 docker-desktop-
   37 root      20   0    1752     76      0 S   0.0   0.0   0:00.00 init
   38 root      20   0  764528  47708  30916 S   0.0   1.2   0:02.60 docker
  200 root      20   0    1756     80      0 S   0.0   0.0   0:00.00 init
  201 root      20   0    1756     80      0 S   0.0   0.0   0:00.02 init
  202 root      20   0   10044   4964   3304 S   0.0   0.1   0:00.15 bash
  217 root      20   0   10872   3700   3188 R   0.0   0.1   0:00.09 top
``` 
ps와 top의 차이점
: ps는 ps한 시점에 proc에서 검색한 cpu 사용량을 출력하고 top은 proc에서 일정 주기로 합산해 cpu 사용율 출력
*top 실행 후 명령어*
|내용|설명|
|---|---|
|shift + p | CPU 사용률 내림차순|
|shit + m | 메모리 사용률 내림차순|
|shift + t | 프로세스가 돌아가고 있는 시간 순|
|k | kill. k 입력 후 PID 번호 작성. signal은 9|
|f | sort field 선택 화면 -> q 누르면 RES순으로 정렬|
|a | 메모리 사용량에 따라 정렬|
|b | Batch 모드로 작동|
|1 | CPU Core별로 사용량 보여줌|

### 2) ps 
: process status의 약자, ps 명령의 옵션 따라 자세한 프로세스 정보를 확인할 수 있다. grep과 결합을 하면 특정 프로세스를 보여줄 수 있다.
|내용|설명|
|---|---|
|-A, -e | 시스템상의 모든 프로세스에 대한 정보 출력|
|a | 다른 사용자의 프로세서도 출력|
|-a | 세션 리더 빼고 출력|
|-u | 사용자의 프로세스 출력|
|-l , -f | 전체 목록 출력|

**ps와 top의 차이점**
: ps는 ps한 시점에 proc에서 검색한 cpu 사용량을 출력하고 top은 proc에서 일정 주기로 합산해 cpu 사용율 출력 

### 3) jobs
: 작업이 중지된 상태나 백그라운드로 진행 중인 상태를 표시한다. 

|상태|설명|
|---|---|
|Running|작업이 계속 진행중임|
|Done|작업이 완료되어 0을 반환|
|Done(code)|작업이 종료되었으며 0이 아닌 코드를 반환|
|Stopped|작업이 일시 중단|
|Stopped(SIGTSTP)|SIGTSTP 시그널이 작업을 일시 중단|
|Stopped (SIGSTOP)|SIGSTOP 시그널이 작업을 일시 중단|
|Stopped (SIGTTIN)| SIGTTIN 시그널이 작업을 일시 중단|
|Stopped (SIGSTTOU)| SIGSTTOU 시그널이 작업을 일시 중단|

### 4) kill 
: 프로세스에 종료 시그널을 보낸다. 
```
kill -9 <name>  => 강제 종료
```
[Linux](https://zzsza.github.io/development/2018/07/18/linux-top/)
[Linux](https://yurmu.tistory.com/12)
[Linux](https://imjeongwoo.tistory.com/71)

***

## 2. vim 에디터에서 매크로 사용 방법에 대하여 조사하기 (q , @)
+ q를 누른 후 a~z를 누르고 매크로 저장할 알파벳 선정
+ 매크로로 등록할 행동을 한다
+ 마지막에 q를 눌러 등록 종료
```
@a  1회 실행 
@@ 방금 실행한 매크로 실행
10@a 매크로 10회 실행
```
[vim](https://forcecore.tistory.com/1255)
[vim](https://booolean.tistory.com/849)
[vim](https://dongjumoon.tistory.com/3)
***
 



