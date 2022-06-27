# Lyric_Generator
#### 1. 프로젝트 개요 : 딥 러닝으로 작사가 실종 사태 방지하기
갑자기 작사가가 사라져 앨범에 넣을 가사가 없다면? 이란 가정을 바탕으로, **인공지능을 통한 작사**를 시도하고 성공한다면 기존에 비해 더 음악제작비를 감소시킬 수 있을 것이라 생각해 프로젝트를 진행함
- 데이터는 음원 사이트에서 특정 가수를 검색해 나온 가사를 활용함

#### 2. 프로젝트 진행 과정
데이터 크롤링 - 전처리 및 토큰화 - 딥 러닝을 통한 학습 - 사전 훈련 모델을 통한 학습 - 외부 사이트를 활용한 학습
- **데이터 크롤링**
  - **selenium** 패키지를 사용해 벅스에서 10cm 노래를 대상으로 진행

- **전처리 및 토큰화**
  - 가사가 없는 연주곡의 경우 삭제하고 딥 러닝에 사용하기 위해 **konlpy의 kkma**를 사용해 토큰화를 진행

- **딥 러닝을 통한 학습**
  - 앞의 토큰을 기억하며 가장 간단히 학습할 수 있는 **LSTM**을 활용해 학습
  - batch size 128, epoch 100으로 간단히 진행하였으며 정확도 0.9962로 측정
  
- **사전 훈련 모델을 통한 학습**
  - 같은 데이터를 현시점 가장 좋은 성과를 보이는 **KOGPT**2를 사용해 학습시킴
  - batch size 16, epoch 500으로 진행하였음

- **외부 사이트를 활용한 학습**
  - **[외부 사이트 ainize](https://ainize.ai/teachable-nlp)**를 사용해 학습시킴

#### 3. 결론
작사가 없는 작사는 가능은 하지만 가사다운 문장이라 판단하긴 어려움  
현재 수준으로는 3가지 방법 중 외부 사이트를 사용한 학습이 가장 가사다운 가사를 만들 수 있음

#### 4. 파일 구성
**1_web_crawl.ipynb** : 크롤링을 진행하고 간단한 전처리를 진행한 파일  
**2_token.ipynb** : 토큰화를 진행한 파일  
**3_easy_model_lstm.ipynb** : lstm 모델을 통해 딥러닝을 진행한 파일  
**4_fine_tuning.ipynb** : 사전 훈련 모델을 통한 학습을 진행한 파일
**5_use_ainize.ipynb** : 외부 사이트를 활용한 학습을 보여주는 파일
chromedriver.exe : selenium 사용을 위한 실행 파일
data.pickle : 크롤링을 통해 모은 데이터를 저장한 파일  
data.txt : 상동  
requirements.txt : 환경설정 데이터를 기록한 파일
token.pickle: 토큰화된 데이터를 저장한  파일  
token.txt : 상동  

#### 5. 프로젝트 진행 기간
22.01.07 ~ 22.01.12

#### 6. 프로젝트 과정에서 느낀 것
- **결과물의 만족도가 낮음**
    - 가수가 발매한 음악이 적으면 딥 러닝의 결과 퀄리티가 낮아질 수밖에 없음
      - 그로 인해 사전 학습 모델을 사용한 것이 결과가 더 좋은 것으로 분석
      - 이를 개선하기 위해선 문학적인 문장만을 학습한 사전 학습 모델이 구축해야 할 것이라 생각함
    - LSTM 모델의 경우 수학적으로 무척 높은 정확도가 나왔으나 실질적으로 가사를 생성했다기엔 문제가 있는 결과인 점이 아쉬웠음

- **딥 러닝 특유의 모호한 진행**  
    - 프로젝트 진행에서 '나'가 아니라 라이브러리의 활용, 구글링의 역할 등이 중요하단 느낌이 듦
    - 딥 러닝 특성 상 내부 과정까지 완전히 이해할 수가 없어서 답답함을 종종 느낌

- **흥미로움**
    - 위 두 문제에도 불구하고 관심 분야와 취미가 섞여 어려운 과정을 푸는 과정이 무척 흥미로웠음
