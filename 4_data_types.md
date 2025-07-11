# 🔸 4. 데이터 유형 및 변환

## ■ 4.1 개념 정의

NumPy 배열은 **고정된 데이터 타입(dtype)**을 가집니다. dtype은 배열 요소의 메모리 크기와 수치 표현 방식을 결정합니다.

## 🔍 4.2 이론적 배경

-  **NumPy**는 C 언어 기반의 고정 타입 배열을 사용합니다.

-  **Python** 리스트는 서로 다른 타입 허용 → 느림

-  **NumPy**는 동질적 타입만 허용 → 연산 최적화 가능

✔️ 데이터 타입은 **메모리 사용량, 연산 속도, 정밀도**에 직결됩니다.

## 🔍 4.3 동작 원리

-  배열 생성 시 자동으로 **dtype 결정 또는 명시 가능**

-  **astype**을 통해 타입 변환 가능

-  타입 혼합 시 자동 업캐스팅(upcasting) 적용

## 🔍 4.4 수학적 원리 및 메모리 구조

| dtype   | 크기 | 값 범위            | 용도              |
| ------- | -- | --------------- | --------------- |
| int8    | 1B | -128 \~ 127     | 메모리 제한된 환경      |
| uint8   | 1B | 0 \~ 255        | 이미지 픽셀 데이터      |
| int32   | 4B | 정수              | 표준 정수형          |
| float32 | 4B | 단정밀도 부동소수점      | GPU 최적화 연산      |
| float64 | 8B | 배정밀도 부동소수점 (기본) | 고정밀 수치 계산       |
| bool    | 1B | True, False     | 마스킹, 조건 연산      |
| object  | 동적 | 임의 객체           | 일반 Python 객체 배열 |


✔️ → dtype에 따라 **stride와 메모리 구조**가 달라집니다.

## 📌 4.5 활용 사례

-  **이미지 처리:** uint8 (0~255 픽셀 값)

-  **머신러닝:** float32로 메모리 절약 및 GPU 최적화

-  **금융 데이터:** float64로 정밀도 유지

-  **NLP:** 문자열을 object 배열로 변환

## 🚀 4.6 코드 예시
```
import numpy as np

arr = np.array([1.7, 2.8, 3.9])
print("기본 타입:", arr.dtype)

# 타입 변환
int_arr = arr.astype(np.int32)
print("정수형 변환:", int_arr)

# 부울 배열
bool_arr = (arr > 2)
print("2보다 큰 값들:", bool_arr)

# 메모리 절약 예시
img = np.array([255, 128, 64], dtype=np.uint8)
print("이미지 데이터:", img, img.dtype)
```


## ■ 4.7 출력 예시

```
기본 타입: float64
정수형 변환: [1 2 3]
2보다 큰 값들: [False  True  True]
이미지 데이터: [255 128  64] uint8
```

## ✔️ 4.8 주의사항 및 한계

-  float → int 변환 시 소수점 절삭 발생

-  int8는 -128 ~ 127 범위를 넘으면 오버플로우 발생

-  object dtype은 성능이 매우 나쁨 → 수치 연산에서는 지양
