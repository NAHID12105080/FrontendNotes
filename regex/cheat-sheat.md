# 📝 **RegEx Cheat Sheet with Real-World Examples**

---

## 1. 🎯 **Anchors**

| **Pattern**   | **Explanation**             | **Real-World Example**                                                                                                 |
|---------------|-----------------------------|------------------------------------------------------------------------------------------------------------------------|
| `^`           | Start of a line              | `^Hello` will match "Hello" only if it's at the **start of a line**. Text: `Hello World!` ✔️|
| `\A`          | Start of a string            | `\AHello` matches "Hello" only if it's at the **start of the entire string**. Text: `Hello Everyone!` ✔️|
| `$`           | End of a line                | `World$` matches "World" if it's at the **end of a line**. Text: `Hello World!` ✔️|
| `\Z`          | End of a string              | `World\Z` matches "World" at the **end of a string**. Text: `Welcome to the World` ✔️|
| `\b`          | Word boundary                | `\bcat\b` matches the **whole word** "cat". Text: `My cat is cute.` ✔️|
| `\B`          | Not a word boundary          | `\Bcat` matches "cat" **not at a word boundary**. Text: `catalog` ✔️|
| `\<`          | Start of a word              | `\<apple` matches "apple" only at the **start of a word**. Text: `apple pie` ✔️|
| `\>`          | End of a word                | `apple\>` matches "apple" only at the **end of a word**. Text: `green apple` ✔️|

---

## 2. 🧮 **Character Classes**

| **Pattern**   | **Explanation**                  | **Real-World Example**                                                                                          |
|---------------|----------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `\c`          | Control character                | `\cM` matches control characters like **Ctrl + M** (carriage return). Example: Control sequences in old text formats. ✔️|
| `\s`          | Any whitespace                   | `\s+` matches **spaces, tabs, or newlines**. Text: `Hello    World!` ✔️|
| `\S`          | Non-whitespace                   | `\S+` matches any **non-whitespace characters**. Text: `HelloWorld!` ✔️|
| `\d`          | Any digit                        | `\d+` matches a **number**. Text: `The price is 100 dollars.` ✔️|
| `\D`          | Non-digit                        | `\D+` matches **non-digit characters**. Text: `Product ID: ABC123` ✔️|
| `\w`          | Any word character               | `\w+` matches **letters, numbers, and underscores**. Text: `username_123` ✔️|
| `\W`          | Non-word character               | `\W+` matches **special characters or spaces**. Text: `@user!` ✔️|
| `\xhh`        | Hexadecimal character            | `\x41` matches **ASCII "A"**. Example: useful for matching ASCII characters via hex in encoded data. ✔️|

---

## 3. 🔢 **Quantifiers**

| **Pattern**   | **Explanation**                  | **Real-World Example**                                                                                          |
|---------------|----------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `*`           | Matches 0 or more occurrences    | `ab*c` matches **"ac"**, **"abc"**, **"abbc"**, etc. ✔️|
| `+`           | Matches 1 or more occurrences    | `ab+c` matches **"abc"**, **"abbc"**, but **not** "ac". ✔️|
| `?`           | Matches 0 or 1 occurrence        | `colou?r` matches both **"color"** and **"colour"**. ✔️|
| `{3}`         | Exactly 3 occurrences            | `a{3}` matches **"aaa"**. ✔️|
| `{3,}`        | 3 or more occurrences            | `a{3,}` matches **"aaa"**, **"aaaa"**, and so on. ✔️|
| `{3,5}`       | Between 3 and 5 occurrences      | `a{3,5}` matches **"aaa"**, **"aaaa"**, and **"aaaaa"**. ✔️|

---

## 4. ⚙️ **Pattern Modifiers**

| **Pattern**   | **Explanation**                | **Real-World Example**                                                                                          |
|---------------|--------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `g`           | Global match                   | `/abc/g` matches all occurrences of **"abc"** in the string. ✔️|
| `i`           | Case-insensitive match         | `/abc/i` matches **"abc"**, **"ABC"**, and any case variations. ✔️|
| `s`           | Single-line match              | `/a.b/s` matches "a\nb" (newline in between). ✔️|
| `m`           | Multi-line match               | `/^abc/m` matches **"abc"** at the start of each line in a multi-line string. ✔️|
| `U`           | Ungreedy pattern               | `/a.*?b/U` matches the shortest string between "a" and "b". ✔️|

