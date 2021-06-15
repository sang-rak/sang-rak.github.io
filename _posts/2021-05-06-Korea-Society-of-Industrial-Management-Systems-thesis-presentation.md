---
date: 2021-05-06 12:26:40
layout: post
title: Water supply Pipe Leak Preventive Maintenance Model
subtitle: NGBoost 모델로 상수관의 노후도 평가를 위한 새로운 평가방법
description: Lorem ipsum dolor sit amet, consectetur adipisicing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua.
image: 2021-05-06-한국산업경영시스템학회 논문발표.assets/image-20210615021312294.png
optimized_image: 2021-05-06-한국산업경영시스템학회 논문발표.assets/image-20210615021312294.png
category: Thesis Presentation
tags:
  - SHAP
  - QGIS
  - XGBoost
  - NGBoost
author: sang-rak
---



​        **Water    supply Pipe Leak Preventive**     **Maintenance Model**         **Sangrak Park1, Jonghwan Lee2**         **Department of Industrial Engineering, Kumoh    National Institute of Technology**              **상수도관 누수 예지 보전 관리 모델**         **박상락1, 이종환****2**         **금오공과대학교    산업공학부**              South Korea's water flow rate is    lower than that of developed countries, most of which are believed to be    due to leaks in the water supply and drainage channels. Leakage is judged    to be a leak when the supply volume increases compared to the previous day.             However, sudden increase and    decrease in demand often occur, and in the event of an accident, it is    impossible to predict a real-time leak, so it takes a long time to take    measures after the accident.         However, it is not possible to    repair and replace all old pipes at the same time, so the priority for    upgrading water pipes should be determined by predicting the deterioration    of the pipes in use. This study suggested that the NGBoost (Natural Gradient Boosting) technique could be a new    evaluation method for assessing the deterioration of water pipes.          In this paper, the drainage pipe    network of the GM area of Gyeongsanbuk-do was applied, and the data of the    GIS pipeline of the city hall and the leakage construction ledger of the    waterworks office were matched through NNJOIN Algorithm of QGIS.          The life expectancy prediction    was carried out based on the model year of the leaky pipe among the matched    total tubes. In order to intuitively understand the degree of deterioration    of the entire target pipeline, the aging level was divided into five grades    and displayed on the pipe network map.         The aging tube evaluation    technique proposed in this study was applied with various factors in the    surrounding environment that affect the characteristics and old age of the    pipe by identifying the leakage by tube, not by block unit of the pipe. It    is expected that the water flow rate will increase through the preservation    of pipe network forecasts through objective and reasonable predictions for    maintenance of water pipes rather than the evaluation of aging over a    simple period.                                  Keywords: Ant Colony Optimization Algorithm, Leak Pipeline Problem,    prediction manager,         



 **1.** **연구배경 및 방법**



 

대한민국의 유수율은 선진국에 비해 낮게 나타나고 있는데 이는 대부분 배·급수 관망에서의 누수에 기인한 것으로 추정된다. 상수도 관망에서 누수는 공급량이 이전 일들과 비교하여 증가할 시 누수라 판단한다. 하지만 단발적 수요증가 및 감소가 발생하는 경우가 많고 [Fig.1]과 같이 사고가 발생한 경우 실시간 누수예측 불가로 사고 후 주민의 신고 후 조치까지 장시간이 소요된다. 모든 노후 관을 동시에 보수 및 교체하는 것은 불가능하므로, 사용 중인 관의 노후도를 예측하여 상수관의 개량 우선순위를 결정해야 한다. 

 

본 연구에서는 NGBoost(Natural Gradient Boosting)기법이 상수관의 노후도 평가를 위한 새로운 평가방법이 될 수 있음을 제시하였다. 

 

​                                ![image-20210615021312294](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021312294.png)

                     <Figure 1> Leak Pipe Problem 

 



