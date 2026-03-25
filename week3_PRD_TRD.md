# 🧠 Week 3 Homework — Neural Network Visualizer

<div align="center">

![Project](https://img.shields.io/badge/Project-Neural_Network_Visualizer-1F3864?style=for-the-badge&logo=python&logoColor=white)
![Version](https://img.shields.io/badge/Version-v1.0-2E75B6?style=for-the-badge)
![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=for-the-badge&logo=python&logoColor=white)
![PySide6](https://img.shields.io/badge/GUI-PySide6-41CD52?style=for-the-badge&logo=qt&logoColor=white)

</div>

---

# 📋 PRD (Product Requirements Document)

## 1. 제품 개요

### 1.1 목적

> Week 3에서 학습한 신경망 기초 개념을 **PySide6 GUI**로 시각화하여 직관적으로 이해할 수 있도록 돕는 학습 도구입니다.
> Perceptron, Activation Functions, Forward Propagation, MLP, Universal Approximation 5개 Lab을 하나의 앱으로 통합합니다.

### 1.2 대상 사용자

- 🎓 신경망 기초를 처음 학습하는 학생
- 📊 수학적 개념을 시각적으로 이해하고 싶은 학습자
- 🤖 AI / ML 입문자

### 1.3 핵심 가치

| 가치 | 설명 |
|------|------|
| ⚡ 인터랙티브 | 파라미터를 조작하면 실시간으로 그래프가 변함 |
| 👁️ 직관적 | 복잡한 수식을 시각화하여 이해 용이 |
| 🗂️ 통합 | 5개 Lab이 하나의 앱에 탭으로 구성 |

---

## 2. 기능 요구사항

### 🔬 Lab 1 — Perceptron

| 기능 ID | 기능명 | 설명 | 우선순위 |
|---------|--------|------|----------|
| F-01 | 게이트 선택 | AND / OR / XOR 게이트 선택 드롭다운 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-02 | 학습 실행 | Train 버튼 클릭 시 퍼셉트론 학습 실행 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-03 | 결정경계 시각화 | 학습 후 결정 경계선을 matplotlib으로 표시 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-04 | 정확도 표시 | 학습 결과 정확도(%) 레이블로 표시 | ![Medium](https://img.shields.io/badge/Medium-f39c12?style=flat-square) |

### ⚡ Lab 2 — Activation Functions

| 기능 ID | 기능명 | 설명 | 우선순위 |
|---------|--------|------|----------|
| F-05 | 함수 선택 | Sigmoid / Tanh / ReLU / Leaky ReLU 체크박스 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-06 | 함수 그래프 | 선택된 함수를 같은 축에 비교 플롯 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-07 | 미분 그래프 | 함수와 미분값을 나란히 표시 | ![Medium](https://img.shields.io/badge/Medium-f39c12?style=flat-square) |

### 🔄 Lab 3 — Forward Propagation

| 기능 ID | 기능명 | 설명 | 우선순위 |
|---------|--------|------|----------|
| F-08 | 입력값 설정 | x1, x2 슬라이더로 입력값 조절 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-09 | 레이어 시각화 | z, a 값을 단계별로 표시 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-10 | 네트워크 다이어그램 | 뉴런 연결 구조 시각화 | ![Medium](https://img.shields.io/badge/Medium-f39c12?style=flat-square) |

### 🧠 Lab 4 — MLP (XOR 해결)

| 기능 ID | 기능명 | 설명 | 우선순위 |
|---------|--------|------|----------|
| F-11 | 학습률 설정 | Learning Rate 슬라이더 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-12 | 은닉층 뉴런 수 | Hidden neurons 스핀박스 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-13 | 학습 시작 | Train 버튼으로 학습 실행 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-14 | Loss 그래프 | 에폭별 Loss 감소 실시간 플롯 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-15 | 결정경계 표시 | 학습 후 비선형 결정경계 시각화 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |

### 🌌 Lab 5 — Universal Approximation

| 기능 ID | 기능명 | 설명 | 우선순위 |
|---------|--------|------|----------|
| F-16 | 함수 선택 | Sine / Step / Complex 함수 선택 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-17 | 뉴런 수 조절 | 3 / 10 / 50 뉴런 비교 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-18 | 근사 결과 비교 | 원본 함수와 근사 함수 오버레이 플롯 | ![High](https://img.shields.io/badge/High-2ecc71?style=flat-square) |
| F-19 | MSE 표시 | 각 뉴런 수별 MSE 수치 표시 | ![Medium](https://img.shields.io/badge/Medium-f39c12?style=flat-square) |

---

## 3. 비기능 요구사항

| 항목 | 요구사항 |
|------|----------|
| ⚡ 성능 | 버튼 클릭 후 2초 이내 그래프 렌더링 |
| 🖥️ 호환성 | Windows 10/11, Python 3.10+ |
| 🎨 UI | 탭 기반 단일 윈도우, 최소 해상도 1280×720 |
| 📦 의존성 | PySide6, numpy, matplotlib만 사용 (외부 ML 라이브러리 없음) |

---

# 🔧 TRD (Technical Requirements Document)

## 1. 기술 스택

| 구분 | 기술 | 버전 | 용도 |
|------|------|------|------|
| ![Python](https://img.shields.io/badge/-Python-3776AB?style=flat-square&logo=python&logoColor=white) | Python | 3.10+ | 전체 구현 |
| ![Qt](https://img.shields.io/badge/-PySide6-41CD52?style=flat-square&logo=qt&logoColor=white) | PySide6 | 최신 | 위젯, 레이아웃, 이벤트 |
| ![NumPy](https://img.shields.io/badge/-NumPy-013243?style=flat-square&logo=numpy&logoColor=white) | NumPy | 최신 | 행렬연산, 신경망 구현 |
| ![Matplotlib](https://img.shields.io/badge/-Matplotlib-11557c?style=flat-square) | Matplotlib | 최신 | 그래프 렌더링 |
| — | matplotlib-backend-qt | — | PySide6에 matplotlib 삽입 |

---

## 2. 아키텍처

### 2.1 파일 구조

```
week3_hw/
├── main.py              # 진입점, MainWindow (QTabWidget)
│   ├── Lab1Tab          # 🔬 Perceptron
│   ├── Lab2Tab          # ⚡ Activation Functions
│   ├── Lab3Tab          # 🔄 Forward Propagation
│   ├── Lab4Tab          # 🧠 MLP (XOR)
│   └── Lab5Tab          # 🌌 Universal Approximation
├── week3_PRD_TRD.md     # 이 문서
└── README.md
```

### 2.2 클래스 구조

| 클래스 | 상속 | 역할 |
|--------|------|------|
| `MainWindow` | `QMainWindow` | 앱 진입점, 탭 컨테이너 |
| `Lab1Tab` | `QWidget` | Perceptron 게이트 학습 UI |
| `Lab2Tab` | `QWidget` | 활성화함수 비교 UI |
| `Lab3Tab` | `QWidget` | Forward Pass 단계 시각화 UI |
| `Lab4Tab` | `QWidget` | MLP XOR 학습 UI |
| `Lab5Tab` | `QWidget` | Universal Approximation UI |
| `Perceptron` | — | 퍼셉트론 학습 / 예측 로직 |
| `MLP` | — | NumPy 기반 2-layer MLP |

---

## 3. 핵심 알고리즘

### 3.1 Perceptron 학습 규칙

```
w_new = w_old + η × (y - ŷ) × x
b_new = b_old + η × (y - ŷ)
활성화 함수: 계단 함수 (출력 >= 0이면 1, 아니면 0)
```

### 3.2 MLP Forward / Backward

```
Forward:
  z1 = X @ W1 + b1
  a1 = ReLU(z1)
  z2 = a1 @ W2 + b2
  a2 = Sigmoid(z2)

Loss:
  L = mean((a2 - y)²)

Backward:
  dz2 = a2 - y
  dW2 = a1.T @ dz2 / m
  da1 = dz2 @ W2.T,  dz1 = da1 * relu_deriv(z1)
  dW1 = X.T @ dz1 / m

Update:
  W -= lr * dW
  b -= lr * db
```

### 3.3 Universal Approximation 네트워크

```
구조: Input(1) → Hidden(N, ReLU) → Output(1, 선형)
최적화: SGD, 학습률 0.005, 에폭 8000
평가: MSE = mean((y_pred - y_true)²)
```

---

## 4. UI 레이아웃 설계

| 탭 | 레이아웃 | 좌측 (컨트롤) | 우측 (시각화) |
|----|----------|---------------|---------------|
| 🔬 Lab1 | QHBoxLayout | 게이트 선택, Train 버튼, 결과 레이블 | matplotlib 결정경계 |
| ⚡ Lab2 | QHBoxLayout | 함수 체크박스, 범위 슬라이더 | matplotlib 함수/미분 그래프 |
| 🔄 Lab3 | QHBoxLayout | x1, x2 슬라이더 | 네트워크 다이어그램 + 값 표시 |
| 🧠 Lab4 | QHBoxLayout | LR, neurons 설정, Train 버튼 | Loss 그래프 + 결정경계 |
| 🌌 Lab5 | QHBoxLayout | 함수 선택, 뉴런 수 | 원본 vs 근사 오버레이 플롯 |

---

## 5. 실행 방법

```bash
# 1. 의존성 설치
pip install PySide6 numpy matplotlib

# 2. 실행
python main.py
```

---

## 6. 개발 일정

| 단계 | 작업 | 산출물 | 상태 |
|------|------|--------|------|
| 1 | PRD/TRD 작성 | 이 문서 | ![Done](https://img.shields.io/badge/Done-2ecc71?style=flat-square) |
| 2 | 신경망 로직 구현 | Perceptron, MLP 클래스 | ![Done](https://img.shields.io/badge/Done-2ecc71?style=flat-square) |
| 3 | PySide6 UI 구성 | 5개 탭 위젯 | ![Done](https://img.shields.io/badge/Done-2ecc71?style=flat-square) |
| 4 | matplotlib 연동 | FigureCanvasQTAgg 삽입 | ![Done](https://img.shields.io/badge/Done-2ecc71?style=flat-square) |
| 5 | 통합 테스트 & GitHub 업로드 | 최종 main.py | ![Done](https://img.shields.io/badge/Done-2ecc71?style=flat-square) |
