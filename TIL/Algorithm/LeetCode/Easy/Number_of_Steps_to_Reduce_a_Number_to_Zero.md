# 알고리즘 문제 풀이 - Number of Steps to Reduce a Number to Zero(LeetCode)

## 문제 설명

Given an integer `num`, return the number of steps to reduce it to zero.

In one step, if the current number is even, you have to divide it by `2`, otherwise, you have to subtract `1` from it.

<br />

## Example

**Example 1**

    Input: num = 14
    Output: 6
    Explanation:
    Step 1) 14 is even; divide by 2 and obtain 7.
    Step 2) 7 is odd; subtract 1 and obtain 6.
    Step 3) 6 is even; divide by 2 and obtain 3.
    Step 4) 3 is odd; subtract 1 and obtain 2.
    Step 5) 2 is even; divide by 2 and obtain 1.
    Step 6) 1 is odd; subtract 1 and obtain 0.

**Example 2**

    Input: num = 8
    Output: 4
    Explanation:
    Step 1) 8 is even; divide by 2 and obtain 4.
    Step 2) 4 is even; divide by 2 and obtain 2.
    Step 3) 2 is even; divide by 2 and obtain 1.
    Step 4) 1 is odd; subtract 1 and obtain 0.

**Example 3**

    Input: num = 123
    Output: 12

<br />

## Constraints

- 0 <= num <= 10<sup>6</sup>

<br />

## 코드 작성

```js
/**
 * @param {number} num
 * @return {number}
 */
const numberOfSteps = (num) => {
  let steps = 0;
  while (num > 0) {
    if (num % 2) {
      num--;
      steps++;
    } else {
      num = num / 2;
      steps++;
    }
  }
  return steps;
};
```

<br />