---

## 5. 🛠️ **Special Characters**

| **Pattern**   | **Explanation**                | **Real-World Example**                                                                                          |
|---------------|--------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `\\`          | Escape special character       | `\.` matches a literal dot **"."** instead of any character. Text: `This is a test.` ✔️|
| `\n`          | Newline                        | `\n` matches a **newline**. Text: `Hello\nWorld`. ✔️|
| `\r`          | Carriage return                | `\r` matches **carriage return**. Useful in old text formats. ✔️|
| `\t`          | Tab                            | `\t` matches a **tab** character. Text: `Item\tPrice` ✔️|
| `\v`          | Vertical tab                   | `\v` matches a **vertical tab**. Less common, but useful in structured text. ✔️|
| `\f`          | Form feed                      | `\f` matches **form feed**. Used in old printing formats. ✔️|
| `\a`          | Alarm (bell)                   | `\a` matches an **alarm (bell)** character. ✔️|
| `[\b]`        | Backspace                      | `[\b]` matches a **backspace** character. ✔️|

---

## 6. 📊 **Ranges**

| **Pattern**        | **Explanation**              | **Real-World Example**                                                                                          |
|--------------------|------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `.`                | Any character except newline  | `a.b` matches "aXb" or "a1b" (any character between a and b). ✔️|
| `(a|b)`            | Matches "a" or "b"            | `I like (cats|dogs)` matches either "I like cats" or "I like dogs". ✔️|
| `(...)`            | Groups part of a pattern      | `(abc){3}` matches "abcabcabc". ✔️|
| `[^abc]`           | Not "a", "b", or "c"          | `[^abc]` matches any character **except** "a", "b", or "c". ✔️|
| `[a-z]`            | Lowercase letters a to z      | `[a-z]+` matches all **lowercase letters**. ✔️|
| `[0-9]`            | Digits from 0 to 9            | `[0-9]+` matches all **numbers**. ✔️|

---

## 7. 🔐 **Assertions**

| **Pattern**        | **Explanation**              | **Real-World Example**                                                                                          |
|--------------------|------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `(?=...)`          | Positive lookahead           | `apple(?=\sjuice)` matches "apple" only if it's followed by **" juice"**. ✔️|
| `(?!...)`          | Negative lookahead           | `apple(?!\spie)` matches "apple" only if **not** followed by "pie". ✔️|
| `(?<=...)`         | Positive lookbehind          | `(?<=\$)\d+` matches **digits** preceded by a dollar sign ($). ✔️|
| `(?<!...)`         | Negative lookbehind          | `(?<!@)\w+` matches words not preceded by "@". ✔️|

---

## 8. 🌐 **Common Regex Patterns**

| **Pattern**                                         | **Explanation**                                        | **Real-World Example**                                                                                          |
|-----------------------------------------------------|--------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------|
| `MD5 [a-fA-F0-9]{32}`                               | Matches an MD5 hash.                                    | Useful for validating **MD5 checksums** (32 hex chars). ✔️|
| `SHA256 [a-fA-F0-9]{64}`                            | Matches a SHA256 hash.                                  | Useful for validating **SHA256 checksums** (64 hex chars). ✔️|
| `(?:\d{1,3}\.){3}\d{1,3}`                           | Matches an IPv4 address.                                | Matches **IPv4 addresses** like "192.168.0.1". ✔️|
| `[0-9A-F]{2}([-:]?)(?:[0-9A-F]{2}\1){4}[0-9A-F]{2}` | Matches a MAC address.                                  | Matches **MAC addresses** like "00:1A:2B:3C:4D:5E". ✔️|
| `^([a-z0-9_\.-]+)@([\da-z\.-]+)\.([a-z\.]{2,6})$`   | Matches a valid email address.                          | Matches emails like `user@example.com`. ✔️|
| `(?i)(https?://[^\s]+)`                             | Matches a URL.                                          | Matches URLs starting with **http** or **https**. ✔️|

