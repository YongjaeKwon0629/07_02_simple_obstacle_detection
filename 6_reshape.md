# 배열 형태 변경 (Reshape)

## 📌 개요
Reshape는 데이터를 변경하지 않고 배열의 형태만 변경합니다. 데이터의 총 요소 수는 변하지 않습니다.

## 사용법
```python
arr = np.array([1, 2, 3, 4, 5, 6])
reshaped = arr.reshape(2, 3)
```

## 자동 계산
```python
reshaped = arr.reshape(-1, 2)  # 행 자동 계산
```

## 🚀 활용도
- 딥러닝에서 입력 데이터 형식 변환 (예: 이미지 → (28,28))
- 시계열 데이터 → (batch_size, time_step, feature)로 변경
