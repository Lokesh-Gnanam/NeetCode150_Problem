# NEETCODE 2026

## 1.Two Sum [neetcode](https://neetcode.io/problems/two-integer-sum/question?list=neetcode150)
Solved 
Easy
Topics
Company Tags
Hints
Given an array of integers nums and an integer target, return the indices i and j such that nums[i] + nums[j] == target and i != j.

You may assume that every input has exactly one pair of indices i and j that satisfy the condition.

Return the answer with the smaller index first.

Example 1:

Input: 
nums = [3,4,5,6], target = 7

Output: [0,1]
Explanation: nums[0] + nums[1] == 7, so we return [0, 1].

Example 2:

Input: nums = [4,5,6], target = 10

Output: [0,2]
Example 3:

Input: nums = [5,5], target = 10

Output: [0,1]

```cpp
class Solution {
public:
    vector<int> twoSum(vector<int>& nums, int target) {
        for (int i = 0; i < nums.size(); i++) {
            for (int j = i + 1; j < nums.size(); j++) {
                if (nums[i] + nums[j] == target) {
                    return {i, j};
                }
            }
        }
        return {};
    }
};
```
-------------------------------------
-------------------------------------
## 2.Given an integer array nums, return true if any value appears more than once in the array, otherwise return false [neetcode](https://neetcode.io/problems/duplicate-integer/question)

Example 1:

Input: nums = [1, 2, 3, 3]

Output: true

Example 2:

Input: nums = [1, 2, 3, 4]

Output: false

```java
class Solution {
    public boolean hasDuplicate(int[] nums) {
        for(int i=0;i<nums.length;i++){
            for(int j=i+1;j<nums.length;j++){
                if(nums[i] == nums[j]){
                    return true;
                }
            }
        }
        return false;
    }
}
```
------------------------------
------------------------------

## 3.Valid Anagram [neetcode](https://neetcode.io/problems/is-anagram/question)
Solved 
Easy
Topics
Company Tags
Hints
Given two strings s and t, return true if the two strings are anagrams of each other, otherwise return false.

An anagram is a string that contains the exact same characters as another string, but the order of the characters can be different.

Example 1:

Input: s = "racecar", t = "carrace"

Output: true
Example 2:

Input: s = "jar", t = "jam"

Output: false

s and t consist of lowercase English letters.

```cpp
class Solution {
public:
    bool isAnagram(string s, string t) {
        if(s.length()!= t.length()){
            return false;
        }
        sort(s.begin(), s.end());
        sort(t.begin(), t.end());
        return s == t;
    }
};
```
----------------------------
----------------------------

## 4. Best Time to Buy and Sell Stock [neetcode](https://neetcode.io/problems/buy-and-sell-crypto/question)
Easy
Topics
Company Tags
Hints
You are given an integer array prices where prices[i] is the price of NeetCoin on the ith day.

You may choose a single day to buy one NeetCoin and choose a different day in the future to sell it.

Return the maximum profit you can achieve. You may choose to not make any transactions, in which case the profit would be 0.

Example 1:

Input: prices = [10,1,5,6,7,1]

Output: 6
Explanation: Buy prices[1] and sell prices[4], profit = 7 - 1 = 6.

Example 2:

Input: prices = [10,8,7,5,2]

Output: 0
Explanation: No profitable transactions can be made, thus the max profit is 0.

Constraints:

1 <= prices.length <= 100
0 <= prices[i] <= 100

```cpp
class Solution {
public:
    int maxProfit(vector<int>& prices) {
        int l = 0, r = 1;
        int maxP = 0;

        while (r < prices.size()) {
            if (prices[l] < prices[r]) {
                int profit = prices[r] - prices[l];
                maxP = max(maxP, profit);
            } else {
                l = r;
            }
            r++;
        }
        return maxP;
    }
};
```
---------------------------------------------
---------------------------------------------

## 5.
