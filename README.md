# 오픈 소스sw 과제 20223101 위영림 
![KakaoTalk_20220604_015252015](https://user-images.githubusercontent.com/106826654/171910374-c0f0a973-43c0-4367-a682-c19f08c1640e.jpg)
<img src=“” width=“640” height=“480”>

## 1. 리눅스 명령어 : top, ps, jobs, kill 명령어 조사하기
### 1) top
 : 실시간으로 프로세스 정보를 확인할 수 있는 명령어이다. q를 눌러 작동을 멈출 수 있다. ps와 달리 지속적인 모니터링 기능(작업관리자와 유사)
실행 상태에서 다양한 명령을 입력하여 프로세스 상태를 출력하거나 제어가 가능하다.
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

*ps와 top의 차이점*
: ps는 ps한 시점에 proc에서 검색한 cpu 사용량
top은 proc에서 일정 주기로 합산해 cpu 사용율 출력

### 2) ps 
: process status의 약자, ps 명령의 옵션 따라 자세한 프로세스 정보를 확인할 수 있다. grep과 결합을 하면 특정 프로세스를 보여줄 수 있다.
|내용|설명|
|---|---|
|-A, -e | 시스템상의 모든 프로세스에 대한 정보 출력|
|a | 다른 사용자의 프로세서도 출력|
|-a | 세션 리더 빼고 출력|
|-u | 사용자의 프로세스 출력|
|-l , -f | 전체 목록 출력|

### 3) jobs
 : 작업이 중지된 상태나 백그라운드로 진행 중인 상태를 표시한다. 
- j : job 중심 형태
### 4) kill 
: 프로세스에 종료 시그널을 보낸다. (-9는 강제 종료)

## 2. vim 에디터에서 매크로 사용 방법에 대하여 조사하기 (q , @)
### 1) 매크로 기록
커맨드 모드 (esc 누른 상태)  
매크로를 사용하려면 커맨드 모드에서 @+a~z 를 입력
q 를 누르고 a ~ z 사이 문자 입력하면 매크로 recording 시작한다. 커맨드 모드로 돌아와서 q를 누르면 recording 종료

### 2) 매크로 재생
중립모드에서 @a 라고 누르면 매크로 a가 재생
@a  1회 실행 
@@ 방금 실행한 매크로 실행
10@a 매크로 10회 실행

### 3) 매크로 파일 저장
 ~/.vimrc 파일을 연다.
매크로 이름을 h라고 짓고 싶으면
 let @h= ‘ 까지 친 다음에 insert 모드에서 Ctrl-R Ctrl-R h를 누르면 매크로 h의 내용이 입력 된다.

[Linux](https://zzsza.github.io/development/2018/07/18/linux-top/)
[Linux](https://yurmu.tistory.com/12)
[Linux](https://imjeongwoo.tistory.com/71)
[vim](https://forcecore.tistory.com/1255)
[vim](https://booolean.tistory.com/849)

 



