# ๐ค Roman to Integer

Roman numerals are represented by seven different symbols: `I`, `V`, `X`, `L`, `C`, `D` and `M`.

```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000
```

For example, `2` is written as `II` in Roman numeral, just two one's added together. `12` is written as `XII`, which is simply `X + II`. The number `27` is written as `XXVII`, which is `XX + V + II`.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not `IIII`. Instead, the number four is written as `IV`. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as `IX`. There are six instances where subtraction is used:

I can be placed before `V` (5) and `X` (10) to make `4` and `9`.
X can be placed before `L` (50) and `C` (100) to make `40` and `90`.
C can be placed before `D` (500) and `M` (1000) to make `400` and `900`.
Given a roman numeral, convert it to an integer.

```
Example 1:

Input: s = "III"
Output: 3
```

# ๐ค ํ์ด

```
1) function romanToNum(s) {
2)  const numObj = {
    "I": 1,
    "V": 5,
    "X": 10,
    "L": 50,
    "C": 100,
    "D": 500,
    "M": 1000,
  };

3) const sArr = s.split("");
  for (i in sArr) {
    sArr[i] = numObj[sArr[i]]
  }
  let result = 0;
4) if (!s) { return false };
  for (let i = 0; i < sArr.length; i++) {
    if (sArr[i] < sArr[i + 1]) {
      result -= sArr[i];
    } else {
      result += sArr[i];
    }
  }
    return result;
}
```

# ๐บ ์ค๋ช

1. ํจ์ romanToNum์ s๋ฅผ ์ธ์๋ก ๋ฐ๋๋ฐ, ๊ทธ ์ธ์๋ ๋ก๋ง์๋ก ๋ค์ด์จ๋ค. ์ด ํจ์์์ ์ฐ๋ฆฌ๋ ๋ค์ด์จ ๋ก๋ง์์ ๊ฐ๊ฐ์ ๊ธ์๋ฅผ ์ซ์๋ก ๋ณํํ ๋ค, ๊ฐ๊ฐ์ ๊ธ์๋ฅผ ๊ณ์ฐํ์ฌ ์ด๋ค ์์ธ์ง ๋ํ๋ด๋ ค๊ณ  ํ๋ค.
2. ๋จผ์  ๋ก๋ง์๋ฅผ ์ซ์๋ก ๋ด๊ธฐ ์ํด์ ๋์ฌ ์ ์๋ ๋ชจ๋  ๋ก๋ง์์ ๋ฌธ์๋ฅผ ์ซ์๋ก ๋ด์ ๊ฐ์ฒด๋ฅผ ํ๋ ๋ง๋ค์ด์ค๋ค.
3. ๋น ๋ฐฐ์ด์ธ sArr๋ ๋ก๋ง์ ๊ฐ๊ฐ์ ์ซ์๋ฅผ ํ๋์ฉ ๋ผ์ด๋ด์ ๋ฐฐ์ด์ ๊ฐ์ผ๋ก ๋ด๋๋ค
   `์: 'XVII' ๋ผ๋ ๋ฌธ์๊ฐ ๋ค์ด์์ ๋, sArr =['X', 'V', 'I', 'I']` -๊ทธ๋ฆฌ๊ณ  ๋ง๋ค์ด์ง sArr๋ฐฐ์ด์ ๋ฌธ์๋ฅผ ์ซ์๋ก ๋ฐ๊พธ์ด์ฃผ๊ธฐ ์ํด `sArr[i] = numObj[sArr[i]`๋ผ๊ณ  ์์ ๋ง๋ค์ด์ฃผ์๋ค. -๊ทธ ๋ค์, ๋ฐฐ์ด ์์ ๋ค์ด์๋ ๊ฐ๋ค์ ๊ณ์ฐํด์ ์ฐจํ ์๋ก์ด ๊ฒฐ๊ณผ๊ฐ์ ๋ด์์ฃผ๊ธฐ ์ํด result๋ฅผ ์ ์ธํด์ฃผ์๊ณ  0์ผ๋ก ์ด๊ธฐ๊ฐ์ ์ธํํด์ฃผ์๋ค.
4. sArr ๋ฐฐ์ด์ ๊ฐ์ ๊ณ์ฐํด result์ ๋ฃ์ด์ฃผ๊ธฐ ์ํด์ for๋ฌธ ์์์ ๋ชจ๋  ๋ฐฐ์ด์ ๊ฐ์ ๋น๊ตํด ๊ณ์ฐ ํ  ์ ์๋ ์์ ๋ง๋ค์ด์ค๋ค. ๊ทธ ์ ์ s์ ๊ฐ์ด ์์๋๋ false๋ฅผ ๋ฆฌํดํ์ฌ ์์ธ์ฒ๋ฆฌ๋ฅผ ๋จผ์  ํด์ฃผ์๋ค.
   _
   ! ๋ก๋ง์ ๊ณ์ฐ๋ฒ -์ด๋ ๋ก๋ง์์ ๊ณ์ฐ๋ฒ์ ์๊ณ  ์์ด์ผ ํ๋๋ฐ ๋ก๋ง์์ ๊ฒฝ์ฐ ์๊ธ์๊ฐ ๋ท๊ธ์๋ณด๋ค ๊ฐ์ด ์์ ๊ฒฝ์ฐ ๋ท๊ธ์์ ๊ฐ์์ ์๊ธ์์ ๊ฐ์ ๋นผ์ค๋ค. `IV(5-1)`์ ์ ๊ฐ์ด ๋ค์ V์์ I๋ฅผ ๋นผ์ค ๊ฐ์ธ 4๊ฐ ๋์จ๋ค. -๋ง์ฝ ์๊ธ์๊ฐ ๋ท๊ธ์์ ๊ฐ๋ณด๋ค ํฌ๊ฑฐ๋ ๊ฐ์ ๊ฒฝ์ฐ์ ์๋ค์ ๋ํด์ค๋ค. `III(1+1+1)`, `VII(5+1+1)`
   _

๋ก๋ง์์ ๊ณ์ฐ๋ฒ์ ๋ฐ๋ผ for๋ฌธ์ด sArr์ ๊ธธ์ด๋งํผ ๋๋ฉด์ ๊ฐ ์ธ๋ฑ์ค๋ฅผ ๋น๊ตํ๋ค. ๋ง์ฝ ๋ท๊ธ์๊ฐ ๋ ํฌ๋ค๋ฉด `if(sArr[i] < sArr[i+1])` result์๋ ๋ค์์ ์์๊ฒ์ ๋บ ๊ฐ์ ๋ฃ์ด์ค๋ค.`result -=sArr[i]`

๊ทธ๋ ์ง ์๋ค๋ฉด, result์๋ ์์๊ฒ๊ณผ ๋ค์ ๊ฐ์ ๋ํด์ ๋ฃ์ด์ค๋ค.`result +=sArr[i]`
