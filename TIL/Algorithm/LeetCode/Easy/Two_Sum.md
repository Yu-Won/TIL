# 알고리즘 문제 풀이 - Two Sum(LeetCode)

## 문제 설명

Given an array of integers `nums` and an integer `target`, return indices of the two numbers such that they add up to `target`.

You may assume that each input would have **exactly one solution**, and you may not use the same element twice.

You can return the answer in any order.

<br />

## Example

**Example 1:**

    Input: nums = [2,7,11,15], target = 9
    Output: [0,1]
    Output: Because nums[0] + nums[1] == 9, we return [0, 1].

**Example 2:**

    Input: nums = [3,2,4], target = 6
    Output: [1,2]

**Example 3:**

    Input: nums = [3,3], target = 6
    Output: [0,1]

<br />

## Constraints

- 2 <= nums.length <= 10<sup>4</sup>
- -10<sup>9</sup> <= nums[i] <= 10<sup>9</sup>
- -10<sup>9</sup> <= target <= 10<sup>9</sup>
- **Only one valid answer exists.**

<br />

## 코드 작성

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
const twoSum = (nums, target) => {
  if (nums.length === 2) return [0, 1];
  const len = nums.length;
  let map = {};
  for (let i = 0; i < len; i++) {
    let n = target - nums[i];
    let find = map[n];
    if (find !== undefined) return [find, i];
    else map[nums[i]] = i;
  }
};
```

<br />