본 논문에서는 경상북도 GM지역의 배·급수 관망을 적용대상으로 진행하였으며, 시청의 GIS관로 자료와 상하수도사업소의 누수공사대장주소를 Geocoding 하여 QGIS의 NNJOIN알고리즘을 통해 누수지점을 매칭하여 [Fig.2]와 같이 표현하였다. 

 

매칭된 전체 관 중 누수 관의 연식을 기준으로 수명 예측을 진행하였다. 전체 관의 노후도 정도를 직관적으로 파악할 수 있도록 노후도를 5등급으로 나누어 관망도에 도시하였다. 본 연구에서 제안한 노후관 평가기법은 관의 블록단위가 아닌 관 별로 누수를 파악하여 관의 특성과 노후에 영향을 미치는 주변환경의 다양한 요인을 적용하였다. 단순 시간에 따른 노후도 평가가 아닌 상수관의 유지관리를 위한 객관적이고 합리적인 예측을 통해 관망 예지보전을 통한 유수 율 증가를 기대한다. 

  ![image-20210615021401345](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021401345.png)

<Figure 2> Leak Set NNJOIN 



**2.** **노후관로 문제**

 

 

노후관 관리 문제는 전국의 상하수도사업소의 문제 중 하나이다. 30년이상된 노후관에는 이물질과 누수 위험률이 올라가는 문제가 발생한다.     노후관을 알아내기 위해선 매설 당시 관에 관내 상태여부를 파악할 수 있는 많은 센서를 달아 관리하여야 한다. 하지만 관마다 센서를 구축하는 비용은 천문학적으로 많이 들기에 불가능하다. 현재 관 시스템은 누수가 일어나면 주민이 이를 신고 후 조치를 하여 긴급누수공사에 착수하게 된다. 그 사이의 시간 동안의 물 손실 문제는 유수율에 악영향을 미친다. 이러한 문제점을 개선하기위해 각 시도부처에서는 여러가지 솔루션들이 제시되었다. 가장 대표적인 것으로는 NIA(한국 정보화 진흥원)의 표준 분석 모델로 Random forest Model을 통해 정상관과 누수관을 예측하여 위험도를 표시하는 모델을 개발하였다. 

 

**3.** **트리 모델**

 

 

3.1 트리 모델

 

Decision Tree는 분류(Classification)와 회귀(Regression) 모두 가능한 지도 학습 모델 중 하나입니다. 결정 트리는 질문을 이어가며 이분법적으로 학습합니다. 기린과 코뿔소를 구분한다면 ‘목의 길이가 2m이상인가요?’ 라는 질문을 통해 기린과 코뿔소를 나눌 수 있습니다. 코뿔소와 토끼는 ‘뿔이 있나요?’ 라는 질문으로 나눌 수 있습니다. 아래는 결정 트리를 도식화한 것입니다.

![image-20210615021408717](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021408717.png)

  <Figure 3> Tree Model 



이렇게 특정 기준에 따라 데이터를 이 분류하는 모델을 결정 트리 모델이라고 합니다. 한번의 분기 때마다 변수 영역을 두 개로 구분합니다. 결정 트리에서 질문이나 정답을 담은 네모 상자를 노드라고 합니다. 첫 질문을 Root Node라고 하고, 마지막 노드를 Terminal Node라고 한다.

 

 ![image-20210615021412332](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021412332.png)

<Figure 4> Leak Set NNJOIN 

전체적인 모양이 나무를 거꾸로 놓은 것과 닮아 Decision Tree라고 부른다.

 

3.2 Random Forest

 

누수관의 위험도를 예측하기 위해서는 많은 요소를 고려해야 합니다. 관 재질, 관 경, 매설 깊이 등 수많은 요소가 필요할 것입니다. 

 

