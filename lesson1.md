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
contract SimpleStorage
```

--

## 状态变量
```
uint storedData;
```

--

## 合约方法

```
    function set(uint x) {
        storedData = x;
    }

    function get() constant returns (uint) {
        return storedData;
    }
```

---

## 背景介绍

* 传统的员工系统<!-- .element: class="fragment" -->

---

## 目标

1. 薪水将全部基于以太币 <!-- .element: class="fragment" -->
2. 每30天发放一次 <!-- .element: class="fragment" -->

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

* balance
* transfer
* send
* call, callcode and delegatecall

---

## 目标

1. 薪水将全部基于以太币
  * unint salary <!-- .element: class="fragment" -->
  * address frank <!-- .element: class="fragment" -->
2. 每30天发放一次
  * unit payDuration <!-- .element: class="fragment" -->
  * unit lastPayday <!-- .element: class="fragment" -->

---

## 问题

如何发放薪水

* 定时器？<!-- .element: class="fragment" -->
* 老董每月通过合约给Frank打钱？<!-- .element: class="fragment" -->
* 如何防止老董拖欠Frank工资 <!-- .element: class="fragment" -->
* 在合约上存钱，Frank在每30天领取薪水<!-- .element: class="fragment" -->
  * function addFund
  * function calculateRunway
  * function hasEnoughFund
  * function getPaid

---

##  通用

*  `address frank` -> `address employee`
* function updateEmployee

