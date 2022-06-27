Given an array of strings strs, group the anagrams together. You can return the answer in any order.

An Anagram is a word or phrase formed by rearranging the letters of a different word or phrase, typically using all the original letters exactly once.

 

Example 1:
```
Input: strs = ["eat","tea","tan","ate","nat","bat"]
Output: [["bat"],["nat","tan"],["ate","eat","tea"]]
```

My Code:
```
use std::collections::HashMap;
impl Solution {
  pub fn group_anagrams(strs: Vec<String>) -> Vec<Vec<String>> {
    let mut dstVec:Vec<Vec<String>> = Vec::new();

    if strs.len() == 0{
      return dstVec;
    }
    else if strs.len() == 1{
      dstVec.push(strs.clone());
      return dstVec;
    }

    let mut tempStrs = strs.clone();

    for index in 0..strs.len(){
      
      let mut tempbytes = tempStrs[index].clone().into_bytes();
      tempbytes.sort();
      let mut tempstr = std::str::from_utf8(&tempbytes).unwrap();
      tempStrs[index] = tempstr.to_string();
    }

    let mut tempHash:HashMap<String,usize> = HashMap::new();
    let mut cindex:usize = 0;
    for index in 0..strs.len(){
      let count = tempHash.entry(tempStrs[index].clone()).or_insert(cindex);
      //println!("{} {}",*count,cindex);
      if *count < cindex{
        dstVec[*count].push(strs[index].clone());
       
      }else{
        let mut tv:Vec<String>  = Vec::new();
        tv.push(strs[index].clone());

        dstVec.push(tv);
           cindex += 1;
      }
    }

    dstVec
  }
}
```


study other code 
```
use std::collections::HashMap;
impl Solution {
  pub fn group_anagrams(strs: Vec<String>) -> Vec<Vec<String>> {
 
    let mut ans:HashMap<String,Vec<String>> = HashMap::new();

    for str in strs{
      let mut tempbytes = str.as_bytes().to_owned();
      tempbytes.sort();
      let m = ans.entry(std::str::from_utf8(&tempbytes).unwrap().to_string()).or_insert(vec![]);
      m.push(str.clone());
    }

    ans.values().cloned().collect()
 
  }
}
```
