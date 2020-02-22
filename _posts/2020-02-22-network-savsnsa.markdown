---  
layout: post  
title: "[Network] 진짜 5G, 가짜 5G? LTE를 이용해 5G를 상용화하다 - NSA, SA에 대하여"  
subtitle: "Network"  
categories: network  
tags: network
comments: true  
header-img: img/network/2020-02-21/5g_launch.jpeg
published: true
---  
  
## 개요  
> 현재(2020.02) 5G가 상용화되는 방식인 NSA가 뭔지<br>그리고 곧 상용화 될 5G SA는 뭔지, 간략한 설명
  
- 목차  
   - [현재 5G 운용 방식](#현재-5g-운용-방식)
   - [용어](#용어)
   - [SA vs. NSA](#sa-vs-nsa)
   - [이통 3사가 SA로 넘어갈 때 고려해야 할 사항](#이통-3사가-sa로-넘어갈-때-고려해야-할-사항)
   - [reference](#reference)

  
<br><br><br>

## 현재 5G 운용 방식
---  
현재 5G는 독자적인 코어(5GC)를 가지고 상용화된 것이 아니다.<br>
기존에 깔려있던 LTE 환경에 5G 기지국(gNB)을 연결한 mixed 방식을 사용한다.
* 코어? gNB? - [관련 포스팅 보기](https://dokylee54.github.io/network/2020/02/21/network-ran/)

<br>

즉, 쉽게 말해서 5G를 빨리 상용화해서 고객들에게 제공하고 싶은데<br>5G 환경으로 다시 망을 구축하려면 시간이 오래 걸리니까<br>`기존 LTE 환경에 5G 기지국을 연결`해서 네트워크 망을 제공하는 것이다.

<br>

그게 바로 `NSA(Non-Standalone)`방식이다.<br><br>
이렇게 하나 이상의 RX/TX를 지원하는 단말이 하나 이상의 기지국들이 제어하는 리소스를 동시에 사용하는 기술을 `Dual Connectivity (DC)`라고 부르는데 5G NSA 구조는 3GPP 표준 단체에서 정의한 이 DC 기술에 기반하고 있다.<br><br>
그리고 이 구조는 LTE radio 지원 기지국의 3GPP 공식 명칭인 E-UTRA을 사용하여 `E-UTRA New Radio Dual Connectivity (EN-DC)`라고 명명한다.

<br><br><br>


## 용어
---
대응되는 용어들을 먼저 보자<br><br>
4G -> 5G(Five Generation)<br><br>
LTE -> NR(New Radio)

<br><br><br>


## SA vs. NSA
---  
먼저 좋은 레퍼런스 사진을 보자!
![savsnsa](https://github.com/dokylee54/dokylee54.github.io/blob/master/assets/img/network/2020-02-22/savsnsa.gif?raw=true)
여기서 주의해서 볼 부분은<br>
> `NSA`는 4G 코어 EPC + LTE 기지국 eNB + NR 기지국 gNB<br>
`SA`는 5G 코어 5GC + 5G 기지국 gNB

라는 것!<br><br>
그리고 곧 2020년 상반기 안에 이통 3사가 SA 서비스 또한 제공하겠다고 발표했다.<br><br>
EPC보다 5GC가 1. latency도 작고 2. Network Slicing도 가능하기 때문에 상당 부분에서 좋은 서비스가 될 것이다.<br><br>

<br><br><br>


## 이통 3사가 SA로 넘어갈 때 고려해야 할 사항
---  
현재 5G 상용화는 NSA로 하고 있지만, 언급했듯 2020년 상반기 안에 이통 3사가 SA 서비스를 제공하겠다고 발표했다.<br><br>
하지만 고려해야 할 사항이 좀 있다.<br><br><br>


`1. 단말(UE)의 SA 서비스 지원 여부`
> 현재 단말(UE)들이 NSA를 지원하는 기종들이기 때문에, 어떤 식으로 사용자들이 SA로 넘어오게끔 할 지가 중요 고려사항이 될 것이다.<br><br>
보통 소프트웨어 업데이트로 한다는데, 업데이트를 잘 미루는 나로써는 분명 SA로 넘어오지 않을 사용자들이 생길 거라고 생각된다..<br><br>
그렇게되면, 현재 운용하고 있는 NSA 서비스도 종료할 수가 없어지겠지?
* UE? - [관련 포스팅 보기](https://dokylee54.github.io/network/2020/02/21/network-ran/)

<br><br>

`2. 도입 초기에는 SA 성능이 NSA보다 안좋을 수 있음`
> 잘 생각해보자.<br><br>
먼저, NSA는 LTE 환경에 NR을 섞어서 사용한다고 했다.<br>
그렇다면, 단순히 생각해서 주파수 대역으로 봤을 때 LTE와 NR을 합친 만큼을 사용하고 있다고 볼 수 있다.<br><br>
근데 SA는? LTE 대역을 안쓰니까 주파수 대역이 더 적어지겠지?<br>
주파수 대역이 적으면, 전송 데이터량도 작다.<br>
게다가, DC로 얻을 수 있는 커버리지 확장도 얻지 못하니까 더 작은 구역만 서비스가 가능하겠다.<br>
* 주파수 대역? 커버리지?> [관련 포스팅](https://dokylee54.github.io/network/2020/02/21/network-frequency/)

<br><br>

`3. 커버리지를 늘릴 수 있는 방법, Dynamic Spectrum Sharing(DSS)`
> 앞서 계속 말했듯이 주파수 대역의 특징으로 인해 LTE 커버리지가 더 넓다고 했지 않은가?<br>
그러면 SA를 할 때, LTE에서 그랬던 것처럼 낮은 주파수 대역을 5G NR로써 사용하면 커버리지가 더 늘어날 것이다.<br>
그걸 구현할 수 있는 방법이 DSS이다. 이건 다른 포스팅에서 더 설명하도록 하겠다.



<br><br><br>


## reference
---
포스팅> [NETMANIAS TECH-BLOG Post](https://netmanias.com/ko/post/blog/13951/5g/5g-standard-part-2)




