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
  - Node.js v16.1.5
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
이 서비스의 핵심 기능은 예약기능입니다.<br>
서울시 내의 보드게임 매장을 검색하여 원하는 자리, 날짜, 시간, 인원을 예약하면 됩니다.<br>
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

## 5. 핵심 트러블 슈팅
### 5.1. 매장마다 다른 데이터 가져오는 법
- 이 사이트의 매장이 약 150개 있는데, 각 매장에 맞는 날짜, 시간, 자리, 인원 데이터를 가져오고 싶었습니다.

- 처음엔 전체 매장의 예약 데이터들을 전부 다 가져와서 각 매장에 맞게 가공하여 제공할 예정이었지만,<br>
모든 조건을 만족할 데이터를 매장에 맞게 출력하는게 쉽지 않았습니다.

<details>
<summary><b>axios로 가져온 기존 코드</b></summary>
<div markdown="1">

~~~react.js
useEffect(() => {
  async function axiosdata(){
    try {
      const response = await axios.get('/api/reserve');
      for (var i=0; i<2600; i++) {
        dispatch(setPlace(response.data[i].place));
      for (var i=0; i < response.data.length; i++) {
        dispatch(setSaveReserve(response.data[i].place));
        dispatch(setSaveReserve(response.data[i].arrage[0].arrage));
        console.log(response);
      }
      };
      console.log(response);
    } catch (error) {
      console.log(error);
    }
  }
  axiosdata();
axiosdata();
},[dispatch])
~~~

</div>
</details>

- 기존 redux로 이용한 state 자료입니다.

<details>
<summary><b>기존 redux 코드</b></summary>
<div markdown="1">

~~~react.js
// 자리 데이터를 저장하는 state입니다.
// 초기 state : [ [] ]
// 수정 state : [ ['강남점',1,2,3,...],['홍대점',1,2,3,...], [...] ]
// 초기 state : []
// 수정 state : [ ['강남점',1,2,3..],['홍대점',1,2,3,...], ]
import { createSlice } from "@reduxjs/toolkit";

