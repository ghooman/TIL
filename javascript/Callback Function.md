# Callback Function

## π μ½λ°±ν¨μ(Callback Function)λ?
`νλΌλ―Έν°λ‘ ν¨μλ₯Ό μ λ¬νλ ν¨μ`
μ½λ°±ν¨μ(Callback Function)λ νλΌλ―Έν°λ‘ ν¨μλ₯Ό μ λ¬λ°μ, ν¨μμ λ΄λΆμμ μ€ννλ ν¨μμ΄λ€.

```javascript
let number = [1, 2, 3, 4, 5]
number.forEach(el => console.log(el * 2));

/*
<output>
2
4
6
8
10
*/
```
  
μ½λ°±ν¨μλ μ΄λ―Έ μ°λ¦¬μ μ½λ μμμ μμ£Ό μ¬μ©λκ³  μλ€.
μλ₯Ό λ€μ΄, `forEach`ν¨μμ κ²½μ° ν¨μ μμ μ΅λͺμ ν¨μλ₯Ό λ£μ΄μ `forEach`λ¬Έμ λμμν¨λ€.
***

## π μ½λ°± ν¨μ(Callback Function)μ¬μ© μμΉ
__βοΈ μ΅λͺμ ν¨μ μ¬μ©__

```javascript
let number = [1, 2, 3, 4, 5];

number.forEach(function(x) {
  console.log(x * 2);
});
```

μμ μμ λ₯Ό νμ΄ν ν¨μμμ μΌλ° ν¨μλ‘ λ°κΎΌ μμ μ΄λ€.   
μ½λ°±ν¨μλ μ΄λ¦μ΄ μλ 'μ΅λͺμ ν¨μ'λ₯Ό μ¬μ©νλ€. ν¨μμ λ΄λΆμμ μ€νλκΈ° λλ¬Έμ μ΄λ¦μ λΆμ΄μ§ μμλ λλ€.

__βοΈ ν¨μμ μ΄λ¦(λ§) λκΈ°κΈ°__

```javascript
function whatYourName(name, callback) {
  console.log('name:', name);
  callback();
}

function finishFunc() {
  console.log('finish function');
}

whatYourName('jihoo', finishFunc);

/*
<output>
name: jihoo
finish function
*/
```
