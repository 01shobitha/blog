---
layout: post
title: Solving Two Strings
published: true
permalink: /:title
---

You may find the link to the question [here][link-to-question].

Problem statement: Given two array of strings- a and b, for each pair of corresponding strings in the two arrays, check if a there is a string that is substring of both strings. If yes, Print "YES", else print "NO". 
Assuming the size of array is 'n', there should be n lines of output.

Example: 

    array a = ['ab', 'cd', 'ef']
    array b = ['af', 'ee', 'ef']

    The two strings in the first iteration are: 'ab' and 'af'. The substring 'a' is common.
    
    Second - 'cd' and 'ee'. No common substrings are present.

    Third - 'ef' and 'ef'. Here 'e' and 'f' are common subtrings.

    Hence the output will be: 

    YES
    NO
    YES

You can view other example from the link provided.

Here is my approach:

    Iterate through both arrays.
        For each string in array a, store the charecters in a set S.
        Set flag to false
        For each string in array b
            check if char is present in the set S.
            If yes, set flag to true and break
        If flag is true:
            print "YES"
        Else
            print "NO"

Here is the code snippet in C++ :

```c++
void CommonString(vector<string> a, vector<string> b)
{
    for(int i = 0; i < a.size(); ++i)
    {
        string str_a = a[i];
        string str_b = b[i];

        set<int>s;
        for(int j = 0; j < str_a.length(); ++j)
        {
            s.insert(str_a[j]);
        }

        bool is_substring = false;
        for(int j = 0; j < str_b.length(); ++j)
        {
            set<int>::iterator itr = s.find(str_b[j]); 
            if(itr != s.end())
            {
                is_substring = true;
                break;
            }
        }

        if(is_substring)
            cout<<"YES";

        else
            cout<<"NO";
        cout<<endl;
    }
}

```

[link-to-question]: https://www.hackerrank.com/challenges/two-strings/problem