#### Describe how to make different comparisons between JavaScript values (like greater-than, less-than, etc).

# Comparison Operators
How to properly compare values in JavaScript.

## Equality Operators
Equality operators are used to check if both operands have the same type and value or only the same value.

### Values and Data Types
Variables or expresions evaluations in JavaScript have a value and a data type.

For comparisons, the following data types are relevant:

- Null
- Undefined
- Boolean
- Number
- String
- Object

Possible values for those data types are:

- Null: `null`
- Undefined: `undefined`
- Boolean: `true` or `false`
- Number: `-2`, `-1`, `0`, `1`, `2`, `2.3`, `5.34`,...
- String: `'Hello'`, `'World!!!'`, `'Mike'`, `'1'`, `'2'`,...
- Object: `{a: 1, b: 5}`

If we want to compare both type and value we are checking for ***strict equality***.

If we want to compare only the value we are checking for ***abstract equality***.

### Abstract Equality
In *abstract equality*, if the data types of the operands are not the same, a type conversion must be made in order to properly compare the values.

Given two operands, `x` and `y`, the following rules apply for type conversion:
- `null` is equal to `undefined`
- If one is a Number and the other is a String, the String is converted to Number
- If `x` or `y` are Boolean, the Boolean is converted to Number
- If one is String or Number and the other is Object, it tries to convert the Object to String or Number. If the conversion fails, a runtime error is generated.
- If none of the previous rules apply, the values are **not** equal.

#### Equality
The operator for abstract equality is `==`.
```js
1 == 1            // true
null == undefined // true
1 == '1'          // true
'2' == 2          // true
0 == false        // true
true == 2         // false
'a' == ['a']      // true
0 == null         // false

```

#### Inequality
The operator for abstract inequality is `!=`.
```js
1 != 2            // true
1 != '1'          // false
0 != false        // false
true != 0         // true
'a' != ['b']      // true
0 != null         // true

```

### Strict Equality
In *strict equality*, if the data types of the operands are not the same, the operands are **not** equal.

#### Equality
The operator for strict equality is `===`.
```js
1 === 1            // true
'a' === 'a'        // true
null === undefined // false
1 === '1'          // false

```

#### Inequality
The operator for strict inequality is `!==`.
```js
1 !== 1            // false
'a' !== 'a'        // false
null !== undefined // true
1 !== '1'          // true

```

### Object Equality
Objects are equal **only** when they are the same object. Even for abstract equality.
```js
{a: 5} == {a: 5} // false
var a = {a: 5}
var b = {a: 5}
a == a  // true
a == b  // false
a === a // true
a === b // false

```

## Relational Operators
Relational operators are used to compare values.

### Greater than
The operator for greater than is `>`.
```js
2 > 1        // true
'abc' > 'ac' // false

```

### Greater than or equal
The operator for greater than or equal is `>=`.
```js
2 >= 1         // true
'abc' >= 'abc' // true

```

### Less than
The operator for less than is `<`.
```js
2 < 1         // false
'abc' < 'abc' // false

```

### Less than or equal
The operator for less than or equal is `<=`.
```js
2 <= 1         // false
'abc' <= 'abc' // true

```

### Abstract Relational Comparisons
There a no such a *strict relational comparisons*. If you need to check for types, you must do it manually before the comparison.

For relational comparisons, if a type conversion is needed, both operands are first converted to primitives. Then, if both are strings, an alphabetic comparison is performed. In any other case, both values are converted to numbers and a numeric comparison is performed.

```js
'50' > 49 // true

```

Complex abstract relational comparisons are generally **not** recommended, as results can be hard to predict. If you need to use such comparisons, the recommended way is to make a *explicit conversion* before performing them.

```js
'02' > [1]                 // false
Number('02') > Number([1]) // true

```

## Conclusion
Comparisons in JavaScript can be tricky, specially if different types are involved. Be careful when comparing values of different types.


---

Carlos Coves Prieto

05/20/2016

Career Path 3: Modern Frontend Developer
