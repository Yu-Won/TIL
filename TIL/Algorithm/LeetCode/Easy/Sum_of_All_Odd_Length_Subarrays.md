# 알고리즘 문제 풀이 - Sum of All Odd Length Subarrays(LeetCode)

## 문제 설명

Given an array of positive integers arr, calculate the sum of all possible odd-length subarrays.

A subarray is a contiguous subsequence of the array.

Return the sum of all odd-length subarrays of arr.

<br />

## Example 1

    Input: arr = [1,4,2,5,3]
    Output: 58
    Explanation: The odd-length subarrays of arr and their sums are:
    [1] = 1
    [4] = 4
    [2] = 2
    [5] = 5
    [3] = 3
    [1,4,2] = 7
    [4,2,5] = 11
    [2,5,3] = 10
    [1,4,2,5,3] = 15
    If we add all these together we get 1 + 4 + 2 + 5 + 3 + 7 + 11 + 10 + 15 = 58

<br />

## Example 2

    Input: arr = [1,2]
    Output: 3
    Explanation: There are only 2 subarrays of odd length, [1] and [2]. Their sum is 3.

<br />

## Example 3

    Input: arr = [10,11,12]
    Output: 66

<br />

## Constraints

- 1 <= arr.length <= 100
- 1 <= arr[i] <= 1000

<br />

## 코드 작성

```js
/**
 * @param {number[]} arr
 * @return {number}
 */
const sumOddLengthSubarrays = (arr) => {
  let result = 0,
    n = arr.length;
  for (let i = 0; i < n; ++i) {
    result += parseInt(((i + 1) * (n - i) + 1) / 2) * arr[i];
  }
  return result;
};
```

<br />
