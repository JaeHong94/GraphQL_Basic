# GraphQL

## typeDef와 resolver 역할

typeDef(s)

- GraphQL Schema를 정의하는곳
  - Object
  - Query
  - Mutation
  - Input
- gql과 Tageed Template Literals로 작성한다.

resolvers(s)

- Schema에 해당하는 구현을 하는 곳
- 요청을 받아 데이터를 조회, 수정, 삭제

## 특정 데이터 조회하기

![image](https://user-images.githubusercontent.com/74242937/124099210-40ae9700-da98-11eb-9f95-328f089ee77f.png)

Query에 bookId 변수를 가진 book의 요청이 들어오면 Book을 내보내주는 쿼리 작성

![image](https://user-images.githubusercontent.com/74242937/124099449-81a6ab80-da98-11eb-996f-cec2a4fd6d90.png)

resolvers에 json 데이터를 받아와 book.bookID와 args.bookID가 같다면 결과를 출력해주는 코드 작성

![image](https://user-images.githubusercontent.com/74242937/124099689-c03c6600-da98-11eb-96bf-9c853c12cadb.png)

결과 확인

## 데이터 추가하기

![image](https://user-images.githubusercontent.com/74242937/124101188-11008e80-da9a-11eb-9dd6-006c7a832a71.png)

데이터를 추가할때는 type Mutation에 작성해야합니다.  
addBook 파라미터에 넣고싶은 데이터와 타입을 작성합니다.

![image](https://user-images.githubusercontent.com/74242937/124101985-e6630580-da9a-11eb-8c1c-14f969d08ec7.png)

resolvers에도 마찬가지로 Mutation으로 작성합니다.  
json 데이터를 받아오는 books, bookId의 최대값을 구하는 maxId를 만들고 데이터를 추가하면 bookId + 1과 작성한 데이터들을 저장하는 newBook 작성  
추가한 데이터를 writeFileSync 메서드를 통해 books.json 파일에 저장해줍니다.

## 데이터 수정하기

![image](https://user-images.githubusercontent.com/74242937/124106717-7145ff00-da9f-11eb-8e33-4568a2b359ab.png)

데이터 수정도 type Mutation에 작성합니다.  
editBook 파라미터에 수정하고 싶은 bookId와 수정하고 싶은 나머지 파라미터를 작성

![image](https://user-images.githubusercontent.com/74242937/124106983-b9652180-da9f-11eb-81b9-0205155e3ada.png)

resolvers -> Mutation에 작성합니다.  
json 데이터를 받아오는 books, book.bookId와 args.bookId가 같으면 수정한 args 반환, 다르다면 book을 그대로 반환하는 newBooks 작성  
수정한 데이터를 writeFileSync 메서드를 통해 books.json 파일에 저장합니다.

## 데이터 삭제하기

![image](https://user-images.githubusercontent.com/74242937/124106717-7145ff00-da9f-11eb-8e33-4568a2b359ab.png)

데이터 삭제도 type Mutation에 작성합니다.

![image](https://user-images.githubusercontent.com/74242937/124107411-2a0c3e00-daa0-11eb-9baf-79dde8d4f297.png)

resolvers -> Mutation에 작성합니다.  
find 메서드를 통해 book.bookId와 args.bookId 일치하는 데이터 반환 후 filter 메서드를 통해서 삭제할 데이터를 제외한 정보들 저장  
삭제한 데이터를 writeFileSync 메서드를 통해 books.json 파일에 저장합니다.
