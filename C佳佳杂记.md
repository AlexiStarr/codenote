- C++ 代码 面对大量数据 读取 输出作，最好用scanf 和 printf，耗时会小很多
- scanf 返回值
  
      scanf 函数返回成功读取的输入项的数量：
          如果成功读取两个整数，则返回 2。
          如果没有读取任何有效的输入（例如，用户输入格式错误），则返回 0。
          如果发生其他错误（比如文件结束），则可能返回 EOF，通常是 -1。
      按位取反 ~
          按位取反运算符 ~ 对返回值进行按位取反的效果如下：
          当 scanf 成功读取两个整数时：
              返回值 2 经过取反后变为 ~2，这里的计算是 -3（在二进制下，2 为 0000 0010，取反后变为 1111 1101，即 -3）。
              -3 被视为真值，因此 while 循环继续执行。
          当 scanf 没有读取任何有效输入（返回 0）时：
              取反后的值为 ~0 变成 -1，也被视为真值，循环还会继续。
          当 scanf 遇到输入错误或者到达输入流的末尾返回 EOF（通常是 -1）时：
              取反后的值为 ~(-1) 变为 0，这使得 while 条件为假，从而退出循环。
      因此可用while(~scanf("%d",&a))来进行循环输入
- INT_MAX INT_MIN会用到头文件#include <climits>
- 求绝对值 x = abs();
- stl对于std::vector< bool>进行了模板特化，其行为和性能不如其它容器一致，应当避免使用。  
  可以适当替换为std::vector< char>，std::vector<uint8_t>, std::bitset。
- void *memset(void *str, int c, size_t n) 用于将一段内存区域设置为指定的值。(在清空内存区域或者为内存区域赋值时)
  ```
  void *memset(void *str, int c, size_t n)
  ```
  eg: memset(next, 0, sizeof(next)); // 将next数组初始化为nullptr
- lambda函数写法
  1. ![image](https://github.com/user-attachments/assets/d482aa76-6432-4e9b-bee7-a512b433b5ed)
     占用内存小 ，快
  3. ![image](https://github.com/user-attachments/assets/ec2b2917-df9d-47f7-aeb2-7e8208cadceb)
     占用内存大
  3. 


