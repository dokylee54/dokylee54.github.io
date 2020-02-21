---  
layout: post  
title: "[Network] 5G에 왜 3.5GHz, 28GHz 대역을 쓸까.. 그리고 주파수 경매?"  
subtitle: "Network"  
categories: network  
tags: network
comments: true  
header-img: img/network/2020-02-21/5g_launch.jpeg
published: true
---  
  
## 개요  
> 네트워크에서 주파수가 어떤 의미를 가지는지 간략하게!
  
- 목차  
   - [주파수의 특징](#주파수의-특징)
   - [5G 주파수 대역의 특징](#용어-terminology)
   - [주파수 경매](#주파수-경매)

  
<br><br><br>


## 주파수의 특징
---  
많은 데이터를 전달하기 위헤서는 `고주파`를 사용해야 함.
<br><br>
허나 단점! `고주파`는 직진성이 강하여 방해물을 만나면 되돌아오거나 비나 눈이 오면 전파가 비나 눈에 흡수되거나 소멸됨.
<br><br>
자 그러면 `저주파`는? 반대!
<br><br>
`저주파`는 회절률이 좋아 벽과 벽 사이의 제한도 쉽게 통과하고 눈이나 비와 같은 자연 현상에 강함.
<br><br>
그러나 전송할 수 있는 데이터 양이 적음.

<br>
> 고주파: 많은 양의 데이터 전달 / 장애물에 막혀서 멀리 도달하지 못함<br>
저주파: 적은 양의 데이터 전달 / 장애물을 피해서 멀리 도달 가능

<br><br><br>


## 5G 주파수 대역의 특징
---
주파수의 특징을 알았다! 그러면 요즘 난리치는 5G는 고주파일까 저주파일까?
<br><br>
정답은 고주파! 뿐만 아니라 초고주파까지 사용한다.
<br><br><br>
5G는 고주파 `3.5GHz`과, 초고주파 `28GHz`를 사용한다.
<br><br>
그래서 아까 말했듯이 LTE보다 데이터를 많이 많이 전달할 수 있지만,
<br><br>
장애물에 막혀서 멀리 못가기 때문에, 기지국을 하나 세우면 LTE보다 훨씬 작은 지역에서 이용 가능하다 :(
<br><br><br>
아래 그림을 보면 커버리지(도달 가능한 지역)가 얼마나 차이나는지 알 수 있을 거다.
![coverage](https://dokylee54.github.io/assets/img/network/2020-02-21/coverage.jpg)
source: ["5G 서비스 지도 보니…단말기 교체할까 말까?"](https://news.kbs.co.kr/news/view.do?ncd=4176392)



<br><br><br>


## 주파수 경매
---

주파수는 정부꺼라서 SKT, KT, LGU+가 돈주고 사서 쓴다!
<br><br>
아래 기사를 보면 이번 5G 상용화를 위해 이통3사가 경매한 결과를 볼 수 있다.
<br><br>
현재 2020년 2월 5G는 3.5GHz를 쓰고있다. 28GHz는 곧 RFP가 나온다고 한다.
* RFP가 뭔지 궁금하면: ["이전 게시물"](포스팅URL)
<br><br><br>
![coverage](https://dokylee54.github.io/assets/img/network/2020-02-21/spectrum_auction.png)
>기사["5G 주파수 경매 '쩐의 전쟁' 없었다…SKT·KT 최대 대역폭 확보"](https://news.joins.com/article/22726257)


