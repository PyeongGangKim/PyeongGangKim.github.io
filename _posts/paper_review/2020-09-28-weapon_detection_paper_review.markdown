---
layout: post
title: A Handheld Gun Detection using Faster R-CNN Deep Learning
date: 2020-09-027 21:38:23 +0900
category: paper_review
tag: ['paper review' ,'weapon detection', 'cnn','Faster-RCNN']
---

A Handheld Gun Detection using Faster R-CNN Deep Learning
=====

2017년도에 나온 handheld gun detection에 관한 논문이다.        

#### introduction
이 논문에서는 gun detection을 할 때 특히 cctv에서 할 때 문제점에 대해서 말을 해준다.       

이 논문에서는 gun's occlusion에 대해 말한다.      
gun이 occulsion 될 수 있는 경우는 크게 세 가지가 있다.      

1. Self-occlusion - gun 끼리 서로를 가렸을 때를 말한다.      
2. Inter class occlusion - 손이나 옷 같은 것으로 가렸을 때이다.     
3. background site/scene structure - background의 structure에 가려졌을 때이다.      

위에 문제를 해결하기 위한 방법은 depth analysis of object, fusion of color, shape features of object, optimal position of camera 등이 있다. 하지만 이 논문에서는 위에 나온 occlusion에 대한 것을 다루지 않고, CNN과 여러 classifier를 비교해서 좋은 model을 취했다.

#### METHODOLOGY
DATABASE는 Internet Movie Firearms Database(IMFDB), benchmark database of firearms를 사용 하였다.
positive는 IMFDb database에서 얻은 것이고, negative image는 internet에서 randomly하게 flower,landscape,animal etc을 얻었다고 나와있다. 하지만 negative에도 총 이미지가 존재한다.....      
- ![Image Alt 텍스트](/assets/img/weapon-detection-paper-(a)positive.png)
- ![Image Alt 텍스트](/assets/img/weapon-detection-paper-(a)negative.png)     

Deep Learningd Model은 MATLAB에 MatConvNet을 사용해서 구현을 했다. 그리고 ImageNet으로 pretrain 된 VGG-16을 model을 사용하였다.

#### EXPERIMENTAL SETUP
