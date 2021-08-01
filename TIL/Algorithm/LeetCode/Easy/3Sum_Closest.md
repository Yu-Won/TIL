# 알고리즘 문제 풀이 - 3Sum Closest(LeetCode)

## 문제 설명

Given an array `nums` of n integers and an integer `target`, find three integers in `nums` such that the sum is closest to `target`. Return the sum of the three integers. You may assume that each input would have exactly one solution.

<br />

## Example 1

    Input: nums = [-1,2,1,-4], target = 1
    Output: 2
    Explanation: The sum that is closest to the target is 2. (-1 + 2 + 1 = 2).

<br />

## Constraints

- 3 <= nums.length <= 10^3
- -10^3 <= nums[i] <= 10^3
- -10^4 <= target <= 10^4

<br />

## 접근법

1. nums의 길이가 3 이하일 경우 바로 return 한다.
2. 반복문을 돌면서 세 정수의 합을 확인한다.
3. 세 정수의 합이 같으면 바로 return 한다.
4. sum과 target 숫자의 차가 closestSum과 target의 숫자의 차보다 작으면 sum을 closestSum에 할당한다.

<br />

## 코드 작성

```js
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number}
 */
const threeSumClosest = function (nums, target) {
  if (nums.length <= 3) return nums[0] + nums[1] + nums[2];

  let closestSum;
  for (let i = 0; i < nums.length; i++) {
    for (let j = i + 1; j < nums.length; j++) {
      for (let k = j + 1; k < nums.length; k++) {
        let sum = nums[i] + nums[j] + nums[k];
        if (sum === target) {
          return sum;
        } else if (
          !closestSum ||
          Math.abs(closestSum - target) > Math.abs(sum - target)
        ) {
          closestSum = sum;
        }
      }
    }
  }
  return closestSum;
};
```

<br />