수많은 요소를 기반으로 누수의 위험도를 예측한다면 분명 Overfitting 문제가 발생한다. 예를 들어 Feature가 25개일 때 25개의 Feature를 기반으로 하나의 결정 트리를 만든다면 트리의 가지가 많아지고 이는 Overfitting 결과를 야기한다.

 

 Overfitting 문제를 해결하기 위해 30개의 Feature 중 랜덤으로 5개의 Feature만 선택해서 하나의 결정 트리를 만들고 30개 중 랜덤으로 5개의 Feature를 선택해서 또 다른 결정 트리를 만든다.

 

 이 과정을 반복하여 여러 개의 결정 트리를 만든다면 결정 트리마다 예측 값을 산출한다. 여러 결정 트리들이 내린 예측 값들 중 가장 많이 나온 값을 최종 예측으로 정한다. 이렇게 의견을 통합하거나 여러 가지 결과를 합치는 방식을 앙상블이라 한다.

 

 즉, 분류를 위해 하나의 깊이가 깊은 결정 트리를 만들지 않고 여러 개의 작은 결정 트리를 만드는 것이다. 여러 개의 작은 결정 트리가 예측한 값들 중 가장 많은 값 혹은 평균값을 최종 예측 값으로 정하는 것이다. 

 

 ![image-20210615021422257](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021422257.png)

<Figure 5>               Random Forest Conceptual Diagram

**4.** **알고리즘 개발**

 

 

4.1 기존의 알고리즘 및 데이터 셋 구성

 

표준분석모델의 데이터 셋은 과거에 누수가 되었던 데이터들을 활용하여 누수가 여부를 예측하는 지도학습 분류모델이라고 볼 수 있다. 

 

다년간의 누수데이터 셋으로 하였지만 누수가 일어나는 상황 자체가 특수 상황이라는 점에서 누수여부가 있었던 누수관의 수가 정상관의 수와 20배 차이가 발생하여 불균형 데이터셋 문제가 발생하였다. 또한 수기로 작성하던 자료에서 자료의 손실이 발생하여 정상관 또한 누수여부가 있었음에도 정상관으로 분류되는 데이터 신뢰성 문제 또한 발생하였다.

 이러한 문제점을 해결하고 높은 정확도로 분류하였다 하여도 이 모델은 과거 몇년간에 누수 여부를 예측하는 모델인 한계 때문에 누수가 일어날 연도를 예측하기에는 적합하지 않은 데이터셋이라고 볼 수 있다.

 

 ![image-20210615021428744](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021428744.png)

<Figure 6> Standard Analysis Model    Data Set



4.2 새로운 알고리즘 및 데이터 셋 구성

 

새롭게 개선된 누수관 예측 알고리즘에서는 누수관의 연식을 전체관에 적용시키는 새롭게 개선된 누수관 예측 알고리즘을 계획하였다.

 기존의 누수관 예측 Random Forest 알고리즘에서는 accuracy이 높으면 좋은 모델이라고 착각할 수 있다. Random Forest 분류 모델로 누수관과 정상관을 예측하는 모델을 개발하였다.

이 데이터셋으로는 현재의 시점에서 누수가 되었던 관과 정상이었던 관을 예측하는 것으로 미래를 예측하는 것은 불가능하다. 또한 예측율이 좋지 않아 [Fig.7]과 같이 정상관을 찾는 F1-score를 기준으로 삼았다. 누수관을 찾는 F1-score값은 현저히 떨어진다. 기존 데이터셋은 정상관과 누수관 둘 간의 간격이 20배차이가 발생하는 불균형 데이터 셋으로 단순히 정확도로 구분하는 것이 아닌 누수관을 찾아내는 Recall을 보아야한다.

 

 

  ![image-20210615021433745](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021433745.png)

<Figure 7> Standard Analysis Model Matrix 

 여기서 Recall이란 누수관을 찾는 기준으로 보아야한다. 단순히 모두 정상관이라 예측 하더라도 누수관이 비교적 작은 값이기에 정확도는 높게 나오는 문제가 발생하기 때문이다. 이러한 데이터의 불균형 문제점을 해결하기 위해 정상관과 누수관을 분류한 데이터셋과 예측모델이 아닌 누수관의 연식을 통해 관의 남은 연식을 예측하는 회귀모델로 구상하고 회귀모델에 적합하게 데이터셋 구성을 [Fig.8]과 같이 하였다.

  ![image-20210615021437869](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021437869.png)

