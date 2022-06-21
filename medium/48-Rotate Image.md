不知道为什么leetcode 网站进不去了，囧
那就先在leetcode.cn 这里记录下题目。

题目描述：

给定一个 *n *× n 的二维矩阵表示一个图像。

将图像顺时针旋转 90 度。


My Code:

```
impl Solution {
  pub fn rotate(matrix: &mut Vec<Vec<i32>>) {
    let mut n = matrix.len();
    let mut temp = matrix[0][0];
    let mut tempA = matrix[0][0];

    for row in 0..n/2{
      for col in row..n-row-1{
        // 1 -> 2
        temp = matrix[col][n-1-row];
        println!("1 -> 2 : {} -> {}",matrix[col][n-1-row],matrix[row][col]);
        matrix[col][n-1-row] = matrix[row][col];

        // 2 -> 3
        tempA = matrix[n-1-row][n-1-col];
        println!("2 -> 3 : {} -> {}",matrix[n-1-row][n-1-col],temp);
        matrix[n-1-row][n-1-col] = temp;
        
        // 3 -> 4
        temp = matrix[n-1-col][row];
        println!("3 -> 4 : {} -> {}",matrix[n-1-col][row],tempA);
        matrix[n-1-col][row] = tempA;

        // 4 -> 1
        println!("4 -> 1 : {} -> {}",matrix[row][col],temp);
        matrix[row][col] = temp;
      }
    }
  }
}
```
