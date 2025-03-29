## 二叉树
### 二叉树的种类
- 满二叉树
    ![image](https://github.com/user-attachments/assets/8f4a25c3-6ecb-452d-9f06-20db0499cc23)
- 完全二叉树（集中在左边 , 且除了最后一层全部填满）
    ![image](https://github.com/user-attachments/assets/c5f420c8-02cc-40d8-a00f-ed450332855f)
- 二叉搜索树
- 平衡二叉搜索树
  
      左右两个子树的高度差的绝对值不超过1 ，且左右两子树都是二叉搜索树。
      C++中map、set、multimap，multiset的底层实现都是平衡二叉搜索树，所以map、set的增删操作时间时间复杂度是logn。
      注意unordered_map、unordered_set底层实现是哈希表。
### 二叉树的存储
- 链式存储（链表）
- 顺序存储（数组）
### 二叉树的遍历
- 深度优先
    - 前序（递归 ，迭代）根左右
    - 中序（递归 ，迭代）左根右
    - 后序（递归 ，迭代）左右根
      ![image](https://github.com/user-attachments/assets/875062bf-be7c-48e3-b77a-cbe44e00c7f1)
- 广度优先
    - 层序（迭代）
        - 因为层序的递归其实是通过dfs标层数实现的，本质上还是dfs
### 二叉树的定义
```
struct TreeNode{
    int val;
    TreeNode* left;
    TreeNode* right;
    TreeNode(int x) : val(x) , left(NULL) , right(NULL){}
}
```


