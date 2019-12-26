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
  
  
## 분류기 성능 측정 방법의 종류: 4가지
---  
분류기(classifier)의 성능에 대한 `4가지` 측정 방법이 있다.

1. accuracy
2. precision
3. recall
4. f1-score

이들을 계산하려면, 한 가지 개념이 더 필요하다. 바로 `TP, TN, FP, FN`!

## TP, TN, FP, FN?
---
개념은 간단하다. 

1. TP (True Positive)
2. TN (True Negative)
3. FP (False Positive)
4. FN (False Negative)

처음 봤을 땐 매우 매우 헷갈리는데, 난 하나의 포맷을 만들어서 이해했다.

일단 `TP, TN, FP, FN`는 모두 두 개의 문자를 가졌으니 `자리를 분리`해서 이해해보자!

![tp-tn-fp-fn-format](https://dokylee54.github.io/assets/img/statistics/2019-12-26/tp-tn-fp-fn-format.jpg)
![test](https://dokylee54.github.io/assets/img/statistics/2019-12-26/tp-tn-fp-fn-format.jpg)

약간의 말장난 같기도 한데..

머신러닝 모델이 예측을 맞춘 경우에 1을 1이라고 해서 맞췄는지, 1이 아닌 걸 1이 아니다 라고 해서 맞췄는지는 분명 다르기 때문에 개념을 분리해서 사용하나보다..!

## dataset에서 TP, TN, FP, FN 구해보기
---
- 위의 손글씨 노트에서 가정했던 것처럼, `class A를 예측한다고 가정`
- 표

   - `행(가로줄)은 모델에 넣어 준 input`을 의미

   - `열(세로줄)은 모델이 예측한 output`을 의미

#### 1. TP (True Positive)
![tp](https://dokylee54.github.io/assets/img/statistics/2019-12-26/tp.png)
TP : A라고 예측해야 할 것을




#### 2. TN (True Negative)


#### 3. FP (False Positive)


#### 4. FN (False Negative)

## accuracy, presicion, recall, f1-score 구해보기
---