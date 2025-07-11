# 🔸 9.수학 및 통계 함수

## 📌 9.1 개념 정의

-  **NumPy**는 배열 기반의 수학 연산 및 통계 함수들을 제공합니다.

-  반복문 없이 벡터화 연산을 통해 빠르고 효율적인 계산 가능.
### 🚩수학 함수
  
```
arr = np.array([1, 2, 3])
result = np.add(arr, arr)  # → [2 4 6]
```

### 🚩통계 함수

```
arr = np.array([1, 2, 3, 4, 5])
np.mean(arr)    # 평균
np.median(arr)  # 중앙값
np.std(arr)     # 표준편차
```

---

## 🔍 9.2 이론적 배경

✔️ **NumPy**는 내부적으로 C 언어 기반의 수치 연산 라이브러리 (BLAS, LAPACK)를 활용합니다.

✔️ 메모리 연속성과 **SIMD(Vectorization)** 최적화를 통해 빠른 연산 지원.

---
## 🔁 9.3 동작 원리

-  브로드캐스팅 규칙에 따라 배열 연산 자동 확장

-  통계 함수는 축(axis) 별로 적용 가능
 
---

## 🔍 9.4 주요 수학 함수

| 함수           | 설명   |
| ------------ | ---- |
| np.sum()     | 합계   |
| np.mean()    | 평균   |
| np.std()     | 표준편차 |
| np.var()     | 분산   |
| np.min()     | 최소값  |
| np.max()     | 최대값  |
| np.cumsum()  | 누적 합 |
| np.cumprod() | 누적 곱 |

✔️ → **axis** 인자를 통해 차원별로 연산 가능

---

## 📌 9.5 활용 사례
-  데이터 분석 평균/표준편차 계산

-  시계열 데이터 누적 합산

-  머신러닝 데이터 정규화

---

## 🔁 9.6 코드 예시

```
import numpy as np

arr = np.array([[1, 2, 3], [4, 5, 6]])

print("합계:", np.sum(arr))
print("평균 (axis=0):", np.mean(arr, axis=0))
print("표준편차:", np.std(arr))
print("누적합:", np.cumsum(arr))
```

---

##  🚀 9.7 출력 예시

```
합계: 21
평균 (axis=0): [2.5 3.5 4.5]
표준편차: 1.707825127659933
누적합: [ 1  3  6 10 15 21]
```

---

## ■ 9.8 주의사항 및 한계
✔️매우 큰 배열에서는 부동소수점 오차 누적 가능

✔️데이터 타입(dtype)에 따라 정밀도 차이 발생

---

## 🚀 활용도
- 데이터의 중심성과 산포도 이해
- 머신러닝 입력값 정규화
