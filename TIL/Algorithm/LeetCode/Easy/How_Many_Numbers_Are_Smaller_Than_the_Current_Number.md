# 알고리즘 문제 풀이 - How Many Numbers Are Smaller Than the Current Number(LeetCode)

## 문제 설명

Given the array `nums`, for each `nums[i]` find out how many numbers in the array are smaller than it. That is, for each `nums[i]` you have to count the number of valid `j's` such that `j != i` **and** `nums[j] < nums[i]`.

Return the answer in an array.

<br />

## Example

**Example 1:**

Input: nums = [8,1,2,2,3]
Output: [4,0,1,1,3]
Explanation:
For nums[0]=8 there exist four smaller numbers than it (1, 2, 2 and 3).
For nums[1]=1 does not exist any smaller number than it.
For nums[2]=2 there exist one smaller number than it (1).
For nums[3]=2 there exist one smaller number than it (1).
For nums[4]=3 there exist three smaller numbers than it (1, 2 and 2).

**Example 2:**

Input: nums = [6,5,4,8]
Output: [2,1,0,3]

**Example 3:**

Input: nums = [7,7,7,7]
Output: [0,0,0,0]

<br />

## Constraints

- 2 <= nums.length <= 500
- 0 <= nums[i] <= 100

<br />

## 코드 작성

```js
/**
 * @param {number[]} nums
 * @return {number[]}
 */
const smallerNumbersThanCurrent = (nums) => {
  const sorted = [...nums].sort((a, b) => a - b);
  return nums.map((el) => sorted.indexOf(el));
};
```

<br />
