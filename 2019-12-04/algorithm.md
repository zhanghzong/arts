# 算法

## 两数之和

给定一个整数数组 `nums` 和一个目标值 `target`，请你在该数组中找出和为目标值的那 两个 整数，并返回他们的数组下标。

你可以假设每种输入只会对应一个答案。但是，你不能重复利用这个数组中同样的元素。

示例:

```
给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
```

## 题目地址

> https://leetcode-cn.com/problems/two-sum/

## 解题思路

1. 声明一个对象map
2. 循环遍历nums数组,用`target-nums[i]`得出结果判断是否存在map中.存在则返回.否则把数组元素加入对象中

## 答案

```javascript
/**
 * @param {number[]} nums
 * @param {number} target
 * @return {number[]}
 */
var twoSum = function (nums, target) {
    let dataResult = {};
    for (let idx in nums) {
        let val = nums[idx];

        let last = dataResult[target - val];
        if (last != undefined) {
            return [last, idx]
        }

        dataResult[val] = idx;
    }

    return [];
};
```