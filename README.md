# 기본sqlite3 사용법을 보여주기 위해 만든 페이지입니다.(맥 기준입니다)
 
artists-MacBook-Pro:~ artist$ `cd Documents`
 
artists-MacBook-Pro:Documents artist$ `cd evcDB`

artists-MacBook-Pro:evcDB artist$ ls

###아래처럼 terminal 에서 생성합니다.

artists-MacBook-Pro:evcDB artist$ `sqlite3 namecard.sql`
### 이제 sqlite command line 이 보입니다

SQLite version 3.8.10.2 2015-05-20 18:17:19
Enter ".help" for usage hints.

```sqlite
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
위에서 보듯이 대소문자를 구별하게 되어 있다.

```sqlite
sqlite> .schema persons
CREATE TABLE persons
(
pk PRIMARY KEY,
name VARCHAR(30),
telno VARCHAR(20),
email VARCHAR(100)
);
```

데이터를 넣어보자.
```sqlite
sqlite> INSERT INTO persons(name,telno,email)
   ...> VALUES
   ...> ('Michel',
   ...> '023334444',
   ...> 'michel@daum.net')
   ...> ;
sqlite> SELECT * FROM persons;
|Michel|023334444|michel@daum.net
```
값을 update 해 보자
```sqlite
sqlite> UPDATE persons SET email='test@gmail.com' 
   ...> WHERE
   ...> name='Michel';
sqlite> SELECT * FROM persons;
|Michel|023334444|test@gmail.com
sqlite> DELETE FROM
   ...> persons
   ...> WHERE
   ...> name='Michel';
sqlite> .tables
persons
sqlite> SELECT * from persons
   ...> ;
sqlite> SELECT * FROM persons;
sqlite> 
```
