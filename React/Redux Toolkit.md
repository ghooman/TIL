## ๐ Redux
๊ณต์๋ฌธ์๋ฅผ ์ฐธ์กฐํ ์ ์๋ ๋ค์๊ณผ ๊ฐ๋ค.   
>  ์๋ฐ์คํฌ๋ฆฝํธ๋ก ๊ตฌ๋๋๋ ์ดํ๋ฆฌ์ผ์ด์์์ ์์ธก ๊ฐ๋ฅํ ์ํ๊ด๋ฆฌ๋ฅผ ๋์์ฃผ๋ ์ํ๊ด๋ฆฌ ๋ผ์ด๋ธ๋ฌ๋ฆฌ

์ฝ๊ฒ ๋งํ๋ฉด Redux๋ props ์์ด state๋ฅผ ๊ณต์ ํ  ์ ์๊ฒ ๋์์ฃผ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ์ด๋ค.   
<img width="364" alt="แแขแธแแฅ" src="https://user-images.githubusercontent.com/85857465/180614082-583c3571-f37b-49b4-9614-8abdd869e885.png">   
์ด๊ฑฐ ์ค์นํ๋ฉด js ํ์ผ ํ๋์ state๋ค์ ๋ณด๊ดํ  ์ ์๋๋ฐ ๊ทธ๊ฑธ ๋ชจ๋  ์ปดํฌ๋ํธ๊ฐ ์ง์  ๊บผ๋ด์ธ ์ ์๋ค.   
๊ทธ๋์ ๊ท์ฐฎ์ props ์ ์ก์ด ํ์์์ด์ง๋ค. (์ปดํฌ๋ํธ๊ฐ ๋ง์์ง ์๋ก ์ข๊ฒ ๋ค.)   
๊ทธ๋์ ์ฌ์ดํธ๊ฐ ์ปค์ง๋ฉด ์ธ ์ ๋ฐ์ ์์ด์ ๊ฐ๋ฐ์ ๊ตฌ์ธ์์๋ redux๊ฐ์ ๋ผ์ด๋ธ๋ฌ๋ฆฌ ์๋ จ๋๋ฅผ ๋๋ถ๋ถ ์๊ตฌํ๋ค๊ณ  ํ๋ค.
***
## ๐ Redux Toolkit
Redux Toolkit์ Redux๋ฅผ ๋ ์ฌ์ฉํ๊ธฐ ์ฝ๊ฒ ๋ง๋ค๊ธฐ ์ํด Redux์์ ๊ณต์ ์ ๊ณตํ๋ ๊ฐ๋ฐ๋๊ตฌ์ด๋ค.    
Redux Toolkit์ ์๋์ ๊ฐ์ Redux์ ๋จ์ ์ ๋ณด์ํ๊ณ ์ ๋ง๋ค์ด์ก๋ค.
- ๋ฆฌ๋์ค์ ๋ณต์กํ ์คํ ์ด ์ค์ 
- ๋ฆฌ๋์ค๋ฅผ ์ ์ฉํ๊ฒ ์ฌ์ฉํ๊ธฐ ์ํด์ ์ถ๊ฐ๋์ด์ผ ํ๋ ๋ง์ ํจํค์ง๋ค
- ๋ฆฌ๋์ค ์ฌ์ฉ์ ์ํด ์๊ตฌ๋๋ ๋ค๋์ ์์ฉ๊ตฌ(boilerplate) ์ฝ๋๋ค

์ด๋ฌํ Redux์ ํ๊ณ๋ฅผ ๊นจ๋ซ๊ณ  "ํจ์จ์ ์ธ Redux ๊ฐ๋ฐ์ ์ํ ๊ณต์์ ์ด๊ณ  ๋๋จ์ ์ธ ๋ฐฐํฐ๋ฆฌ ํฌํจ ๋๊ตฌ ์ธํธ" Redux Toolkit (RTK)๊ฐ ๊ฐ๋ฐ๋์๋ค.
***
### โ๏ธ ์ค์น
```
npm install @reduxjs/toolkit react-redux
```
ํฐ๋ฏธ๋์ ์๋ ฅํ๋ฉด ๋๋ค.   
์ฐธ๊ณ ๋ก `redux toolkit`์ด๋ผ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๋ฅผ ์ค์นํ  ๊ฑด๋ฐ redux์ ๊ฐ์ ๋ฒ์ ์ด๋ผ๊ณ  ๋ณด๋ฉด ๋๋ค.(๋ฌธ๋ฒ์ด ์ข ๋ ์ฌ์์ง)   
๊ทผ๋ฐ ์ค์นํ๊ธฐ ์ ์ package.json ํ์ผ์ ์ด์ด์   

