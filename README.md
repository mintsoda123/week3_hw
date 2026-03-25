# Week 3 Homework - Neural Network Visualizer 🧠
202312143 이민영 week3에 대한 과제 제출입니다.

---

신경망 기초 개념을 PySide6 GUI로 시각화하는 학습 도구입니다.

---

## 📁 파일 구성

```
week3_hw/
├── main.py              # 메인 앱 (5개 탭 통합)
├── week3_PRD_TRD.docx   # PRD & TRD 문서
└── README.md            # 이 파일
```

---

## ⚙️ 설치 및 실행

### 1. 의존성 설치
```bash
pip install PySide6 numpy matplotlib
```

### 2. 실행
```bash
python main.py
```

---

## 🔬 Lab 구성

| 탭 | 내용 | 핵심 기능 |
|----|------|-----------|
| Lab 1 | Perceptron | AND/OR/XOR 게이트 학습 + 결정경계 시각화 |
| Lab 2 | Activation Functions | Sigmoid/Tanh/ReLU/Leaky ReLU 비교 그래프 |
| Lab 3 | Forward Propagation | x1, x2 슬라이더로 레이어별 값 시각화 |
| Lab 4 | MLP (XOR 해결) | Loss 곡선 + 비선형 결정경계 |
| Lab 5 | Universal Approximation | 3/10/50 뉴런으로 함수 근사 비교 |

---

## 🛠️ 기술 스택

- **Python** 3.10+
- **PySide6** — GUI 프레임워크
- **NumPy** — 신경망 로직 (Pure NumPy, 외부 ML 라이브러리 없음)
- **Matplotlib** — 그래프 시각화

---

## 📐 핵심 알고리즘

### Perceptron 학습 규칙
```
w_new = w_old + η × (y - ŷ) × x
b_new = b_old + η × (y - ŷ)
```

### MLP Forward / Backward
```
Forward:  z1 = X @ W1 + b1,  a1 = ReLU(z1)
          z2 = a1 @ W2 + b2,  a2 = Sigmoid(z2)
Backward: Chain Rule로 gradient 계산 후 가중치 업데이트
```

---

## 📄 PRD / TRD

PRD / TRD를 이용한 자세한 요구사항 및 기술 설계는 `week3_PRD_TRD.md` 파일을 참고해주십시오.

---

# Week3 스스로 해보기 — 신경망 구현 실습

> Week3 week3.md의 **스스로 해보기** 문제 1~5번을 직접 구현한 결과물입니다.

---

## 실습 개요

| 번호 | 파일 | 주제 | 기반 파일 |
|:----:|------|------|-----------|
| 1 | `ex01_hidden_neurons.py` | 은닉층 뉴런 수 바꿔보기 (2, 8, 16) | `04_mlp_numpy.py` |
| 2 | `ex02_learning_rate.py` | 학습률 조정 (0.1, 0.5, 1.0) | `04_mlp_numpy.py` |
| 3 | `ex03_activation_compare.py` | 다른 활성화 함수 시도 | `02_activation_functions.py` + `04_mlp_numpy.py` |
| 4 | `ex04_three_layer.py` | 3-Layer 네트워크 구현 | `03_forward_propagation.py` + `04_mlp_numpy.py` |
| 5 | `ex05_mnist.py` | MNIST 데이터셋 도전 | `04_mlp_numpy.py` |

---

## 문제 1 — 은닉층 뉴런 수 바꿔보기

**파일:** `ex01_hidden_neurons.py`

XOR 문제를 기준으로 은닉층 뉴런 수를 **2 / 8 / 16**으로 바꿔가며 성능을 비교했습니다.

- 구조: `입력(2) → 은닉층(n) → 출력(1)` (Sigmoid 활성화, 역전파)
- 뉴런 2개: 표현력이 부족해 XOR 학습이 불안정할 수 있음
- 뉴런 8개: 적절한 표현력으로 XOR 완벽 학습
- 뉴런 16개: 과잉 표현력 (학습은 되지만 과적합 위험)

**결과물:** `outputs/ex01_hidden_neurons.png` (결정 경계 + Loss 곡선 비교)

**핵심 학습:** 문제 복잡도에 맞는 뉴런 수 선택이 중요하다.

---

## 문제 2 — 학습률 조정

**파일:** `ex02_learning_rate.py`

