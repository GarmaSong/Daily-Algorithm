# ๐ค ๋ฌธ์ 

Given an integer `x`, return true if `x` is palindrome integer.

An integer is a palindrome when it reads the same backward as forward. For example, `121` is palindrome while `123` is not.

```
Example 1:

Input: x = 121
Output: true
Example 2:

Input: x = -121
Output: false
Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.
Example 3:

Input: x = 10
Output: false
Explanation: Reads 01 from right to left. Therefore it is not a palindrome.
Example 4:

Input: x = -101
Output: false
```

# ๐ฃ ๋ด๊ฐ ์๊ฐํ ๋ผ๋ฆฌ(๋ผ๊ณ  ์ฐ๊ณ  ์ฝ์ง)

์ค๊ฐ์ ๊ธฐ์ค์ผ๋ก ์๋ค ์ซ์๋ฅผ ๋น๊ตํ๋ ๋ฐฉ์

1. ๋น๊ต๋ฅผ ์ํด ์ซ์๋ฅผ ๋ฌธ์ ๋๋ ๋ฐฐ์ด๋ก ๋ฐ๊พธ๊ธฐ
2. ๊ฐ์ด๋ฐ๋ฅผ ๊ธฐ์ค์ผ๋ก ์๋ถ๋ถ ๋ท๋ถ๋ถ ๋๋๊ธฐ
3. ๋ท๋ถ๋ถ์ ์ญ์์ผ๋ก ๋ฐ๊พธ๊ธฐ
4. ์๋ถ๋ถ์ด๋ ๋ท๋ถ๋ถ์ด๋ ๊ฐ์์ง ๋น๊ตํด์ True/False ๋น๊ต

# ๐ฅ ๋ด ๋ผ๋ฆฌ์ ์ค๋ฅ

- parameter์ ๊ฐ์ ๊ธธ์ด๊ฐ ์ง์๋ก ๋ค์ด์ฌ ๊ฒฝ์ฐ ๋ฐ์ ๋ชป๋๋,,

# ๐ฒ ๋ ๋์ ํด๊ฒฐ์ฑ

- ์ค๊ฐ์ ๋๋ ํ์ ์์ด palindrome ๋จ์ด ๊ทธ๋๋ก ์ญ์์ผ๋ก๋ง ๋ฐ๊พธ๋ฉด ๋๋๊ฑฐ์์,,, (ํด ๋ฐ๋ณด)

```
original = String(x)
reverse = original.split('').reverse().join('')
return original === reverse ? true :false
```

- ์ค์ํ ์ฌ์ค! ๋ฐฐ์ด๊ณผ ๋ฐฐ์ด์ด ๋์ผํ์ง ์ง์  ๋น๊ตํ  ์ ์๋ค.
