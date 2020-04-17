---
hlayout: post
title: "[Web] GET과 POST 방식"
date: 2020-04-17
author : 장성원
categories : Web
---

# GET

- 웹 서버와 클라이언트가 통신을 할 때 **URL 뒤에 파라미터**를 붙여서 데이터를 전달하는 방식이다. 
- 사용자가 보내는 데이터는 이름과 값이 결합된 문자열 형태로 전달된다.
- 이름과 값의 쌍은 &기호로 구분한다.
- 서버로 보낼 수 있는 글자수가 최대 2,048로 제한되어 있다.
- URL을 통해 어떤 데이터를 전송하고자 하는지 알 수 있기 때문에 보안에 취약하다.

```html
<form name="입력 폼 이름" action="웹 프로그램 페이지" method="GET">
    <input type="text" name="user">
    <input type="text" name="dept">
    <input type="submit" value="전송">
    <input type="reset" value="다시작성">
</form>
```

user에 Hong dept에 Computer를 적으면 http://localhost/웹 프로그램 페이지**?user=Hong&dept=Computer** 처럼 URL주소 뒤에 이름과 전공 데이터가 붙어 전달된다.



# POST

- **HTTP Request** 헤더에 파라미터를 붙여서 데이터를 전송하는 방식이다.
- 별도의 헤더를 사용하기 때문에 글자 수의 제한이 없다.
- URL 뒤에 파라미터를 붙여서 데이터를 전송하는 방식이 아니기 때문에 GET에 비해서 보안상 우위에 있다.

GET코드에서 method = "POST"로 수정하면 POST 코드이다.



# GET과 POST

- 목적이 무엇인가?
- 어떤 기능을 구현하고자 하는가?
- 데이터 보안이 중요한가?



세 가지 사항을 고려해서 적절한 방법을 사용하는게 가장 좋은 것 같다. **보안**이 중요하면 POST를 사용하고 **속도**가 중요하면 GET을 사용하면 된다.













