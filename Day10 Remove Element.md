# π€ λ¬Έμ 

Given an integer array `nums` and an integer `val`, remove all occurrences of `val` in nums in-place. The relative order of the elements may be changed.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array `nums`. More formally, if there are `k` elements after removing the duplicates, then the first `k` elements of nums should hold the final result. It does not matter what you leave beyond the first `k` elements.

Return `k` after placing the final result in the first `k` slots of nums.

Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

```
Example 1:

Input: nums = [3,2,2,3], val = 3
Output: 2, nums = [2,2,_,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 2.
It does not matter what you leave beyond the returned k (hence they are underscores).v
```

# π€ νμ΄

```
var removeElement = function(nums, val) {
    for(let i =0; i<nums.length; i++){
  if(nums[i] === val){
    nums.splice(i, 1)
    i = -1
  }
}
    return nums.length

};
```

# π μ€λͺ

- μλ²½νμ§ μμ§λ§ μ²μμΌλ‘ λμ μ κ·Όλ²μ΄ ν΄λ΅ μ€ νλμ 90%μ λ λ§μ λ¨μ΄μ§..(λ¬Όλ‘  μ¬μμ κ·Έλ κΈ°λ νμ§λ§)
- μ λ² λ¬Έμ μμ λ¦¬ν΄λ°λ λ°°μ΄μ κ°μ μ λλ‘ κ³ λ €νμ§ μμκΈ° λλ¬Έμ μ΄λ²μ μ νμΈνλ €κ³  νμΌλ λ μ΄μ§ μ΄κΈλ¬λ€.. κ·Έλμ μ΄λ€ λΆλΆμ΄ μλͺ»λμλμ§ νμΈνκ³  μμ  μλ£..!
- μΌλ¨ λ¬Έμ μ μ‘°κ±΄μ λ°°μ΄μμ λ°λ³΅λλκ²μ μ κ±°νλ κ², κ·Έλ¦¬κ³  λ°λ³΅μμ μ κ±°ν λ°°μ΄μ΄ μ΄ λͺκ°μ μμλ₯Ό κ°μ§κ³  μλμ§ return. μ¬κΈ°μ μ€μνκ±΄ μλ‘μ΄ λ°°μ΄μ λ§λ€λ©΄ μλ¨.
- μ²μ λ©μλλ₯Ό μκ°νμλ filterλ‘ κ±°λ₯΄λ©΄ λμ§ μλ μΆμλλ° μ΄κ±΄ μλ‘μ΄ λ°°μ΄μ λ§λ€κΈ°μ ν¨μ€, spliceλΌλ μλ₯΄κ³ μνλ μμΉμ μλ₯Ό κ°μλ₯Ό μ ν΄μ£Όλ λ©μλλ₯Ό μ΄μ©νμ¬ νμ΄ μλ£
- λ°°μ΄μ μμ°¨μ μΌλ‘ λλ©΄μ μ κ±°ν  λμμΈ valμ κ°μ μκ° λμμ λ ν΄λΉ μμΉλΆν° μκΈ° μμ μ μλ₯Έλ€.
- μ΄ν μλ €μ§ λ°°μ΄μ μΈλ±μ€κ° λΉκ²¨μ ΈμΌ νκΈ° λλ¬Έμ -1μ ν΄μ£Όμλ€.
- return λ  κ°μ νμΌκ°μ΄ μ­μ  λκ³  λ¨μ κ²λ€μ κ°μ!
