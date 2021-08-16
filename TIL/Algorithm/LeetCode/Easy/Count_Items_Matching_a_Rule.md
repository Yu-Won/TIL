# 알고리즘 문제 풀이 - Count Items Matching a Rule(LeetCode)

## 문제 설명

You are given an array `items`, where each `items[i] = [typei, colori, namei]` describes the type, color, and name of the `ith` item. You are also given a rule represented by two strings, `ruleKey` and `ruleValue`.

The `ith` item is said to match the rule if **one** of the following is true:

- `ruleKey == "type"` and `ruleValue == type`<sup>i</sup>.
- `ruleKey == "color"` and `ruleValue == color`<sup>i</sup>.
- `ruleKey == "name"` and `ruleValue == name`<sup>i</sup>.

Return the number of items that match the given rule.

<br />

## Example

**Example 1**

    Input: items = [["phone","blue","pixel"],["computer","silver","lenovo"],["phone","gold","iphone"]], ruleKey = "color", ruleValue = "silver"
    Output: 1
    Explanation: There is only one item matching the given rule, which is ["computer","silver","lenovo"].

**Example 2**

    Input: items = [["phone","blue","pixel"],["computer","silver","phone"],["phone","gold","iphone"]], ruleKey = "type", ruleValue = "phone"
    Output: 2
    Explanation: There are only two items matching the given rule, which are ["phone","blue","pixel"] and ["phone","gold","iphone"]. Note that the item ["computer","silver","phone"] does not match.

<br />

## Constraints

- 1 <= items.length <= 104
- 1 <= typei.length, colori.length, namei.length, ruleValue.length <= 10
- ruleKey is equal to either "type", "color", or "name".
- All strings consist only of lowercase letters.

<br />

## 코드 작성

```js
/**
 * @param {string[][]} items
 * @param {string} ruleKey
 * @param {string} ruleValue
 * @return {number}
 */

const map = {
  type: 0,
  color: 1,
  name: 2,
};

const countMatches = (items, ruleKey, ruleValue) =>
  items.filter((i) => i[map[ruleKey]] === ruleValue).length;
/**
 * @param {string} command
 * @return {string}
 */
const interpret = (command) => {
  return command.replaceAll("(al)", "al").replaceAll("()", "o");
};
```

<br />
