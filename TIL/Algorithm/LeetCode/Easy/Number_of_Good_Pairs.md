# 알고리즘 문제 풀이 - Number of Good Pairs(LeetCode)

## 문제 설명

Given an array of integers nums.

A pair (i,j) is called good if nums[i] == nums[j] and i < j.

Return the number of good pairs.

<br />

## Example

**Example 1:**

    Input: nums = [1,2,3,1,1,3]
    Output: 4
    Explanation: There are 4 good pairs (0,3), (0,4), (3,4), (2,5) 0-indexed.

**Example 2:**

    Input: nums = [1,1,1,1]
    Output: 6
    Explanation: Each pair in the array are good.

**Example 3:**

    Input: nums = [1,2,3]
    Output: 0

<br />

## Constraints

- 1 <= nums.length <= 100
- 1 <= nums[i] <= 100

<br />

## 코드 작성

```js
/**
 * @param {number[]} nums
 * @return {number}
 */
const numIdenticalPairs = (nums) => {
  let count = 0;
  for (let i = 0; i < nums.length - 1; i++) {
    for (let j = 1; j < nums.length; j++) {
      if (i < j && nums[i] === nums[j]) count++;
    }
  }
  return count;
};
```

<br />
