# 배열 복사와 뷰 (Copy vs View)

## 복사 (Copy)
원본과 독립된 배열을 생성합니다.
```python
arr = np.array([1,2,3])
x = arr.copy()
```

## 뷰 (View)
원본 데이터에 대한 포인터만 복사합니다.
```python
y = arr.view()
```

## 차이점 실습
```python
arr[0] = 42
print(x)  # → [1, 2, 3] (독립)
print(y)  # → [42, 2, 3] (원본 반영)
```