<Figure 8-1> GM Region Pipe Data Set

 ![image-20210615021441078](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021441078.png)

<Figure 8-2> GM Region Pipe Data Set  

![image-20210615021455640](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021455640.png)

<Figure 8-3> GM Region Pipe Kind   Data Definition

표준분석모델의 데이터 특성 이외에 추가한 데이터는 연식, 커브횟수, 변류 수, 기차여부(50M)가 있다.

 

회귀모델에 적용하기위해 종속변수를 관 매설 후 누수날짜까지의 기간으로 연식을 구하였다. 커브점은 관의 유속 방향이 급격하게 바뀌는 이형관의 경우 통계적으로 누수가 되는 횟수가 많아 QGIS상에 도면을 만들 당시 사용했던 Point의 개수를 기준으로 커브의 횟수를 추정하여 첨가하였다. 변류 개수는 관의 주요 누수원인중 관과 관을 연결하는 부위에서 나사 또는 고무링이 부식이 되어 누수가 되는 사례가 많음에 따라 관 별로 접합부의 개수를 넣었다. 누수여부에서 전식으로 인한 누수원인이 있다. 기차길 근처(50M)지역의 전식으로 인한 관의 누수 발생을 파악하기 위해 추가하였다.

 

알고리즘 모델로는 Gradient Boosting을 통한 일반적인 확률 예측을 위한 알고리즘 인 Natural Gradient Boosting (NGBoost)을 제시합니다. 

 

일반적인 회귀 모델은 공 변량을 조건으로 포인트 추정치를 반환하지만 확률 적 회귀 모델은 공 변량을 조건으로 결과 공간에 대한 전체 확률 분포를 출력합니다.

 

 이를 통해 예측 불확실성 추정이 가능합니다. NGBoost는 조건부 분포의 매개 변수를 Multiple parameter boosting algorithm으로 처리하여 Gradient Boosting을 확률 적 회귀로 일반화 합니다. 

 

 또한 다중 매개 변수 부스팅 접근 방식의 훈련을 수정하기 위해 Natural Gradient가 어떻게 필요한지 보여줍니다. NGBoost는 모든 기본 학습자, 연속 매개 변수가 있는 모든 분포 계열 및 모든 채점 규칙을 함께 사용할 수 있습니다. NGBoost는 유연성, 확장성 및 유용성 측면에서 추가적인 이점을 제공하면서 확률 적 예측을 위한 기존 방법의 성능과 일치하거나 능가합니다.


**5.** **연구방법**

 

 

5.1 새로운 누수예측 시스템

 

2021년을 기준으로 누수 예상 기간을 예측 하였다. NGBoost의 성능 평가를 위해 통상 쓰이던 XGBoost 와 비교하여 성능이 더욱 향상되었는지 GridSearchCV를 통해 최적의 Hyper Parameter를 찾고 정확도 지표로써 Mean_absolute_error를 기준으로 비교분석 하였다. 문제의 정의를 위해 [Fig.9]에서 각 모델의 최적의 파라미터를 설정하였다.

 

| Parameter     |       |
| ------------- | ----- |
| Learning_rate | 0.005 |
| N_estimators  | 1000  |

<Figure 9-1> XGBoost Hyper Parameter

| Parameter     |      |
| ------------- | ---- |
| Learning_rate | 0.01 |
| N_estimators  | 300  |

<Figure 9-2> NGBoost Hyper Parameter



두모델의 결과값을 Mean_absolute_error를 비교 하면 [Fig.10]의 결과로써 NGBoost 모델이 더욱 좋은 모델임을 알 수 있다.

| Mean_absolute_error |       |
| ------------------- | ----- |
| XGBoost             | 21.22 |
| NGBoost             | 19.02 |

<Figure 10-1> Model comparison table



 ![image-20210615021524332](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021524332.png)

<Figure 10-2> XGBoost model data



 ![image-20210615021527076](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021527076.png)

