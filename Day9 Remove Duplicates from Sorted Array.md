# ๐ค ๋ฌธ์ 

Given an integer array `nums` sorted in non-decreasing order, remove the duplicates in-place such that each unique element appears only once. The relative order of the elements should be kept the same.

Since it is impossible to change the length of the array in some languages, you must instead have the result be placed in the first part of the array `nums`. More formally, if there are k elements after removing the duplicates, then the first `k` elements of nums should hold the final result. It does not matter what you leave beyond the first `k` elements.

Return k after placing the final result in the first `k` slots of `nums`.

Do not allocate extra space for another array. You must do this by modifying the input array in-place with O(1) extra memory.

Custom Judge:

The judge will test your solution with the following code:

```
int[] nums = [...]; // Input array
int[] expectedNums = [...]; // The expected answer with correct length

int k = removeDuplicates(nums); // Calls your implementation

assert k == expectedNums.length;
for (int i = 0; i < k; i++) {
    assert nums[i] == expectedNums[i];
}
```

If all assertions pass, then your solution will be accepted.

Example 1:

```
Input: nums = [1,1,2]
Output: 2, nums = [1,2,_]
Explanation: Your function should return k = 2, with the first two elements of nums being 1 and 2 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

Example 2:

```
Input: nums = [0,0,1,1,1,2,2,3,3,4]
Output: 5, nums = [0,1,2,3,4,_,_,_,_,_]
Explanation: Your function should return k = 5, with the first five elements of nums being 0, 1, 2, 3, and 4 respectively.
It does not matter what you leave beyond the returned k (hence they are underscores).
```

# ๋ด๊ฐ ์๊ฐํ ํ์ด(ํ๋ฆผ ์ฃผ์..)

- nums ๋ฐฐ์ด์ ๋๋ฉด์ ๋ช๋ฒ ์ถํํ๋์ง ์์ผ๋ก result์ ์ ์ฅํ๊ณ  key๊ฐ์ ๊ฐ์๋ค๋ง ๋ฐํ(๊ธธ์ด)ํ๋ฉด ๋์ง ์์๊น ํ์ง๋ง, ์์  ํ๋ฆฐ๋ต์ด์์...
- ์์ธ์ง ์ด์ ๋ ๊ณ ๋ฏผํด๋ด์ผํ  ๊ฒ ๊ฐ์ ใใ
- ์ ์๊ฒ ๋ค.. ๋ฐฐ์ด์ด ์ค๋ณต์ ์ ๊ฑฐํ๊ณ  ๋์จ ๊ฐ์ด๋ ๊ฐ์์ผํ๋๊ตฌ๋...

```
let result = {}
nums.forEach((x)=>{
  result[x]=(result[x] || 0)+1
})

return Object.keys(result).length;
```

# ์๋ฆฌ

- i์ j๋ผ๋ ์์์ ๋ณ์๋ค์ ์ธ๋ฑ์ค์ 0๊ณผ 1๋ก ์ด๊ธฐ ์ค์  ํ ๋ค
- j๊ฐ nums์ ๊ธธ์ด๋งํผ ๋๋ฉด์
- ๋์ด ๊ฐ์ง ์์ผ๋ฉด ์ผ๋จ i์ ๊ฐ์ ํ๋ ์ฆ๊ฐ ์ํค๊ณ (์ธ๋ฑ์ค์ ๊ฐ ์ฆ๊ฐ) nums[j]์ ๊ฐ์ nums[i]์ ํ ๋นํด์ค๋ค.
- ๊ทธ๋ฆฌ๊ณ  ๋ง์ง๋ง์ผ๋ก j๋ 1์ฉ ์ฆ๊ฐ์์ผ์ค๋ค.
- ๋ง์ฝ ๋์ด ๊ฐ์ ๊ฒฝ์ฐ์๋ j๋ง ์ฆ๊ฐ์์ผ ๋น๊ต์์ผ์ค๋ค.
- ![](https://images.velog.io/images/sgr2134/post/e3d089be-6317-412d-800d-93d11bf95679/image.png)

# ํด๋ต ์ค ํ๋

```
var removeDuplicates = function (nums) {
  if (nums.length === 0) return 0; //์์ธ์ฐ~
  let i = 0;
  let j = 1;
  while (j < nums.length) {
    if (nums[j] !== nums[i]) {
      i++;
      nums[i] = nums[j];
      j++;
    } else j++;
  }
  return i + 1;
};
```

~~ํ๋ฆฌ๋๊ฒ๋ ์ง๊ฒจ์,, ๋๋์ฒด ์ธ์ ์ฏค ๋ง์ถฐ๋ณผ๊น,,,ใใ~~
