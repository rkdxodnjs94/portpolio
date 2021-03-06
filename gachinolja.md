# π  κ°μ΄λμ
> λ³΄λκ²μμΉ΄ν μμ½μλΉμ€
> [νλ‘ νΈμλ](https://github.com/rkdxodnjs94/gachinolja.git)
> [λ°±μλ](https://github.com/rkdxodnjs94/gachiback.git)

<br>

## 1. μ μ κΈ°κ° & μ°Έμ¬ μΈμ
- 2022λ 5μ 16μΌ ~ 6μ 21μΌ
- κ°μΈ νλ‘μ νΈ

<br>

## 2. μ¬μ© κΈ°μ 
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

## 3. ERD μ€κ³
![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/gachinolja%20ERD.png)

## 4. ν΅μ¬ κΈ°λ₯
μ΄ μλΉμ€μ ν΅μ¬ κΈ°λ₯μ μμ½κΈ°λ₯μλλ€.<br>
μμΈμ λ΄μ λ³΄λκ²μ λ§€μ₯μ κ²μνμ¬ μνλ μλ¦¬, λ μ§, μκ°, μΈμμ μμ½νλ©΄ λ©λλ€.<br>
μ΄ κΈ°λ₯λ€μ νλ¦μ λ³΄λ©΄, μλΉμ€κ° μ΄λ»κ² λμνλμ§ μ μ μμ΅λλ€.

<details>
<summary><b>ν΅μ¬ κΈ°λ₯ μ€λͺ νΌμΉκΈ°</b></summary>
<div markdown="1">
  
### 4.1. μ μ²΄ νλ¦
![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flowpoint.png)

### 4.2. μ¬μ©μ μμ²­
![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flow1.png)

- **URL μ κ·μ μ²΄ν¬** :pushpin: [μ½λ νμΈ](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/SignUp.js)
  - React.jsλ‘ λ λλ§λ νλ©΄λ¨μμ, μ¬μ©μκ° λ±λ‘μ μλν URLμ λͺ¨μμλ₯Ό μ κ·μμΌλ‘ νμΈν©λλ€.
  - URLμ λͺ¨μμκ° μλ κ²½μ°, μλ¬ λ©μΈμ§λ₯Ό λμλλ€.

- **Axios λΉλκΈ° μμ²­** :pushpin: [μ½λ νμΈ](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/SignUp.js)
  - URLμ λͺ¨μμμΈ κ²½μ°, μ»¨νμΈ λ₯Ό λ±λ‘νλ POST μμ²­μ λΉλκΈ°λ‘ λ λ¦½λλ€.

### 4.3. mongoose & Service

![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flow2.png)

- **mongoose** :pushpin: [μ½λ νμΈ](https://github.com/rkdxodnjs94/gachiback/blob/main/src/models/user.js)
  - mongooseμμ schema λͺ¨λΈμ μμ±ν©λλ€.

- **index** :pushpin: [μ½λ νμΈ](https://github.com/rkdxodnjs94/gachiback/blob/main/src/api/user/index.js)
  - κ·Έ λͺ¨λΈμ ν λλ‘ appμ indexμμ urlμ ν΅ν΄ μμ²­ν©λλ€.

### 4.4. Controller

![](https://raw.githubusercontent.com/rkdxodnjs94/image/main/flow3.png)

- **κ²°κ³Ό μλ΅** :pushpin: [μ½λ νμΈ](https://github.com/rkdxodnjs94/gachiback/blob/main/src/api/user/user.ctrl.js)
  - μμ²­λ°μ urlμ ν λλ‘ λ°μ΄ν°κ° μ λ€μ΄μλμ§ λ‘μ§μ²λ¦¬λ₯Ό ν©λλ€.

- **DBμ μ μ₯** :pushpin:
  - λ‘μ§μ²λ¦¬λ₯Ό λ§μΉ ν, apiμ urlλ‘ mongoDB μλ²μ λ°μ΄ν°λ₯Ό μ μ₯ν©λλ€.

- **μ»¨νμΈ  μ μ₯** :pushpin:
  - μ μ₯λ μ»¨νμΈ λ λ€μ mongoDB - Controller - indexλ₯Ό κ±°μ³ νλ©΄λ¨μ μ‘μΆλ©λλ€.

</div>
</details>

</br>

## 5. ν΅μ¬ νΈλ¬λΈ μν
### 5.1. λ§€μ₯λ§λ€ λ€λ₯Έ λ°μ΄ν° κ°μ Έμ€λ λ²
- μ΄ μ¬μ΄νΈμ λ§€μ₯μ΄ μ½ 150κ° μλλ°, κ° λ§€μ₯μ λ§λ λ μ§, μκ°, μλ¦¬, μΈμ λ°μ΄ν°λ₯Ό κ°μ Έμ€κ³  μΆμμ΅λλ€.

- μ²μμ μ μ²΄ λ§€μ₯μ μμ½ λ°μ΄ν°λ€μ μ λΆ λ€ κ°μ Έμμ κ° λ§€μ₯μ λ§κ² κ°κ³΅νμ¬ μ κ³΅ν  μμ μ΄μμ§λ§,<br>
λͺ¨λ  μ‘°κ±΄μ λ§μ‘±ν  λ°μ΄ν°λ₯Ό λ§€μ₯μ λ§κ² μΆλ ₯νλκ² μ½μ§ μμμ΅λλ€.

<details>
<summary><b>axiosλ‘ κ°μ Έμ¨ κΈ°μ‘΄ μ½λ</b></summary>
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

- κΈ°μ‘΄ reduxλ‘ μ΄μ©ν state μλ£μλλ€.

<details>
<summary><b>κΈ°μ‘΄ redux μ½λ</b></summary>
<div markdown="1">

~~~react.js
// μλ¦¬ λ°μ΄ν°λ₯Ό μ μ₯νλ stateμλλ€.
// μ΄κΈ° state : [ [] ]
// μμ  state : [ ['κ°λ¨μ ',1,2,3,...],['νλμ ',1,2,3,...], [...] ]
// μ΄κΈ° state : []
// μμ  state : [ ['κ°λ¨μ ',1,2,3..],['νλμ ',1,2,3,...], ]
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

- μλ κ°μ λ μ½λκ°μ΄, axiosλ‘ get μμ²­ν  λ μ λΆ κ°μ Έμ€μ§ λ§κ³ ,<br>
[query stringμ μ΄μ©νμ¬](https://velog.io/@bang9dev/axios-with-qs) κ·Έ λ§€μ₯μ λ§λ λ°μ΄ν°λ§ κ°κ³  μ¨ λ€μ,<br>
λ μ§μ λ§κ² μ κ°κ³΅νμ¬ λ³΄μ¬μ£Όλ λ‘μ§μ μ§°μ΅λλ€.

<details>
<summary><b>κ°μ λ axios μ½λ</b></summary>
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
          dispatch(setSaveDate(moment(response?.data[i].date).format('YYYYλ MMμ DDμΌ')));
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
<summary><b>κ°μ λ redux μ½λ</b></summary>
<div markdown="1">

~~~react.js
// μλ¦¬ λ°μ΄ν°λ₯Ό μ μ₯νλ stateμλλ€.
// μ΄κΈ° state : []
// μμ  state : [1,2,...]
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

## 6. κ·Έ μΈ νΈλ¬λΈ μν
<details>
<summary>μμ½ν  μ μλ¦¬ μ€μκ° λ―Έλ°μ μ€λ₯</summary>
<div markdown="1">

- λΆλͺ¨ μ»΄ν¬λνΈμ useState μμλ€μ μ€μ  ν, μμ½λ²νΌμ stateλ₯Ό λ³κ²½νκ² λ§λ  λ€μ<br>
  useEffectμ κ·Έ μμλ₯Ό λ°μ
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
          dispatch(setSaveDate(moment(response?.data[i].date).format('YYYYλ MMμ DDμΌ')));
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
<summary>μ΄λ―Έ μμ½λ μλ¦¬ μμ λ μμ½ λͺ»νκ² νκΈ°</summary>
<div markdown="1">
  
  - ArragePlace.jsμμ includes ν¨μλ₯Ό μ¬μ©νμ¬ ν΄κ²°
  - [https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/components/Reserve/ArragePlace.js](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/components/Reserve/ArragePlace.js)
  
</div>
</details>

<details>
<summary>BoardGameλ©λ΄μμ μλλλ‘ λ©λ΄ κ΅¬ν</summary>
<div markdown="1">
  
  - `setMinFilter('')` μ κ°μ΄ stateκ°μ λΉ κ°μΌλ‘ λ³κ²½νκΈ°
  
</div>
</details>
    
<details>
<summary> proxyλ₯Ό μ¬λ¬ κ²½λ‘λ‘ λ§λ€κ³  μΆμ λ </summary>
<div markdown="1">
  
- setupProxy.jsμ λͺ¨λννμ¬ μ¬λ¬ κ²½λ‘λ₯Ό μ€μ ν  μ μμμ΅λλ€.
  
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
<summary> λͺ¨μ§μλ£ λλ₯Ό λ, μ μ²­μΈμ λ―Έλ°μ μ€λ₯</summary>
<div markdown="1">
  
  - useEffectμ [setData]λ₯Ό μΆκ°νμ¬ axios λ°μ΄ν°κ° λ³κ²½λ  λλ§λ€ useEffectλ₯Ό μ μ©νκ² μ€μ νμ΅λλ€.
    - [https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/Party/ReadParty.js](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/Party/ReadParty.js)
   
</div>
</details>    

<details>
<summary> Google μμλ‘κ·ΈμΈ κ΅¬ν</summary>
<div markdown="1">
  
  - μ νλΈ μμμ μ°Έκ³ νμ¬ ν΄κ²°
    - μ°Έκ³ 
      - [https://www.youtube.com/watch?v=roxC8SMs7HU](https://www.youtube.com/watch?v=roxC8SMs7HU)
        
</div>
</details>  
    
<details>
<summary>νμκ°μ μ€λ³΅νμΈμ state λ―Έλ°μ μ€λ₯</summary>
<div markdown="1">
  
  - onChangeμ stateκ°μ κΈΈμ΄λ₯Ό μΈ‘μ νλ € ν΄λ μ λλ‘ λ°μμ΄ μλμ΅λλ€.
  
  - ν΄κ²°
  
    - μ€λ³΅νμΈ λ²νΌμ λ§λ€μ΄ state λ°μ΄ν°κ°κ³Ό axios λ°μ΄ν°κ°μ΄ μΌμΉνλλ‘ λ‘μ§ κ΅¬ν
    - [https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/SignUp.js](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/SignUp.js)
        
</div>
</details> 
    
<details>
<summary> stateλ³κ²½μ μ‘°νμ null μ€λ₯</summary>
<div markdown="1">
  
   - Schemaμ typeμ νμ Numberμμ StringμΌλ‘ λ³κ²½νκ³ , defaultκ°μ '0'μΌλ‘ λ³κ²½νκ³ ,<br>
   axiosμ patch μμ²­ν  λ, Stringμ Numberλ‘ λ³νν μνμμ +1 νμ¬ λ³κ²½λ λ°μ΄ν° λ°μν©λλ€.
     - [Schema λ§ν¬](
     - [axios λ§ν¬](https://github.com/rkdxodnjs94/gachinolja/blob/frontend/frontend/src/pages/Inquiry/NoticeDetail.js)
        
</div>
</details> 

<details>
<summary> λ‘κ·ΈμΈμ°½μ κ»λ€ ν¬ λ λ λ² λλ¬μΌ λμ€λ νμ</summary>
<div markdown="1">
  
  - λ³κ²½stateλ₯Ό !stateλ‘ νμ¬ ν΄λ¦­ν  λ μλμΌλ‘ true, falseλ‘ λ³κ²½λλλ‘ μ€μ μ νλλ°,<br>
   λ€λ₯Έ νμ΄μ§λ₯Ό μ΄λν  λ λ‘κ·ΈμΈνμμλ λ‘κ·ΈμΈνλΌλ μ°½μ΄ λ¨λ λ¬Έμ κ° λ°μνμ΅λλ€.

  - ν΄κ²°
    - μ΄κΈ° stateλ₯Ό falseλ‘ μ€μ νκ³ , λ³κ²½ stateκ°μ true λλ falseλ‘ λ³κ²½νμ¬ <br>
  μ΄λ²€νΈ λ°μν λλ§λ€ `dispatch(setLogin(false))`κ°μ΄ λ³κ²½stateλ₯Ό μμ±νμ΅λλ€. 
        
</div>
</details> 

    
</br>
