---
layout: post
title: Python boto3으로 AWS EC2 접속하기
date:
categories: []
tag: []
comments: true
---
#  Python boto3으로 AWS EC2 접속하기

* Python의 `boto3` 라이브러리는 AWS 홈페이지에 로그인해서 Console을 이용하지 않고, 
Python에서 코드로 인스턴스(가상 서버)와 같은 인프라를 관리하기 위한 SDK (Software Development Kit)입니다.
 
---
## **Contents**
{:.no_toc}
0. this unordered seed list will be replaced by toc as unordered list
{:toc}
---

## What for boto3?

`boto3`는 파이썬의 한 라이브러리인데요. 

API 직접 호출하는 방법 대신에 코드로 인프라를 관리하기 위함 


1. IAM 사용자 생성
 

2. boto3 설치

~~~python
conda install boto3
pip install boto3
~~~

1. boto3으로 EC2접속

AWS S3 버킷을 파이썬으로 만드는게 왜 중요한가? 그냥 AWS Console의 GUI를 이용하면 더 쉽지 않은가? 맞다. 만약 하나의 S3 버킷을 만든다고 하면 AWS 콘솔에서 하는것이 더 간단할 수 있다. 하지만 AWS Console을 이용하면 항상 개발자 또는 오퍼레이터가 콘솔에 접속해 클릭 클릭해야한다. 자바, 파이썬, 루비등의 언어와 boto3 라이브러리를 이용하면 이 과정을 자동화 할 수 있다. 실제로 많은 기업들이 클라우드 인프라(Cloud Infrastructure)를 코드로 자동화 해 관리한다.

---
## **References**
* [삐멜 소프트웨어 엔지니어](https://imasoftwareengineer.tistory.com/98 )