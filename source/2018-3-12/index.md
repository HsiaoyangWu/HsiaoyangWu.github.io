---
title: 2018-3-12
date: 2018-03-12 01:02:50

---

最近一直在学习C++以及数据结构、算法，在网上找资料的时候发现了leetcode、codewar等OJ网站，尝试一下发现里面的题目都很经典，因此这四天一直在刷，目前已经完成了初级算法部分，想记录下个人所得，下个难度以后再找时间做做。



leetcode官网<https://leetcode.com/>  英语不好的我选择

Leetcode中国 官网<https://leetcodechina.com/>





## 数组array

正常的array表示，形式为[ ]

在C++里还有另外的一种类似的变量*vector*，从本质上而言，*array*是特殊的*vector*。

两者所不同的是 ，array的方法只有赋值，vector的方法包含：push_back(),insert() 等等，做题的时候明显感觉到这些方法的必要性。

比如这道题

### [leetcode] Two Sum

####题目原文

给定一个整数数列，找出其中和为特定值的那两个数。

你可以假设每个输入都只会有一种答案，同样的元素不能被重用。

示例:

```c++
给定 nums = [2, 7, 11, 15], target = 9

因为 nums[0] + nums[1] = 2 + 7 = 9
所以返回 [0, 1]
```


```c++
class Solution {
public:

    vector<int> twoSum(vector<int>& nums, int target) {
        unordered_map<int,int> my_map;
        vector<int>result;
        for(int i =0; i<nums.size(); i++){
            my_map[nums[i]]=i;
        }
        for(int i=0;i<nums.size();i++){
            auto iter = my_map.find(target-nums[i]);
            if(iter !=my_map.end() && iter->second > i){
                result.push_back(i);
                result.push_back(iter->second);
                break;
                    
            }
        }
        return result;
        
    }
};
```

## 字符串

字符串其实就是存储为char类型的array,与python中并无二致。

只要熟练使用关于array遍历的方法，以及注意char类型就OK了，问题不大。

### [leetcode]Longest Common Prefix

题目解读：编写一个函数来查找字符串数组中最长的公共前缀字符串。

*Solution*

```c++
class Solution {
public:
    string longestCommonPrefix(vector<string>& strs) {
    if(strs.empty())return "";
        for(int i=0; i<strs[0].length();i++){
            for(int j=0; j<strs.size();j++){
            if( i > strs[j].length() || strs[j][i] != strs[0][i]){
                return strs[0].substr(0,i);
            }
            }
        }
        return strs[0];
    }
};
```

## 链表

break有空再更
