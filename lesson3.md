# 第三课

### 支持多人的员工系统(二)

@老董区块链干货铺

---

## 如何减少gas的消耗?

---

## Mapping

* key (bool, int, address, string) <!-- .element: class="fragment" -->
* value (任何类型) <!-- .element: class="fragment" -->
* mapping(address => Employee) employees <!-- .element: class="fragment" -->
* keccak256hash <!-- .element: class="fragment" -->
* employees[key] = value <!-- .element: class="fragment" -->

---

## 可视度

* public <!-- .element: class="fragment" -->
* external <!-- .element: class="fragment" -->
* internal <!-- .element: class="fragment" -->
* private <!-- .element: class="fragment" -->

--

区块链上所有的信息都是公开可见的！

区块链上所有的信息都是公开可见的！

区块链上所有的信息都是公开可见的！

--

* 状态变量: public, internal, private <!-- .element: class="fragment" -->
  * 默认internal <!-- .element: class="fragment" -->
  * public: 取值方程 <!-- .element: class="fragment" -->
* 方程 public, external, internal, private <!-- .element: class="fragment" -->
  * 默认public <!-- .element: class="fragment" -->

---

## 继承

```
pragma solidity ^0.4.0;

contract owned {
    function owned() { owner = msg.sender; }
    address owner;
}

contract mortal is owned {
    function kill() {
        if (msg.sender == owner) selfdestruct(owner);
    }
}

contract Base1 is mortal {
    function kill() { /* do cleanup 1 */ super.kill(); }
}


contract Base2 is mortal {
    function kill() { /* do cleanup 2 */ super.kill(); }
}


contract Final is Base1, Base2 {
}
```
 <!-- .element: class="fragment" -->

---

```
pragma solidity ^0.4.0;

contract C {
    uint private data;

    function f(uint a) private returns(uint b) { return a + 1; }
    function setData(uint a) { data = a; }
    function getData() public returns(uint) { return data; }
    function compute(uint a, uint b) internal returns (uint) { return a+b; }
}


contract D {
    function readData() {
        C c = new C();
        uint local = c.f(7); // 错误
        c.setData(3);
        local = c.getData();
        local = c.compute(3, 5); // 错误
    }
}


contract E is C {
    function g() {
        uint val = compute(3, 5);  // 正确
    }
}
```

---

## 回顾

--

## Mapping

* mapping(address => Employee) employees
* employees[key] = value

--

## 可视度

* public
* external
* internal
* private
* 取值方程

--

## 功能

* 继承
* modifier
* library
  * zeppelin

--

## 其他

* 命名返回参数