"react"
"react-dom" 

ํญ๋ชฉ์ ๋ฒ์ ์ ํ์ธํด์ผ ๋๋ค.   

์ด๊ฑฐ ๋๊ฐ๊ฐ 18.1.x ์ด์์ด๋ฉด ์ฌ์ฉ ๊ฐ๋ฅํ๋ค.
***
### โ๏ธ ์ํ
srcํด๋์ store.jsํ์ผ(state๋ค์ ๋ณด๊ดํ๋ ํ์ผ์ด๋ค.)์ ๋ง๋ค์ด์ ์๋ ์ฝ๋๋ฅผ ๋ณต๋ถํ๋ค.
```javascript
import { configureStore } from '@reduxjs/toolkit'

export default configureStore({
  reducer: { }
}) 
```

`index.js` ํ์ผ์ ๋ฐ์ ์ฒ๋ผ ์์ฑํด ์ค๋ค.
```javascript
import { Provider } from "react-redux";
import store from './store.js'

const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(
  <React.StrictMode>
    <Provider store={store}>
      <BrowserRouter>
        <App />
      </BrowserRouter>
    </Provider>
  </React.StrictMode>
); 
```
Provider๋ผ๋ ์ปดํฌ๋ํธ์ store.js๋ฅผ importํด์จ๋ค.   
๊ทธ๋ฆฌ๊ณ  ๋ฐ์ <Provider store={importํด์จ๊ฑฐ}> ์ด๊ฑธ๋ก App ์ปดํฌ๋ํธ๋ฅผ ๊ฐ์ธ๋ฉด ๋๋ค.   
๊ทธ๋ผ ์ด์  App ์ปดํฌ๋ํธ์ ๊ทธ ๋ชจ๋  ์์ ์ปดํฌ๋ํธ๋ค์ store.js์ ์๋ state๋ฅผ ๋ง๋๋ก ๊บผ๋ด์ธ ์ ์๋ค.
***
### โ๏ธ ์ฌ์ฉ๋ฒ
>Redux store์ state ๋ณด๊ดํ๋ ๋ฒ 

store.js ํ์ผ ์ด์ด์ ์ด๋ ๊ฒ ์ฝ๋์ง๋ฉด state ํ๋ ๋ง๋ค ์ ์๋ค.   

step 1. createSlice( ) ๋ก state ๋ง๋ค๊ณ    
step 2. configureStore( ) ์์ ๋ฑ๋กํ๋ฉด ๋๋ค.
```javascript
import { configureStore, createSlice } from '@reduxjs/toolkit'

let user = createSlice({
  name : 'user',
  initialState : 'kim'
})

export default configureStore({
  reducer: {
    user : user.reducer
  }
})
```
1. createSlice() ์๋จ์์ import ํด์จ ๋ค์์   
{ name : 'state์ด๋ฆ', initialState : 'state๊ฐ' } ๋ฃ์ผ๋ฉด state ํ๋ ์์ฑ ๊ฐ๋ฅํ๋ค.     
(createSlice()๋ useState() ์ ์ฉ๋๊ฐ ๋น์ทํ๋ค๊ณ  ๋ณด๋ฉด ๋๋ค.)   

2. state ๋ฑ๋ก์ configureStore() ์์ ํ๋ฉด ๋๋ค.   
{ ์๋ช : createSlice๋ง๋ ๊ฑฐ.reducer } ์ด๋ฌ๋ฉด ๋ฑ๋ก ๋์ด๋ค.   
์ฌ๊ธฐ ๋ฑ๋กํ state๋ ๋ชจ๋  ์ปดํฌ๋ํธ๊ฐ ์์ ๋กญ๊ฒ ์ฌ์ฉ ๊ฐ๋ฅํ๋ค.   

>Redux store์ ์๋ state ๊ฐ์ ธ๋ค ์ฐ๋ ๋ฒ
```javascript
import { useSelector } from "react-redux"

function Cart(){
  let a = useSelector((state) => { return state })
  console.log(a)

  return (์๋ต)
}
```

์๋ฌด ์ปดํฌ๋ํธ์์ ์๋จ์ useSelctor๋ฅผ importํด์ค๊ณ    
useSelector((state) => { return state } ) ์ฐ๋ฉด store์ ์๋ ๋ชจ๋  state๊ฐ ๊ทธ ์๋ฆฌ์ ๋จ๋๋ค.   
์ถ๋ ฅํด ๋ณด๋ฉด { user : 'kim' } ์ถ๋ ฅ ๋๋ค.

