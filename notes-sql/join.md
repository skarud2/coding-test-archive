# JOIN

두 테이블에서 조건에 맞는 행을 연결해서 조회
여기서 JOIN은 INNER JOIN. 연결 조건에 맞는 행만 가져옴

```sql
SELECT 가져올_컬럼
FROM 테이블A a
JOIN 테이블B b ON 연결_조건
WHERE 조회_조건;
```

ON은 연결 조건, WHERE는 연결한 결과에서 가져올 행의 조건
컬럼 이름이 같다고 연결하는 게 아니라 어떤 값을 가리키는지 보고 연결

a, b는 테이블 별칭. 컬럼 앞에 붙이면 어느 테이블의 컬럼인지 구분 가능

## 예시

ITEM_INFO는 아이템 정보, ITEM_TREE는 업그레이드 관계
PARENT_ITEM_ID는 업그레이드 전 아이템의 ID

```sql
SELECT t.ITEM_ID
FROM ITEM_INFO i
JOIN ITEM_TREE t ON i.ITEM_ID = t.PARENT_ITEM_ID
WHERE i.RARITY = 'RARE';
```

RARE 아이템의 ID와 그 아이템을 부모로 가진 기록을 연결

## 콤마 방식

```sql
SELECT t.ITEM_ID
FROM ITEM_INFO i, ITEM_TREE t
WHERE i.ITEM_ID = t.PARENT_ITEM_ID
  AND i.RARITY = 'RARE';
```

위 JOIN 예제와 같은 결과. JOIN ON으로 쓰면 연결 조건이 따로 보여서 읽기 편함
연결 조건을 빼면 모든 행 조합이 나옴 (카테시안 곱)
SQL 오류가 나는 건 아니지만 의도보다 행이 많아질 수 있음

[적용한 문제](problems/273711.md)
