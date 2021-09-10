# 알고리즘 문제 풀이 - Range Sum of BST(LeetCode)

## 문제 설명

Given the `root` node of a binary search tree and two integers `low` and `high`, return the sum of values of all nodes with a value in the **inclusive** range `[low, high].`

<br />

## Example

**Example 1:**

    Input: root = [10,5,15,3,7,null,18], low = 7, high = 15
    Output: 32
    Explanation: Nodes 7, 10, and 15 are in the range [7, 15]. 7 + 10 + 15 = 32.

**Example 2:**

    Input: root = [10,5,15,3,7,13,18,1,null,6], low = 6, high = 10
    Output: 23
    Explanation: Nodes 6, 7, and 10 are in the range [6, 10]. 6 + 7 + 10 = 23.

<br />

## Constraints

- The number of nodes in the tree is in the range [1, 2 * 10<sup>4</sup>].
- 1 <= Node.val <= 10<sup>5</sup>
- 1 <= low <= high <= 10<sup>5</sup>
- All Node.val are **unique.**

<br />

## 코드 작성

```js
/**
 * Definition for a binary tree node.
 * function TreeNode(val, left, right) {
 *     this.val = (val===undefined ? 0 : val)
 *     this.left = (left===undefined ? null : left)
 *     this.right = (right===undefined ? null : right)
 * }
 */
/**
 * @param {TreeNode} root
 * @param {number} low
 * @param {number} high
 * @return {number}
 */
const rangeSumBST = (root, low, high) => {
  let sum = 0;
  if (root === null) return sum;
  if (root.val > low) sum += rangeSumBST(root.left, low, high);
  if (root.val <= high && root.val >= low) sum += root.val;
  if (root.val < high) sum += rangeSumBST(root.right, low, high);
  return sum;
};
```

<br />