<Figure 10-3> NGBoost model data

5.2 연구 프로세스

 

엑셀 데이터를 GIS상에 띄우기 위해 주소데이터로 전 처리 후 Geocoding을 사용하여 좌표 값을 얻고 송수관을 배수관과 급수관으로 용도별 구분 후 누수지점과 상수관을 QGIS의 NNJOIN으로 매칭하여 정확한 관 (급수관, 배수관)의 연식을 구하였다.

NGBoost를 사용하기 위해 Python언어를 사용하였다. 본 논문에서는 GM지역의 상수도 본부의 복구공사대장 데이터와 GM시청의 QGIS상에 있는 관의 데이터를 사용하였다.

 

 

**6.** **실험 및 결과분석-**

 

 

본 연구에서는 결과의 확률까지 계산할 수 있는 NGboost 알고리즘을 이용해서 도시의 관 누수 위험도 예측 문제들을 풀어보았다. 위와 같은 알고리즘을 python을 통해 구현해보았다. Learning_rate를 0.01로 진행하였고, 같은 실험을 300회 반복하여 데이터를 앙상블 하여 구하였다.

 

 모델의 결과치가 나온 원인을 분석하기위해 SHAP알고리즘을 사용하여 추정하였다. 결과치의 특성중요도인 [Fig.11]을 보면 상위 5개의 Feature중 BUILD_Y가 압도적으로 높은 결과가 나왔다. 이는 관의 누수 위험 중 가장 큰 요소로 관의 나이가 중요하다는 의미로 해석된다. 그 외에도 Leak_CNT는 이전에 누수가 되었던 이력이 있는 관이 더욱 자주 누수 되었다는 의미로 보인다. 특성중요도로는 가정까지 밖에 하지 못하기에 나머지 추정은 SHAP알고리즘에서 나온 결과인 [Fig.12]를 보면 된다. 

 

   SHAP의 결과치를 보면 모델이 99라는 기한을 낸 이유가 Leak_CNT=0 이라서 연식이 98.99가 될 것 이라고 예측했다. 이 결과치를 보면 이전에 누수가 나지않은 관이 더욱 오랫동안 누수가 나지 않음을 추정 할 수 있다. 또한 Area_6=0이라는 지역적 특성에 의해 오랜 기간 연식을 가질 수 있다고 설명하고 있다.

 이러한 블랙박스 설명모델을 통해 예측모델이 왜 이러한 판단을 내렸는지 추정이 가능하다.

 

 ![image-20210615021532861](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021532861.png)

<Figure 11> NGBoost Feature Importance



 ![image-20210615021537533](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021537533.png)

<Figure 12-1> SHAP Result

 ![image-20210615021549878](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021549878.png)

 

  

 



NGBoost의 결과치를 2021년기준 남은 누수까지의 연식을 위험할수록 빨강, 주황, 노랑, 파랑, 초록 순으로 5단계로 분류하였다. 

​    

 ![image-20210615021557800](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021557800.png)

<Figure 13-1> Risk visualization    [Five-step classification]

​    ![image-20210615021601266](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021601266.png)

<Figure 13-2> Risk visualization    [Five-step classification]

​    ![image-20210615021604434](/2021-05-06-Korea-Society-of-Industrial-Management-Systems-thesis-presentation.assets/image-20210615021604434.png)

<Figure 13-3> Risk visualization    [Five-step classification]

**7.** **결론 및 향후 과제**

 

 

7.1 결론

 

누수 된 관을 예측했을 때 정확도 범위는 평균 1년 6개월 정도였다. 하지만 결과치에서 -119년이라는 이론상 맞지 않는 데이터가 나왔다. 이상치 예측 값을 확인해보니 모델의 예측 오류 문제가 아닌 관이 1900년에 매설되어 현재까지 사용 중 이라고 최신화가 되어 있지 않은 관 정보가 기입되어 있어서 이상 결과 나온 것 이였다.

 

