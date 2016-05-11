---
layout: post
section-type: post
title: Container With Most Water
category: leetcode
tags: [ 'array' ]
---

### Container With Most Water

Given n non-negative integers *a_1*, *a_2*, ..., *a_n*, where each represents a point at coordinate (*i*, *a_i*). *n* vertical lines are drawn such that the two endpoints of line *i* is at (*i*, *a_i*) and (*i*, 0). Find two lines, which together with x-axis forms a container, such that the container contains the most water.

Note: You may not slant the container. 

���⣺�и��߶����飬���൱�ڸ���ĸ߶ȣ��������������������ʢˮ��������������ľ�����ϵ͸���ĸ߶ȳ˻���Ϊʢˮ��������

����������ָ������˿�ʼ���м俿£���������߶ζ����Ҷˣ���ô������ƣ���֮�Ҷ����ƣ�ֱ�����������Ƶ��м��غϣ��Ƚ����������ÿһ�����ľͰ���ݻ��������������ġ�ʱ�临�Ӷ�O(n),�ռ临�Ӷ�O(1).���ͣ�������߶�leftС���Ҷ��߶�rightʱ�����ǰ�left���ƣ���ʱ��������left���Ҷ������߶Σ�right-1, right-2, ...����ɵ�ľͰ����ЩľͰ��û��Ҫ�жϵģ���Ϊ��ЩľͰ���ݻ��϶���û��left��right��ɵ�ľͰ�ݻ���,��֮ͬ���������£�
```cpp
class Solution {
public:
    int maxArea(vector<int>& height) {
        int res=INT_MIN,left=0,right=height.size()-1;
        while(left<right)
        {
            res=max(res,min(height[right],height[left])*(right-left));
            if(height[left]<height[right]) ++left;
            else --right;
        }
        return res;
    }
};
```

