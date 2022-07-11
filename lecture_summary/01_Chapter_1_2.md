# Chapter 1-2
## Introduction & O/S Structures

### 운영체제, 컴퓨터, 정보
* 운영체제란?
  - An operating system is a __software that operates a computer system__
  - HW 상에서 SW 가 돌아 가도록 자원을 관리 역할 
  - 항상 컴퓨터에서 실행되고 있는 프로그램
  - application program 이 동작하기 위해 필요
  - __process__, resource, user interfaces 등을 관리하는 프로그램
  - 예) 리눅스, 윈도우, Mac OS
  - a software that manages a computer's hardware
  - It also provides a basis for application programs and acts as an intermediary between the computer user and the computer hardware.
  - `KERNEL` 이라고도 불림

* 컴퓨터란?  
  - A computer is a mahcine that processes the __INFORMATION__  

* 정보란?
  - An information is can be defined as a __quantitative representation that measures the uncertainty__
  - $I(x) = -\log_{2}{P(x)}$ called `bit(binary digit)`
  - `놀람의 정도` - 해당 사건의 확률이 낮을수록, 더 많은 정보량을 나타냄 
    - 잘 일어나지 않은 사건의 정보는 자주 발생할만한 사건보다 정보량이 많다는 것을 의미
  - 예1. 사건 X가 일어날 확률이 1/32 라 했을때 해당 사건의 정보량은?
    - $I(x) = -\log_{2}{1/32} = 5$ 즉 5bit 의 정보량이 있음
  - Shannon entropy : 모든 사건의 정보량의 기대값
    $$ H(X) = -\sum_{i=1}^{n} P(x_{i})log_{2}{P(x_{i})} $$  
    $$ H(X) = -E_{X\~P}{I(X)} = -E_{X\~P}{log{P(X)}} $$

* 컴퓨터의 정보 처리 방법
  - 정보의 최소 단위 : bit
  - 정보의 처리 : 정보의 상태 변환 (0->1, 1->0)
  - 부울 대수 (Boolean Algebra) : NOT, AND, OR
  - 논리 게이트 : NOT, AND, OR, XOR, NAND, NOR
  - 논리 회로
  - 데이터의 저장과 전송 : 플립-플롭, 데이터 버스

* 컴퓨터의 특징
  - 범용성(universality)
    - NOT, AND, OR 게이트 만으로 모든 계산 가능
    - NAND 게이트 만으로 모든 계산을 할 수 있다.
    
  - 계산가능성(computability)
    - Turing-computable : 튜링 머신으로 계산가능한 것
    - Halting Problem(정지 문제) : 튜링 머신으로 풀 수 없는 문제
    

### 컴퓨터의 할아버지 & 컴퓨터의 아버지 
* 컴퓨터의 할아버지 
  - Alan Turing - Turing Machine
