# 1. API Gateway

## API Gateway 란?

- REST API 및 Websocket API를 생성, 유지, 관리하는 AWS 서비스
- API로 호출될 시 Lambda Function 또는 HTTP응답을 만들수 있음

![apig작동방식](https://user-images.githubusercontent.com/79297534/108957821-78a26980-76b5-11eb-9363-a6c04c165e4a.png)

- 작성중

## API Gateway와 Lambda를 활용한 RestFul API 생성 실습
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
- 수정완료후 Deploy(전개)선택

![image](https://user-images.githubusercontent.com/79297534/109103636-9aabf280-776e-11eb-91ab-996cd4ace804.png)

### POST Lambda 함수생성
- 함수용도에 따른 이름 설정 (함수이름) : Lambda-hello-post
- 함수를 작성할때 사용할 언어 선택 (런타임) : Python 3.7

![image](https://user-images.githubusercontent.com/79297534/109104641-b5329b80-776f-11eb-8fa6-3bfe66c26072.png)

### POST Lambda 함수코드 수정
- API Gateway로 넘어오는 데이터는 JSON 형식으로 넘어오며, event안에 담겨있음
- JSON데이터에 key를 'key'로 정의하여, post 방식일때 호출된 메세지를 설정
- 수정완료후 Deploy(전개)선택 

![image](https://user-images.githubusercontent.com/79297534/109105793-f5931900-7771-11eb-89a2-296f5c70defa.png)

### API Gateway 생성
- 검색에서 API Gateway를 쳐서 API Gateway 서비스 선택

![image](https://user-images.githubusercontent.com/79297534/109106230-b9ac8380-7772-11eb-821f-d7af2a8495a5.png)

- 실습에서는 REST 프로토콜을 활용하므로 REST API 구축 선택

![image](https://user-images.githubusercontent.com/79297534/109107540-40626000-7775-11eb-9650-d42e2854ce79.png)

- 이름과 설명, 지역 설정

![image](https://user-images.githubusercontent.com/79297534/109108042-1e1d1200-7776-11eb-84f4-b7f6537780be.png)

### API Gateway 리소스 생성
- /영역을 잡고 작업에 리소스 생성 선택

![image](https://user-images.githubusercontent.com/79297534/109108160-53c1fb00-7776-11eb-8fdf-2c8aeb9ea20b.png)

- 리소스 이름과 경로를 설정하고 리소스 생성

![image](https://user-images.githubusercontent.com/79297534/109108180-5ae90900-7776-11eb-9df6-ae39ec1ca568.png)

### API Gateway 메서드 생성
- 생성한 리소스 hello를 잡고 작업에서 메서드 생성 선택

![image](https://user-images.githubusercontent.com/79297534/109108340-ae5b5700-7776-11eb-9a9d-a461892e8cb0.png)

- 메서드를 GET으로 설정하고 체크표시 선택

![image](https://user-images.githubusercontent.com/79297534/109108437-eb274e00-7776-11eb-824b-96e0077bca7d.png)

- 통합환경에 Lambda 함수를 선택하므로 /hello에 GET 메서드로 요청시 Lambda 함수를 실행하도록 설정됨 
- Lambda 함수를 생성한 리전을 선택
- 사용할 Lambda함수 선택   

![image](https://user-images.githubusercontent.com/79297534/109108543-1d38b000-7777-11eb-8ee4-e7d946642ed3.png)

- GET과 같은 방식으로 POST 메서드 설정

![image](https://user-images.githubusercontent.com/79297534/109109166-2bd39700-7778-11eb-8d34-a5da59e403c9.png)

- 메서드 설정까지 완료후 Lambda에 트리거 부분에 API Gateway가 자동으로 등록됨 (Lambda 부분으로 넘어가서 확인 가능) 

![image](https://user-images.githubusercontent.com/79297534/109109480-bf0ccc80-7778-11eb-9a3c-5ee81c85190e.png)

### REST API 배포
- 리소스에서 /영역을 선택하고 작업에서 API배포를 선택

![image](https://user-images.githubusercontent.com/79297534/109110037-b4066c00-7779-11eb-83e5-369067fc81e7.png)


- 새 스테이지로 선택하고, 스테이지의 이름, 설명, 배포의 설명을 아래 그림과 같이 채워줌

![image](https://user-images.githubusercontent.com/79297534/109110137-df895680-7779-11eb-905c-8a769b0ebf57.png)

- 좌측 스테이지 탭에서 생성된 스테이지 선택후 "URL호출"에 있는 주소 복사해두기 

![image](https://user-images.githubusercontent.com/79297534/109110658-dfd62180-777a-11eb-8617-442e225930c2.png)

### URL에 접근해보기
- 복사한 URL주소를 크롬 주소창에 붙여넣기 
- 복사한 주소는 "/" 즉 루트 리소스를 가르키므로 "/"에 대한 메서드가 정의되지 않으면 아래와 같은 오류가 발생함

![image](https://user-images.githubusercontent.com/79297534/109111379-2415f180-777c-11eb-96ae-75386c66166c.png)

- 복사한 주소뒤에 "/hello"(메서드를 정의해둔 리소스 이름)를 붙여넣기
- GET으로 설정한 람다에서 설정한 메세지 출력 확인

![image](https://user-images.githubusercontent.com/79297534/109111924-1e6cdb80-777d-11eb-9bd7-36733041a993.png)

### POST 메서드 요청해보기(python)
- requests 라이브러리 설치후 이를 활용한 get, post 메서드 요청

![image](https://user-images.githubusercontent.com/79297534/109112128-799ece00-777d-11eb-999c-24140212816b.png)

![image](https://user-images.githubusercontent.com/79297534/109112146-81f70900-777d-11eb-98dd-c7d58664b224.png)


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
