---
layout: post
title: network(네트워크) 1주차 
date: 2020-09-04 16:38:23 +0900
category: network
tag: ['network', '네트워크', 'hosts', 'access network', 'physical media', 'packet switching']
---

Network 1주차
=====

chapter 1은 용어와 전체적인 흐름을 보는 chapter이다

#### 1-1 What is the internet?

인터넷의 기본적인 hardware와 software를 이루고 있는 nuts and bolts에 대한 설명을 하고, distributed application에게 서비스를 제공하는 networking infrastructure에 대해 설명할 것이다.  

##### A Nuts and Bolts Descriptiop


**end system** - 인터넷에 연결된 컴퓨터나 다른 장비들. 최종 사용자를 위한 어플리케이션을 수행하는 주체.(ex. 인터넷 pc, 스마트폰, 태플릿 pc같은 단말기.)
app들이 실행되는 device이자. host라고도 부른다.    
host = end system
end system은 network의 communication link와 packet switch에 연결된다.       
**packet** - the resulting packages of information, chunks of data            
**Communication Link** - 두 개 이상의 물리적 장티를 연결해주는 link.(ex.fiber, copper, radio, satelite, etc)
**packet switch** - comunication link로 packet을 주고 받는 switch
**Internet** - 네트워크들을 연결한 네트워크이다. Internet Service Providers(ISPs)와 end systems들과 연결되어서 사용된다.      
**Protocol** - 정보를 주고 받을때 지켜야될 약속.  the format, order of messages sent and received among network entities, and actions taken on msg trasmission, receipt  
**Internet standard**
- RFC(Request for Comments)
- IETF(Internet Engineering Task Force)


Network structure = network edge + access network + physical media + network core
#### 1-2 The Network Edge
##### network edge   
- end system = host 에서 실행되는 시스템.   
- host는 clients 와 server로 나뉜다.   
- client는 일반전으로 request를 날리는 애로 desktop, mobile pc, smartphone, 등이 있다.   
- server는 response를 주는 애로 보통 data center이다.
##### Access network     
end system과 다른 end system 사이의 경로상에 있는 첫 번째 라우터에 연결하는 네트워크.
    edge- core - edge의 구성을 하는 네트워크에서, access network는 결국 edge router들을 core 쪽으로 어떻게 연결하느냐를 다룬다. 
    access network가 사용되는 환경에 따라 각각의 환경이 end system을 인터넷에 연결시키는 방식이 나뉘는 데, 가정에서는 DSL과 케이블, 그리고 FTTH방식을, 기업에서는 이더넷과 와이파이로 인터넷에 접속한다.
###### Home Access ######
**upstream** - 클라이언트나 로컬 기기에서 서버나 원격 호스트로 데이터를 보내는 것.    
**downstream** - upstream 반대       
***DSL*** - 가정의 DSL모뎀은 PC의 data를 받아서 co로 전달하기 위해 디지털 데이터를 아날로그 신호로 바꿔준다. DSLAM은 Existing telephone line으로 받은 아날로그 신호를 디지털 포맷으로 변환해 data와 음성 신호를 분리시켜, 각각 인터넷 ISP와 telephone network로 보낸다.
 digital subscriber line 은 broadband residential access으로 center office와 residence간에 거리가 좁은 거리에서만 사용되게 디자인 되었다.  
***Cable-based Access*** - cable modem이 필요하다. cable 모뎀은 데이터와 tv신호를 서로 다른 주파수에 전송 시킨다.
- fiber와 coaxial cable를 둘 다 사용하는 것을 hybrid fiber coax(HFC)라 부르고 asymmetric하다.
- fiber는 가정에서 동네까지 연결시키는 physical media이고, coaxial cable은 동네에서 집까지 연결하는 phyiscal media
***FTTH** - fiber to the home으로 central office에서 home까지 optical fiber path를 제공해주는 것.
- OLT(Optical Line Terminator)는 광신호와 전기신호간의 변환을 제공한다.
- Optical splitter로 여러 개의 optical fiber로 나눈다.
- ONT(Optical Network Terminator) 라우터로써 인터넷 접속을 가능하게 해준다.


###### Enterprise Access ######
- sheared wireless aceess network로 endsytem과 router와 연결된다.


###### Physical Media ######
***guided media*** - 유선 매체로 signal들이 solid media(copper, fiber, coax)로 전파된다.    
***unguided media*** - 무선 매체로 대기나 자유롭게 전파되고 예로는 radio가 있다.    
***Twisted pair*** - 두 개의 insulated copper wire로 이루어져 있다. wire가 꼬여 있으므로 electrical interference를 감소 시킨다.
- Unshielded twisted pair(UTP)는 LAN을 만들때 사용된다.      


***coaxial cable*** - HFC나 FTTH에 사용된다. 양방향 통신을 하고 하나의 케이블로 전기 신호를 주고 받으면 end system 케이블 들에 직접 연결 되어있다. broadband 통신으로 다른 주파수를 사용하기 위해 주파수 대역들 사이에서 변조를 한다.     
***Fiber Optic Cable*** - high-speed operation, low error rate.     
***radio*** - phyiscal wire가 따로 필요없다. 무선이기에 주변 환경 영향을 많이 받아 전기 신호 bit들의 경로 손실, 신호 강도가 약해지는 현상, 간섭 등이 발생 할수 잇따.