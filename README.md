# 🗄️ 오라클 DBMS 학습 프로젝트

이 레포지토리는 오라클 DBMS에서 데이터베이스를 효과적으로 관리하고 쿼리하는 방법을 학습한 내용을 정리한 것입니다. 데이터 조회, 테이블 관리, 그리고 트랜잭션 처리 등 다양한 기능을 다룹니다.

## 📘 주요 학습 내용

### 1. 🔍 SELECT 문
- 데이터를 조회하는 가장 기본적인 쿼리입니다. 다양한 컬럼을 선택하고 조건을 추가해 데이터를 효율적으로 가져오는 방법을 학습했습니다.
```sql
SELECT column1, column2 FROM table_name;

### 2. 📑 WHERE 절
- 데이터를 필터링하는 조건을 정의하는 구문으로, 특정 조건에 맞는 데이터를 조회할 때 사용합니다.
```sql
SELECT * FROM table_name WHERE condition;

### 3. 🔢 ORACLE FUNCTION
- 내장 함수를 사용하여 문자열 처리, 숫자 계산, 날짜 변환 등을 쉽게 처리하는 방법을 배웠습니다. `TO_DATE`, `TO_CHAR`, `NVL`, `SUBSTR` 등의 함수를 익혔습니다.
```sql
SELECT TO_DATE('2024-10-21', 'YYYY-MM-DD') FROM dual;
SELECT SUBSTR('Oracle', 1, 3) FROM dual;

### 4. 📊 GROUP BY / HAVING
- 데이터를 그룹화하여 집계할 때 사용하며, `HAVING` 절을 통해 그룹별 조건을 추가할 수 있습니다. 이로써 특정 조건에 맞는 그룹화된 데이터를 필터링합니다.
```sql
SELECT department, COUNT(*) FROM employees GROUP BY department HAVING COUNT(*) > 5;

### 5. 🔗 JOIN
- 여러 테이블을 연결하여 데이터를 조회하는 방법을 학습했습니다. INNER JOIN, OUTER JOIN 등을 통해 다양한 방식으로 테이블 간의 데이터를 결합할 수 있습니다.
```sql
SELECT e.name, d.department_name 
FROM employees e 
INNER JOIN departments d ON e.department_id = d.department_id;

### 6. 🛠️ DDL (Data Definition Language)
- 데이터베이스 구조를 정의하는 명령어로, 테이블 생성, 수정, 삭제 등을 처리합니다. `CREATE`, `ALTER`, `DROP` 명령어를 다루었습니다.
```sql
CREATE TABLE employees (
    employee_id NUMBER PRIMARY KEY,
    name VARCHAR2(100),
    department_id NUMBER
);

### 7. ✍️ DML (Data Manipulation Language)
- 테이블에 데이터를 삽입, 수정, 삭제하는 명령어입니다. `INSERT`, `UPDATE`, `DELETE` 명령어를 사용해 데이터를 조작하는 방법을 배웠습니다.
```sql
INSERT INTO employees (employee_id, name, department_id) VALUES (1, 'John Doe', 10);
UPDATE employees SET name = 'Jane Doe' WHERE employee_id = 1;
DELETE FROM employees WHERE employee_id = 1;

### 8. 🔄 서브쿼리(Subquery)
- 쿼리 내에 또 다른 쿼리를 작성하여 복잡한 데이터를 조회할 수 있습니다. 중첩된 쿼리를 통해 더 세부적인 데이터를 추출하고 처리하는 기술을 익혔습니다.
```sql
SELECT name FROM employees WHERE department_id = (SELECT department_id FROM departments WHERE department_name = 'HR');

### 9. ⚙️ TCL (Transaction Control Language)
- 트랜잭션을 제어하는 명령어로, 데이터의 일관성과 무결성을 보장합니다. `COMMIT`, `ROLLBACK`, `SAVEPOINT` 등을 사용해 트랜잭션의 시작과 종료를 관리합니다.
```sql
BEGIN;
INSERT INTO employees (employee_id, name, department_id) VALUES (2, 'Alice', 20);
COMMIT;
ROLLBACK;

### 10. 🔒 DCL (Data Control Language)
- 데이터베이스에 대한 권한을 부여하거나 회수하는 명령어입니다. `GRANT`, `REVOKE`를 통해 사용자에게 권한을 부여하고 제어하는 방법을 학습했습니다.
```sql
GRANT SELECT ON employees TO user_name;
REVOKE SELECT ON employees FROM user_name;