```javascript
let a = useSelector((state) => state.user)
```
์ด๋ฐ์์ผ๋ก ์ฐ๋ฉด kim์ด ์ถ๋ ฅ ๋๋ค.
***
### โ๏ธ store์ state ๋ณ๊ฒฝํ๋ ๋ฒ   
>1. store.js ์์ state ์์ ํด์ฃผ๋ ํจ์๋ถํฐ ๋ง๋ ๋ค.
```javascript
let user = createSlice({
  name : 'user',
  initialState : 'kim',
  reducers : {
    changeName(state){
      return 'john ' + state
    }
  }
}) 
```
slice ์์ reducers: { } ์ด๊ณ  ๊ฑฐ๊ธฐ ์์ ํจ์ ๋ง๋ค๋ฉด ๋๋ค.   
- ํจ์ ์๋ช ๋ง์๋๋ก ํ๋ค.   
- ํ๋ผ๋ฏธํฐ ํ๋ ์๋ชํ๋ฉด ๊ทธ๊ฑด ๊ธฐ์กด state๊ฐ ๋๋ค.   
- return ์ฐ์ธก์ ์๋ก์ด state ์๋ ฅํ๋ฉด ๊ทธ๊ฑธ๋ก ๊ธฐ์กด state๋ฅผ ๊ฐ์์น์์ค๋ค.   

์ด์  changeName() ์ธ ๋ ๋ง๋ค 'kim' -> 'john kim' ์ด๋ ๊ฒ ๋ณํ๋ค.   

>2. ๋ค๋ฅธ ๊ณณ์์ ์ฐ๊ธฐ์ข๊ฒ export ํด๋๋ค.
```javascript
export let { changeName } = user.actions
```
์ด๋ฐ ์ฝ๋๋ฅผ store.js ๋ฐ์ ์ถ๊ฐํ๋ฉด ๋๋ค.   
slice์ด๋ฆ.actions ๋ผ๊ณ  ์ ์ผ๋ฉด state ๋ณ๊ฒฝํจ์๊ฐ ์ ๋ถ ๊ทธ ์๋ฆฌ์ ์ถ๋ ฅ๋๋ค.   
๊ทธ๊ฑธ ๋ณ์์ ์ ์ฅํ๋ค๊ฐ export ํ๋ผ๋ ๋ป์ด๋ค.   

>3. ์ํ  ๋ import ํด์ ์ฌ์ฉํ๋ค. dispatch()๋ก ๊ฐ์ธ์ ์ฌ์ฉํด์ผ ๋๋ค.

์๋ฅผ ๋ค์ด์ Cart.js ์์ ๋ฒํผ๊ฐ์๊ฑฐ ํ๋ ๋ง๋ค๊ณ 
๊ทธ ๋ฒํผ ๋๋ฅด๋ฉด state๋ฅผ 'kim' -> 'john kim' ์ด๋ ๊ฒ ๋ณ๊ฒฝํ๊ณ  ์ถ์ผ๋ฉด
```javascript
(Cart.js)

import { useDispatch, useSelector } from "react-redux"
import { changeName } from "./../store.js"

(์๋ต) 

<button onClick={()=>{
  dispatch(changeName())
}}>๋ฒํผ์</button>
```
์ด๋ ๊ฒ ์ฝ๋์ง๋ฉด ๋๋ค.
- store.js์์ ์ํ๋ state๋ณ๊ฒฝํจ์ ๊ฐ์ ธ์ค๋ฉด ๋๊ณ    
- useDispatch ๋ผ๋ ๊ฒ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ์์ ๊ฐ์ ธ์จ๋ค.   
- ๊ทธ๋ฆฌ๊ณ  dispatch( state๋ณ๊ฒฝํจ์() ) ์ด๋ ๊ฒ ๊ฐ์ธ์ ์คํํ๋ฉด state ์ง์ง๋ก ๋ณ๊ฒฝ๋๋ค. 
***
### โ๏ธ redux state๊ฐ array/object์ธ ๊ฒฝ์ฐ ๋ณ๊ฒฝํ๋ ๋ฒ
{name : 'kim', age : 20} ์ด๋ ๊ฒ ์๊ธด ์๋ฃ๋ฅผ state๋ก ๋ง๋ค์ด๋ณธ๋ค.   
'kim' -> 'park' ์ด๋ ๊ฒ ๋ณ๊ฒฝํ๊ณ  ์ถ์ผ๋ฉด
```javascript
let user = createSlice({
  name : 'user',
  initialState : {name : 'kim', age : 20},
  reducers : {
    changeName(state){
      return {name : 'park', age : 20}
    }
  }
}) 
```
์ด๋ ๊ฒ ์ฐ๋ฉด changeName() ์ฌ์ฉ์ ๋ณ๊ฒฝ๋๋ค.   
return ์ค๋ฅธ์ชฝ์ ์ ์๊ฑธ๋ก ๊ธฐ์กด state๋ฅผ ๋ฐ๊ฟ์ฃผ๊ธฐ ๋๋ฌธ์ด๋ค.   
  
