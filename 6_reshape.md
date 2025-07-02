# 배열 형태 변경 (Reshape)

## reshape의 역할
배열의 데이터를 변경하지 않고 배열의 구조만 바꿉니다.

## 사용 예시
```python
arr = np.array([1, 2, 3, 4, 5, 6])
reshaped = arr.reshape(2, 3)
```

## 자동 계산 기능
```python
arr.reshape(-1, 2)
```

## 주의
요소의 총 개수는 변경 불가
