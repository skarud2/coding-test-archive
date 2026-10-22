# 서브쿼리

쿼리 안에 들어가는 쿼리. 괄호로 감싸서 사용
다른 조회 결과를 조건으로 쓰고 싶을 때 활용

## IN과 같이 사용

```sql
SELECT 가져올_컬럼
FROM 테이블A
WHERE 비교할_컬럼 IN (
    SELECT 목록으로_쓸_컬럼
    FROM 테이블B
    WHERE 조건
);
```

안쪽에서 조회한 목록에 포함되는 행만 바깥에서 가져옴
이렇게 한 컬럼을 비교할 때는 서브쿼리도 한 컬럼만 조회

## 예시

ITEM_TREE는 업그레이드 관계를 저장한 테이블
PARENT_ITEM_ID가 0이면 아이템 0에서 업그레이드된 아이템이라는 뜻

```sql
SELECT ITEM_ID, ITEM_NAME
FROM ITEM_INFO
WHERE ITEM_ID IN (
    SELECT ITEM_ID
    FROM ITEM_TREE
    WHERE PARENT_ITEM_ID = 0
);
```

안쪽에서는 아이템 0의 다음 아이템 ID 목록을 조회
바깥에서는 그 ID에 해당하는 이름을 가져옴

이건 쿼리를 이해하는 흐름. DB가 실제로 안쪽부터 실행한다는 뜻은 아님

[IN 사용법](where.md) / [적용한 문제](problems/273711.md)
