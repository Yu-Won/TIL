# 알고리즘 문제 풀이 - Jewels and Stones(LeetCode)

## 문제 설명

You're given strings `jewels` representing the types of stones that are jewels, and stones representing the `stones` you have. Each character in stones is a type of `stone` you have. You want to know how many of the stones you have are also jewels.

Letters are case sensitive, so `"a"` is considered a different type of stone from `"A"`.

<br />

## Example

**Example 1:**

    Input: jewels = "aA", stones = "aAAbbbb"
    Output: 3

**Example 2:**

    Input: jewels = "z", stones = "ZZ"
    Output: 0

<br />

## Constraints

- 1 <= jewels.length, stones.length <= 50
- jewels and stones consist of only English letters.
- All the characters of jewels are unique.

<br />

## 코드 작성

```js
/**
 * @param {string} jewels
 * @param {string} stones
 * @return {number}
 */
const numJewelsInStones = (jewels, stones) => {
  let count = 0;

  for (let i = 0; i < stones.length; i++) {
    if (jewels.indexOf(stones[i]) >= 0) count++;
  }
  return count;
};
```

<br />
