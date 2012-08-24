Original JTcl source code was modified in order to support iRule operators like:

- starts_with Tests if one string starts_with another string
- ends_with Tests if one string ends with another string
- contains Tests if one string contains another string

- matches_glob Implement glob style matching within a comparison
- matches_regex Tests if one string matches a regular expression

- equals Tests if one string equals another string
  - equivalent of "eq" operator  

- and Performs a logical "and" comparison between two values
  - equivalent of "&&" operator
- or Performs a logical "or" comparison between two values
  - equivalent of "||" operator
- not Performs a logical "not" on a value
  - equivalent of "!" operator

The only files that have been modified are:

- Expr.java
- expr.test