# **Using Python as a Calculator** 🧮

## 2️⃣.1️⃣ **Number**

> The interpreter acts as a simple calculator. It will print the value as you type in an expression. 

* ***The operators*** : `+`, `-`, `*`, `/`, `%` work like other languages.

```console
>>> 2 + 2
4
>>> 50 - 5*6
20
>>> (50 - 5*6) / 4
5.0
>>> 8 / 5  # division always returns a floating point number
1.6
>>> 3 % 2
1
```
* ***Parentheses*** : `()` can be used to group expressions.

* ***Other operators*** like:
    * `%` to return the remainder of the division.
    * `//` for floor division (remove fractional part)
    * `**` use as **power** equation `^`.

```console
>>> 17 % 3️
2
>>> 17 // 3️
5
>>> 2 * * 3
8
```

* ***The equal sign*** `=` is used to assign value (or a string) to a variable.

```console
>>> y = 34
>>> x = 17
>>> y / x
2
```

***If variables haven't been defined, it will cause error.***

```console
>>> n  # try to access an undefined variable
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'n' is not defined
```

* If there are ***float and integer vars in the same equation***, operators will convert the integer to float type. (`float` + `integer` = `float`)

```console
>>> 5 * 2 / 4
2.5
```

* variable `_` will be assigned to the ***last printed expression***. (You can use it to continue calculation. - like `Ans`)

```console
>>> x = 12
>>> y = 13
>>> x + y
25
>>> z  = 10 + _ # '_' won't create a local var
>>> z           # so do not assign a val to it
35
```

* In addition to `int` and `float`, Python supports other types of numbers, such as `Decimal` and `Fraction`. Python also has built-in support for complex numbers, and uses the `j` or `J` suffix to indicate the imaginary part (e.g. 3+5j).

## 2️⃣.2️⃣ **Strings**

* String in Python can be expressed in several ways :
    - ***Single quotes*** : `'...'`
    - ***Double quotes*** : `"..."`
    - ***Slash*** : `\` can be use to escape quotes.

```console
>>> 'I am NMT'
'I am NMT'
>>> 'I\'m NMT' # use slash to escape single quote.
'I'm NMT'
# or you can use double quote instead.
>>> "You aren't the only one."
"You aren't the only one."
>>> "\"Yes,\" they said."
'"Yes," they said.'
>>> '"Isn\'t," they said.'
'"Isn\'t," they said.'
```

## 2️⃣.3️⃣ **Lists**



### ***Fibonacci number Example***
