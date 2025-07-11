# 🔸 10. 선형대수 및 푸리에 변환
---
## 📌 10.1 개념 정의
-  선형대수(Linear Algebra): 행렬 곱셈, 역행렬, 고유값 분해 등의 연산

-  푸리에 변환(Fourier Transform): 신호를 주파수 영역으로 변환

✔️ 과학 계산, 머신러닝, 신호 처리에서 필수

## 🚩 행렬 연산
```
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
np.matmul(a, b)
```

## 🚩 역행렬
```
np.linalg.inv(a)
```

## 🚩 푸리에 변환
```
arr = np.array([1, 2, 3, 4])
np.fft.fft(arr)
```

---

## 🔍 10.2 이론적 배경

-  NumPy는 선형대수 연산을 위해 내부적으로 **BLAS, LAPACK** 라이브러리를 사용

-  푸리에 변환은 빠른 **푸리에 변환 알고리즘 (FFT)** 을 기반으로 동작

✔️ 대규모 선형 시스템 해석, 이미지 변환 등에 활용

---

## 🔁 10.3 동작 원리

-  선형대수는 np.linalg 하위 모듈로 제공

-  푸리에 변환은 np.fft 모듈 사용

-  대부분의 연산은 메모리 효율성을 위해 inplace 연산 지원

---

## 🚩 10.4 주요 선형대수 함수

| 함수                | 설명                 |
| ----------------- | ------------------ |
| np.dot()          | 행렬 곱               |
| np.matmul()       | 행렬 곱 (Python 3.5+) |
| np.linalg.inv()   | 역행렬                |
| np.linalg.det()   | 행렬식                |
| np.linalg.eig()   | 고유값, 고유벡터          |
| np.linalg.solve() | 선형 방정식 풀이          |

---

## 🚩 10.5 주요 푸리에 변환 함수

| 함수             | 설명              |
| -------------- | --------------- |
| np.fft.fft()   | 1D 푸리에 변환       |
| np.fft.ifft()  | 역푸리에 변환         |
| np.fft.fft2()  | 2D 푸리에 변환 (이미지) |
| np.fft.ifft2() | 2D 역푸리에 변환      |
| np.fft.fftn()  | 다차원 푸리에 변환      |

---

## 🚀 10.6 활용 사례

-  이미지 변환: 공간 ↔ 주파수 변환

-  신호 처리: 잡음 제거, 스펙트럼 분석

-  머신러닝: 특성 행렬 변환, PCA 전처리

-  시스템 해석: 전자 회로, 물리 시뮬레이션

---

## 🔍 10.7 코드 예시

```
import numpy as np

# 선형대수
A = np.array([[1, 2], [3, 4]])
inv_A = np.linalg.inv(A)
det_A = np.linalg.det(A)

print("역행렬:\n", inv_A)
print("행렬식:", det_A)

# 푸리에 변환
signal = np.array([0, 1, 0, 0])
fft_signal = np.fft.fft(signal)

print("FFT:", fft_signal)
```

---

## 🚀 10.8 출력 예시

```
역행렬:
 [[-2.   1. ]
  [ 1.5 -0.5]]
행렬식: -2.0000000000000004
FFT: [ 1.+0.j -1.+1.j -1.+0.j -1.-1.j]
```

---

## ✔️ 10.9 주의사항 및 한계

-  역행렬은 존재하지 않는 경우 **(singular matrix)** 오류 발생

-  FFT는 입력 데이터가 정규화되지 않으면 해석 어려움

-  복소수 결과 해석 주의 필요
