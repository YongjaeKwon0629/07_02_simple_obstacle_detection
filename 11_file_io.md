# 🔸 11. 파일 입출력 (File I/O)
---

## ■ 11.1 개념 정의

-  배열 데이터를 파일로 저장하거나, 파일에서 읽어오는 기능

-  바이너리(.npy, .npz) 또는 텍스트(.csv, .txt) 형식 지원


## 📥 저장

```
arr = np.array([1, 2, 3])
np.save('data.npy', arr)
```

## 📤 불러오기

```
loaded = np.load('data.npy')
print(loaded)
```

---

## 🔍 11.2 이론적 배경

-  **NumPy**는 메모리 효율성을 위해 바이너리 형식 **.npy, .npz**를 권장

- 텍스트 파일은 가독성이 좋지만 저장 용량과 속도 측면에서 비효율적

✔️ 데이터 분석, 머신러닝 모델 저장, 중간 결과 저장에 필수

---

## 🔁 11.3 동작 원리

-  **저장:** np.save(), np.savetxt()

-  **로드:** np.load(), np.genfromtxt(), np.loadtxt()

✔️ 바이너리 저장은 **dtype, shape** 정보까지 포함

✔️ 텍스트 저장은 **float** 또는**int**만 가능하며, 구조 손실 가능

---

## 🔍 11.4 수학적 원리 및 메모리 구조

| 형식   | 저장 방식   | 특징                    |
| ---- | ------- | --------------------- |
| .npy | 바이너리    | 단일 배열 저장 (fast, safe) |
| .npz | 압축 바이너리 | 여러 배열 저장 (zip 구조)     |
| .txt | 텍스트     | 가독성 ↑, 용량 ↑, 속도 ↓     |
| .csv | 텍스트     | 구조화된 데이터 저장           |

✔️ .npy → 메모리 dump 형태로 직렬화

✔️ .npz → zip 압축 내부에 다중 .npy 파일

---

## 📌 11.5 활용 사례
-  머신러닝 데이터셋 저장 및 로드

-  모델 중간 상태 저장

-  대규모 시뮬레이션 데이터 저장 및 공유

---

## 📥11.6 코드 예시

```
import numpy as np

arr = np.arange(6).reshape(2, 3)

# 저장
np.save('array.npy', arr)
np.savetxt('array.txt', arr, fmt='%d')

# 로드
arr_bin = np.load('array.npy')
arr_txt = np.loadtxt('array.txt', dtype=int)

print("바이너리 로드:\n", arr_bin)
print("텍스트 로드:\n", arr_txt)
```

---

## 📤 11.7 출력 예시

```
바이너리 로드:
 [[0 1 2]
  [3 4 5]]
텍스트 로드:
 [[0 1 2]
  [3 4 5]]
```

---

## 🚀 11.8 주의사항 및 한계

✔️ 텍스트 저장은 데이터 타입과 구조 제한 존재

✔️ 바이너리 저장은 NumPy 외부 호환성 낮음

✔️ 대규모 데이터는 npz 사용 추천 (압축)
