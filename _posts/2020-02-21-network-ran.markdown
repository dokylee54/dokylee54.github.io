---  
layout: post  
title: "[Network] 듣기만 해도 어려워 보이는 RAN? 간단히 알아보기"  
subtitle: "Network"  
categories: network  
tags: network
comments: true  
header-img: img/network/2020-02-21/5g_launch.jpeg
published: true
---  
  
## 개요  
> 듣기만 해도 모르겠는 RAN 간략한 설명
  
- 목차  
   - [Access망은 무선망 Core망은 유선망](#access망은-무선망-core망은-유선망)
   - [용어 Terminology](#용어-terminology)
   - [reference](#reference)

  
<br><br><br>

## Access망은 무선망 Core망은 유선망
---  

여기서부터 `천천히` 읽으면서 따라오면 쉬움! (모르는 용어가 나오면 밑의 [용어](#용어-terminology) 탭 참고)

아래 그림은 서울에서 부산으로 전화통화를 하는 과정을 도식화한 것이다.<br><br><br>
![ran](https://dokylee54.github.io/assets/img/doubleqoute.png)
> 1. 서울 핸드폰(UE)에서 내가 전화한 곳과 가장 가까운 eNB(LTE 기지국)으로 wireless하게 신호 전달
2. 서울에 있는 Core망으로 신호 전달
3. 부산에 있는 Core망으로 신호 전달
4. 부산 친구와 가장 가까운 eNB로 신호 전달
5. wireless하게 부산 핸드폰(UE)로 신호 전달

Core망(유선망) = CN
<br>
Access망(무선망) = RAN 


<br><br>

## 용어 Terminology
---
*	UE: user equipment, 단말
*	Core망: 유선망
*	Access망: 무선망
* eNB: LTE 기지국
* gNB (지노드비, next generation Node B, gNodeB, gNB): 이동 통신 사실 표준화 기구 3GPP에서 제정한 5세대 이동 통신 NR(New Radio) 기지국. 3GPP에서 기존 4세대(4G) 이동 통신의 LTE 기지국의 이름 이노드비(eNodB)와 구별하여 5G NR(New Radio) 기지국을 ‘다음 세대(next generation)’의 알파벳 ‘g’를 인용하여 gNodeB로 정하였다.


<br><br>


## reference
---
블로그 포스팅 > ["LTE 기본 개념 - Access망, Core망"](https://m.blog.naver.com/PostView.nhn?blogId=thinktabl2&logNo=220254249723&proxyReferer=https%3A%2F%2Fwww.google.com%2F)


