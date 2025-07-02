# 검색과 필터링

## 값 검색
```python
arr = np.array([10,20,30,40,50])
result = np.where(arr > 30)  # → (array([3,4]),)
```

## 조건 필터링
```python
arr = np.array([41,42,43,44])
filtered = arr[arr > 42]  # → [43,44]
```
