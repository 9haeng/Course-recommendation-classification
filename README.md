# Course recommendation classification
-----

![image](https://user-images.githubusercontent.com/70729822/193014169-150e1e62-3de8-41b3-a56f-7ed2b7c9f140.png)
![image](https://user-images.githubusercontent.com/70729822/193014210-e25184b1-811c-44f9-8ee3-5a78cf201656.png)


[Ratemyprofessor](https://www.ratemyprofessors.com) 내 수강평에 포함된 지표와 강의계획서를 활용한 강좌 추천 여부를 분류하는 프로젝트



## 프로젝트 배경
----
**대학생들의 수강 신청**은 새 학기가 시작되기 전 이루어집니다.

학생들은 보통 본인이 **필요로하는 강좌의 정보**와 **해당 강좌를 담당하는 교수의 대한 정보**를 종합해 의사결정을 내리는데요.

이번 프로젝트를 통해 학생들이 `리뷰 커뮤니티`와 `교수의 강의계획서`를 통해 해당 강좌의 `추천 여부`를 예측해 의사결정에 활용할 수 있도록

**수강 추천도**를 분류하는 모델을 만들어 보겠습니다.

## 프로젝트 목표
----
다양한 숫자형 feature를 활용한 강좌 추천/ 비추천 분류



## 프로젝트 과정
- 데이터 준비를 위한 EDA 및 전처리
    -  결측값, 중복값 처리
        -  범주형 features
        -  숫자형 features
    - `Target feature` 생성
        - 상관성 확인
- Baseline
    - 다양한 `Classifier`를 활용한 모델 생성과 `Hyper parameter tuning`
         - Feature importance
----
![image](https://user-images.githubusercontent.com/70729822/193017443-d8fdc39f-0816-4dc9-b493-2f33c574e830.png)
- 전처리 과정

![image](https://user-images.githubusercontent.com/70729822/193017670-5c52a98a-3707-42a5-af2a-5bf68e2fc7df.png)
![image](https://user-images.githubusercontent.com/70729822/193017726-a9f1bdb0-e548-41b1-9e13-a566e7ef5b49.png)
![image](https://user-images.githubusercontent.com/70729822/193017758-c8f114b9-bc36-4594-8f4c-3b9385e58343.png)

- `EDA`

![image](https://user-images.githubusercontent.com/70729822/193017964-2d0b6eba-a0cd-45ed-8c53-731f731bd958.png)

- 상관성 확인

![image](https://user-images.githubusercontent.com/70729822/193018041-34c5a4dc-6ce6-4453-997a-362a82ed6937.png)

- `Classifier` 별 최적의 파라미터 적용 후 `confusion matrix`

![image](https://user-images.githubusercontent.com/70729822/193018208-bcd62c9a-3c50-454e-9091-f8d2dadad343.png)

- `Classifier` 별 `Feature importance`

## 결론 및 후기
----
다양한 `Classifier` 와 `GridSearchCV`를 통한 하이퍼 파라미터 튜닝으로 각 모델들을 학습해 보았습니다.

성능을 평가하자면 주어진 데이터를 활용해 2가지 라벨을 분류해내는 능력이 좋지는 않았습니다. 

하지만 각 모델별로 개별 특성들의 중요도를 얼만큼 여기는지 확인하고, 공통적으로 중요하다 여긴 피쳐를 알아냄으로써,

학생들이 **교수의 강좌를 평가**할 때 **어떤 부분을 가장 중요하게 여기는지** 알 수 있었습니다.

### **그렇다면 왜 성능이 좋지 못했을까요?**

제 견해를 말씀드리자면 모델 학습을 진행하기 전 제거한 feature 중 `comment`의 영향력이 다른 수치형 feature들 보다 더 컸을 거로 생각합니다.

1. 교수의 강좌 구성에는 시험의 양이 많다,
2. 교수의 강좌 구성이 훌륭하다.

이런 질문에 대해 `예 / 아니오`로 구성된 Feature보다, 학생이 직접 말로 풀어낸 데이터가 전달하는 `feature importance`가 더 많이 담겨 있을 거라는 가정을 남기겠습니다.

### **다음 목표**

이번 프로젝트에서 수치형 데이터들을 활용해 강좌 추천 여부를 분류하는 모델을 만들어봤다면,

다음 프로젝트 에서는 데이터속 `comment`를 활용해 강좌 추천 여부를 분류하는 프로젝트를 진행할 계획입니다.

감사합니다.


