# **Using Python as a Calculator** 🧮

## 2️⃣.1️⃣ **Number**

> The interpreter acts as a simple calculator. It will print the value as you type in an expression. 

* ***The operators*** : `+`, `-`, `*`, `/`, `%` work like other languages.

```python
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

```python
>>> 17 % 3️
2
>>> 17 // 3️
5
>>> 2 * * 3
8
```

* ***The equal sign*** `=` is used to assign value (or a string) to a variable.

```python
>>> y = 34
>>> x = 17
>>> y / x
2
```

***If variables haven't been defined, it will cause error.***

```python
>>> n  # try to access an undefined variable
Traceback (most recent call last):
  File "<stdin>", line 1, in <module>
NameError: name 'n' is not defined
```

* If there are ***float and integer vars in the same equation***, operators will convert the integer to float type. (`float` + `integer` = `float`)

```python
>>> 5 * 2 / 4
2.5
```

* variable `_` will be assigned to the ***last printed expression***. (You can use it to continue calculation. - like `Ans`)

```python
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

```python
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

* The string is **enclosed in double quotes** if it contains a single quote (and no double quotes), otherwise it is **enclosed in single quotes**.
  
  * Without and with `print()` function

  ```python
  >>> '"Halo" he said.'
  '"Halo" he said.' # the output still contains single quotes.
  >>> print('"Halo" he said.')
  "Halo" he said.  # the output doesn't have the single quotes.
  ```
  
  * When using `print()`, `\n` means print in newline, and `\t` means insert a tab.

  * Use ***raw string*** `r` if you don't want characters prefaced by `\` to be interpreted as special char.

  ```python
  >>> print(r'C:\some\name')  # note the r before the quote
  C:\some\name
  ```

* String can **span multiple lines** by using `"""..."""` or `'''...'''`.
  * End of lines are automatically included, but can be prevent by adding a `\` at the end of the line.

```python
>>> print("""\
... Usage: thingy [OPTIONS]
...     -h                        Display this usage message
...     -H hostname               Hostname to connect to
""")
Usage: thingy [OPTIONS]
     -h                        Display this usage message
     -H hostname               Hostname to connect to
