# 1. API Gateway

## API Gateway 란?

- RESTful API를 생성 및 구성 할 수 있게 지원하는 서비스
- API로 호출될 시 Lambda Function 또는 HTTP응답을 만들수 있음

![apig작동방식](https://user-images.githubusercontent.com/79297534/108957821-78a26980-76b5-11eb-9363-a6c04c165e4a.png)


## API Gateway와 Lambda를 활용한 RestFul API 생성
### GET API를 위한 Lambda 함수생성 화면
- 함수용도에 따른 이름 설정 (함수이름) : Lambda-hello-get
- 함수를 작성할때 사용할 언어 선택 (런타임) : Python 3.7

![함수생성](https://user-images.githubusercontent.com/79297534/108957159-59570c80-76b4-11eb-8f92-4c2e65f82506.png)

### GET Lambda 함수생성 완료 화면
- 현재는 API Gateway를 만들기전이라 트리거는 비어있음
- 트리거 : Lambda의 실행을 일으키게 하는 매개체 (실습에서는 API 게이트웨이 사용)

![image](https://user-images.githubusercontent.com/79297534/109100565-8bc24180-7768-11eb-8df0-3bc81c5dd94a.png)

### GET Lambda 함수코드 수정
- GET함수에서 출력될 메세지 설정 (body 부분 수정)

![image](https://user-images.githubusercontent.com/79297534/109103636-9aabf280-776e-11eb-91ab-996cd4ace804.png)

### POST Lambda 함수생성
- GET과 동일 함수명만 POST로 지정

![image](https://user-images.githubusercontent.com/79297534/109104641-b5329b80-776f-11eb-8fa6-3bfe66c26072.png)

### POST Lambda 함수코드 수정
- API Gateway로 넘어오는 데이터는 JSON 형식으로 넘어오며, event안에 담겨있음
- JSON데이터에 key를 'key'로 정의하여, post 방식일때 호출된 메세지를 설정 

![image](https://user-images.githubusercontent.com/79297534/109105793-f5931900-7771-11eb-89a2-296f5c70defa.png)

### API Gateway 생성
- 검색에서 API Gateway를 쳐서 API Gateway 서비스 선택
- 현실습에서는 REST API를 활용하므로 REST API 구축 선택

![image](https://user-images.githubusercontent.com/79297534/109106230-b9ac8380-7772-11eb-821f-d7af2a8495a5.png)
![image](https://user-images.githubusercontent.com/79297534/109107540-40626000-7775-11eb-9650-d42e2854ce79.png)

### API Gateway 생성
- 검색에서 API Gateway를 쳐서 API Gateway 서비스 선택
- 현실습에서는 REST API를 활용하므로 REST API 구축 선택

### 용어정리
#### Elastic Block Store(EBS) 
- 대규모로 처리량과 트랜잭션 집약적인 워크로드 모두를 지원하기 위해 Elastic Compute Cloud(EC2)에서 사용하도록 설계된 사용하기 쉬운 고성능 블록 스토리지 서비스
- 일종의 하드디스크
- CloudWatch를 통해서 EBS의 통계 열람 가능
- EC2 인스턴스를 제거해도 EBS는 데이터가 유지됨
#### 트리거
- Lambda의 실행을 일으키게 하는 매개체
#### Lambda
- 서버를 프로비저닝하거나 관리하지 않고도 코드를 실행할 수 있게 해주는 컴퓨팅 서비스
- 프로비저닝:사용자의 요구에 맞게 시스템 자원을 할당, 배치, 배포해 두었다가 필요 시 시스템을 즉시 사용할 수 있는 상태로 미리 준비해 두는 것
- 참고 : https://brownbears.tistory.com/428
#### API
- API(Application Programming Interface)는 응용 프로그램에서 사용할 수 있도록, 운영 체제나 프로그래밍 언어가 제공하는 기능을 제어할 수 있게 만든 인터페이스를 의미함
- 참고 : https://moonspam.github.io/What-is-an-API/
