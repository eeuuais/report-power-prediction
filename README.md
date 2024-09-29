# ARIMA 모델 기반 전력 생산량 예측

### 📣 프로젝트 개요
- 팀 구성 : 4인 팀 프로젝트
- 역할 : 데이터 수집, 예측모델 생성, 각 모델 비교
- 데이터 수집 : FRED(연방 준비 은행 경제 데이터) 활용
- 배운 점 :
    - 시계열 데이터 분석을 진행하면서 분석하고자 하는 데이터가 stationary한 데이터인지 확인하고 검증하는 과정을 주요하게 학습할 수 있었다. 이 과정이 중요한 이유는 우리의 데이터(표본)가 일정한 평균과 분산을 가진 확률 과정(stochastic process)을 따른다고 가정해야만 시계열 예측을 할 수 있기 때문이다. 만약 시간의 흐름에 따라서 이 확률 분포가 크게 변동한다면, 그 실현 값들의 평균이나 분산 등의 의미가 없어져버린다. 그래서 적어도 이 평균과 분산이 우리가 다루고자 하는 확률 과정을 설명하기에 문제가 없도록 하기 위해 정상성(Stationarity)이라는 조건이 필요한 것이다. 본 리포트를 통해 정상성 조건의 당위성을 인지하게 되었고, 앞으로 해나갈 모든 시계열 분석에의 기초가 되는 내용으로 새기게 되었다.
    - 또한 전력생산이라는 평소에는 관심이 덜하던 주제에 대해 다뤄보면서 정책분야의 의사결정권자의 시선을 체험해보는 소중한 기회가 되었다. 정책 결정에도 시계열 분석이 유의미한 insight 를 충분히 얻을 수 있는 도구로 작용하는 것을 알게되었다. 향후 다양한 분야의 데이터 활용에 대한 시야를 넓힐 수 있는 계기가 된 것 같다.

### 🎯 분석목표

---

- 미국의 1985 년부터 2018 년까지 미국의 전기산업의 월별 생산량 데이터를 시계열 분석해보고 그 결과를 통해 미래의 생산량을 예측하는 정량적 모델을 구축해 보고자 한다. 현재 우리나라의 산업통상자원부는 연도별 전력수급동향을 참고하여 장기 전력수급기본계획을 수립하고 있는데, 본 리포트와 같은 시계열적 접근이 많아진다면 우리나라의 향후 전력수급 안정에 이바지할 수 있을 것이다.
- 전력 수요가 생산과 비례하여 정확한 정책이 이루어졌고 생산량이 최적화되어 생산되었다는 가정 하에 전력 생산량 데이터 기반으로 전력 생산량에 대하여 분석하고 예측해보고자 한다.

### 🔍 진행과정

---

- 데이터 확인을 통해 Original 데이터 및 평균과 표준편차를 확인하였다. Augmented Dicekey-Fuller Test를 통해 시계열 데이터가 안정성이 있는지 확인하였으며, Decomposition 단계를 통해 trend를 분리하였다.
- ACF & PACF를 통해 관측 값과의 관계 강도를 확인하였다. 또한 Persistence Model, Autoregression Model, Moving Average Model, ARIMA Model을 통해 10 일 간의 전력 생산량을 예측하고 결과를 MSE로 판단하였다.

### 🔬결론

---

- 전력생산에서의 시계열 예측을 위해 지난 1985 년부터 2018 년까지 미국의 전기생산량의 월별
데이터를 살펴보았다. 데이터를 정상성을 갖춘 데이터로 변환후 Persistence Model, Autoregression Model, Moving Average Model, ARIMA Model을 통해 10 일 간의 전력 생산량을 예측해보고 그 결과는 MSE로 평가하였다.
- 결과는 ARIMA Model 이 성능이 가장 우수한 모델로 나타났다. Moving Average Model과 Autoregression Model 은 본 데이터에 대해 Persistence Model, ARIMA Model 에 비해 성능이 낮은 것으로 확인되었다. 전력생산량이 향후에도 계속 증가할 것임을 예측할 수 있었다. 향후 우리나라 데이터 수집 및 추가 연구를 통해 단기, 장기적인 예측을 해 나간다면 전력 관련 정책 수립 및 국가 재난 상황 등 갑작스러운 전기수요를 방어할 수 있는 대비책을 마련할 수 있을 것이다.
- 현재 전력에 대한 수요는 5G 활성화, 전기차 수요, 이상기온, 4 차 산업혁명 등 여러 요인으로 인해 미래 예측이 매우 불확실하다. 그러나 발전설비는 단기간에 건설이 불가능한 설비이고 짧게는 5년, 길게는 20년 정도의 기간이 필요하므로 장기 전력 수요와 그에 따른 생산량 예측을 통한 발전설비 건설계획이 매우 중요하다. 본 리포트와 같은 시계열적 접근이 많아진다면 우리나라 정책 결정자들이 적절한 전력 공급 계획을 세우는 데 합리적인 기초 자료로서 사용될 수 있을 것이다.

### 🗣️아쉬운 점

---

- 본 리포트의 데이터는 FRED(연방 준비 은행 경제 데이터)의 데이터이며 실제 전력 생산량만을 가지고 분석한 것이다. 전력 생산량은 정책 및 전염병 등 다양한 요인에 의하여 영향을 받을 수 있다. 추가적인 입력변수를 고려하지 않고 분석하였기에 정확한 분석 또는 예측에 한계가 있을 수 있다. 참고 문헌 ‘ARIMA-Intervention 모형을 통한 최대전력 수요예측 연구’에서도 코로나 19 라는 입력변수를 넣은 ARIMA-Intervention 모델이 ARIMA 모델보다 우수한 결과를 제시할 수 있었다고 한다. 따라서, 주요 정책이나 전염병과 같은 여러 입력 변수를 넣어 분석한다면 더욱 성능이 우수한 모델을 제시할 수 있을 것이다.