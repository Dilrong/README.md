# API Doc

## 개요
* **목적**  
  본문서는 github README.md에서 협업으 위하 API 문서 양식입니다.

* **BASE URL**   
  `https://test.com`

* **Authorize**  
  `jwt`  

## Model
* **member**
  ```
  member {
    id: int,
    memberName*: string,
    memberEmail*: string,
    memberPassword*: string,
    createdAt: timestamp,
    updatedAt: timestamp
  }
  ```


## member
### token의 member 정보를 보여준다.
* **URL**  
  `/members`

* **Method**  
  `GET`

* **Parameters**  
  `Authorize`

* **Success Response**  
  * **Code**: 200  
  **Content**  
  ```
  {
    memberModel
  }
  ```
### token의 member 정보를 수정한다.
* **URL**  
  `/members`

* **Method**  
  `PUT`

* **Parameters**  
  `Authorize`
  ```
  {
    memberPassword*: string,
    memberPhone*: string
  }
  ```

* **Success Response**  
  * **Code**: 200  
  **Content**  
  ```
  [boolean]
  ```
### member를 추가한다.
* **URL**  
  `/members`

* **Method**  
  `POST`

* **Parameters**  
  ```
  {
    memberModel
  }
  ```

* **Success Response**  
  * **Code**: 200  
  **Content**  
  ```
  {
    memberModel
  }
  ```

### id의 계정정보를 삭제한다.
* **URL**  
  `/members/:id`

* **Method**  
  `DELETE`

* **Parameters**  
  none

* **Success Response**  
  * **Code**: 200  
  **Content**  
  ```
  Boolean
  ```

* **Success Response**  
  * **Code**: 200  
  **Content**  
  ```
  {
    token: string
  }
  ```
## Error Code
* **Code**: 400  
  **Content**: `Bad Request`
  
  
  OR  
  
  
* **Code**: 401  
  **Content**: `Unauthorized`  
  
  
  OR  
  
  
* **Code**: 403  
  **Content**: `Forbidden`  
  
  
  OR  
  
  
* **Code**: 405  
  **Content**: `Method Not Allowed`  
  
  
  OR  
  
  
* **Code**: 500  
  **Content**: `Internal Server`  
  
  
  OR  
  
  
* **Code**: 502  
  **Content**: `Bad Gateway`  
  
  
  OR  
  
  
* **Code**: 504  
  **Content**: `Gateway Timeout`  
