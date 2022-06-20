

## Basics

String literal

- match telephone number 707-827-7019
-  `707-827-7019` to match
- `7` just to count the number of “7”

Character set

- `[0-9]` is a range, and `[]` are called metacharacters, and entire expression is also called character class
- `[012789]` limits the range precisely.

Character shorthand

- `\d` will match all digits
- `\d\d\d-\d\d\d-\d\d\d\d` will match the digits along with the pattern, and `-` is using the string literal format
- \d\d\d`\D`\d\d\d`\D`\d\d\d\\d uses the `\D` which matches any character <u>that is not a digit</u>
- \d\d\d`.`\d\d\d`.`\d\d\d\d use the `.` <u>to match any character</u>. The `.` has some limitations that it will not match a new line character (U+000A)

Capturing group and Quantifier

- `(\d{3,4}[.-]?)+` 
  - `()` is a capturing group
  - `\d` is a character shorthand
  - `{3-4}` is a quantifier
    - 3 minimum quantity to match and 4 maximum quantity to match
  - `[.-]` is a character class
    - `.-` matches the literal dot and literal dash
    - `?`is a metacharacter and matches zero or one quantifier
  - `+` is a metacharacter and matches one or more quantifiers

- `(\d{3}[.-]?{2}\d{4})`
  - `()` is a capturing group
  - `\d{3}` is a character shorthand occuring 3 times by using a quantifier
    - `[.-]?` explained above
    - `{2}` implies two occurrences of the capturing group
  - `\d{4}` implies character shorthand occurring 4 times.

## Reference

- https://regexpal.com

  