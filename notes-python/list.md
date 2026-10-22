# 리스트

## index(찾을값)

값이 처음 나오는 인덱스를 반환. 인덱스는 0부터 시작

```python
names = ["Lee", "Kim", "Park", "Kim"]

print(names.index("Kim"))  # 1
```

같은 값이 여러 개 있어도 첫 번째 위치만 반환
값이 없으면 -1이 아니라 ValueError가 발생

```python
if "Kim" in names:
    position = names.index("Kim")
```

index()는 리스트에 붙여 쓰는 메서드라 import 없이 사용
