---
layout: inner
title: 'String -- Leetcode'
date: 2016-09-01 13:26:34
categories: blog development
tags: leetcode string algorithm
lead_text: 'All solutions and reviews about string exercises on leetcode'
---

344. Reverse String  QuestionEditorial Solution  My Submissions
Total Accepted: 72892
Total Submissions: 124678
Difficulty: Easy
Write a function that takes a string as input and returns the string reversed.

Example:
Given s = "hello", return "olleh".
	
```
// Basic run time: 100ms
var reverseString = function(s) {
    var arr = s.split(""),
        len = arr.length,
        result = '';

    for (var i = arr.length - 1; i >= 0; i--) {
      result += arr[i];
    }

    return result;
};

console.log(reverseString('hello'));	

// run time: 104ms
var reverseString = function(s) {
    var result = "";
  
    for(var i=s.length-1; i>=0; i--) {
      result += s[i];
    }
  
    return result;
};

console.log(reverseString("hello"));
	
// run time: 88ms
var reverseString = function(s) {
var arr = s.split(""),
    len = arr.length;

for (var i = 0, max = (len - 1) / 2; i < max; i++) {
  var temp = arr[i];
      arr[i] = arr[len - 1 - i];
      arr[len - 1 - i] = temp;
}

return arr.join("");
};

console.log(reverseString('hello'));
```

242. Valid Anagram  QuestionEditorial Solution  My Submissions
Total Accepted: 102563
Total Submissions: 236093
Difficulty: Easy
Given two strings s and t, write a function to determine if t is an anagram of s.

For example,
s = "anagram", t = "nagaram", return true.
s = "rat", t = "car", return false.

Note:
You may assume the string contains only lowercase alphabets.

Follow up:
What if the inputs contain unicode characters? How would you adapt your solution to such case?

```
// run time: 96ms
var isAnagram = function(s, t) {
    
    if (s.length !== t.length) {
      return false;
    }

    var str1 = s.split("").sort().join("");
    var str2 = t.split("").sort().join("");

    return str1 === str2;
};

console.log(isAnagram("anagrah", "nagaram"));
```

290. Word Pattern

Given a pattern and a string str, find if str follows the same pattern.

Here follow means a full match, such that there is a bijection between a letter in pattern and a non-empty word in str.

Examples:
pattern = "abba", str = "dog cat cat dog" should return true.
pattern = "abba", str = "dog cat cat fish" should return false.
pattern = "aaaa", str = "dog cat cat dog" should return false.
pattern = "abba", str = "dog dog dog dog" should return false.
Notes:
You may assume pattern contains only lowercase letters, and str contains lowercase letters separated by a single space.



                                                                       165. Compare Version Numbers                                     ```
/**
 * @param {string} version1
 * @param {string} version2
 * @return {number}
 */
var compareVersion = function(version1, version2) {
    var s1 = version1.toString(),
        s2 = version2.toString();
  
    var num1 = parseInt(s1.slice(0, s1.indexOf('.'))),
        num2 = parseInt(s2.slice(0, s2.indexOf('.')));
  
    if(num1 > num2 ) return 1;
  
    if(num1 < num2) return -1;
  
    if(num1 == num2) {
      var pose1 = parseInt(s1.slice(s1.indexOf('.') + 1)),
          pose2 = parseInt(s2.slice(s2.indexOf('.') + 1));
      
      if(pose1 > pose2) {
        return 1;
      } else if (pose1 < pose2) {
        return -1;
      } else {
        return 0;
      }
    }
                        
};

console.log(compareVersion(2.1, 1.1));
```                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                    



6. ZigZag Conversion


28. Implement strStr() 