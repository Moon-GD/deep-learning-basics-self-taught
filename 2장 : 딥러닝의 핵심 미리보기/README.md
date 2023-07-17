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

<br>

<img width="1020" alt="데이터 참조 결과" src="https://github.com/Moon-GD/deep-learning-basics-self-taught/assets/74173976/e3568659-e9df-4cd0-8629-24b8365523bc">


<br>

- data 폴더의 데이터들은 numpy를 활용하여 불러올 수 있음

```python
data_set = np.loadtxt('상대 경로', delimiter=',')  # csv 파일인 경우가 많기에 ,(콤마)로 구분하여 읽도록 설정
```

- 현재 data sample을 살펴보면 아래와 같음

(사진 첨부하기)

- 딥러닝 데이터는 크게 attribute, class로 구분 가능
    - attribute (속성) : 결과 값 도출을 위해 사용될 정보
    - class (클래스) : 대응되는 attribute의 정답
- 현재 데이터 집합에서는, 처음부터 16개의 항목이 attribute, 17번째 항목이 class!
- 따라서 아래와 같이 데이터 집합을 분리

```python
X = Data_set[:, 0:16]  # 16번째 attribute까지의 데이터 셋
y = Data_set[:, 16]  # 17번째 attribute의 데이터 셋
```

- 참고로, 여러 개의 속성이 담기는 집합은 대문자로(위의 X처럼), 하나의 원소만이 담기는 집합은 소문자로(위의 y처럼) 표기하는게 관례

<br>

### 3️⃣ 구조 결정
- 사용된 코드 

```python
model = Sequential()
model.add(Dense(30, input_dim=16, activation='relu'))
model.add(Dense(1, activation='sigmoid'))
```

- 현재로써는 각 code가 무슨 역할을 하는지 하나도 모르겠음... 🤯
- 다만, model.add()를 수행할 때마다 딥러닝의 층을 쌓는다고만 알아두자
    - 현재는 2개의 층을 쌓은 거임!

<br>

### 4️⃣ 모델 실행
- 사용된 코드

```python
model.compile(loss=binary_crossentropy, optimizer='adam', metrics=['accuracy'])
history = model.fit(X, y, epochs=5, batch_size=16)
```

- 이 코드 또한 무슨 역할인지 하나도 모르겠음..
- 여기서 배울 건! 딥러닝은 3️⃣ 구조 결정 단계에서 생성된 여러 개의 층을 위 아래로 오가며 model 최적화를 진행
- 이 때, 몇 번 위 아래 이동을 반복할 것인지, 각 이동마다 몇 개의 데이터를 활용하는지 등을 4️⃣ 모델 실행 단계에서 설정한다고 알아두자!

<br>

---

updated : 2023.07.17 (월)
