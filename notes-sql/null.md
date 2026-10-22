# NULL 처리

## IFNULL(컬럼명, 대체값)

값이 NULL이면 대체값으로 보여줌
NULL이 아니면 원래 값 그대로

```sql
SELECT IFNULL(phone, '없음') AS phone
FROM users;
```

phone이 NULL이면 '없음'으로 나옴
빈 문자열('')은 NULL이 아니라서 그대로 나옴

## IS NOT NULL

NULL이 아닌 값만 조회할 때 사용

```sql
SELECT *
FROM users
WHERE phone IS NOT NULL;
```

phone이 NULL인 행은 제외됨
빈 문자열('')은 NULL이 아니라서 포함됨

NULL 비교는 != NULL 말고 IS NOT NULL 사용
반대로 NULL인 것만 찾으려면 IS NULL
