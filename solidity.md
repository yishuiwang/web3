Solidity

基础数据类型

```jsx
// SPDX-License-Identifier: MIT
pragma solidity ^0.8.0;

contract BasicDataTypes {
    // 布尔类型
    bool public isActive = true;

    // 整数类型
    int public signedInt = -42;
    uint public unsignedInt = 42;

    // 地址类型
    address public owner;
    address payable public wallet;

    // 固定长度字节数组
    bytes32 public fixedData = "Hello, Solidity!";

    // 动态字节数组和字符串
    bytes public dynamicData = "Dynamic";
    string public greeting = "Hello, World!";

    // 定长数组
    uint[3] public fixedArray = [1, 2, 3];

    // 动态数组
    uint[] public dynamicArray;

    // 枚举类型
    enum State { Inactive, Active, Paused }
    State public currentState;

    // 结构体
    struct Book {
        string title;
        string author;
        uint256 copies;
    }
    Book public myBook;

    // 构造函数
    constructor() {
        owner = msg.sender;
        wallet = payable(msg.sender);
        currentState = State.Inactive;
        myBook = Book("Solidity 101", "Alice", 5);
    }

    // 添加到动态数组
    function addToArray(uint _value) public {
        dynamicArray.push(_value);
    }

    // 改变状态
    function changeState(State _newState) public {
        currentState = _newState;
    }
}

```

关键词区别

![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8a343b86-3c21-4ea2-a85c-1468f2d5b98d/d74c0bab-edd5-4ed9-bea3-d512f8baf005/image.png)
