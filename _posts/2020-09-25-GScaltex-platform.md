---
date: 2020-09-25 12:26:40
layout: post
title: GS Caltex 복합수지 물성 예측 플랫폼
subtitle: Lorem ipsum dolor sit amet, consectetur adipisicing elit.
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
image: /assets/img/posts/gscaltex-platform-1.png
optimized_image: /assets/img/posts/gscaltex-platform-1.png
category: GS Caltex
tags:
  - flask
  - HTML
  - DNN
author: sang-rak
---

GS Caltex 물성수지 예측 플랫폼

todolist: url heroku로 수정 예정이였으나

tensorflow의 용량이 500mb이넘어서 동영상대체 or 해결방안(AWS) 제시 필요
URL: https://gscaltex-platform.netlify.app

![gscaltex-platform-result](/assets/img/posts/gscaltex-platform-result.png)



- **실행방법**

```
%pip install tensorflow
python flask_app.py
```





- **개발목적**

최소한의 재료를 사용하면서 환경 오염을 덜 시키는 소재로 복합 수지 물성을 예측하여 같은 효과를 내는 재료 중 친환경적 비용이 덜 드는 재료를 사용하는 상품성과 광고성 두 마리 토끼를 잡는 알고리즘을 개발한다.



- **문제정의**

동일한 성분, 동일한 조건 하에서 실험한 데이터임에도 같은 결과가 나오지 않는다.



- 결과 데이터 예시

| 항목          | 시험조건     | 단위    | #1    |
| ------------- | ------------ | ------- | ----- |
| MI            | 230℃, 2.16Kg | g/10min | 34.77 |
| 비중          | -            | -       | 0.938 |
| 인장강도      | 50mm/min     | MPa     | 25.3  |
| 굴곡강도      | 2mm/min      | MPa     | 35.1  |
| 굴곡탄성률    | 2mm/min      | MPa     | 1746  |
| IZOD 충격강도 | 23℃          | kJ/m2   | 7.2   |
| IZOD 충격강도 | -10℃         | kJ/m2   | 4.3   |
| 경도          | R scale      | -       | 89.7  |
| *HDT          | 0.45MPa      | ℃       | 92.2  |
| HDT           | 1.8MPa       | ℃       |       |

*HDT:열 변형 온도 또는 열 변형 온도는 중합체 또는 플라스틱 샘플이 특정 하중 하에서 변형되는 온도입니다. 주어진 플라스틱 재료의 이러한 특성은 열가소성 성분을 사용하는 제품의 제품 설계, 엔지니어링 및 제조의 여러 측면에 적용됩니다

![image-20210615223519622](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615223519622.png)

![image-20210615223614346](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615223614346.png)



- 모델링 선택

![image-20210615224036858](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615224036858.png)

- ML

![image-20210615224133034](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615224133034.png)



![image-20210615224247888](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615224247888.png)

- DNN
  - 하이퍼 파라미터 연구

![image-20210615223743992](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615223743992.png)

![image-20210615223824813](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615223824813.png)

- 최종 모델 선택 : DNN

![image-20210615224314941](/assets/img/posts/2020-09-25-GScaltex-platform.assets/image-20210615224314941.png)