const SaveReserve = createSlice({
  name : 'savereserve',
  initialState : [
    []
  ],
  initialState : [],
  reducers : {
    setSaveReserve(state, action){
      if (action.payload !== Number){ 
        const setplace = [[...state],[action.payload]];
        return setplace.filter(function(item, idx){
          return setplace.indexOf(item) === idx;
        })
      } else if(action.payload === Number){
        const setarrage = [[...state,action.payload]];
        return setarrage.filter(function(item, idx){
          return setarrage.indexOf(item) === idx;
        })
      }
    setSavePlace(state, action){
      const arr = new Array(state.length).fill(state);
      arr.push(action.payload);
    },
    setSaveArg(state, action){
      const arr = new Array(state.length).fill(state);
      arr.push(action.payload);
    }
  }
});

export const { setSaveReserve } = SaveReserve.actions;
export const { setSavePlace, setSaveArg } = SaveReserve.actions;

export default SaveReserve; 
~~~

</div>
</details>

- 아래 개선된 코드같이, axios로 get 요청할 때 전부 가져오지 말고,<br>
[query string을 이용하여](https://velog.io/@bang9dev/axios-with-qs) 그 매장에 맞는 데이터만 갖고 온 다음,<br>
날짜에 맞게 잘 가공하여 보여주는 로직을 짰습니다.

<details>
<summary><b>개선된 axios 코드</b></summary>
<div markdown="1">

~~~react.js
useEffect(() => {
    async function axiosdata(){
      try {
        const response = await axios.get('/api/reserve/place',{
          params : {place : revdata[id-1].name}
        });
        for ( let i=0; i<response?.data.length; i++) {
          dispatch(setSaveArg(response?.data[i].arrage));
          dispatch(setSavePbID(response?.data[i].publisherID));
          dispatch(setSaveDate(moment(response?.data[i].date).format('YYYY년 MM월 DD일')));
        }
        dispatch(setArray());
      } catch (error) {
        console.log(error);
      }
    }
    axiosdata();
    return () => {
      dispatch(clear());
    }
  },[dispatch]);
~~~

</div>
</details>
  
<details>
<summary><b>개선된 redux 코드</b></summary>
<div markdown="1">

~~~react.js
// 자리 데이터를 저장하는 state입니다.
// 초기 state : []
// 수정 state : [1,2,...]
import { createSlice } from "@reduxjs/toolkit";
const initialState = [];
const SaveReserve = createSlice({
  name : 'savereserve',
  initialState,
  reducers : {
    setSaveArg(state, action){
      state.push(action.payload);
    },
    setSavePbID(state, action){
      state.push(action.payload);
    },
    setSaveDate(state, action){
      state.push(action.payload);
    },
    setArray(state, action){
      const result = [];
      for (let i=0; i<state.length; i+=3){
        result.push(state.slice(i, i+3));
      }
      return result;
    },
    clear : () => initialState
  }
});

export const { clear, setSaveArg, setSavePbID, setSaveDate } = SaveReserve.actions;
export const { clear, setSaveArg, setSavePbID, setSaveDate, setArray } = SaveReserve.actions;

export default SaveReserve; 
~~~

</div>
</details>

</br>

## 6. 그 외 트러블 슈팅
<details>
<summary>예약할 시 자리 실시간 미반영 오류</summary>
<div markdown="1">

- 부모 컴포넌트에 useState 요소들을 설정 후, 예약버튼에 state를 변경하게 만든 다음<br>
  useEffect에 그 요소를 반영
~~~react.js
useEffect(() => {
    async function axiosdata(){
      try {
        const response = await axios.get('/api/reserve/place',{
          params : {place : revdata[id-1].name}
        });
        for ( let i=0; i<response?.data.length; i++) {
          dispatch(setSaveArg(response?.data[i].arrage));
          dispatch(setSavePbID(response?.data[i].publisherID));
          dispatch(setSaveDate(moment(response?.data[i].date).format('YYYY년 MM월 DD일')));
        }
        dispatch(setArray());
      } catch (error) {
        console.log(error);
      }
    }
},[dispatch, props.render]);
  
~~~

</div>
</details>

<details>
<summary>이미 예약된 자리 있을 때 예약 못하게 하기</summary>
<div markdown="1">
  
  - ArragePlace.js에서 includes 함수를 사용하여 해결
  - [https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/components/Reserve/ArragePlace.js](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/components/Reserve/ArragePlace.js)
  
</div>
</details>

<details>
<summary>BoardGame메뉴에서 원래대로 메뉴 구현</summary>
<div markdown="1">
  
  - `setMinFilter('')` 와 같이 state값을 빈 값으로 변경하기
  
</div>
</details>
    
<details>
<summary> proxy를 여러 경로로 만들고 싶을 때 </summary>
<div markdown="1">
  
- setupProxy.js에 모듈화하여 여러 경로를 설정할 수 있었습니다.
  
~~~react.js
const {createProxyMiddleware} = require('http-proxy-middleware');``
module.exports = function(app) {
    app.use('/api/',
    createProxyMiddleware( 
        { target: 'http://localhost:4001/', changeOrigin: true }
    ));
    app.use('/v1/nid/me',
    createProxyMiddleware(
        { target: "https://openapi.naver.com/", changeOrigin: true}
    ));
}
~~~
   
</div>
</details>    

<details>
<summary> 모집완료 누를 때, 신청인원 미반영 오류</summary>
<div markdown="1">
  
  - useEffect에 [setData]를 추가하여 axios 데이터가 변경될 때마다 useEffect를 적용하게 설정했습니다.
    - [https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/Party/ReadParty.js](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/Party/ReadParty.js)
   
</div>
</details>    

<details>
<summary> Google 소셜로그인 구현</summary>
<div markdown="1">
  
  - 유튜브 영상을 참고하여 해결
    - 참고
      - [https://www.youtube.com/watch?v=roxC8SMs7HU](https://www.youtube.com/watch?v=roxC8SMs7HU)
        
</div>
</details>  
    
<details>
<summary>회원가입 중복확인시 state 미반영 오류</summary>
<div markdown="1">
  
  - 중복확인 버튼을 만들어 state 데이터값을 
        
</div>
</details> 
    
<details>
<summary> 컨텐츠수정 모달창에서 태그 셀렉트박스 드랍다운이 뒤쪽에 보이는 문제</summary>
<div markdown="1">
  
   - ElementUI의 Global Config에 옵션 추가하면 해결
     - main.js 파일에 `Vue.us(ElementUI, { zIndex: 9999 });` 옵션 추가(9999 이하면 안됌)
   - 참고
     - [https://element.eleme.io/#/en-US/component/quickstart#global-config](https://element.eleme.io/#/en-US/component/quickstart#global-config)
        
</div>
</details> 

<details>
<summary> HTTP delete Request시 개발자도구의 XHR(XMLHttpRequest )에서 delete요청이 2번씩 찍히는 이유</summary>
<div markdown="1">
  
  - When you try to send a XMLHttpRequest to a different domain than the page is hosted, you are violating the same-origin policy. However, this situation became somewhat common, many technics are introduced. CORS is one of them.

        In short, server that you are sending the DELETE request allows cross domain requests. In the process, there should be a **preflight** call and that is the **HTTP OPTION** call.

        So, you are having two responses for the **OPTION** and **DELETE** call.

        see [MDN page for CORS](https://developer.mozilla.org/en-US/docs/Web/HTTP/Access_control_CORS).

    - 출처 : [https://stackoverflow.com/questions/35808655/why-do-i-get-back-2-responses-of-200-and-204-when-using-an-ajax-call-to-delete-o](https://stackoverflow.com/questions/35808655/why-do-i-get-back-2-responses-of-200-and-204-when-using-an-ajax-call-to-delete-o)
        
</div>
</details> 

<details>
<summary> 이미지 파싱 시 og:image 경로가 달라서 제대로 파싱이 안되는 경우</summary>
<div markdown="1">
  
  - UserAgent 설정으로 해결
        - [https://www.javacodeexamples.com/jsoup-set-user-agent-example/760](https://www.javacodeexamples.com/jsoup-set-user-agent-example/760)
        - [http://www.useragentstring.com/](http://www.useragentstring.com/)
        
</div>
</details> 
    
<details>
<summary> 구글 로그인으로 로그인한 사용자의 정보를 가져오는 방법이 스프링 2.0대 버전에서 달라진 것</summary>
<div markdown="1">
  
  - 1.5대 버전에서는 Controller의 인자로 Principal을 넘기면 principal.getName(0에서 바로 꺼내서 쓸 수 있었는데, 2.0대 버전에서는 principal.getName()의 경우 principal 객체.toString()을 반환한다.
    - 1.5대 버전에서 principal을 사용하는 경우
    - 아래와 같이 사용했다면,

    ```jsx
    @RequestMapping("/sso/user")
    @SuppressWarnings("unchecked")
    public Map<String, String> user(Principal principal) {
        if (principal != null) {
            OAuth2Authentication oAuth2Authentication = (OAuth2Authentication) principal;
            Authentication authentication = oAuth2Authentication.getUserAuthentication();
            Map<String, String> details = new LinkedHashMap<>();
            details = (Map<String, String>) authentication.getDetails();
            logger.info("details = " + details);  // id, email, name, link etc.
            Map<String, String> map = new LinkedHashMap<>();
            map.put("email", details.get("email"));
            return map;
        }
        return null;
    }
    ```

    - 2.0대 버전에서는
    - 아래와 같이 principal 객체의 내용을 꺼내 쓸 수 있다.

    ```jsx
    UsernamePasswordAuthenticationToken token =
                    (UsernamePasswordAuthenticationToken) SecurityContextHolder
                            .getContext().getAuthentication();
            Map<String, Object> map = (Map<String, Object>) token.getPrincipal();

            String email = String.valueOf(map.get("email"));
            post.setMember(memberRepository.findByEmail(email));
    ```
        
</div>
</details> 
    
<details>
<summary> 랭킹 동점자 처리 문제</summary>
<div markdown="1">
  
  - PageRequest의 Sort부분에서 properties를 "rankPoint"를 주고 "likeCnt"를 줘서 댓글수보다 좋아요수가 우선순위 갖도록 설정.
  - 좋아요 수도 똑같다면..........
        
</div>
</details> 
    
</br>
