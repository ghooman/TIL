## π Number(str)
Number λ©μλλ λ¬Έμμ΄μ μΈμλ‘ λ°μΌλ©΄ ν΄λΉ λ¬Έμμ΄μ μ«μλ‘ λ°κΏμ€λ€.
```javascript
var num = Number('1234'); // 1234
```

μλμ²λΌ λ¬Έμμ΄μ΄ μ«μκ° μλ κ²½μ° numμλ NaNμ΄ μ μ₯λλ€.
```javascriptΒ 
let num = Number('1000μ'); // NaN
```

μμμ μ΄ μλ κ²½μ°μλ λͺ¨λ μ«μνμΌλ‘ λ°λκ² λλ€.
```javascript
let num = Number('10.123'); // 10.123
```
***
## π parseInt(str)
κΈ°λ³Έμ μΌλ‘ Number(str)μ λμΌνκ² λ¬Έμμ΄μ μΈμλ‘ λ°μΌλ©΄ ν΄λΉ λ¬Έμμ΄μ μ«μλ‘ λ°κΏμ€λ€.   
μλμ μ½λλ '1234'λΌλ λ¬Έμμ΄μ 1234λΌλ μ«μλ‘ ν λ³ννμ¬ λ³μ numμ λ΄λ μ½λμ΄λ€.
```javascript
let num = parseInt('1234'); // 1234
```

λ¬Έμμ΄μ΄ μ«μκ° μλ κ²½μ°κ° Number()μ μ‘°κΈ λ€λ₯Έλ°, λ¬Έμμ΄μ΄ μ«μλ‘ μμνλ κ²½μ°μλ μ«μκ° λλ  λκΉμ§λ§ ν λ³νμ νμ¬ numμ μ μ₯λλ€.   
μμμ΄ μ«μκ° μλλ©΄ Number()μ λ§μ°¬κ°μ§λ‘ numμ΄ NaNμ΄ μ μ₯λλ€.
```javascriptΒ 
let num = parseInt('1000μ'); // numμ 1000μ΄ μ μ₯
let num = parseInt('κ°κ²© : 1000μ'); // numμ NaNμ΄ μ μ₯
```

μμμ μ΄ ν¬ν¨λ κ²½μ°μ, 10.123μμ μ μλ§ λ½μμ νμκ° λλ©°, μ«μνμΌλ‘ λ°λκ² λλ€.
```javscript
let num = parseInt('10.123'); // 10
```
</br>
</br>
μ¦, parseIntμ Numberλ λΉμ·νλ©΄μλ λ€λ₯Έ λΆλΆμ΄ μλ€. λ λͺ¨λ μ«μνμΌλ‘ νμμ λ°κΏμ£Όμ§λ§, λ¬Έμμ΄μ΄ μ«μλ‘ μμνλ κ²½μ°μ μμμ μ νμνλ λΆλΆμ λν΄μλ μ°¨μ΄μ μ΄ μμΌλ, μ΄ μ°¨μ΄λ₯Ό μκ³  μ νμ©νλ€λ©΄ μ’μλ―μΆλ€.
