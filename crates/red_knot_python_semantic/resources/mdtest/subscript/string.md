# Subscript on strings

## Simple

```py
s = 'abcde'

reveal_type(s[0])  # revealed: Literal["a"]
reveal_type(s[1])  # revealed: Literal["b"]
reveal_type(s[-1])  # revealed: Literal["e"]
reveal_type(s[-2])  # revealed: Literal["d"]

a = s[8]  # error: [index-out-of-bounds] "Index 8 is out of bounds for string `Literal["abcde"]` with length 5"
reveal_type(a)  # revealed: Unknown

b = s[-8]  # error: [index-out-of-bounds] "Index -8 is out of bounds for string `Literal["abcde"]` with length 5"
reveal_type(b)  # revealed: Unknown 
```

## Function return

```py
def add(x: int, y: int) -> int:
    return x + y

a = 'abcde'[add(0, 1)]
# TODO: Support overloads... Should be `str`
reveal_type(a)  # revealed: @Todo
```