---
title: 9.Palindrome Number
tags: [Leetcode]

---

## 9.Palindrome Number
### Problem description
Given an integer x, return true if x is a palindrome, and false otherwise.

<hr>

When I saw this problem, I solved in roughly 5 mins. It's easy to do. And If you have good programming skills, maybe you can solve in 1 min.

### Solution
##### Complexity: O(n)
```cpp=
#include <string>
class Solution {
public:
    bool isPalindrome(int x) {
        string str = to_string(x);
        int len = str.size();
        bool ans = false;
        for(int i = 0 ; i < len; i++){
            if(str[i] == str[len - 1 - i]){
                ans = true;
                continue;
            }
            else{
                ans = false;
                break;
            }
        }
        return ans;
    }
};
```
![截圖 2024-12-19 中午12.08.12](https://hackmd.io/_uploads/By5rTfZSJe.png)
And I got 100% beats and 0ms. Hence, I think it's good enough.
If you have another better solution, leave your comment.

### Thinking process
At that time, the first step I think is convert the number into string. Otherwise, we cannot do any operation on Integer.

So, the first step I took was to convert it into a String. Meanwhile, I was thinking about how to get the last character.

Finally, I came up with the condition which is  

    if(str[i] == str[len - 1 - i])
so that I can compare the first character and the last.
If not equal, then we break the loop and return false, that it.

