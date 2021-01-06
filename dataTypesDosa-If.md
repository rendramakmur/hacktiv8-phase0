[**Back to Home**](./../README.md)


# Data Types
To be able to operate on variables, it is important to know something about the type.

## Primitive
```javascript
let string = "Ini adalah sebuah string";
let number = 1234567890;
let boolean = true;
let empty = Null; // special primitive
let notDefined;
```
## Structured
Specialized format for organizing, processing, retrieving and storing data. Each data structure contains information about the data values
```javascript
let names = ["Afifah", "Daniel"];
let afifah = {
  name : "Afifah",
  gender : "female",
  age : 23,
  isStudent : false
}
```

# Variables, Operators, and Assignment

## Declaration Variable
```javascript
let string; 
const pi;
var global;
let names;
```
## Assignment (=) Variable
```javascript
let string = "name"; 
const pi = 3.14;
var global = true;
let names = ["Afifah", "Daniel"];
```

## Operators
```
+	  Addition
-	  Subtraction
*	  Multiplication
**	  Exponentiation (ES2016)
/	  Division
%	  Modulus (Division Remainder)
++	  Increment
--	  Decrement
```

## Assignment + Operator
```
=	  x = y       x = y
+=	  x += y	  x = x + y
-=	  x -= y	  x = x - y
*=	  x *= y	  x = x * y
/=	  x /= y	  x = x / y
%=	  x %= y	  x = x % y
**=	  x **= y	  x = x ** y
```

## Comparision Operators
```
==	  equal to
===	  equal value and equal type
!=	  not equal
!==	  not equal value or not equal type
>	  greater than
<	  less than
>=	  greater than or equal to
<=	  less than or equal to
?	  ternary operator
```

## Logical Operators
```
&&	logical and
||	logical or
!	logical not
```

# Booleans (Truthy Falsy)

## Comparisons and Conditions
Everything With a "Value" is True
```js
100
3.14
-15
"Hello"
"false"
7 + 1 + 3.14
true
```
Everything Without a "Value" is False
```js
var x = 0;  // 0 (Number)
var x = -0; // -0 (Number)
var x = ""; // Empty String
var x; // undefined
var x = null; // null
var x = false; // boolean false
var x = 10 / "H"; // NaN (Not a Number)
```

# Conditional Statements
Use `if` to specify a block of code to be executed, if a specified condition is true
Use `else` to specify a block of code to be executed, if the same condition is false
Use `else if` to specify a new condition to test, if the first condition is false

## IF Statement
```js
if (condition) {
  //  block of code to be executed if the condition is true
}
```
```js
if (condition) {
  //  block of code to be executed if the condition is true
} else {
  //  block of code to be executed if the condition is false
}
```
```js
if (condition1) {
  //  block of code to be executed if condition1 is true
} else if (condition2) {
  //  block of code to be executed if the condition1 is false and condition2 is true
} else {
  //  block of code to be executed if the condition1 is false and condition2 is false
}
```

# contoh Dosa-Dosa ketika bikin IF
## DOSA UTAMA, indentasinya kusut
```js
/* kalau udah "beda kasus" atau IF BARU, wajib enter */
if (condition){
  // (WAJIB KASIH TAB, jangan rata kiri semua)
} if (newCondition){ // DOSA
  // code ...
}

if (condition){
  // code ...
} 
if (newCondition){ // PAHALA, ngga disambung sama atasnya.
  // code ...
}

/* "satu kasus" dua kondisi */
if (newCondition){ 
  // code ...
} else { // PAHALA, masih satu kasus, elsenya nyambung
  // code ...
}

/* "satu kasus" banyak kondisi */
if (condition1){
  // code ...
} else if (condition2){
  // code ...
} else { // else gaperlu kondisi ()
  // code ...
}
```

## DOSA 1, bikin kondisi tapi bukan pake comparision operator
```js
let name = "Afifah"
if (name = "Afifah"){ //DOSA, "=" itu assignment bukan comparision
  console.log(false)
}
if (name === "Afifah"){ //PAHALA
  console.log(true)
}
```

## DOSA 2, comparision < > dan operator - % * / ++ -- malah dipake buat string
```js
let name = "A", age = 17;

if (name < "Stef"){ //DOSA, yg bisa dibandingkan dengan < dan > hanya angka
  //string nggabisa di-kalkulasikan
  name++    //DOSA
  if (name % 1 === 0){ //DOSA

  }  
}

if (age < 18){ //PAHALA, < > % hanya untuk angka
  age--
  if (age % 1 === 0){

  }
}
```

## DOSA 3, bikin kondisi tapi tidak tau bedanya == dan ===
```js
let zeroNumber = 0
let zeroString = "0"

//DOSA, "==" valuenya doang wajib sama
if (zeroNumber == zeroString){ 
  console.log(true)
}
//PAHALA, "===" value sama datatype wajib sama
if (zeroNumber === zeroString){ 
  console.log(false)
}
```

## DOSA 4, pake Logical Operator kondisi-kondisinya ngasal
```js
let zeroNumber = 0
let zeroString = "0"

//DOSA, kondisi 1 sama kondisi 2nya ngga jelas
if (typeof zeroNumber || typeof zeroString){ 
  console.log(false)
}
//PAHALA
if (typeof zeroNumber == "number" && typeof zeroString == "string"){ 
  console.log(true)
}
```