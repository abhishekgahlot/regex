# Regex ( Notes )


# Global 

```
/g
```


# Optional

```
?
```

## Parenthesis

```
 (word)? another_word
```


# Character Classes

```
  bl[ab]k
```

```
  [a-z0-9]
  [a-zA-Z]
```

# Multiple Matches
```
  d.*
  d+
```

# OR |
```
  wh(i|t)e
  whi | te
```

# Carots (Beginning) /gm ( global and multiline )

Start string with
```
  ^Hello
```

# Dollar (End) /gm
End with

```
^Hello$
```

# Capturing Matches

Multiple matches

```
  $1
  $2
```

```
?:
```

# Greedy Matches ( + is greedy )

Matches XabcadadXXXXabacabX ( matches till end of X even skipping middle X)
```
  X.+X
```

# Non greedy
Stops at second X 
```
  X.+?X
```


# Ranges and Curly Brace

```
\d - digits
\w - words
\s - space
\n - newline
\r - carriage -> ()
```

Match any digit

```
\d{3, 4}
```

```
^[0-9]+
```
 
 Match any word

 ```
  \w+

  ^[a-z]+
 ```


 Match any space or use a space in regex

 ```
  \s
 ```

# Positive Lookahead

```
  (?=abc)
```


# Positive Lookbehind

```
  (?<=abc)
```



# Negative Lookbehind

Following expression cannot match before main regex

```
  (?<!ABC)\d+
```

eg
```
  (?<!me)@.+

  me@abhishek.it
  abhishek@|abhishek|.com

```


# Negative Lookahead

Matches a group after main regex

```
  (?!)
```

```
@.+(?=\.[a-z]{2,4})

me@|abhishek|.it
abhishek@|abhishek|.com
```

*From stackoverflow*

```

Look ahead positive (?=)
Find expression A where expression B follows:

A(?=B)
Look ahead negative (?!)
Find expression A where expression B does not follow:

A(?!B)
Look behind positive (?<=)
Find expression A where expression B precedes:

(?<=B)A
Look behind negative (?<!)
Find expression A where expression B does not precede:

(?<!B)A

```


# Lookahead ( Regex after should match and follow )

```
  A(?=B) Positive Lookahead ( Regex after should match and follow )
  A(?!B) Negative Lookahead ( Regex after should match and do not follow )
```

# Lookbehind

```
  (?<=B)A Positive Lookbehind ( Regex before should match and follow )
  (?<!B)A Negative Lookbehind ( Regex before should match and do not follow )
```


# Non-capturing Groups ( Capturing usually with parenthesis )

```
  (?: )
  \w+(?:email).com
```


# Backreferences


```
Match : abhishek bla bla abhishek
(abhishek).+?(abhishek)

or

(abhishek).+?(\1)
```

This is backreferencing the first group.



# Spaces

```
  \s{2,} 
```

Match any space of length 2 or more


# Length of String Match

```
  .{5,}
```



# Conditional Expressions

```
  (?(condition)then|else)

  ^(?(?=l)log|cog)

  (?=l) -> lookahead l

  log
  cog
```


# Difference between square and parenthesis

Square brackets are character classes and or with each one.

Parenthesis are for matching groups.
