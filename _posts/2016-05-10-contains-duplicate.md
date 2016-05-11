---
layout: post
section-type: post
title: Contains Duplicate & Contains Duplicate II & Contains Duplicate III
category: leetcode
tags: [ 'array' ]
---

### Contains Duplicate

Given an array of integers, find if the array contains any duplicates. Your function should return true if any value appears at least twice in the array, and it should return false if every element is distinct. 

�ҳ��������Ƿ����ظ�ֵ��ʹ��һ����ϣ��������飬�����ϣ������ڣ�����true,�������򽫵�ǰֵ�����ϣ���У��������£�

```cpp
class Solution {
public:
    bool containsDuplicate(vector<int>& nums) {
        unordered_map<int,int> m;
        for(size_t i=0;i<nums.size();i++)
        {
            if(m.find(nums[i])!=m.end()) return true;
            ++m[nums[i]];
        }
        return false;
    }
};
```

### Contains Duplicate II

Given an array of integers and an integer k, find out whether there are two distinct indices i and j in the array such that nums[i] = nums[j] and the difference between i and j is at most k.

����������Ĳ�֮ͬ�����ظ�ֵ�������ܳ���k��Ҳ���ҳ�һ�Լ��ɡ�

```cpp
class Solution {
public:
    bool containsNearbyDuplicate(vector<int>& nums, int k) {
        unordered_map<int, int> m;
        for (int i = 0; i < nums.size(); ++i) {
            if (m.find(nums[i]) != m.end() && i - m[nums[i]] <= k) return true;
            else m[nums[i]] = i;
        }
        return false;
    }
};
```
### Contains Duplicate III
