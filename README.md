
# Week 3 Homework - Neural Network Visualizer 🧠
202312143 이민영 week3에 대한 과제 제출입니다. 

---

신경망 기초 개념을 PySide6 GUI로 시각화하는 학습 도구입니다.

---

##  파일 구성

```
week3_hw/
├── main.py              # 메인 앱 (5개 탭 통합)
├── week3_PRD_TRD.docx   # PRD & TRD 문서
└── README.md            # 이 파일
```

---

##  설치 및 실행

### 1. 의존성 설치
```bash
pip install PySide6 numpy matplotlib
```

### 2. 실행
```bash
python main.py
```

---

## Lab 구성

| 탭 | 내용 | 핵심 기능 |
|----|------|-----------|
| Lab 1 | Perceptron | AND/OR/XOR 게이트 학습 + 결정경계 시각화 |
| Lab 2 | Activation Functions | Sigmoid/Tanh/ReLU/Leaky ReLU 비교 그래프 |
| Lab 3 | Forward Propagation | x1, x2 슬라이더로 레이어별 값 시각화 |
| Lab 4 | MLP (XOR 해결) | Loss 곡선 + 비선형 결정경계 |
| Lab 5 | Universal Approximation | 3/10/50 뉴런으로 함수 근사 비교 |

---

##  기술 스택

- **Python** 3.10+
- **PySide6** — GUI 프레임워크
- **NumPy** — 신경망 로직 (Pure NumPy, 외부 ML 라이브러리 없음)
- **Matplotlib** — 그래프 시각화

---

##  핵심 알고리즘

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

##  PRD / TRD

PRD와 NRD를 이용해서 자세한 요구사항 및 기술 설계를 만들었고 이는 `week3_PRD_TRD.docx` 파일에 만들었습니다.
