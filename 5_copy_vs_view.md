# 배열 복사와 뷰 (Copy vs View)

## 📌 개요
NumPy 배열에서 copy와 view는 메모리 관리와 연산 속도에 큰 영향을 줍니다.

## 복사 (Copy)
- 메모리 상 독립적인 새 배열 생성
```python
arr = np.array([1, 2, 3])
copy_arr = arr.copy()
```

## 뷰 (View)
- 원본 배열을 참조 (메모리 공유)
```python
view_arr = arr.view()
```

## 차이점 실습
```python
arr[0] = 99
print(copy_arr)  # → [1 2 3]
print(view_arr)  # → [99 2 3]
```

## 🚀 활용도
- 메모리 최적화가 필요한 대규모 연산
- 데이터 변형 시 의도적 선택 필수
