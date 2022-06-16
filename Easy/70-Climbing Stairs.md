

You are climbing a staircase. It takes n steps to reach the top.

Each time you can either climb 1 or 2 steps. In how many distinct ways can you climb to the top?

 

Example 1:
```
Input: n = 2
Output: 2
Explanation: There are two ways to climb to the top.
1. 1 step + 1 step
2. 2 steps
```


My Code:
```
impl Solution {
  pub fn climb_stairs(n: i32) -> i32 {
    let mut sum_nums:u128 = 0;
    let mut two_nums:u128 = (n/2) as u128;
    let mut one_nums:u128 = (n%2) as u128;


    let mut up:u128 = 1;
    let mut down:u128 = 1;

    while two_nums > 0{
      up = 1;
      down = 1;
      for count in 0..two_nums{
        up *= (two_nums+one_nums - count);
        down *= (count+1);
      }
      sum_nums += (up/down);

      two_nums -= 1;
      one_nums += 2;
    }

    sum_nums+=1;
    sum_nums as i32

  }
}
```
