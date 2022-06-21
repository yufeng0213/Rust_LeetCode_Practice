Roman numerals are represented by seven different symbols: I, V, X, L, C, D and M.
```
Symbol       Value
I             1
V             5
X             10
L             50
C             100
D             500
M             1000

```
For example, 2 is written as II in Roman numeral, just two one's added together. 12 is written as XII, which is simply X + II. The number 27 is written as XXVII, which is XX + V + II.

Roman numerals are usually written largest to smallest from left to right. However, the numeral for four is not IIII. Instead, the number four is written as IV. Because the one is before the five we subtract it making four. The same principle applies to the number nine, which is written as IX. There are six instances where subtraction is used:

I can be placed before V (5) and X (10) to make 4 and 9. 
X can be placed before L (50) and C (100) to make 40 and 90. 
C can be placed before D (500) and M (1000) to make 400 and 900.
Given an integer, convert it to a roman numeral.



My Code:
```
impl Solution {
  pub fn int_to_roman(num: i32) -> String {
      let mut dstStr:String="".to_string();
      let mut srcnum = num;

      let mut thousands = srcnum / 1000;
      srcnum = srcnum % 1000;

      let mut hundreds = srcnum/100;
      srcnum = srcnum % 100;

      let mut tens = srcnum / 10;
      srcnum = srcnum %10;

      for index in 0..thousands{
        dstStr += "M";
      }

      match hundreds {
          0 => {},
          4 => {dstStr += "CD";},
          5 => {dstStr += "D";},
          9 => {dstStr += "CM"},
          other => {
            if hundreds<4{
              for index in 0..hundreds{
                dstStr += "C";
              }
            }else{
              dstStr += "D";
              for index in 5..hundreds{
                dstStr += "C";
              }
            }
          },
          NONE => {}
      }

      
      match tens {
        0 => {},
        4 => {dstStr += "XL";},
        5 => {dstStr += "L";},
        9 => {dstStr += "XC"},
        other => {
          if tens<4{
            for index in 0..tens{
              dstStr += "X";
            }
          }else{
            dstStr += "L";
            for index in 5..tens{
              dstStr += "X";
            }
          }
        },
        NONE => {}
    }


    match srcnum {
      0 => {},
      4 => {dstStr += "IV";},
      5 => {dstStr += "V";},
      9 => {dstStr += "IX"},
      other => {
        if srcnum<4{
          for index in 0..srcnum{
            dstStr += "I";
          }
        }else{
          dstStr += "V";
          for index in 5..srcnum{
            dstStr += "I";
          }
        }
      },
      NONE => {}
    }

      dstStr
  }
}

```
