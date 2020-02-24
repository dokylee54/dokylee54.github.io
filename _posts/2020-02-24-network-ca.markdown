---  
layout: post  
title: "[Network] 하나의 대역으로는 성능 부족! Carrier Aggregation(CA)으로 높이기 간단 설명"  
subtitle: "Network"  
categories: network  
tags: network
comments: true  
header-img: img/network/2020-02-21/5g_launch.jpeg
published: true
---  
  
## 개요  
> throughput과 같은 성능을 높여주는 Carrier Aggregation(CA) 간단 설명
  
- 목차  
   - [CA란?](#ca란)
   - [심플한 설명!](#심플한-설명)
   - [CC? 용어 설명](#cc-용어-설명)
   - [CA의 종류](#ca의-종류)
   - [reference](#reference)

  
<br><br><br>

## CA란?
---  
CA는 서로 다른 주파수 대역을 동시에 이용하여 광대역을 만들어 통신하는 것<br>
레퍼런스 사진을 보자!
![ca]()
>두 주파수 대역 (e.g. 850MHz, 1.8GHz)을 사용하는 CA 기지국에서 LTE 단말 (CA 지원 안함)과 LTE-A 단말 (CA 지원함)이 통신하는 경우를 나타냅니다.<br><br>
LTE 단말기는 850MHz 또는 1.8GHz 중 `하나의 대역`으로 최대 75Mbps까지 통신할 수 있고, LTE-A 단말기는 `CA`를 이용해 850MHz와 1.8GHz로 `동시에` 통신하여 최대 150Mbps까지 통신할 수 있습니다.<br><br>
그러나, `대역별 커버리지가 다르므로` LTE-A 단말은 위치나 전파 수신 상태에 따라 LTE 단말기처럼 하나의 주파수로만 통신할 수도 있습니다.<br>
* 커버리지?> [관련 포스팅](https://dokylee54.github.io/network/2020/02/21/network-frequency/)

<br><br>
잘 느낌이 안온다면 아래의 심플 설명을 읽고 다시 보자!

<br><br><br>



## 심플한 설명!
---  
간단하게 말해서, 당신이 서서 핸드폰을 딱 쓰려고 하면<br><br>
핸드폰이 알아서 그때 어떤 기지국이 가장 가까운지 or 어떤 주파수 대역들을 사용할 수 있는지 확인한다.<br><br>
그렇게 딱 알아내고! 만약에 핸드폰이 CA를 사용 가능하고+주파수 대역도 여러가지 잘 잡히고 하면!<br><br>
그때 CA를 사용해서 통신을 하는 거다! 무작정 나 CA할래~~해서 할 수 있는게 아니다. 상황이 잘 맞아야 됨 =)


<br><br><br>

## CC? 용어 설명
---
만약에 두 주파수 대역 850MHz, 1.8GHz으로 CA를 한다고 하자. 이때 850MHz, 1.8GHz를 각각 1CC라고 칭한다. `CC`가 주파수 대역을 세는 하나의 단위라고 보면 된다. 그럼 850MHz 1CC, 1.8GHz 1CC로 CA를 하니까, 2CC CA라고 말할 수 있겠지?
<br><br>
하나 `주의`할 것은, 1CC가 무조건 한 주파수 대역(밴드)에 한 개만 있을 수 있는 건 아니라는거!<br> 
예를 들어, 2.1GHz에 20MHz가 1CC, 10MHz가 1CC 이렇게 나뉘어져서, 2.1GHz에 총 2CC가 있을 수 있다.


<br><br><br>


## CA의 종류
---
CA도 종류를 나눌 수 있는데, 어떤 주파수 대역을 사용할 거냐에 따라 나뉘게 된다.

<br><br>
그림 한 장으로 정리해보면

![ca_category]()

> 같은 주파수 대역(이하 밴드라고 칭하겠음)안에서 하는 건 intra-band, 다른 밴드면 inter-band<br>
둘이 연속적으로 이어져 있으면 contiguous, 떨어져 있으면 non-contiguous<br>



<br><br><br>


## reference
---  
[넷마니아스 포스팅](https://www.netmanias.com/ko/post/blog/5761/carrier-aggregation-lte-lte-a/mwc-2013-technology-analysis-part-2-lte-advanced-carrier-aggregation)


<br><br><br>



