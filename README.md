#개요
1. 코드스테이츠 AI/빅 데이터 부트캠프 섹션 4 프로젝트입니다.  
2. '가수가 갑자기 가사를 쓰지 못한다면 이를 딥러닝을 통해 해결할 수 있지 않을까?'라는 상황을 가정하고, 딥러닝을 활용해 해결해보았습니다.
3. 파일에 적힌 숫자 순서대로 작업을 진행하였습니다. 즉, 1_web_crawl.ipynb를 통해 데이터 크롤링을 진행하고, 2_token.ipynb를 통해 토큰화를 실행하였으며, 3_easy_model_lstm.ipynb를 통해 간단히 모델 학습을 진행하고, 4_fine_tuning.ipynb를 통해 미리 학습된 모델을 활용해 진행한 것을 확인하실 수 있습니다.
4. 이 문서들은 conda 가상환경에서 진행되었습니다. 단, 4_fine_tuning.ipynb의 경우 Google Colab에서 작성되었습니다.
5. pip 등을 통해 추가 설치한 라이브러리는 다음과 같습니다 : konlpy[링크](https://github.com/konlpy/konlpy), gensim, transformers, gluonnlp, sentencepieces, JPype1