# Chapter 1-2
## Introduction & O/S Structures

* 운영체제란?
  - An operating system is a __software that operates a computer system__
  - HW 상에서 SW 가 돌아 가도록 자원을 관리 역할 
        
* 컴퓨터란?  
  - A computer is a mahcine that processes the __INFORMATION__  

* 정보란?
  - An information is can be defined as a __quantitative representation that measures the uncertainty__
  - $I(x) = -\log_{2}{P(x)}$ called `bit(binary digit)`
  - `놀람의 정도` - 해당 사건의 확률이 낮을수록, 더 많은 정보량을 나타냄 
    - 잘 일어나지 않은 사건의 정보는 자주 발생할만한 사건보다 정보량이 많다는 것을 의미
  - 예1. 알파벳을 표시하기 위한 정보량은?
    - 알파벳은 총 26글자 이므로 $I(x) = -\log_{2}{26} < 5$ 즉 약 5bit 로 표현 가능
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
    
* 컴퓨터의 할아버지 
  - Alan Turing - Turing Machine

* 컴퓨터의 아버지 
  - John von Neumann - ISA (Instruction Set Architecture)