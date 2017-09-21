# 第二课

### 支持多人的员工系统

@老董区块链干货铺

---

## 延伸

可调整地址和薪水的员工系统

* address frank -> address employee <!-- .element: class="fragment" -->
* function updateEmployee <!-- .element: class="fragment" -->

---

## 错误检测

* assert(bool)
* require(bool)

---

## 目标

支持多人的员工系统

---

## 数组

* 固定长度 (uint[5] a) <!-- .element: class="fragment" -->
* 动态长度 (uint[] a) <!-- .element: class="fragment" -->
* 成员 <!-- .element: class="fragment" -->
 * length <!-- .element: class="fragment" -->
 * push <!-- .element: class="fragment" -->

---

## 设计

 * 通过数组来存储多个员工的信息
  * address[] employee <!-- .element: class="fragment" -->
  * uint[] salary <!-- .element: class="fragment" -->
  * uint[] lastPayday <!-- .element: class="fragment" -->

---

## struct

```
struct Employee {
  address id;
  uint salary;
  uint lastPayday;
}
```

---

## 设计

 * 通过数组来存储多个员工的信息
  * Employee[] employees <!-- .element: class="fragment" -->
  * function addEmployee <!-- .element: class="fragment" -->
  * function removeEmployee <!-- .element: class="fragment" -->

---

## 数据存储 Data Location

* storage
* memory
* calldata
* 强制 <!-- .element: class="fragment" -->
  * 状态变量: storage <!-- .element: class="fragment" -->
  * function输入参数: calldata <!-- .element: class="fragment" -->
* 默认 <!-- .element: class="fragment" -->
  * function返回参数: memory <!-- .element: class="fragment" -->
  * 本地变量: storage <!-- .element: class="fragment" -->

---

---

## 回顾

--

## 错误检测

* assert(bool)
* require(bool)

--

## 数组

* 固定长度 (uint[5] a)
* 动态长度 (uint[] a)
* 成员
 * length
 * push

--

## struct

```
struct Name {
}
```

--

## 数据存储 Data Location

* storage
* memory
* calldata
* 强制
  * 状态变量: storage
  * function输入参数: calldata
* 默认
  * function返回参数: memory
  * 本地变量: storage

--

## 语法

* for
* delete

--

## 其他

* 辅助function
* 可见度

---

## 延伸

如何减少gas的消耗?