![Turing Machine](../images/01_1.png)
![Turing Machine](https://github.com/philhoonoh/os/blob/main/images/01_1.png)


* 컴퓨터의 아버지 
  - John von Neumann 
    - stored-program 
      - a computer that stores programs in a memory
      - RAM과 CPU
    - Instruction Set Architecture
      - program is a set of instructions
      - Instruction으로 하드웨어를 구동
    - 작동 방법
      - 먼저 메모리에서 명령어들을 읽기
      - 명령어들을 IR(Insturction Register)에 저장
      - 피연산들을 메모리에서 읽기 
      - internal register에 저장 
      - 연산 실행
      - 연산 실행후 메모리에 결과 값 저장

### 운영체제, 컴퓨터 구조, bootstrap, interrupts, stoarge
* 운영체제도 프로그램
  - 항상 컴퓨터에서 실행되는 프로그램
  - application program 이 동작하기 위해 필요
  - process, resource, user interfaces 등을 관리하는 프로그램  
  
* 컴퓨터 시스템의 구조
  - Hardware
  - Operating System
  - Application Program
  - User  
  
![Components of Computer System](../images/01_2.png)

* __bootstrap__ program
  - 컴퓨터가 시작할때 실행되는 프로그램으로써 OS를 실행시키기 위한 프로그램
  - ROM 에 저장되어 있음

* __Interrupts__
  - I/O device 등에서 CPU 에 신호를 보내는 작업 

* starge (용량, 속도 순)
  * register
  * cache
  * main memory(RAM)
  * solid-state disk
  * hard disk
  * optical disk
  * magnetic tapes

* OS의 대부분은 I/O를 관리하는데 사용

### CPU(Processor), Core, Thread
* Definitions of Computer System Components   
  - CPU : The hardware that executes instructions.  
  - Processor : A physical chip that contains one or more CPUs.
  - Core : The back computation unit of the CPU.
  - Multicore - Including multiple computing cores on the same CPU
  - Multiprocessor - Including multiple processors.
  
  - 프로세서 - CPU라고도 불림 
    - 프로세서가 여러개 -> Multiprocessor 
  - 코어 - CPU에 있는 작업 연산 단위
    - 듀얼 코어, 4코어, 8코어 -> Multicore
  - 쓰레드 - 실제 프로세스의 연산 단위
    - 2코어 4 쓰레드, 4코어 8 쓰레드 등

* Symmetric multiprocessing (SMP)
  * The most common multiprocessor systems,
    * in which each peer CPU processor performs all tasks.
    
![SMP](../images/01_3.png)
    
* Multi-core design
  * with several cores on the same processor chip.
  
![Multi-core design](../images/01_4.png)

### Multi- 정리
* Multi-processing
  - 여기서 말하는 __processing__ 은 __processor__ 를 뜻하는 것임  
  - 다수의 프로세서가 협력적으로 작업을 동시에 처리하는 것
  - 각각의 프로세서가 다수의 작업을 처리
  - 하나의 프로세서가 고장이 났을때 해당 작업은 정지되지 않음

* Multi-programming
  - 여러 개의 프로그램을 동시에 실행하는 것
  - 낭비되는 시간동안 다른 프로세스를 수행하는 것
  - 예를 들어 프로그램 실행 도중 I/O interrupt가 발생하면, 해당 프로세스는 응답을 대기하고, 그 사이 다른 프로세스를 실행하여 CPU 활용을 늘리는 것
  * runs more than one program at a time
  * keeps several processes in memory simultaneously
  * __to increase CPU utilization__

* Multi-tasking
  - multi-programming의 확장 개념
  - 다수의 task(process)를 스케줄링에 의해 번갈아 수행하는 것으로써 사용자가 동시에 여러 Task를 수행할 수 있게 해줌
  - multi-programming 과의 다른 점은 Multi-programming CPU 활용을 늘리다는점
  - Multi-tasking 은 스케줄러에 의해 정해진 시간동안 번갈아 가면서 Task를 처리한다는 점입니다.
  * a logical extension of multiprogramming.
    - in which CPU switches jobs so frequently that users can interact with each job while it is running
  * __CPU scheduling__
    - If several processes are ready to run at the same time, the system must choose which process will run next

* Multi-threading
  - 하나의 작업(하나의 process) 를 여러 쓰레드로 병렬처리
    - 메모리를 공유함으로써 context-switching 같은 오베해드를 줄임, 효율성
    - 하나의 쓰레드가 실패하면, 프로세스가 종료
    - 동기화 문제
  - Multi-processing 은 여러개의 processor들로 여러 작업을 병렬 처리
    - 하나의 processor가 실패해도 다른 processor가 작업을 실행, 안정성
  
### OS operations, Virtualization, Computing Environments
* OS operations
  - 2가지 존재
    - user mode
    - kernel mode
  - kernel mode 에서만 HW을 제어하도록 함으로써 시스템의 보안을 증대

* Virtualization
  - 가상화
  - 하나의 machine에서 다양한 OS 를 제공함
![Virtualization](../images/01_5.png)

* Computing Environments
  - Traditional Computing
  - Mobile Computing : Android
  - Client-Server Computing
  - Peer-to-Peer Computing : Torrent
  - Cloud Computing : AWS, Azure, GCP
  - Real-Time Embedded Systems : Raspberry pi

### Operating System Services, User and Operating-System Interface, System Calls
* Operating System Services
  - OS provides an environment for the execution of programs
  - User interface
  - __Program execution__
  - I/O operation
  - File-system manipulation 
  - Communications
  - Error detection
  - Resource allocation
  - Logging
  - Protection and security 

![Operating System Services](../images/01_6.png)

* Operating-System Interface
  - Three fundamental ways for users to interface with the OS
    - CLI: command line interface, or command interpreter
      - knownasshells:sh,bash,csh,tcsh,zsh,etc. 
    - GUI: graphical user interface
      - Windows, Aqua for MacOS, KDE/GNOME for Linux, etc. 
    - Touch-Screen Interface
      - Android UI, iPhone UI, etc.

* System Calls
  - 응용프로그램들과 OS하고 의사소통하는 방법
  - OS의 API = System Call
  - API 라고 불리기도 했음 (현재는 API 정의가 확장됨)
  - 라이브러리들로 정의 되어있음
    - 예) standard C library 로 system call interface 호출
  - provide an interface to the services made available by the OS.
  - API: Application Programming Interface
![System Calls](../images/01_7.png)

