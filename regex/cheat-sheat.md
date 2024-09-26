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

# 📝 **Advanced Regex Concepts with Real-World Examples**

---

## 1. 🔄 **Backreferences**

| **Pattern** | **Explanation** | **Real-World Example** |
|-------------|-----------------|------------------------|
| `\1`, `\2`, etc. | Matches the same text as previously matched by a capturing group. | In a form validation scenario, `(abc)\1` would match "abcabc", ensuring that the same sequence appears twice consecutively. |

---

## 2. 🏷️ **Named Groups**

| **Pattern** | **Explanation** | **Real-World Example** |
|-------------|-----------------|------------------------|
| `(?P<name>...)` | Allows you to name a capturing group for easier reference. | In a date parsing application, `(?P<year>\d{4})` captures a four-digit year like "2024", making it easy to extract and use later. |

---

## 3. ⚡ **Atomic Groups**

| **Pattern** | **Explanation** | **Real-World Example** |
|-------------|-----------------|------------------------|
| `(?>...)`    | Prevents backtracking within the group, improving performance. | In a complex search operation, `(?>\d{2})` matches two digits without reconsidering previous matches, speeding up the process in large datasets. |

---

## 4. 🌐 **Unicode Properties**

| **Pattern**      | **Explanation** | **Real-World Example** |
|------------------|-----------------|------------------------|
| `\p{Property}` or `\P{Property}` | Matches characters based on their Unicode properties. | For international applications, `\p{L}` matches any letter from any language, allowing for multilingual text processing. |

---

## 5. ❓ **Conditional Patterns**

| **Pattern**           | **Explanation** | **Real-World Example** |
|-----------------------|-----------------|------------------------|
| `(?(id)yes|no)`      | Matches a pattern based on whether a capturing group has been matched. | In a configuration file parser, `(?(1)yes|no)` checks if group 1 matched and adjusts behavior accordingly, such as enabling or disabling features. |

---

## 6. 🔒 **Possessive Quantifiers**

| **Pattern**       | **Explanation**               | **Real-World Example** |
|-------------------|-------------------------------|------------------------|
| `*+`, `++`, `?+`, `{n,m}+` | Similar to greedy quantifiers but do not allow backtracking. | In log file analysis, `a*+b` matches "aaab" without trying to match "a" again if it fails, ensuring faster processing of large logs. |

---

## 7. 🔍 **Lookaround Assertions**

| **Pattern**                       | **Explanation**                                                                                       | **Real-World Example** |
|-----------------------------------|-------------------------------------------------------------------------------------------------------|------------------------|
| Positive Lookahead: `(?=...)`     | Checks for conditions before a match without including them in the match itself.                    | In user input validation, `\d(?=\D)` ensures that digits are followed by non-digits without including them in the match. |
| Negative Lookahead: `(?!...)`     | Ensures that a pattern is not followed by another pattern without including it in the match itself.  | In password validation, `(?=.*[A-Z])(?!.*[0-9])` checks for at least one uppercase letter while ensuring no digits are present. |
| Positive Lookbehind: `(?<=...)`   | Checks for conditions after a match without including them in the match itself.                     | In currency formatting, `(?<=\$)\d+` captures numbers preceded by a dollar sign without including the dollar sign itself in the match. |
| Negative Lookbehind: `(?<!...)`   | Ensures that a pattern is not preceded by another pattern without including it in the match itself.  | In filtering emails, `(?<!@example\.com)$` matches any email not from "example.com". |

---

## 8. 🔒 **Escaped Characters**

| **Pattern**                | **Explanation**                                              | **Real-World Example** |
|----------------------------|--------------------------------------------------------------|------------------------|
| `\` followed by special characters  | Used to escape special characters so they can be treated as literals (e.g., \., \*, \?).   | In search queries, using `\.` allows matching literal periods instead of treating them as wildcards (e.g., matching file extensions like `.txt`). |

---

## 9. 🐍 **Greedy vs. Non-Greedy Matching**

| **Type**         | **Explanation**                                          | **Real-World Example** |
|------------------|----------------------------------------------------------|------------------------|
| Greedy           | Tries to match as much text as possible.                | In HTML parsing, `<.*>` captures everything between tags greedily, potentially capturing too much if nested tags exist (e.g., `<div><span>Text</span></div>`). |
| Non-Greedy (Lazy)| Tries to match as little text as possible using `?`.    | Using `<.*?>` ensures only the nearest closing tag is matched, preventing over-capturing in nested structures (e.g., only capturing `<span>`). |

---

## 10. 🔄 **Subpattern Matching**

| **Concept**      | **Explanation**                                          | **Real-World Example** |
|------------------|----------------------------------------------------------|------------------------|
| Subpattern Matching   | Allows matching of repeated patterns using groups and backreferences for complex definitions.| In data validation, using groups and backreferences can help ensure formats like phone numbers are consistently captured (e.g., `(123)-456-7890`). |

---
