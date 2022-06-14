You have n boxes. You are given a binary string boxes of length n, where boxes[i] is '0' if the ith box is empty, and '1' if it contains one ball.

In one operation, you can move one ball from a box to an adjacent box. Box i is adjacent to box j if abs(i - j) == 1. 

Note that after doing so, there may be more than one ball in some boxes.

Return an array answer of size n, where answer[i] is the minimum number of operations needed to move all the balls to the ith box.

Each answer[i] is calculated considering the initial state of the boxes.


 Example 1:
```
Input: boxes = "110"
Output: [1,1,3]
Explanation: The answer for each box is as follows:
1) First box: you will have to move one ball from the second box to the first box in one operation.
2) Second box: you will have to move one ball from the first box to the second box in one operation.
3) Third box: you will have to move one ball from the first box to the third box in two operations, and move one ball from the second box to the third box in one operation.
```

My Code:
```
impl Solution {
  pub fn min_operations(boxes: String) -> Vec<i32> {
      let my_bytes = boxes.into_bytes();
      let lenA = my_bytes.len();
      let mut dstVec :  Vec<i32> = vec![0;lenA];
      let mut nums : i32 = 0;
      
      for i in 0..lenA{
            nums = 0;
          for index in 0..lenA{
              nums += (my_bytes[index] as i32 - 48)*((index - i) as i32).abs();
                
          }  
          dstVec[i] = nums;
      }

      dstVec
  }
}

```
