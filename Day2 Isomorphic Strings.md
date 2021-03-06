Given two strings `s` and `t`, determine if they are isomorphic.

Two strings `s` and `t` care isomorphic if the characters in `s` can be replaced to get `t`.

All occurrences of a character must be replaced with another character while preserving the order of characters. No two characters may map to the same character, but a character may map to itself.

```
Example 1:

Input: s = "egg", t = "add"
Output: true
```

## π λ΄κ° μκ°ν λ‘μ§

1. stringμ κ°κ°μ κΈμλ₯Ό λ°°μ΄λ‘ λ°κΎΌλ€. => [e,g,g] / [a,d,d]
2. λ°°μ΄λ‘ λ°κΎΌ κΈμλ€μ μΆν νμλ₯Ό μΉ΄μ΄νΈ νμ¬ μλ‘μ΄ λ°°μ΄λ‘ λ°κΎΌλ€. => [1,2,2]/[1,2,2]
3. 2)μμ λμ¨ λ°°μ΄μ λΉκ΅νμ¬ True/False κ°μ λ°ννλ€.

## π νμ΄

μΌλμλμ λμμ μ»μ΄ νμ΄ μ±κ³΅!

```
let isIsomorphic = function (s, t) {
  const changetoNum = str => {
    let arr = str.split('');
    let answer = [];
    let counter = 0;
    for (let i = 0; i < arr.length; i++) {
      for (let z = 0; z < arr.length; z++) {
        if (arr[i] === arr[z]) counter += 1;
        if (z === arr.length - 1) {
          answer.push(counter);
          counter = 0;
        }
      }
    }
    return answer;
  };
  const result = () => {
    if (String(changetoNum(s)) === String(changetoNum(t))) {
      return true;
    } else {
      return false;
    }
  };
  return result();
};
```
