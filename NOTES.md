Original JTcl source code was modified in order to support iRule operators like:

- contains Tests if one string contains another string
- ends_with Tests if one string ends with another string
- equals Tests if one string equals another string
- matches_glob Implement glob style matching within a comparison
- matches_regex Tests if one string matches a regular expression
- starts_with Tests if one string starts_with another string
- and Performs a logical "and" comparison between two values
- not Performs a logical "not" on a value
- or Performs a logical "or" comparison between two values

The one files that have been modified are:

- Expr.java
- expr.test