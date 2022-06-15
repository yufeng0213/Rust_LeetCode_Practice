Implement strStr().

Given two strings needle and haystack, return the index of the first occurrence of needle in haystack, or -1 if needle is not part of haystack.

Clarification:

What should we return when needle is an empty string? This is a great question to ask during an interview.

For the purpose of this problem, we will return 0 when needle is an empty string. This is consistent to C's strstr() and Java's indexOf().

Example 1:

```
Input: haystack = "hello", needle = "ll"
Output: 2
```

My Code:

```
impl Solution {
  pub fn str_str(haystack: String, needle: String) -> i32 {
    if haystack.len() == 0  {
      return 0;
    }
    
    //let tempStr = needle.clone();
    let index = haystack.find(&needle);
    match index{
      Some(ind) => return  ind as i32,
      None => return -1
    }
    
  }
}
```
