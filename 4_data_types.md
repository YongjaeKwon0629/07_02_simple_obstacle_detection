# 데이터 유형 및 변환

## 데이터 유형 확인
```python
arr = np.array([1,2,3])
print(arr.dtype)  # → int32
```

## 데이터 유형 변환
```python
arr = np.array([1.2, 2.5, 3.8], dtype='int')
print(arr)  # → [1 2 3]
```

## 주요 데이터 타입
| 코드 | 설명             |
|------|------------------|
| i    | 정수형 (integer) |
| f    | 실수형 (float)   |
| b    | 불리언 (bool)    |
| U    | 유니코드 문자열  |
