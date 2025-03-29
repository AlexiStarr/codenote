## 特性
1. 内存空间地址连续
2. 数组元素不能删除只能覆盖，所谓的删除也只是将数组内所有元素前移而已
3. C++中二维数组在地址上的空间也是连续的
## 经典题目
- 二分法
  - 写法一 : 左闭右闭
     ```
      class Solution {
      public:
          int search(vector<int>& nums, int target) {
              int left = 0;
              int right = nums.size() - 1; // 定义target在左闭右闭的区间里，[left, right]
              while (left <= right) { // 当left==right，区间[left, right]依然有效，所以用 <=
                  int middle = left + ((right - left) / 2);// 防止溢出 等同于(left + right)/2
                  if (nums[middle] > target) {
                      right = middle - 1; // target 在左区间，所以[left, middle - 1]
                  } else if (nums[middle] < target) {
                      left = middle + 1; // target 在右区间，所以[middle + 1, right]
                  } else { // nums[middle] == target
                      return middle; // 数组中找到目标值，直接返回下标
                  }
              }
              // 未找到目标值
              return -1;
          }
      };
     ```
  - 写法二 ： 左闭右开   
    ```
      class Solution {
      public:
          int search(vector<int>& nums, int target) {
              int left = 0;
              int right = nums.size() - 1; // 定义target在左闭右闭的区间里，[left, right]
              while (left < right) { // 当left==right，区间[left, right]依然有效，所以用 <=
                  int middle = left + ((right - left) >> 1);// 防止溢出 等同于(left + right)/2
                  if (nums[middle] > target) {
                      right = middle; // target 在左区间，所以[left, middle - 1]
                  } else if (nums[middle] < target) {
                      left = middle + 1; // target 在右区间，所以[middle + 1, right]
                  } else { // nums[middle] == target
                      return middle; // 数组中找到目标值，直接返回下标
                  }
              }
              // 未找到目标值
              return -1;
          }
      };
     ```
    - 注意：直接使用 (left + right) / 2 可能会导致整数溢出，尤其是在 left 和 right 都很大的情况下。  
      例如，如果 left 和 right 都接近 INT_MAX（整型最大值），left + right 的结果可能会超过 INT_MAX，导致未定义行为或产生错误的索引。  
      通过先计算 right - left，然后再加上 left，可以有效避免这个问题。
- 双指针
  - 快慢指针（都是从头开始）
  - 对撞指针（头尾指针）
  - ***C++ 代码 面对大量数据 读取 输出操作，最好用scanf 和 printf，耗时会小很多***
- 滑动窗口
- 前缀和
- 模拟（螺旋矩阵）
