# 파일 입출력

## 저장
```python
arr = np.array([1, 2, 3])
np.save('myarray', arr)
```

## 불러오기
```python
loaded = np.load('myarray.npy')
print(loaded)
```
