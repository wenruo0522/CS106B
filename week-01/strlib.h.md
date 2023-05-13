### The Stanford `libcs106` library, Fall Quarter 2022

***

**strlib.h**

This file exports several useful string functions that are not included in the C++ string library. It also includes some functions that effectively re-write standard C++ string functions, in order to provide that same funtionality in a simpler or safer formulation.

| Functions                                                    |                                                              |
| ------------------------------------------------------------ | ------------------------------------------------------------ |
| [boolToString(b)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:boolToString) | Converts a boolean value into the corresponding string form. |
| [charToInteger(c)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:charToInteger) | Converts a digit character into the corresponding integer.   |
| [charToString(c)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:charToString) | Converts a character value into the corresponding string form. |
| [endsWith(str, suffix)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:endsWith) | Returns `true` if the string `str` ends with the specified suffix, which may be either a string or a character. |
| [equalsIgnoreCase(s1, s2)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:equalsIgnoreCase) | Returns `true` if `s1` and `s2` are equal discounting differences in case. |
| [integerToString(n)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:integerToString) | Converts an integer into the corresponding string of digits. |
| [realToString(d)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:realToString) | Converts a floating-point number into the corresponding string form. |
| [startsWith(str, prefix)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:startsWith) | Returns `true` if the string `str` starts with the specified prefix, which may be either a string or a character. |
| [stringContains(str, substr)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringContains) | Returns whether the given substring can be found in the given string. |
| [stringIndexOf(str, substr)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringIndexOf) | Returns the index of the start of the first occurrence of the given substring in the given string. |
| [stringIsInteger(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringIsInteger)  [stringIsInteger(str, radix)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringIsInteger) | Returns whether the given string can be successfully converted into an integer. |
| [stringIsReal(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringIsReal) | Returns whether the given string can be successfully converted into a real number. |
| [stringJoin(v, delimiter)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringJoin) | Concatenates the given vector of strings into a single string using the given separator. |
| [stringLastIndexOf(str, substr)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringLastIndexOf) | Returns the index of the start of the last occurrence of the given substring in the given string. |
| [stringReplace(str, old, new)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringReplace) | Returns a new string with all occurrences of old changed into new. |
| [stringSplit(str, delimiter)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringSplit) | Breaks apart the given string using the given separator.     |
| [stringToBool(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringToBool) | Converts a string representing a boolean value into its corresponding value. |
| [stringToChar(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringToChar) | Converts a single-character string into its corresponding char value. |
| [stringToInteger(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringToInteger) [stringToInteger(str, radix)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringToInteger) | Converts a string of digits into an integer.                 |
| [stringToReal(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:stringToReal) | Converts a string representing a real number into its corresponding value. |
| [toLowerCase(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:toLowerCase) | Returns a new string in which all uppercase characters have been converted into their lowercase equivalents. |
| [toUpperCase(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:toUpperCase) | Returns a new string in which all lowercase characters have been converted into their uppercase equivalents. |
| [trim(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:trim) | Returns a new string after removing any whitespace characters from the beginning and end of the argument. |
| [trimEnd(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:trimEnd) | Returns a new string after removing any whitespace characters from the end of the argument. |
| [trimStart(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:trimStart) | Returns a new string after removing any whitespace characters from the beginning of the argument. |
| [urlDecode(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:urlDecode) | Returns a URL-decoded version of the given string.           |
| [urlEncode(str)](https://web.stanford.edu/dept/cs_edu/resources/cslib_docs/strlib.html#Function:urlEncode) | Returns a URL-encoded version of the given string.           |

**Function detail**

***

```
string integerToString(int n);
```

Converts an integer into the corresponding string of digits. For example, calling `integerToString(123)` returns the string `"123"`.

Usage:

```
string s = integerToString(n);
```

***

```
int stringToInteger(string str);
int stringToInteger(string str, int radix);
```

Converts a string of digits into an integer. If the string is not a legal integer or contains extraneous characters other than whitespace, `stringToInteger` calls `error` with an appropriate message. The function accepts an optional radix (base); for example, `stringToInteger("234", 16)` assumes that the string is in base-16 and returns 2*16*16 + 3*16 + 4 = 564.

Usage:

```
int n = stringToInteger(str);
int n2 = stringToInteger(str, radix);
```

***

```
bool stringIsInteger(string str);
bool stringIsInteger(string str, int radix);
```

Returns `true` if the given string can be successfully converted into an integer; that is, if it consists of digits and an optional +/- sign at the front. It can be useful to call this function before calling `stringToInteger` to make sure that the conversion will not fail. Optionally accepts a radix (base) parameter if base-10 is not desired.

Usage:

```
if (stringIsInteger(str)) { ...
```

***

```
bool stringIsReal(string str);
```

Returns `true` if the given string can be successfully converted into a real number; that is, if it consists of digits, an optional decimal point, an optional +/- sign at the front, and so on. It can be useful to call this function before calling `stringToReal` to make sure that the conversion will not fail.

Usage:

```
if (stringIsReal(str)) { ...
```

***

```
string realToString(double d);
```

Converts a floating-point number into the corresponding string form. For example, calling `realToString(23.45)` returns the string `"23.45"`.

Usage:

```
string s = realToString(d);
```

***

```
double stringToReal(string str);
```

Converts a string representing a real number into its corresponding value. If the string is not a legal floating-point number or contains extraneous characters other than whitespace, `stringToReal` calls `error` with an appropriate message.

Usage:

```
double d = stringToReal(str);
```

***

```
string boolToString(bool b);
```

Converts a boolean value into the corresponding string form. For example, calling `boolToString(true)` returns the string `"true"`.

Usage:

```
string s = boolToString(b);
```

***

```
bool stringToBool(string str);
```

Converts a string representing a boolean value into its corresponding value. The only values recognized are the string literals `"true"` or `"false"`. If the string is not `"true"` or `"false"` or contains extraneous characters other than whitespace, `stringToBool` calls `error` with an appropriate message.

Usage:

```
bool b = stringToBool(str);
```

***

```
int charToInteger(char c);
```

Converts a digit character into the corresponding integer. For example, `charToInteger('3')` returns the int 3. If the character is not a valid digit character '0' through '9', `charToInteger` calls `error`.

Usage:

```
int n = charToInteger(c);
```

***

```
string charToString(char c);
```

Converts a character into the corresponding string form. For example, calling `charToString('Q')` returns the string `"Q"`.

Usage:

```
string s = charToString(c);
```

***

```
char stringToChar(string str);
```

Converts a single-character string into its corresponding `char` value. Typically you can just write `str[0]` to access the first character of a string; this function is merely provided for consistency with the other type-conversion functions. If the string is not exactly 1 character in length or contains extraneous characters other than whitespace, `stringTochar` calls `error` with an appropriate message.

Usage:

```
char c = stringToChar(str);
```

***

```
bool stringContains(string str, string substr);
```

Returns `true` if the given substring can be found within the given string.

Usage:

```
if (stringContains(str, substr)) { ...
```

***

```
string stringReplace(string str, string old, string replacement);
```

Returns a new string that is the same as `str` but with all occurrences of `old` changed into `replacement`.

Usage:

```
string s = stringReplace(s, "foo", "bar");
```

***

```
string toUpperCase(string str);
```

Returns a new string in which all lowercase characters have been converted into their uppercase equivalents.

Usage:

```
string s = toUpperCase(str);
```

***

```
string toLowerCase(string str);
```

Returns a new string in which all uppercase characters have been converted into their lowercase equivalents.

Usage:

```
string s = toLowerCase(str);
```

***

```
bool equalsIgnoreCase(string s1, string s2);
```

Returns `true` if `s1` and `s2` are equal discounting differences in case.

Usage:

```
if (equalsIgnoreCase(s1, s2)) ...
```

***

```
bool startsWith(string str, string prefix);
bool startsWith(string str, char prefix);
```

Returns `true` if the string `str` starts with the specified prefix, which may be either a string or a character.

Usage:

```
if (startsWith(str, prefix)) ...
```

***

```
bool endsWith(string str, string suffix);
bool endsWith(string str, char suffix);
```

Returns `true` if the string `str` ends with the specified suffix, which may be either a string or a character.

Usage:

```
if (endsWith(str, suffix)) ...
```

***

```
string trim(string str);
```

Returns a new string after removing any whitespace characters from the beginning and end of the argument.

Usage:

```
string trimmed = trim(str);
```

***

```
string trimEnd(string str);
```

Returns a new string after removing any whitespace characters from the end of the argument.

Usage:

```
string trimmed = trimEnd(str);
```

***

```
string trimStart(string str);
```

Returns a new string after removing any whitespace characters from the beginning of the argument.

Usage:

```
string trimmed = trimStart(str);
```

***

```
int stringIndexOf(string s, string substring);
```

Returns the index of the start of the first occurrence of the given substring in `s`, if it occurs in `s`. If it does not occur, returns `-1`. This function is very similar to `string.find`, but `find` returns `string::npos` when the string is not found.

Usage:

```
int index = stringIndexOf(s, sub);
```

***

```
int stringLastIndexOf(string s, string substring);
```

Returns the index of the start of the last occurrence of the given substring in `s`, if it occurs in `s`. If it does not occur, returns `-1`. This function is very similar to `string.rfind`, but `find` returns `string::npos` when the string is not found.

Usage:

```
int index = stringLastIndexOf(s, sub);
```

***

```
Vector<string> stringSplit(string str, string delimiter);
```

Returns a Vector whose elements are strings formed by splitting the given string by the given delimiter. Any adjacent delimiters are coalesced. For example, splitting `"Hi there  Jim!"` on delimter `" "` returns `{"Hi", "there", "Jim!"}`.

Usage:

```
Vector<string> v = stringSplit(str, delimiter);
```

***

```
string stringJoin(const Vector<string>& v, string delimiter = "\n");
```

Combines the elements of the given Vector into a single string, with the given delimiter separating neighboring elements, and returns it. For example, joining the elements of the vector `{"Hi", "there", "", "Jim"}` with the delimiter `"-"` returns `"Hi-there--Jim"`.

Usage:

```
string s = stringJoin(v, delimiter);
```

***

```
string urlDecode(string value);
```

Returns a URL-decoded version of the given string, where any %xx character codes are converted back to the equivalent characters.

Usage:

```
string s = urlDecode(value);
```

***

```
string urlEncode(string value);
```

Returns a URL-encoded version of the given string, where most non- alphabetic characters are replaced by %xx character codes.

Usage:

```
string s = urlEncode(value);
```

***

