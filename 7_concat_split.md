# 배열 결합과 분할

## 배열 결합 (Concatenate)
```python
a = np.array([1,2])
b = np.array([3,4])
result = np.concatenate((a, b))  # → [1 2 3 4]
```

## 배열 분할 (Split)
```python
arr = np.array([1,2,3,4,5,6])
result = np.array_split(arr, 3)  # → [array([1,2]), array([3,4]), array([5,6])]
```