XOR 문제에서 학습률을 **0.1 / 0.5 / 1.0**으로 바꿔가며 수렴 속도와 안정성을 비교했습니다.

- `lr=0.1` (낮음): 안정적이지만 수렴이 느림
- `lr=0.5` (중간): 균형 잡힌 수렴 속도 (`04_mlp_numpy.py`의 기본값)
- `lr=1.0` (높음): 빠르게 수렴하거나 Loss가 진동(발산)할 수 있음

**결과물:** `outputs/ex02_learning_rate.png`, `outputs/ex02_learning_rate_compare.png`

**핵심 학습:** 학습률이 너무 크면 발산, 너무 작으면 학습이 느리다.

---

## 문제 3 — 다른 활성화 함수 시도

**파일:** `ex03_activation_compare.py`

`02_activation_functions.py`에서 배운 활성화 함수 3가지를 실제 MLP에 적용해 XOR 문제를 풀었습니다.

| 활성화 함수 | 출력 범위 | 특징 |
|------------|----------|------|
| Sigmoid | (0, 1) | 기울기 소실 위험, 이진 분류 출력층에 적합 |
| Tanh | (-1, 1) | 0 중심 → Sigmoid보다 학습 빠름 |
| ReLU | [0, ∞) | 계산 빠름, 현대 신경망의 표준 (Dying ReLU 주의) |

- 출력층은 항상 Sigmoid 사용 (이진 분류)
- 은닉층 활성화 함수만 교체하며 비교

**결과물:** `outputs/ex03_activation_compare.png`, `outputs/ex03_activation_functions.png`

**핵심 학습:** 은닉층은 ReLU/Tanh, 출력층은 Sigmoid(이진)/Softmax(다중분류).

---

## 문제 4 — 3-Layer 네트워크 구현

**파일:** `ex04_three_layer.py`

`03_forward_propagation.py`의 순전파 구조를 참고해 은닉층 3개짜리 네트워크를 직접 구현했습니다.

```
입력층(2) → 은닉층1(ReLU) → 은닉층2(ReLU) → 은닉층3(ReLU) → 출력층(Sigmoid)
```

- **역전파 4단계** (체인룰): δ4 → δ3 → δ2 → δ1
- **테스트 문제:** 원형(Circle) 분류 — XOR보다 복잡한 비선형 문제
- 1층 은닉층 vs 3층 은닉층 성능 비교 포함
- XOR 문제도 3층으로 추가 검증

**결과물:** `outputs/ex04_three_layer.png`

**핵심 학습:** 층이 깊어질수록 복잡한 경계를 학습할 수 있고, 역전파는 레이어마다 체인룰을 반복 적용한다.

---

## 문제 5 — MNIST 데이터셋 도전

**파일:** `ex05_mnist.py`

`04_mlp_numpy.py`의 MLP를 실제 손글씨 숫자 데이터셋(MNIST)에 적용했습니다.

**네트워크 구조:**
```
784(입력) → 128(ReLU) → 64(ReLU) → 10(Softmax)
총 파라미터: 109,386개
```

**학습 설정:**
- 데이터: 학습 60,000개 / 테스트 10,000개
- 정규화: 픽셀값 0~255 → 0~1
- 레이블: One-hot 인코딩
- 손실 함수: Cross-Entropy
- 배치 크기: 256 (미니배치 SGD)
- 에포크: 10

**결과물:** `outputs/ex05_mnist.png`, `outputs/ex05_mnist_samples.png`
- Loss 곡선, 정확도 곡선, 숫자별 정확도, 혼동 행렬(Confusion Matrix) 포함

**핵심 학습:** numpy MLP가 실제 데이터에서도 동작하며, Softmax + Cross-Entropy로 다중 분류를 구현할 수 있다.

---

## 실행 방법

```bash
# 1~4번: 추가 설치 불필요
python ex01_hidden_neurons.py
python ex02_learning_rate.py
python ex03_activation_compare.py
python ex04_three_layer.py

# 5번: scikit-learn 필요
pip install scikit-learn
python ex05_mnist.py
```

결과 이미지는 week3.md의 01~05의 결과와 함께 week3_hw의 Do_Own 폴더에 저장했습니다.

---

## 사용한 라이브러리

- `numpy` — 신경망 순전파 / 역전파 구현
- `matplotlib` — 결정 경계, Loss 곡선, 혼동 행렬 시각화
- `scikit-learn` — MNIST 데이터 로드 (ex05만 해당)
