# 🔸배열 복사와 뷰 (Copy vs View)

## 📌 5.1 개념 정의

-  View: 메모리 데이터를 공유하는 배열의 또 다른 시각화
  
```python
view_arr = arr.view()
```

-  Copy: 메모리를 복제하여 완전히 독립적인 배열 생성
  
```
arr = np.array([1, 2, 3])
copy_arr = arr.copy()
```

✔️ → View는 메모리 절약, Copy는 데이터 보호에 유리합니다.

---

## 차이점 실습
```
arr[0] = 99
print(copy_arr)  # → [1 2 3]
print(view_arr)  # → [99 2 3]
```

## 🚀 활용도
- 메모리 최적화가 필요한 대규모 연산
- 데이터 변형 시 의도적 선택 필수