```

* Strings can be **concatenated** `+` operator, and **repeated with** `*`:

  ```python
  >>> 3 * 'un' + 'ium'
  'unununium'
  ```

* Two or more string (enclosed) next to each other are **automatically concatenated**.

  ```python
  >>> 'Py' 'thon'
  'Python'
  ```

  * Useful when breaking long strings:

  ```python
  >>> text = ('Put several strings within parentheses '
  ...         'to have them joined together.')
  >>> text
  'Put several strings within parentheses to have them joined together.'
  ```

  ***⚠️ This only works with two literals though, not with variables or expressions:***

  ```python
  >>> prefix = 'Py'
  >>> prefix 'thon'  # can't concatenate a variable and a string literal
    File "<stdin>", line 1
      prefix 'thon'
                  ^
  SyntaxError: invalid syntax
  >>> ('un' * 3) 'ium'
    File "<stdin>", line 1
      ('un' * 3) 'ium'
                    ^
  SyntaxError: invalid syntax
  ```

  * Use `+`, then the problem will be solved 👍

  ```python
  >>> prefix + 'thon'
  'Python'
  ```

* Strings **can be indexed** (first character is indexed 0 )

  ```python
  >>> word = 'Python'
  >>> word[0]  # character in position 0
  'P'
  >>> word[5]  # character in position 5
  'n'
  ```

  * Indices may also be negative numbers, to start counting from the right (start from -1)

  ```python
  >>> word[-1]  # last character
  'n'
  >>> word[-2]  # second-last character
  'o'
  >>> word[-6]
  'P' 
  ```


  * **Slicing is also supported** to obtain substrings:

  ```python
  >>> word[0:2]  # characters from position 0 (included) to 2 (excluded)
  'Py'
  >>> word[2:5]  # characters from position 2 (included) to 5 (excluded)
  'tho'
  ----
  >>> word[:2]   # character from the beginning to position 2 (excluded)
  'Py'
  >>> word[4:]   # characters from position 4 (included) to the end
  'on'
  >>> word[-2:]  # characters from the second-last (included) to the end
  'on'
  ```
  * `s[:i] + s[i:] = s` 

* One way to remember how slices work is to think of the indices as ***pointing between characters***, with the ◀️ edge of the first character numbered 0. Then the ▶️ edge of the last character of a string of n characters has index n, for example:

  ```console
  +---+---+---+---+---+---+
  | P | y | t | h | o | n |
  +---+---+---+---+---+---+
  0   1   2   3   4   5   6
  -6  -5  -4  -3  -2  -1
  ```

  1. The first row of numbers gives the position of the indices 0…6 in the string
  
  2. The second row gives the corresponding negative indices. 
  
  3. The slice from i to j consists of all characters between the edges labeled i and j.

  4. For non-negative indices, the length of a slice is the difference of the indices, if both are within bounds. For example, the length of word[1:3] is 2.

* Attempting to use an index that is **too large will result in an error**:
  ```python
  >>> word[42]  # the word only has 6 characters
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  IndexError: string index out of range
  ```

  * However, out of range slice indexes are handled gracefully when used for slicing:
    ```python
    >>> word[4:42]
    'on'
    >>> word[42:] # ko có từ nào phía sau
    '' 
    ```

* Python strings cannot be changed — **they are immutable**. Therefore, assigning to an indexed position in the string results in an error:

  ```python
  >>> word[0] = 'J'
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: 'str' object does not support item assignment
  >>> word[2:] = 'py'
  Traceback (most recent call last):
    File "<stdin>", line 1, in <module>
  TypeError: 'str' object does not support item assignment
  ```
 -> You should create a new one:

```python
>>> 'J' + word[1:]
'Jython'
>>> word[:2] + 'py'
'Pypy'
```

* The built-in function `len()` returns the **length of a string**:

  ```python
  >>> s = 'supercalifragilisticexpialidocious'
  >>> len(s)
  34
  ```

## 2️⃣.3️⃣ **Lists**

> Python knows a number of compound data types, used to group together other values. The most versatile is the list, which can be written as a list of comma-separated values (items) between square brackets. Lists might contain items of different types, but usually the items all have the same type.

```python
>>> squares = [1, 4, 9, 16, 25]
>>> squares
[1, 4, 9, 16, 25]
```

* Like strings, lists can be **indexed** and **sliced**:

  ```python
  >>> squares[0]  # indexing returns the item
  1
  >>> squares[-1]
  25
  >>> squares[-3:]  # slicing returns a new list
  [9, 16, 25]
  ```

  * All slice operations return a new list containing the requested elements.
    ```python
    >>> squares[:] # from the first to the last
    [1, 4, 9, 16, 25]
    ```

* Lists also support **concatenation** :

  ```python
  >>> squares + [36, 49, 64, 81, 100]
  [1, 4, 9, 16, 25, 36, 49, 64, 81, 100]
  ```

* The difference between lists and strings is that list is immutable. That means their elements can be changed  by users:

  ```python
  >>> cubes = [1, 8, 27, 65, 125]  # the rule of the list is a^3
  >>> 4 ** 3                       # 4 power 3
  64
  >>> cubes[3] = 64                # replace the wrong value
  >>> cubes
  [1, 8, 27, 64, 125]
  ```

* To add new items at the end of the list, we can use `append()` method

  ```python
  >>> list = ["Minh Tu", "Nhat Minh", "Quang Long", "Thi Ngoan"]
  >>> list.append("Quoc Khanh")
  >>> list
  ['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan', 'Quoc Khanh']
  >>> list.pop()
  'Quoc Khanh'
  >>> Me = list.pop()
  >>> Me
  'Thi Ngoan'
  >>> list.append(Me)
  >>> list
  ['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan']
  ```

* Assignment to slices is also possible, and this can even change the size of the list or clear it entirely:

  ```python
  >>> letters = ['a', 'b', 'c', 'd', 'e', 'f', 'g']
  >>> letters
  ['a', 'b', 'c', 'd', 'e', 'f', 'g']
  >>> # replace some values
  >>> letters[2:5] = ['C', 'D', 'E']
  >>> letters
  ['a', 'b', 'C', 'D', 'E', 'f', 'g']
  >>> # now remove them
  >>> letters[2:5] = []
  >>> letters
  ['a', 'b', 'f', 'g']
  >>> # clear the list by replacing all the elements with an empty list
  >>> letters[:] = []
  >>> letters
  []
  ```

* The built-in function `len()` also applies to lists:
```python
>>> letters = ['a', 'b', 'c', 'd']
>>> len(letters)
4
```

* It is possible to **nest lists** (create lists containing other lists)

```python
>>> list = ["Minh Tu", "Nhat Minh", "Quang Long", "Thi Ngoan"]
>>> list
>>> list.pop()
>>> Me = list.pop()
>>> Me
'Thi Ngoan'
>>> list.append(Me)
>>> list
['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan']
>>> family1 = list[:]
>>> family1
['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan']
>>> family2 = ["Hung Dong", "Tuyet Nhung", "Gia Khang", "Phuong Mai"]
>>> family3 = "Vui"
>>> nha_ngoai = [family1, family2, family3]
>>> nha_ngoai
[['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan'], ['Hung Dong', 'Tuyet Nhung', 'Gia Khang', 'Phuong Mai'], 'Vui']
>>> nha_ngoai[0]
['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan']
>>> nha_ngoai[1]
['Hung Dong', 'Tuyet Nhung', 'Gia Khang', 'Phuong Mai']
>>> nha_ngoai[2]
'Vui'
>>> nha_ngoai[-1]
'Vui'
>>> nha_ngoai[:1]
[['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan']]
>>> nha_ngoai[:2]
[['Minh Tu', 'Nhat Minh', 'Quang Long', 'Thi Ngoan'], ['Hung Dong', 'Tuyet Nhung', 'Gia Khang', 'Phuong Mai']]
>>> nha_ngoai[0][3]
'Thi Ngoan
```

### ***Fibonacci number Example***
