Given two strings s and t, return true if t is an anagram of s, and false otherwise.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 
 My Code:
 
 ```
 impl Solution {
  pub fn is_anagram(s: String, t: String) -> bool {
      let mut a = s.clone().as_bytes().to_vec();
      a.sort();
      let mut b = t.clone().as_bytes().to_vec();
      b.sort();

      if a == b{
        return true;
      }

      false
  }
}
 
 ```
