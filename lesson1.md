# 第一课

### 简单的员工系统

@老董区块链干货铺

---

## Hello World智能合约

```
pragma solidity ^0.4.0;

contract SimpleStorage {
    uint storedData;

    function set(uint x) {
        storedData = x;
    }

    function get() constant returns (uint) {
        return storedData;
    }
}
```

--

## 程序版本

```
pragma solidity ^0.4.0;
```

--

## 合约声明

```
pragma solidity ^0.4.0;

contract SimpleStorage {
}
```

--

## 状态变量
```
pragma solidity ^0.4.0;

contract SimpleStorage {
    uint storedData;
}
```

--

## 合约方法

```
pragma solidity ^0.4.0;

contract SimpleStorage {
    uint storedData;

    function set(uint x) {
        storedData = x;
    }

    function get() constant returns (uint) {
        return storedData;
    }
}
```

---

## 背景介绍

* 传统的员工系统 <!-- .element: class="fragment" -->
* 问题 <!-- .element: class="fragment" -->
 * 成本 <!-- .element: class="fragment" -->
 * 信任（拖欠工资）<!-- .element: class="fragment" -->

---

## 目标

1. 高效低成本 <!-- .element: class="fragment" -->
2. 防止违约，拖欠工资 <!-- .element: class="fragment" -->

---

## 类型系统

静态类型<!-- .element: class="fragment" -->

--
## 布尔型bool

* true
* false
* 操作符
  * !
  * &&
  * ||
  * ==
  * !=

--
## 整型uint/int

* 操作符
  * 比较: `<=, <, ==, !=, >=, >`
  * 位操作： `&, |, ^,~,>>,<<`
  * 计算: `+, -, *, /, %, **`

--
## 地址address

* address.balance
* address.transfer(value)
* address.send(value)
* address.call, address.callcode and address.delegatecall

---

## 设计

1. 薪水将全部基于以太币 <!-- .element: class="fragment" -->
  * uint salary <!-- .element: class="fragment" -->
  * address frank <!-- .element: class="fragment" -->
2. 每30天发放一次 <!-- .element: class="fragment" -->
  * uint payDuration <!-- .element: class="fragment" -->
  * uint lastPayday <!-- .element: class="fragment" -->

---

## 全局变量

--

## Ether单位

* wei
* szabo = 10 ^ 12 wei
* finney = 10 ^ 15 wei
* ether = 10 ^ 18 wei

--

## 时间单位
* seconds
* minutes
* hours
* days
* weeks
* years

--
## 块

* block.blockhash(uint blockNumber) returns (bytes32)
* block.coinbase (address)
* block.difficulty (uint)
* block.gaslimit (uint)
* block.number (uint)
* block.timestamp (uint)
* now

--

## 消息

* msg.data
* msg.gas (uint)
* msg.sender (address)
* msg.sig
* msg.value (uint)

---

## 设计

如何发放薪水

* 定时器？<!-- .element: class="fragment" -->
* 老董每月通过合约给Frank打钱？<!-- .element: class="fragment" -->
* 如何防止老董拖欠Frank工资 <!-- .element: class="fragment" -->
* 在合约上存钱，Frank在每30天领取薪水<!-- .element: class="fragment" -->
  * function addFund <!-- .element: class="fragment" -->
  * function calculateRunway <!-- .element: class="fragment" -->
  * function hasEnoughFund <!-- .element: class="fragment" -->
  * function getPaid <!-- .element: class="fragment" -->

---

##  通用

*  `address frank` -> `address employee`
* function updateEmployee

---

## 回顾

--

## 合约的基本结构

* 程序版本
* contract声明
* 状态变量声明
* function 声明

--

## 类型系统

* bool
* uint/int
* address

--

## 全局变量

* Ether变量
* 时间变量
* block
* msg

--

## 关键词

* constant
* payable
* this
* revert

--

##  其他

* if
* 本地变量

---

## 延伸

可调整地址和薪水的员工系统