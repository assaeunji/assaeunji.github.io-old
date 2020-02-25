---
layout: post
title: "Bayesian A/B Testing"
date: 2020-02-27 
categories: [Bayesian]
tag: [bayesian,ABtesting]
---
# Bayesian A/B Testing

## **Contents**
{:.no_toc}
0. this unordered seed list will be replaced by toc as unordered list
{:toc}

---


---
## **Terminology**
* A/B Testing
* Counterfactual
* Conversion rate

---
## **Summary**
* 왜 A/B testing을 사용할까?
* Bayesian A/B testing은 무엇이 다를까?
---

## **Conversion Testing**
* Conversion Testing은 A와 B 중 전환율이 높은 쪽이 어딘 지를 보는 가설 검정입니다. 
* 여기서 전환율은 전체 방문자 중 A나 B를 통해 구매/가입를 한 사람들의 "비율"이기 때문에 데이터 자체는 이항 분포 (Binomial Distribution)를 따름을 알 수 있습니다. 이항 분포의 확률 변수는 $$N$$ 명의 사람 중 어떤 event를 성공한 사람 수이고, 우리가 관심있는 모수 (parameter)는 그 **성공 확률**입니다. 
* 베이지안은 모수에 사전 분포 (Prior distribution)를 가정해 모수의 실제 값이 하나가 아니라, 사람들의 믿음 (belief)에 따라 달라지는 분포 형태를 띠고 있다 생각합니다. 여기서 관심 모수는 성공 확률 (전환율)이기 때문에 이에 잘 맞는 사전 분포를 가정하는 것이 중요합니다. 
* 이러한 성공 확률을 위한 사전 분포로 베타 분포 (Beta Distribution)을 가정합니다. 베타 분포를 따르는 확률 변수는 항상 $$(0,1)$$사이의 값이기 때문에, 성공 확률 분포의 자연스러운 가정이 됩니다. 또한, 베타 분포의 모양에 따라 확률이 '어느 값에 밀집되어 있을 것이다'에 대한 사전적인 지식을 부여할 수 있습니다. 

### Relationship between Beta-Binomial Distribution: Conjugacy
* 이제 A, B 방법의 전환율을 구하는 데 있어서 사전분포는 베타 분포, 가능도는 이항 분포로 두는 것에 대해 자연스러우셔야 합니다. 
* 사전분포와 가능도를 각각 베타와 이항분포로 설정하는 것의 또 하나의 장점은 **켤레성**(Conjugacy)를 이용할 수 있다는 점입니다.
* **켤레성**이란 사후분포를 analytic하게 구했을 때, 그 형태가 사전분포와 같은 분포일 때 켤레성을 띤다고 말합니다. 
* 사후분포를 analytic하게 구하면 

$$
p(\theta|\text{Data}) = \frac{p(\text{Data}|\theta) \times p(\theta)}{p(\text{Data})} \propto \frac{p(\text{Data}|\theta) \times p(\theta)}
$$ 