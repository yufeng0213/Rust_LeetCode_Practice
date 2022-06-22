
Given a string containing digits from 2-9 inclusive, return all possible letter combinations that the number could represent. Return the answer in any order.

A mapping of digits to letters (just like on the telephone buttons) is given below. Note that 1 does not map to any letters.


 
Example 1:
```
Input: digits = "23"
Output: ["ad","ae","af","bd","be","bf","cd","ce","cf"]
```

My Code:
```
use std::collections::VecDeque;
impl Solution {
  pub fn letter_combinations(digits: String) -> Vec<String> {
      
    let mut dstVec:Vec<String> = Vec::new();
    let len = digits.len();
    let my_bytes = digits.as_bytes();

    let mut tempVec : Vec<Vec<String>> = Vec::new();
    let vec2 : Vec<String> = vec!["a".to_string() ,"b".to_string(),"c".to_string()];
    tempVec.push(vec2);
    let vec3 : Vec<String> = vec!["d".to_string(),"e".to_string(),"f".to_string()];
    tempVec.push(vec3);
    let vec4 : Vec<String> = vec!["g".to_string(),"h".to_string(),"i".to_string()];
    tempVec.push(vec4);
    let vec5 : Vec<String> = vec!["j".to_string(),"k".to_string(),"l".to_string()];
    tempVec.push(vec5);
    let vec6 : Vec<String> = vec!["m".to_string(),"n".to_string(),"o".to_string()];
    tempVec.push(vec6);
    let vec7 : Vec<String> = vec!["p".to_string(),"q".to_string(),"r".to_string(),"s".to_string()];
    tempVec.push(vec7);
    let vec8 : Vec<String> = vec!["t".to_string(),"u".to_string(),"v".to_string()];
    tempVec.push(vec8);
    let vec9 : Vec<String> = vec!["w".to_string(),"x".to_string(),"y".to_string(),"z".to_string()];
    tempVec.push(vec9);

    let mut vd:VecDeque<String> = VecDeque::new();


    for &index in my_bytes {
      if index < '2' as u8 || index > '9' as u8{
        continue;
      }
      
      if vd.is_empty(){
        for ind in &tempVec[(index - '0' as u8) as usize - 2]{
          vd.push_back(ind.clone());
        }

        continue;
      }

      let mut size = vd.len();
      
      while size>0{
        let op = vd.pop_front().unwrap().clone();
        for ind in &tempVec[(index - '0' as u8) as usize - 2]{
          let strA = op.clone() + &ind;
          vd.push_back(strA);
        }
        size -=1;
      }
    }

    while !vd.is_empty(){
      dstVec.push(vd.pop_front().unwrap());
    }

    dstVec
  }
}


```
