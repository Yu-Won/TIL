# 알고리즘 문제 풀이 - Search a 2D Matrix(LeetCode)

## 문제 설명

Write an efficient algorithm that searches for a value in an `m x n` matrix. This matrix has the following properties:

- Integers in each row are sorted from left to right.
- The first integer of each row is greater than the last integer of the previous row.

<br />

## Example

**Example 1:**

    Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 3
    Output: true

**Example 2:**

    Input: matrix = [[1,3,5,7],[10,11,16,20],[23,30,34,60]], target = 13
    Output: false

<br />

## Constraints

- m == matrix.length
- n == matrix[i].length
- 1 <= m, n <= 100
- 10<sup>4</sup> <= matrix[i][j], target <= 10<sup>4</sup>

<br />

## 코드 작성

```js
/**
 * @param {number[][]} matrix
 * @param {number} target
 * @return {boolean}
 */
const searchMatrix = (matrix, target) => {
  let result = false;
  for (let i = 0; i < matrix.length; i++) {
    for (let j = 0; j < matrix[i].length; j++) {
      if (matrix[i][j] === target) {
        result = true;
      }
    }
  }
  return result;
};
```

<br />
