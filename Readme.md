
<a name="readmeTop"></a>
<br />
<h1 >json-server  </h1>
프론트 엔드 작업 할 때, 서버 통신 사양서가 정의되고 통신테스트를 진행하고 싶으나 백엔드에서 준비가 되지 않은 경우 있습니다. json-server를 활용해 프로토 서버를 구축할 수 있습니다.<br /><br />

json-server 란? **간단히 DB와 API 서버**를 생성해주는 패키지입니다. **임시적**으로 사용 할 수 있는 mock data를 생성 할 수 있습니다.

<br />

- - -
<br />

## 목차
#### <a href="#패키지-설치">&nbsp;&nbsp;&nbsp;&nbsp;1. 패키지 설치</a>
#### <a href="#서버-구동">&nbsp;&nbsp;&nbsp;&nbsp;2. 서버 구동</a>
#### <a href="#테스트">&nbsp;&nbsp;&nbsp;&nbsp;3. 테스트</a>
<br />

- - -
<br />

## 패키지 설치

```console
npm install -g json-server
```
임시 서버 경로에 DB 역할을 하는 json 파일을 생성한다. 

</br>

### 예시 db.json
```json
{
  "todos": [
    {
      "id": 1,
      "content": "HTML",
      "completed": true
    },
    {
      "id": 2,
      "content": "CSS",
      "completed": false
    },
    {
      "id": 3,
      "content": "Javascript",
      "completed": true
    }
  ],
  "users": [
    {
      "id": 1,
      "name": "Lee",
      "role": "developer"
    },
    {
      "id": 2,
      "name": "Kim",
      "role": "designer"
    }
  ]
}
```


</br>


- - -
</br>

## 서버 구동
```console
json-server --watch db.json --port 3001
```
3001 포트로 임시서버를 구동합니다.

</br>

```console
Contrl + C
```
서버 구동이 중지됩니다.
 
</br>

- - -
</br>

## 테스트

</br>

### ∙ GET 요청

<img width="800" alt="capture1" src="https://user-images.githubusercontent.com/104295833/225837037-1b18d8a5-4492-41a2-bd77-09b84c85a7f8.png">

- http://localhost:3000/todos GET 요청 시 todos 데이터 반환되는 것을 볼 수 있습니다.


</br>

### ∙ POST 요청

<img width="800" alt="capture1" src="https://user-images.githubusercontent.com/104295833/225838207-3cb674f0-ab33-483e-80ae-3d98c82b8985.png">

- http://localhost:3000/todos POST 요청 시 해당 데이터가 생성되며, .json 파일에도 반영이 됩니다.


</br>

### ∙ DELETE 요청

<img width="800" alt="capture1" src="https://user-images.githubusercontent.com/104295833/225839182-4e0ebdd3-9dea-42e3-b1ab-7f7db9e475ab.png">

- http://localhost:3000/todos/2 Delete 요청 시 id 2인 항목이 삭제되며, .json 파일에도 반영이 됩니다.

</br>

- - -

