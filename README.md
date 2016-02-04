# 기본sqlite3 사용법
## 기본 사용법을 보여주기 위해 만든 페이지입니다.(맥 기준입니다)
 
artists-MacBook-Pro:~ artist$ `cd Documents`
 
artists-MacBook-Pro:Documents artist$ `cd evcDB`
artists-MacBook-Pro:evcDB artist$ ls

###아래처럼 terminal 에서 `sql 파일` 을  생성합니다.

artists-MacBook-Pro:evcDB artist$ `sqlite3 namecard.sql`
### 이제 sqlite command line 이 시작됩니다

SQLite version 3.8.10.2 2015-05-20 18:17:19
Enter ".help" for usage hints.

```sql
sqlite> CREATE TABLE persons
   ...> (
   ...> pk PRIMARY KEY,
   ...> name VARCHAR(30),
   ...> telno VARCHAR(20),
   ...> email VARCHAR(100)
   ...> );
sqlite> .TABLES
Error: unknown command or invalid arguments:  "TABLES". Enter ".help" for help
sqlite> .tables
persons
```
위처럼  대소문자를 구별하는군요.😁  자 그럼 이제 잘 만들어졌나 확인해 볼까요?
```sql
sqlite> .schema persons
CREATE TABLE persons
(
pk PRIMARY KEY,
name VARCHAR(30),
telno VARCHAR(20),
email VARCHAR(100)
);
```

데이터를 넣어봅시다.
```sql
sqlite> INSERT INTO persons(name,telno,email)
   ...> VALUES
   ...> ('Eddie',
   ...> '023334444',
   ...> 'michel@daum.net')
   ...> ;
sqlite> SELECT * FROM persons;
|Eddie|023334444|michel@daum.net
```
값을 update 해 봅시다.
```sql
sqlite> UPDATE persons SET email='test@gmail.com' 
   ...> WHERE
   ...> name='Eddie';
sqlite> SELECT * FROM persons;
|Eddie|023334444|test@gmail.com
```
😅 잘 만드셨습니다.
😪 근데 여태 만든 걸 이젠 몽땅 지울겁니다.    
```sql
sqlite> DELETE FROM
   ...> persons
   ...> WHERE
   ...> name='Eddie';
sqlite> .tables
persons
sqlite> SELECT * from persons
   ...> ;
sqlite> SELECT * FROM persons;
sqlite> 
```
