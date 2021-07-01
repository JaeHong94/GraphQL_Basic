# GraphQL

## typeDef와 resolver 역할

typeDef(s)

- GraphQL Schema를 정의하는곳
  - Object
  - Query
  - Mutation
  - Input
- gql과 Tageed Template Literals로 작성한다.

resolver(s)

- Schema에 해당하는 구현을 하는 곳
- 요청을 받아 데이터를 조회, 수정, 삭제

## 특정 데이터 조회하기

![image](https://user-images.githubusercontent.com/74242937/124099210-40ae9700-da98-11eb-9f95-328f089ee77f.png)

Query에 bookId 변수를 가진 book의 요청이 들어오면 Book을 내보내주는 쿼리 작성

![image](https://user-images.githubusercontent.com/74242937/124099449-81a6ab80-da98-11eb-996f-cec2a4fd6d90.png)

resolvers에 json 데이터를 받아와 book.bookID와 args.bookID가 같다면 결과를 출력해주는 코드 작성

![image](https://user-images.githubusercontent.com/74242937/124099689-c03c6600-da98-11eb-96bf-9c853c12cadb.png)

결과 확인
