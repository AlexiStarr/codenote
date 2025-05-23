### 介绍
bitset 是 C++ 标准库中的一个类，主要用于处理位集合（bit set）。它提供了简单的方法来创建和操作固定大小的位序列。bitset 可以用于高效地存储和操作二进制信息，比如布尔值。
### 基本用法
- 需要包含头文件
  ```
  #include <bitset>
  #include <iostream>
  ```
- 基本操作
  - 创建和初始化
    ```
    std::bitset<8> b1; // 创建一个大小为 8 的 bitset，初始值为 0  
    std::bitset<8> b2(42); // 使用整数初始化 bitset，42 的二进制表示为 00101010  
    std::bitset<8> b3("11001100"); // 使用二进制字符串初始化 bitset  
    ```
  - 设置、翻转位
    ```
    b1.set(0);       // 设置第 0 位为 1  
    b1.set(1, 0);    // 设置第 1 位为 0  
    b1.flip(2);      // 翻转第 2 位
    ```
  - 访问、检查位
    ```
    bool bit = b2[3]; // 访问第 3 位  
    if (b2.test(2)) { // 查询第 2 位是否为 1  
        std::cout << "第 2 位是 1" << std::endl;  
    }  
    ```
  - 大小和计数
    ```
    std::cout << "总位数: " << b2.size() << std::endl; // 输出总位数  
    std::cout << "1 的个数: " << b2.count() << std::endl; // 输出 1 的个数  
    ```
  - 清空所有位
    ```
    b1.reset(); // 将所有位设置为 0  
    ```
  - 将bitset转换为无符号整数
    ```
    cin >> s;
    bitset<8> bits(s);
    unsigned long num = bits.to_ulong();
    ```
