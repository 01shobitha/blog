---
layout: post
title: Solving Two-Sum
published: true
permalink: /:title
---

You may find the link to the question [here][link-to-question].

Problem statement: Given an array of integers, return indices of the two numbers such that they add up to a specific target.

You may assume that each input would have exactly one solution, and you may not use the same element twice.

Example:
    
    Given array = [7, 11, 15,2] target = 9,

    Because array[0] + array[3] = 2 + 7 = 9,
    return [0, 3].

Another example:

    Given array = [3, 3], target = 6,

    Because array[0] + array[1] = 3 + 3 = 6,
    return [0, 1].


Lets consider our example array. 
What we can do is, iterate through the given array, find the difference between the given target and i-th element, and search that in the array. If the difference is present, then return the indices.

Since the bruteforce method will give a complexity of O(n²), we can think of a more efficient solution.

Here is the algorithm. 

    Create a map m.
    Create a vector v for storing the resulting indices.
    Loop through the given array.
        Find the difference: diff = target - array[i]\
        if diff is present in m:
            Append m[diff] to the vector v. m[diff] will give the index of second element.
            Append i to the vector v. i will give the index of first element.
            return the result vector v.
        else: if **diff** is not present in m
            insert into map the current element array[i] and i.


Here is the code snippet in C++:

```c++
vector<int> twoSum(vector<int>& a, int target) {
        
    vector<int> v;
    map<int,int> m;
    int difference;
    for(int i = 0; i < a.size(); ++i)
    {
        difference = target - a[i];
        if(m.find(difference) != m.end())
        {
            v.push_back(m[difference]);
            v.push_back(i);
            return v;
        }
        else
        {
            m.insert(pair<int,int>(a[i], i));
        } 
    }
    return v;
    }
```

Hope it helps.


[link-to-question]: https://leetcode.com/problems/two-sum/