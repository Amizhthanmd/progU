---
sidebar_position: 3
---

# Strings

## Python String Methods

| **Category**              | **Method**                       | **Description**                                                                    |
| ------------------------- | -------------------------------- | ---------------------------------------------------------------------------------- |
| **Case Conversion**       | `capitalize()`                   | Converts the first character to uppercase.                                         |
|                           | `lower()`                        | Converts all characters to lowercase.                                              |
|                           | `upper()`                        | Converts all characters to uppercase.                                              |
|                           | `title()`                        | Converts the first character of each word to uppercase.                            |
|                           | `swapcase()`                     | Swaps the case of all characters.                                                  |
| **Alignment**             | `center(width, char)`            | Centers the string in a field of specified width.                                  |
|                           | `ljust(width, char)`             | Left-aligns the string in a field of specified width.                              |
|                           | `rjust(width, char)`             | Right-aligns the string in a field of specified width.                             |
|                           | `zfill(width)`                   | Pads the string with zeros on the left.                                            |
| **Search & Replace**      | `find(substring, start, end)`    | Returns the index of the first occurrence of the substring (or `-1` if not found). |
|                           | `rfind(substring, start, end)`   | Returns the index of the last occurrence of the substring (or `-1` if not found).  |
|                           | `index(substring, start, end)`   | Like `find()`, but raises `ValueError` if not found.                               |
|                           | `rindex(substring, start, end)`  | Like `rfind()`, but raises `ValueError` if not found.                              |
|                           | `replace(old, new, count)`       | Replaces occurrences of `old` with `new`.                                          |
|                           | `count(substring, start, end)`   | Returns the number of occurrences of a substring.                                  |
| **String Validation**     | `isalnum()`                      | Returns `True` if all characters are alphanumeric.                                 |
|                           | `isalpha()`                      | Returns `True` if all characters are alphabetic.                                   |
|                           | `isdigit()`                      | Returns `True` if all characters are digits.                                       |
|                           | `isdecimal()`                    | Returns `True` if all characters are decimals.                                     |
|                           | `isnumeric()`                    | Returns `True` if all characters are numeric.                                      |
|                           | `isidentifier()`                 | Returns `True` if the string is a valid Python identifier.                         |
|                           | `islower()`                      | Returns `True` if all characters are lowercase.                                    |
|                           | `isupper()`                      | Returns `True` if all characters are uppercase.                                    |
|                           | `istitle()`                      | Returns `True` if the string is in title case.                                     |
|                           | `isspace()`                      | Returns `True` if all characters are whitespace.                                   |
|                           | `isascii()`                      | Returns `True` if all characters are ASCII.                                        |
| **Trimming**              | `strip(chars)`                   | Removes leading and trailing characters.                                           |
|                           | `lstrip(chars)`                  | Removes leading characters.                                                        |
|                           | `rstrip(chars)`                  | Removes trailing characters.                                                       |
| **Splitting & Joining**   | `split(sep, maxsplit)`           | Splits the string into a list of substrings.                                       |
|                           | `rsplit(sep, maxsplit)`          | Splits the string from the right into a list of substrings.                        |
|                           | `splitlines(keepends)`           | Splits the string into lines.                                                      |
|                           | `join(iterable)`                 | Joins the elements of an iterable into a single string.                            |
| **Encoding & Formatting** | `encode(encoding, errors)`       | Encodes the string into bytes.                                                     |
|                           | `format(*args, **kwargs)`        | Formats the string.                                                                |
|                           | `format_map(mapping)`            | Formats the string using a mapping.                                                |
|                           | `maketrans(mapping)`             | Creates a translation table.                                                       |
|                           | `translate(table)`               | Translates the string using a translation table.                                   |
| **String Composition**    | `partition(sep)`                 | Splits the string into three parts: before, separator, and after.                  |
|                           | `rpartition(sep)`                | Like `partition()` but splits from the right.                                      |
|                           | `startswith(prefix, start, end)` | Returns `True` if the string starts with the specified prefix.                     |
|                           | `endswith(suffix, start, end)`   | Returns `True` if the string ends with the specified suffix.                       |
| **Miscellaneous**         | `casefold()`                     | Converts the string to casefolded lowercase (more aggressive than `lower()`).      |
|                           | `expandtabs(tabsize)`            | Replaces tabs with spaces.                                                         |
|                           | `removeprefix(prefix)`           | Removes the specified prefix (introduced in Python 3.9).                           |
|                           | `removesuffix(suffix)`           | Removes the specified suffix (introduced in Python 3.9).                           |
