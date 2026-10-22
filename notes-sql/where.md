# 조건 검색

## WHERE

조건에 맞는 행만 조회

```sql
SELECT ITEM_ID
FROM ITEM_INFO
WHERE RARITY = 'RARE';
```

RARITY가 RARE인 행만 가져옴

## IN

목록 중 하나와 일치하면 조회

```sql
SELECT ITEM_ID, ITEM_NAME
FROM ITEM_INFO
WHERE ITEM_ID IN (1, 2, 3, 4);
```

ITEM_ID가 1, 2, 3, 4 중 하나인 행 조회
목록 대신 [서브쿼리](subquery.md)의 조회 결과를 넣을 수도 있음

NULL 조건은 [NULL 처리](null.md)에 정리

[적용한 문제](problems/273711.md)
