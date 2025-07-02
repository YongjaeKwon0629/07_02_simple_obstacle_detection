# 🔸 7. 배열 결합과 분할 (Concatenate & Split)

## 📌 배열 결합 (Concatenate)

-  여러 배열을 특정 축을 기준으로 이어 붙이는 연산
  
```
a = np.array([1, 2])
b = np.array([3, 4])
result = np.concatenate((a, b))  # → [1 2 3 4]
```

## 📌 배열 분할 (Split)

-  하나의 배열을 특정 기준으로 나누는 연산
  
```
arr = np.array([1, 2, 3, 4, 5, 6])
result = np.array_split(arr, 3)
```

✔️ 데이터 전처리, 배치 처리, 샘플링 등에서 필수적인 기능입니다.

---

## 🔍 7.2 이론적 배경
✔️ 결합은 메모리 복사가 필수 → 새로운 배열 생성

✔️ 분할 역시 부분 배열을 반환하되, 보통 Copy가 아닌 View 형태로 반환

   → NumPy는 메모리 효율과 연산 최적화를 위해 내부 stride 계산을 활용합니다.

---

## ■ 7.3 동작 원리

**-  결합:** np.concatenate(), np.vstack(), np.hstack(), np.stack()

**-  분할:** np.split(), np.vsplit(), np.hsplit(), np.array_split()

✔️ **축**(axis)을 기준으로 동작하며, **shape**가 일치해야 합니다.

---

## ■ 7.4 수학적 원리 및 메모리 구조

| 연산           | 필요 조건                   | 반환 형태     |
| ------------ | ----------------------- | --------- |
| concatenate  | 결합 축 외 shape 동일         | Copy      |
| stack        | 모든 shape 동일 → 새 축 추가    | Copy      |
| split        | 분할 축의 길이가 분할 수로 나누어져야 함 | View      |
| array\_split | 나누어 떨어지지 않아도 분할 가능      | View/Copy |

✔️ **결합**은 메모리 복사, **분할**은 대부분 stride 기반 View 반환

---

## 🚀 7.5 활용 사례

-  훈련 데이터와 테스트 데이터 결합/분할

-  이미지 패치 생성 및 합치기

-  배치 단위 데이터 분리

---

## ■ 7.6 코드 예시

```
import numpy as np

a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])

# 수직 결합
v_cat = np.vstack((a, b))

# 수평 결합
h_cat = np.hstack((a, b))

# 분할
split_arr = np.split(v_cat, 2)

print("수직 결합:\n", v_cat)
print("수평 결합:\n", h_cat)
print("분할:\n", split_arr)
```

---

## ■ 7.7 출력 예시

```
수직 결합:
 [[1 2]
  [3 4]
  [5 6]
  [7 8]]
수평 결합:
 [[1 2 5 6]
  [3 4 7 8]]
분할:
 [array([[1, 2],
       [3, 4]]), array([[5, 6],
       [7, 8]])]
```

---

## 📌 7.8 주의사항 및 한계
-  **concatenate**는 항상 Copy → 메모리 사용량 증가

-  **split**은 분할 축 크기 불일치 시 ValueError

-  **array_split**은 불균형 분할 가능

