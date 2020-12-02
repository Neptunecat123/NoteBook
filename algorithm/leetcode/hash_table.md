# 哈希表

## &sect;1 定义


## &sect;2 哈希函数

Hash Function

## &sect;3 哈希冲突

Hash Collisions


## &sect;4 应用

    map = {"jack": 100, 
           "mary": 96
          }

    set = {"jack", "mary", "bob"}


**map**（键值对，键值无重复）和**set**（集合，类似map的键）这两个常用数据结构，通常的实现方式是哈希表和二叉树。

**哈希表实现：HashMap/HashSet**

时间复杂度O(1)，元素乱序存储

**二叉树实现：TreeMap/TreeSet**

时间复杂度O(log(n))，元素有序存储

python内置dict和set的实现方式都是hash，tree的实现需要第三方库，如[pytreemap](https://pypi.org/project/pytreemap/)。

## &sect;5 leetcode

### 242. 有效的字母异位词

#### 题目：

给定两个字符串 s 和 t ，编写一个函数来判断 t 是否是 s 的字母异位词。

示例 1:

    输入: s = "anagram", t = "nagaram"
    输出: true

示例 2:

    输入: s = "rat", t = "car"
    输出: false

说明:
你可以假设字符串只包含小写字母。

#### 解答：

两种方法：

1. 字符串排序，然后比较排序后的字符串是否相等。快排：O(nlogn)

```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        return sorted(s) == sorted(t)
```

2. 用字典记录每个单词中出现字母和该字母出现的次数，然后比较两个字典是否相等。哈希：O(n)


```python
class Solution:
    def isAnagram(self, s: str, t: str) -> bool:
        dic1, dic2 = dict(), dict()
        for item in s:
            dic1[item] = dic1.get(item, 0) + 1
        for item in t:
            dic2[item] = dic2.get(item, 0) + 1
        return dic1 == dic2
```
    




