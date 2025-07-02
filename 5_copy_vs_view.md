# 🔸배열 복사와 뷰 (Copy vs View)

## 📌 5.1 개념 정의

**-  View:** 메모리 데이터를 공유하는 배열의 또 다른 시각화
  
```python
view_arr = arr.view()
```

**-  Copy:** 메모리를 복제하여 완전히 독립적인 배열 생성
  
```
arr = np.array([1, 2, 3])
copy_arr = arr.copy()
```

✔️ → **View**는 메모리 절약, **Copy**는 데이터 보호에 유리합니다.

---

**-차이점 실습**
```
arr[0] = 99
print(copy_arr)  # → [1 2 3]
print(view_arr)  # → [99 2 3]
```

---

## ■ 5.2 이론적 배경

-  **NumPy**는 메모리 효율성을 위해 **슬라이싱**, reshape 등의 연산 시 **View**(데이터 공유)를 반환합니다.

-  **팬시 인덱싱, astype** 등 일부 연산은 반드시 **Copy** (데이터 복사)를 반환합니다.

## 🔁 5.3 동작 원리

**-  슬라이싱:** View 반환 → 메모리 공유

**-  팬시 인덱싱:** Copy 반환 → 메모리 복사

**-  .copy():** 명시적 복사

**-  .reshape():** stride만 변경 → View 반환 (가능한 경우)

✔️ **View**는 **메모리 주소**(base)와 **strides**를 공유합니다.
  
✔️ **Copy**는 **새로운 메모리 공간을 할당**합니다.

---

## 🔍 5.4 수학적 원리 및 메모리 구조

| 연산 유형         | 메모리 공유                   | 메모리 복사 | 적용 사례    |
| ------------- | ------------------------ | ------ | -------- |
| 슬라이싱          | O                        | X      | View     |
| 팬시 인덱싱        | X                        | O      | Copy     |
| astype        | X                        | O      | dtype 변환 |
| reshape       | O (가능시)                  | X      | 차원 변경    |
| ravel/flatten | ravel=View, flatten=Copy |        | 1D 변환    |

---

## 🔍 5.5 활용 사례

-  대규모 데이터 메모리 절약: **View 활용**

-  데이터 독립 필요: **Copy 사용**

-  딥러닝 배치 데이터 생성 시 **View 활용** (속도 ↑ 메모리 ↓)

---

## 🚀 5.6 코드 예시

```
import numpy as np

arr = np.arange(6).reshape(2, 3)
view_arr = arr[:, :2]     # View
copy_arr = arr[:, :2].copy() # Copy

# View 변경
view_arr[0, 0] = 999

print("원본 배열:\n", arr)
print("View 배열:\n", view_arr)
print("Copy 배열:\n", copy_arr)
```

---

## 🚀 5.7 출력 예시

```
원본 배열:
 [[999   1   2]
  [ 3   4   5]]
View 배열:
 [[999   1]
  [ 3   4]]
Copy 배열:
 [[0 1]
  [3 4]]
```

---

## ■ 5.8 주의사항 및 한계

✔️ View를 변경하면 원본 배열도 변경됨 → **의도하지 않은 오류 주의**

✔️ Copy는 **메모리 추가 소비** 발생

✔️ **팬시 인덱싱은 항상 Copy임** → 메모리 최적화 주의