관을 새로 바꾼 후 갱신하지 않은 데이터로 모델의 결과치를 보고 실수로 누락된 데이터를 갱생하는 것에도 사용할 수 있게 되었다. 

 

GM지역의 관중 누수 위험도가 가장 높은 지역은 역근처의 [Fig.13-2]근방에서 많이 보였다. 이는 추후 관을 갱생 계획시에 우선 지역으로 판단하여 빠른 조치가 필요해 보인다.

 

7.2 향후 과제

 

관은 서로 이어져 있는 관과 영향이 커서 RNN계열의 모델이 정확도를 높이는 것에 도움이 된다. 

 

관끼리 접합 여부가 데이터시스템에 들어가 있고 GISID별 유량의 방향성까지 표시하여야 한다. 또한 누수지점의 GIS 좌표지점이 없어 누수여부를 파악하기 힘든 점을 보완하기 위해 누수지점과 관을 관리하는 부서가 한곳에서 통합하여 처리하여야 할 필요성이 있다.

 

또한 분석을 위한 데이터를 만들기 위해서는 현재 XML데이터로 처리하는 시스템에서는 누락과 데이터 정의의 혼돈의 문제가 발생하기에 상수도관리 시스템을 만들어 정형화 할 필요가 있다.

 

**Acknowledgement**

This paper is the result of sabbatical year support from Kumoh National Institute of Technology 

 

**Python code** 

https://colab.research.google.com/drive/1d1t1M0yHnfzTr-RCsZr8EjrO9VSBqYDs?usp=sharing

**References**

 

[1] Joon Hyun Kim, Min-Woo Park, Soo-Young An, Young-Tae Park, Jong-Hyuck Baek, Development of PC and Web Based Management Systems for Optimal Operation of Waterworks Block and Leakage, Journal of the Environment 9(1), 2012, pp. 65-76.

 

[2] Kang. Bok Seon, Park. Byeong Don, Song. Young Cheol, You. Jeong Oh, Kim. Sung hwan, Real-time Leakage Through Analysis of Artificial Neural Network of Block Flow Data, 2019, 37-38.

[3] Lee. Young sil, Lee. Ji Yeong, Ji. Jong Duck, Improved GIS DB accuracy of water supply facilities, ournal of the Korean Association of Intellectual Information Societies, 2014, pp. 83-99.

 

[4] Shin. Seok hyo, Jung. Sung Tae, Ha. Dae Hwan, Development of Waterworks Management System for a Region Self-Government Group Using,2005,pp. 63-71.

 

[5] Lee. Slee min, Kang. Doo sun, Water pipe deterioration assessment using ANN-Clustering, J. Korea Water Resour. Assoc. Vol. 51, No. 11,2018, pp. 959-969

 

[6] NGBoost: Natural Gradient Boosting for Probabilistic Prediction, Tony Duan, Anand Avati, Daisy Yi Ding, Khanh K. Thai, Sanjay Basu, Andrew Y. Ng, Alejandro Schuler.

 

[7] Nia, Public Big Data Standard Analysis Model Manual (Water leak detected).

 

[8] Development of prediction model of corrosion status and pipe deterioration in water distribution systems_the Department of the Environment

 

[9] A Study on the causes of scale generation and reduction of elution material in old distribution channels

 

[10]  Lundberg, Scott M., and Su-In Lee. "A unified approach to interpreting model predictions." Advances in Neural Information Processing Systems. 2017.

 

[11]  Lundberg, Scott M., Gabriel G. Erion, and Su-In Lee. "Consistent individualized feature attribution for tree ensembles." arXiv preprint arXiv:1802.03888 (2018).

 

[12]  Sundararajan, Mukund, and Amir Najmi. "The many Shapley values for model explanation." arXiv preprint arXiv:1908.08474 (2019).

 

[13]  Janzing, Dominik, Lenon Minorics, and Patrick Blöbaum. "Feature relevance quantification in explainable AI: A causality problem." arXiv preprint arXiv:1910.13413 (2019).

 

ORCID

Sangrak Park| https://orcid.org/0000-0001-5864-7470

