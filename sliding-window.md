---
description: Used or arrays & buffers
---

# Sliding Window

This technique is used to create a certain window size of a large buffer or array.  Window usually starts from the first element and keeps moving right by one element.

Example problem: Given a string `s`, find the length of the **longest substring** without repeating characters.  

```javascript
var lengthOfLongestSubstring = function(s) {
    const n = s.length;
    const characters = new Set()
    let ans = 0
    let i = 0
    let j = 0
    while(i<n && j<n) {
        if(!characters.has(s.charAt(j))) {
            characters.add(s.charAt(j++))
            ans = Math.max(ans, j - i)
        } else {
            characters.delete(s.charAt(i++))
        }
    }
    return ans
};
```

Here `i` keeps track of the left side of the window where as `j` has the right.  We start from `i = j` , and then slide `j` to the right.  In the meantime, we store all characters -that are not already- in the `chararacters` set.  This is done until \[j\] is the set.  Now we have the longest substring with index i. Once we do this for all i, we have our answer.

