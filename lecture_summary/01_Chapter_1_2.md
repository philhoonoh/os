# Chapter 1-2
## Introduction & O/S Structures

* 운영체제란?
  - An operating system is a __software that operates a computer system__
  - HW 상에서 SW 가 돌아 가도록 자원을 관리 역할 
        
* 컴퓨터란?  
  - A computer is a mahcine that processes the __INFORMATION__  

* 정보란?
  - An information is can be defined as a __quantitative representation that measures the uncertainty__
  - $I(x) = -\log_{2}{P(x)}$ called BIT
  - `놀람의 정도` - 해당 사건의 확률이 낮을수록, 더 많은 정보량을 나타냄 
    - 잘 일어나지 않은 사건의 정보는 자주 발생할만한 사건보다 정보량이 많다는 것을 의미
  - 예1. 알파벳을 표시하기 위한 정보량은?
    - 알파벳은 총 26글자 이므로 $I(x) = -\log_{2}{26} < 5$ 즉 약 5bit 로 표현 가능
  - Shannon entropy
    - $ H(X) = -\sum_{n}^{i=1}P(x_{i})log_{2}{P(x_{i})} $
    - $ H(X) = -E_{X~P}{I(X)} = -E_{X~P}{log{P(X)}} $