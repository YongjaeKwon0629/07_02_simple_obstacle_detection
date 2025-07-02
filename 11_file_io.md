# 파일 입출력

## 📥 저장
```python
arr = np.array([1, 2, 3])
np.save('data.npy', arr)
```

## 📤 불러오기
```python
loaded = np.load('data.npy')
print(loaded)
```

## 🚀 활용도
- 대규모 데이터셋 저장 및 복원
- 학습된 모델 데이터 관리
