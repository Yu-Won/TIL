# 알고리즘 문제 풀이 - Number Of Rectangles That Can Form The Largest Square

(LeetCode)

## 문제 설명

You are given an array `rectangles` where rectangles[i] = [l<sub>i</sub>, w<sub>i</sub>] represents the i<sup>th</sup> rectangle of length l<sub>>i</sub> and width w<sub>i</sub>.

You can cut the i<sup>th</sup> rectangle to form a square with a side length of `k` if both k <= l<sub>i</sub> and k <= w<sub>i</sub>. For example, if you have a rectangle `[4,6]`, you can cut it to get a square with a side length of at most `4`.

Let `maxLen` be the side length of the **largest** square you can obtain from any of the given rectangles.

Return the **number** of rectangles that can make a square with a side length of maxLen.

<br />

## Example 1

    Input: rectangles = [[5,8],[3,9],[5,12],[16,5]]
    Output: 3
    Explanation: The largest squares you can get from each rectangle are of lengths [5,3,5,5].
    The largest possible square is of length 5, and you can get it out of 3 rectangles.

<br />

## Example 2

    Input: rectangles = [[2,3],[3,7],[4,3],[3,7]]
    Output: 3

<br />

## Constraints

- 1 <= rectangles.length <= 1000
- rectangles[i].length == 2
- 1 <= l<sub>i</sub>, w<sub>i</sub> <= 10<sup>9</sup>
- l<sub>i</sub> != w<sub>i</sub>

<br />

## 코드 작성

```js
/**
 * @param {number[][]} rectangles
 * @return {number}
 */
const countGoodRectangles = (rectangles) => {
  let max = 0;
  let count = 0;

  for (let i = 0; i < rectangles.length; i++) {
    let min = Math.min(rectangles[i][0], rectangles[i][1]);

    if (min > max) {
      count = 0;
      max = min;
    }

    if (min === max) count++;
  }

  return count;
};
```

<br />
