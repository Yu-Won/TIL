# 알고리즘 문제 풀이 - Palindrome Number(LeetCode)

## 문제 설명

Given an integer `x`, return `true` if `x` is palindrome integer.

An integer is a **palindrome** when it reads the same backward as forward. For example, `121` is palindrome while `123` is not.

<br />

## Example

**Example 1:**

    Input: x = 121
    Output: true

**Example 2:**

    Input: x = -121
    Output: false
    Explanation: From left to right, it reads -121. From right to left, it becomes 121-. Therefore it is not a palindrome.

**Example 3:**

    Input: x = 10
    Output: false
    Explanation: Reads 01 from right to left. Therefore it is not a palindrome.

**Example 3:**

    Input: x = -101
    Output: false

<br />

## Constraints

- -2<sup>31</sup> <= x <= 2<sup>31</sup> - 1

<br />

## 코드 작성

```js
/**
 * @param {number} x
 * @return {boolean}
 */
const isPalindrome = (x) => {
  if (x < 0) return false;

  const reverse = `${x}`.split("").reverse().join("");
  return x.toString() === reverse;
};
```

<br />
