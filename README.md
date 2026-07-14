# 📞Voicephishing_detection  
## 📌Project Overview
본 프로젝트는 음성 데이터를 텍스트로 변환한 뒤, KoBERT 기반 자연어처리 모델을 이용하여 보이스피싱 여부를 분류하는 AI 프로젝트입니다.

음성 데이터는 STT(Speech-to-Text)를 통해 텍스트로 변환한 후, KoBERT 분류 모델을 학습시켜 사용자가 업로드 한 음성데이터의 보이스피싱 여부를 분류하고 그 정도를 예측합니다.


## 🎯Project Objectives
- 보이스피싱 분류 모델 구축

	
## 🛠️Tech Stack
### Language
- Python

### AI/Deep Learning
- PyTorch
- KoBERT
- Hugging Face Transformers

### Data Processing
- pandas
- numpy
- scikit-learn
- datasets


## Dataset
데이터는 금융감독원에 업로드되어있는 실제 보이스피싱 사례 음성 데이터와 국립국어원의 언어정보나눔터 일상대화 말뭉치를 수집하여 각각을 보이스피싱 데이터와 일반대화 데이터로 구성했습니다.

### Data Processing
- 데이터 정제
- 클래스 불균형 해소를 위해 일반 대화 데이터를 동일한 개수로 샘플링
- 데이터 셔플
- Train/Validation/Test 분할 (8:1:1)


## 🤖Model
- KoBERT(skt/kobert-base-v1)

### Hyperparameters
|	Parameter	|	Value	|
|---|---|
|	Epoch	|	5	|
|	Learning Rate	|	5e-5	|
|	Optimizer	| AdamW	|
|	Labels	|	2	|


## 🔄Training Pipeline
Text Dataset  
↓  
Data Cleaning  
↓  
Balanced Sampling  
↓  
Train / Validation / Test Split  
↓  
KoBERT Tokenizer  
↓  
KoBERT Fine-tuning  
↓  
Evaluation


## 📊Evaluation Metrics
- Accuracy
- Precision
- Recall
- F1-score

학습 과정에서 validation 성능을 매 epoch마다 확인했으며, 최종적으로는 test dataset에서 모델 성능을 평가하였습니다.


## 💾Model Saving
- Fine-tuned KoBERT Model
- Tokenizer
이를 통해 추론 단계에서 동일한 모델을 사용할 수 있도록 구성했습니다.


## 🚀Future Improvements
- 더 다양한 보이스피싱 데이터 확보
- 데이터 증강을 통한 일반화 성능 향상
