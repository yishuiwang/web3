默克尔树最早由 Merkle Ralf 在 1980 年提出，曾广泛用于文件系统和 P2P 系统中。

其主要特点为：

- 最下面的叶节点包含存储数据或其哈希值；
- 非叶子节点（包括中间节点和根节点）都是它的两个孩子节点内容的哈希值。

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8a343b86-3c21-4ea2-a85c-1468f2d5b98d/73a08bb3-ff22-406c-a81e-424bcd9a8c6e/image.png)

如果 D1 中数据被修改，会影响到 N1，N4 和 Root。因此，一旦发现某个节点如 Root 的数值发生变化，沿着 Root --> N4 --> N1，最多通过 O(lgN) 时间即可快速定位到实际发生改变的数据块 D1。

# **Bloom Filter 布隆过滤器**

布隆过滤器是一种基于 Hash 的高效查找结构，能够快速（常数时间内）回答“某个元素是否在一个集合内”的问题。

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8a343b86-3c21-4ea2-a85c-1468f2d5b98d/85eb3f00-98d6-430d-a9bc-59cace5d2cc7/image.png)

对同一个给定输入来说，多个 Hash 函数计算出多个地址，分别在位串的这些地址上标记为 1。在查找时，进行同样的计算过程，并查看对应元素，如果都为 1，则说明较大概率是存在该输入。
