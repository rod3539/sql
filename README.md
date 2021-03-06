# SQL 기초 문법 정리

SQL문법들을 정리해 보았다.

## SELECT문 - CRUD중 R

* 기본구조
  
    ``` SELECT 필드이름 FROM 테이블 ```

* 여러 필드를 조회하는 경우
  
    ``` SELECT 필드이름 1, 필드이름 2 FROM 테이블 ```

* 모든 필드를 조회하는 경우
  
    ``` SELECT * FROM 테이블 ```

* 중복된 데이터를 없애고 조회하는 경우
  
    ``` SELECT DISTINCT 필드이름 FROM 테이블 ```

* 조건식을 적용하는 경우
  
    ``` SELECT * FROM 테이블 WHERE 필드이름 = 0 ```

* 여러 조건식을 적용하는 경우
  
    ``` SELECT * FROM 테이블 WHERE 필드이름1 = 0 AND 필드이름2 = 0 OR 필드이름3 = 0 ```

## MYSQL 코딩테스트용 기초 문법 정리

SQL문제를 풀기 위해서 알아야 할 가장 기초적인 지식들을 정리해 보았다.

### IF

* SELECT, WHERE에서 사용 가능
  
    ``` SELECT IF(10 > 5, '크다', '작다') AS result; ```

### ORDER BY

* ORDER BY 뒤에 우선순위가 있는 열을 순서대로 적는다
  
  ```
  순서대로 배열
  SELECT * FROM 테이블
  ORDER BY ID
  ```
  
  ```
  오름차순: ASC
  ```
  
  ```
  역순 배열
  SELECT * FROM 테이블
  ORDER BY ID DESC 
  ```

### LIKE

* WHERE과 함께 특정 패턴 검색시 사용
  
  ```
  SELECT * FROM STUDENT
  WHERE STUDENT_ID LIKE 'a%'
  LIKE 'A%' -> A로 시작하는 모든 것
  LIKE 'A_%_%' -> A로 시작되고 최소 3 이상의 길이를 가진 것
  LIKE 'A%' -> 두번 째 자리에 A가 들어가는 모든 것 
  ```

### IN

* WHERE절 내 여러 값을 설정하고자 할 때 사용

* 연산 속도가 상대적으로 빠름

* 연산과 유사한 효과
  
  ```
  SELECT * FROM CUSTOMERS
  WHERE COUNTRY IN ('UK', 'KOREA') // CUSTOMER 중 COUNTRY가 UK이거나 KOREA인 것 다 뽑기
  ```

### BETWEEN

* WHERE절 내 검색 조건으로 범위를 지정하고자 할 때 사용

* BETWEEN과 AND 사이에 들어 가는 값은 ~이상, ~이하이다
  
  ```
  SELECT * FROM PRODUCTS
  WHERE PRICE BETWEEN 10 AND 20;
  
  SELECT * FROM PRODUCTS
  WHERE PRICE NOT BETWEEN 10 AND 20;
  
  SELECT * FROM PRODUCTS
  WHERE (PRICE BETWEEN 10 AND 20) AND NOT ID IN (2, 3); // 이렇게도 쓸 수 있다.
  ```

### NULL의 처리

* IFNULL 사용
  
  ```
  SELECT ANIMAL_TYPE, IFNULL(NAME,'NO NAME')
  ```

### DISTINCT

    중복 데이터를 제거하려면 DISTINCT 키워드를 붙인다.

### GROUP BY

    ```
    SELECT 컬럼 FROM 테이블 GROUP BY 그룹화할 컬럼;
    ```

## JOIN