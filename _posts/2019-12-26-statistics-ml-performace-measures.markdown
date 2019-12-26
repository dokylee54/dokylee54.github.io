---  
layout: post  
title: "[Statistics] 머신러닝 분류기 성능 측정을 위한 지표 accuracy, precision, recall, f1-score 표로 쉽게 계산하기"  
subtitle: "statistics"  
categories: statistics  
tags: statistics classifier model performance measure accuracy precision recall f1-score
comments: true  
header-img: img/statistics/2019-12-26/ml_main_img.jpg
published: true
---  
  
## 개요  
> 본 문서는 youtube 영상 ["[머신러닝] 다중 분류 모델 성능 측정 (accuracy, f1 score, precision, recall on multiclass classification)"](https://youtu.be/8DbC39cvvis)을 보고 정리한 글입니다.
  
- 목차  
   - [분류기 성능 측정 방법의 종류: 4가지](#분류기-성능-측정-방법의-종류-4가지)
   - [TP, TN, FP, FN?](#tp-tn-fp-fn)
   - [dataset에서 TP, TN, FP, FN 구해보기](#dataset에서-tp-tn-fp-fn-구해보기)
   - [accuracy, presicion, recall, f1-score 구해보기](#accuracy-presicion-recall-f1-score-구해보기)
   - [마치며](#마치며)
  
<br><br><br>

## 분류기 성능 측정 방법의 종류: 4가지
---  
분류기(classifier)의 성능에 대한 `4가지` 측정 방법이 있다.

1. accuracy
2. precision
3. recall
4. f1-score

이들을 계산하려면, 한 가지 개념이 더 필요하다. 바로 `TP, TN, FP, FN`!

<br><br><br>

## TP, TN, FP, FN?
---
개념은 간단하다. 

1. TP (True Positive)
2. TN (True Negative)
3. FP (False Positive)
4. FN (False Negative)

처음 봤을 땐 매우 매우 헷갈리는데, 난 하나의 포맷을 만들어서 이해했다.

일단 `TP, TN, FP, FN`는 모두 두 개의 문자를 가졌으니 `자리를 분리`해서 이해해보자!

![4-format](https://dokylee54.github.io/assets/img/statistics/2019-12-26/4-format.jpg)

약간의 말장난 같기도 한데..

머신러닝 모델이 예측을 맞춘 경우에 1을 1이라고 해서 맞췄는지, 1이 아닌 걸 1이 아니다 라고 해서 맞췄는지는 분명 다르기 때문에 개념을 분리해서 사용하나보다..!

<br><br><br>

## dataset에서 TP, TN, FP, FN 구해보기
---
- 위의 손글씨 노트에서 가정했던 것처럼, `class A를 예측한다고 가정`
- 표 (멀티클래스 분류기)

   - `행(가로줄)은 모델에 넣어 준 input`을 의미

   - `열(세로줄)은 모델이 예측한 output`을 의미

   - +) 바이너리 분류기는 2개의 클래스가 있다고 생각하고 표 그리기

<br><br><br>

#### 1. TP (True Positive)
![tp](https://dokylee54.github.io/assets/img/statistics/2019-12-26/tp.png)
> TP: output이 `A라고 예측`한 것 중(P), input을 `A라고 잘 예측`한 것(T)

<br>

class A에 대해서는, 표에서 왼쪽 위 `9가 써져 있는 초록칸만` 해당

<br><br>
 
#### 2. TN (True Negative)
![tn1](https://dokylee54.github.io/assets/img/statistics/2019-12-26/tn1.png)
> TN: output이 `A가 아니라고 예측`한 것 중(N), input을 `A가 아니라고 잘 예측`한 것(T)

<br>

`다른 예시` 하나만 더 들어보면, 이번엔 A말고 `D를 예측`한다고 해보자!

그럼 이렇게 나오겠지?

<br>

![tn2](https://dokylee54.github.io/assets/img/statistics/2019-12-26/tn2.png)
> TN: output이 `D가 아니라고 예측`한 것 중(N), input을 `D가 아니라고 잘 예측`한 것(T)

<br><br>

#### 3. FP (False Positive)
![fp1](https://dokylee54.github.io/assets/img/statistics/2019-12-26/fp1.png)
> FP: output이 `A라고 예측`한 것 중(P), input을 `A가 아니라고 틀리게 예측`한 것(F)

<br>

`다른 예시` 하나만 더 들어보면, 이번엔 A말고 `B를 예측`한다고 해보자!

그럼 이렇게 나오겠지?

<br>

![fp2](https://dokylee54.github.io/assets/img/statistics/2019-12-26/fp2.png)
> FP: output이 `B라고 예측`한 것 중(P), input을 `B가 아니라고 틀리게 예측`한 것(F)

<br><br>
 
#### 4. FN (False Negative)
![fn](https://dokylee54.github.io/assets/img/statistics/2019-12-26/fn.png)
> FN: output이 `A가 아니라고 예측`한 것 중(N), input을 `A라고 틀리게 예측`한 것(F)

<br><br>

## accuracy, presicion, recall, f1-score 구해보기
---
이제 본격적으로 구해보자!

<br>

#### 1. accuracy
![accuracy](https://dokylee54.github.io/assets/img/statistics/2019-12-26/accuracy.png)

<br>

```
accuracy = TP+TN / TP+TN+FP+FN
```

>  이진 분류기의 accuracy는 TP+TN / TP+TN+FP+FN로 구하지만, 
<br>
다중 분류기의 accuracy를 구할 때는, 클래스 따지고 어쩌고 어렵게 생각하지 말고 그냥
<br>
표의 `대각선의 합 / 전체 셀의 합`을 구하자!

<br><br>

#### 2. precision
[precision](#2-precision)과 [recall](#3-recall)은 좀 헷갈릴 수 있는데, 먼저 계산하는 법부터 설명하고 [아래에 차이점](#precision과-recall의-차이점)을 설명하겠다.

<br>

![precision](https://dokylee54.github.io/assets/img/statistics/2019-12-26/precision.png)

<br>

```
precision = TP / TP+FP
```

>  class A에 대해, 
<br>
precision = TP / TP+FP = `분모 중에 잘 예측한 것 / output이 A인 모든 것` 
<br>
(그림에선 전체 클래스 다 구하고 있다)

<br><br>

#### 3. recall

![recall](https://dokylee54.github.io/assets/img/statistics/2019-12-26/recall.png)

<br>

```
recall = TP / TP+TN
```

>  class A에 대해, 
<br>
recall = TP / TP+TN = `분모 중에 잘 예측한 것 / input이 A인 모든 것`
<br>
(그림에선 전체 클래스 다 구하고 있다)

<br><br>

#### +)precision과 recall의 차이점
![precision_recall_difference](https://dokylee54.github.io/assets/img/statistics/2019-12-26/precision-recall-difference.png)
```
precision = TP / TP+FP = 분모 중에 잘 예측한 것 / output이 A인 모든 것
recall = TP / TP+TN = 분모 중에 잘 예측한 것 / input이 A인 모든 것
```

> 잘 보면, 
<br>
precision은 output에 대한 정확도를 나타내고
<br>
recall input 대한 정확도를 나타내고 있다.
<br><br>
즉, `precision`은 모델이 `예측한 것에 대해 얼마나 맞췄는지` 계산을 한거고 
<br>
`recall`은 모델이 `dataset에 대해 얼마나 맞췄는지` 계산한 거다.

<br><br>

#### 4. f1-score

만약, dataset의 클래스 분포가 `imbalanced`하다면, accuracy를 보는 것이 의미 없을 수 있다.

![f1-score-needs](https://dokylee54.github.io/assets/img/statistics/2019-12-26/f1-score-needs.png)

> 위의 그림과 같은 경우
<br>
accuracy는 아래 분류기가 더 높지만,
<br>
class A를 많이 맞춰서 높아진거지 나머지 B, C, D는 많이 못맞춘 것을 볼 수 있다.

<br>

이럴 때 f1-score를 이용한다.

f1-score는 앞서 언급한 precision과 recall의 조화평균이다.

![harmonic-mean](https://dokylee54.github.io/assets/img/statistics/2019-12-26/harmonic-mean.png)
```
h = 2 * AB / (A+B)
```
A와 B의 조화평균은 이렇게 구한다.

![f1-score](https://dokylee54.github.io/assets/img/statistics/2019-12-26/f1-score.png)

이처럼 `A와 B에 precision과 recall`을 넣었을 때의 `h가 바로 f1-score`이다.

따라서, dataset이 `imbalanced`하다면 `accuracy보다 f1-score`를 보는 것이 좋다.

<br><br><br>

### 마치며

여기까지 인공지능 분류기 모델의 성능을 측정할 수 있는 4가지 지표를 알아봤다.

이건 헷갈릴 수 있는 개념이므로 꼭 완전히 이해하고 넘어가자!