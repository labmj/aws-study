# 1. API Gateway

## API Gateway 란?

- RESTful API를 생성 및 구성 할 수 있게 지원하는 서비스
- API로 호출될 시 Lambda Function 또는 HTTP응답을 만들수 있음

![apig작동방식](https://user-images.githubusercontent.com/79297534/108957821-78a26980-76b5-11eb-9363-a6c04c165e4a.png)


## API Gateway와 Lambda를 활용한 RestFul API 생성
### GET API를 위한 Lambda 함수생성
- 함수용도에 따른 이름 설정 (함수이름) : Lambda-hello-get
- 함수를 작성할때 사용할 언어 선택 (런타임) : Python 3.7

![함수생성](https://user-images.githubusercontent.com/79297534/108957159-59570c80-76b4-11eb-8f92-4c2e65f82506.png)

### 참고
- 블루프린트
