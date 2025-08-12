## Generator Expression

제너레이터 표현식은 리스트 컴프리헨션과 비슷하지만, 메모리에 전체 리스트를 생성하는 대신 **제너레이터 객체**라는 반복 가능한(iterable) 객체를 생성합니다.
이 객체는 값이 필요할 때마다 하나씩 값을 생성하므로, 특히 대용량 데이터를 다룰 때 메모리 효율이 매우 높습니다.

### 문법
```python
(표현식 for 항목 in 반복가능객체)
```

### 예제 1: 숫자 제곱하기

다음 예제는 0부터 4까지의 숫자의 제곱을 생성합니다.

```python
squares_generator = (i * i for i in range(5))

# 제너레이터 객체를 순회하며 값을 가져옵니다.
for value in squares_generator:
    print(value)
```

**출력:**

```
0
1
4
9
16
```

### 예제 2: 문자열 정리하기

다음 예제는 문자열에서 알파벳이 아닌 문자를 제거하는 방법을 보여줍니다.

```python
string = "iso-gr-am"
cleaned = ''.join(ch for ch in string.lower() if ch.isalpha())
print(cleaned)
```

**출력:**

```
isogram
```

**설명:**
코드는 먼저 `string.lower()`를 사용해 문자열을 소문자로 변환합니다.
그다음 각 문자(`ch`)를 순회하면서 알파벳인지(`ch.isalpha()`) 판별해, 알파벳인 문자만 필터링합니다.
마지막으로 필터링된 문자들을 ''.join()으로 다시 하나의 문자열로 합칩니다.