```javascript
let user = createSlice({
  name : 'user',
  initialState : {name : 'kim', age : 20},
  reducers : {
    changeName(state){
      state.name = 'park'
    }
  }
}) 
```
๊ทผ๋ฐ state๋ฅผ ์ง์  ์์ ํด๋ ๋ณ๊ฒฝ์ด ์ ๋๋ค.   
state๋ฅผ ์ง์  ์์ ํ๋ ๋ฌธ๋ฒ์ ์ฌ์ฉํด๋ ์ ๋ณ๊ฒฝ๋๋ ์ด์ ๋   
Immer.js๋ผ๋ ๋ผ์ด๋ธ๋ฌ๋ฆฌ๊ฐ state ์ฌ๋ณธ์ ํ๋ ๋ ์์ฑํด์ค ๋๋ถ์ธ๋ฐ Redux ์ค์นํ๋ฉด ๋ธ๋ ค์์ ๊ทธ๋ ๋ค๊ณ  ํ๋ค.   

๊ทธ๋์ ๊ฒฐ๋ก ์ array/object ์๋ฃ์ ๊ฒฝ์ฐ state๋ณ๊ฒฝ์   
state๋ฅผ ์ง์  ์์ ํด๋ ์ ๋๋๊น ์ง์  ์์ ํ๋ฉด ๋๋ค.
***
### โ๏ธ state ๋ณ๊ฒฝํจ์๊ฐ ์ฌ๋ฌ๊ฐ ํ์ํ ๊ฒฝ์ฐ
์๋ฅผ ๋ค์ด์ +1 ํ๋ ๊ธฐ๋ฅ ๋๋ +10, +100์ ํ๋ ๊ธฐ๋ฅ์ ๋ง๋ค๊ณ  ์ถ์ผ๋ฉด   
์ฌ๋ฌ๊ฐ์ ํจ์๋ฅผ ๋ง๋ค์ง ์๊ณ  ํ๋ผ๋ฏธํฐ๋ฌธ๋ฒ ์ด์ฉํ๋ฉด ๋น์ทํ ํจ์ ์ฌ๋ฌ๊ฐ ๋ง๋ค ํ์๊ฐ ์๋ค๊ณ  ํ๋ค.   

state๋ณ๊ฒฝํจ์์๋ ํ๋ผ๋ฏธํฐ๋ฌธ๋ฒ ์ฌ์ฉ๊ฐ๋ฅํจ.
```javascript
let user = createSlice({
  name : 'user',
  initialState : {name : 'kim', age : 20},
  reducers : {
    increase(state, a){
      state.age += a.payload
    }
  }
}) 
```
state๋ณ๊ฒฝํจ์์ ๋์งธ ํ๋ผ๋ฏธํฐ๋ฅผ ์๋ชํ๋ฉด ์ด์    
increase(10)   
increase(100)   
์ด๋ฐ ์์ผ๋ก ํ๋ผ๋ฏธํฐ์๋ ฅ์ ํด์ ํจ์์ฌ์ฉ์ด ๊ฐ๋ฅํ๋ค.   
ํ๋ผ๋ฏธํฐ์๋ฆฌ์ ๋ฃ์ ์๋ฃ๋ค์ a.payload ํ๋ฉด ๋์จ๋ค.   

(์ฐธ๊ณ )   
- a ๋ง๊ณ  action ์ด๋ฐ ์์ผ๋ก ์๋ช ๋ง์ด ํ๋ค๊ณ  ํ๋ค. 
- action.type ํ๋ฉด state๋ณ๊ฒฝํจ์ ์ด๋ฆ์ด ๋์ค๊ณ 
- action.payload ํ๋ฉด ํ๋ผ๋ฏธํฐ๊ฐ ๋์จ๋ค.
