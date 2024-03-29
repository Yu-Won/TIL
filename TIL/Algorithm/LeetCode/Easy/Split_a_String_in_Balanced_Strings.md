# 알고리즘 문제 풀이 - Split a String in Balanced Strings(LeetCode)

## 문제 설명

**Balanced** strings are those that have an equal quantity of `'L'` and `'R'` characters.

Given a **balanced** string `s`, split it in the maximum amount of balanced strings.

Return the maximum amount of split **balanced** strings.

<br />

## Example

**Example 1:**

    Input: s = "RLRRLLRLRL"
    Output: 4
    Explanation: s can be split into "RL", "RRLL", "RL", "RL", each substring contains same number of 'L' and 'R'.

**Example 2:**

    Input: s = "RLLLLRRRLR"
    Output: 3
    Explanation: s can be split into "RL", "LLLRRR", "LR", each substring contains same number of 'L' and 'R'.

**Example 3:**

    Input: s = "LLLLRRRR"
    Output: 1
    Explanation: s can be split into "LLLLRRRR".

**Example 4:**

    Input: s = "RLRRRLLRLL"
    Output: 2
    Explanation: s can be split into "RL", "RRRLLRLL", since each substring contains an equal number of 'L' and 'R'

<br />

## Constraints

- 1 <= s.length <= 1000
- s[i] is either 'L' or 'R'.
- s is a **balanced** string.

<br />

## 코드 작성

```js
/**
 * @param {string} s
 * @return {number}
 */
const balancedStringSplit = (s) => {
  let result = 0;
  let balanced = 0;

  for (let i = 0; i < s.length; i++) {
    if (s[i] === "L") balanced -= 1;
    else if (s[i] === "R") balanced += 1;

    if (balanced === 0) result += 1;
  }
  return result;
};
```

<br />
