# Chapter 2 : 딥러닝의 핵심 미리보기

<br>

## 1. 처음 다루게 될 딥러닝 코드
### 1️⃣ 기존 환자 데이터를 토대로 새로운 환자의 수술 결과를 예측하는 모델
- <a href="https://colab.research.google.com/drive/1jkKmyC4OW4qdLMDlCLrpRSsildhcxm52?usp=sharing">Colab code</a>

<br>

## 2. 딥러닝 code 분석
### 1️⃣ 환경 준비
- 딥러닝 코드 작성을 위해 필요한 라이브러리나 외부 API를 명시적으로 표현해주는 공간
- 주어진 코드

```python
from tensorflow.keras.models import Sequential  # keras에서 Sequentials 함수 가져오기
from tensorflow.keras.layers import Dense  # keras에서 Dense 함수 가져오기
import numpy as np
```

<br>

### 2️⃣ 데이터 준비
- 데이터 준비 방법 : 직접 업로드 & github 참조
- github에서 데이터를 가져오는 방법

```python
!git clone 'github link'
```

- 위의 코드를 실행하면 활성화 중인 Colab 공간에 data라는 폴더가 생기는 것을 확인할 수 있음
<img width="1020" alt="데이터 참조 결과" src="https://github.com/Moon-GD/deep-learning-basics-self-taught/assets/74173976/e3568659-e9df-4cd0-8629-24b8365523bc">


<br>

---

updated : 2023.07.17 (월)
