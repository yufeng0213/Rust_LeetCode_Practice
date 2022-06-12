You own a Goal Parser that can interpret a string command. 

The command consists of an alphabet of "G", "()" and/or "(al)" in some order. 

The Goal Parser will interpret "G" as the string "G", "()" as the string "o", and "(al)" as the string "al". 

The interpreted strings are then concatenated in the original order.

Given the string command, return the Goal Parser's interpretation of command.

Example 1:
```
Input: command = "G()(al)"
Output: "Goal"
Explanation: The Goal Parser interprets the command as follows:
G -> G
() -> o
(al) -> al
The final concatenated result is "Goal".
```

My Code:
```
use std::str;
impl Solution {
    pub fn interpret(command: String) -> String {
        let my_bytes: Vec<u8> = command.into_bytes();
        let mut dstStr:Vec<u8> = Vec::new();
        let len = my_bytes.len();
        
        for mut index in 0..len{
            if my_bytes[index as usize] == 'G' as u8{
                dstStr.push('G' as u8);
            }else if my_bytes[index as usize] == '(' as u8 && my_bytes[index+1 as usize] == ')' as u8{
                dstStr.push('o' as u8);
            }else if my_bytes[index as usize] == '(' as u8 && my_bytes[index+1 as usize] == 'a' as u8{
                dstStr.push('a' as u8);
                dstStr.push('l' as u8);
            }else{
                
            }
        }
        
        let mut s = String::from_utf8_lossy(&dstStr);
        s.to_string()
    }
}
```
