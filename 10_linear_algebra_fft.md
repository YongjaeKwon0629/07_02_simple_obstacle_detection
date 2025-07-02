# 선형대수 및 푸리에 변환

## 📌 행렬 연산
```python
a = np.array([[1, 2], [3, 4]])
b = np.array([[5, 6], [7, 8]])
np.matmul(a, b)
```

## 📌 역행렬
```python
np.linalg.inv(a)
```

## 📌 푸리에 변환
```python
arr = np.array([1, 2, 3, 4])
np.fft.fft(arr)
```

## 🚀 활용도
- 머신러닝 선형 모델
- 신호 처리, 이미지 변환
