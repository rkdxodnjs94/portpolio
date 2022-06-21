# 📌  같이놀자
> 보드게임카페 예약서비스
> AWS 링크

<br>

## 1. 제작 기간 & 참여 인원
- 2022년 5월 16일 ~ 6월 21일
- 개인 프로젝트

<br>

## 2. 사용 기술
#### `Back-end`
  - Node.js ^16.1.5
  - MongoDB v4.6.0
  - Mongoose v6.3.3
  - Koa
  - Joi
  - Selenium

#### `Front-end`
  - React.js v18.1.0
  - BootStrap v5.1.3

<br>

## 3. ERD 설계
![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/gachinolja%20ERD.png)

## 4. 핵심 기능
이 서비스의 핵심 기능은 예약기능입니다.
서울시 내의 보드게임 매장을 검색하여 원하는 자리, 날짜, 시간, 인원을 예약하면 됩니다.
이 기능들의 흐름을 보면, 서비스가 어떻게 동작하는지 알 수 있습니다.

<details>
<summary><b>핵심 기능 설명 펼치기</b></summary>
<div markdown="1">
  
### 4.1. 전체 흐름
![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flowpoint.png)

### 4.2. 사용자 요청
![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flow1.png)

- **URL 정규식 체크** :pushpin: [코드 확인](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/SignUp.js)
  - React.js로 렌더링된 화면단에서, 사용자가 등록을 시도한 URL의 모양새를 정규식으로 확인합니다.
  - URL의 모양새가 아닌 경우, 에러 메세지를 띄웁니다.

- **Axios 비동기 요청** :pushpin: [코드 확인](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/SignUp.js)
  - URL의 모양새인 경우, 컨텐츠를 등록하는 POST 요청을 비동기로 날립니다.

### 4.3. mongoose & Service

![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flow2.png)

- **mongoose** :pushpin: [코드 확인](https://github.com/rkdxodnjs94/gachiback/blob/main/src/models/user.js)
  - mongoose에서 schema 모델을 생성합니다.

- **index** :pushpin: [코드 확인](https://github.com/rkdxodnjs94/gachiback/blob/main/src/api/user/index.js)
  - 그 모델을 토대로 app의 index에서 url을 통해 요청합니다.

### 4.4. Controller

![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flow3.png)

- **결과 응답** :pushpin: [코드 확인](https://github.com/rkdxodnjs94/gachiback/blob/main/src/api/user/user.ctrl.js)
  - 요청받은 url을 토대로 데이터가 잘 들어왔는지 로직처리를 합니다.

- **DB에 저장** :pushpin:
  - 로직처리를 마친 후, api의 url로 mongoDB 서버에 데이터를 저장합니다.

- **컨텐츠 저장** :pushpin:
  - 저장된 컨텐츠는 다시 mongoDB - Controller - index를 거쳐 화면단에 송출됩니다.

</div>
</details>

</br>
