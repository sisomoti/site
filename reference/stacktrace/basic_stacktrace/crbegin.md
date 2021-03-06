# crbegin
* stacktrace[meta header]
* std[meta namespace]
* basic_stacktrace[meta class]
* function[meta id-type]
* cpp23[meta cpp]

```cpp
const_reverse_iterator crbegin() const noexcept; // (1) C++23
```

## 概要
末尾の要素を指す読み取り専用逆順イテレータを取得する。


## 戻り値
```cpp
return reverse_iterator(cend());
```
* cend()[link cend.md]


## 例
```cpp example
#include <iostream>
#include <stacktrace>
#include <algorithm>

void g() {
  std::stacktrace st = std::stacktrace::current();
  std::for_each(st.crbegin(), st.crend(), [](const std::stacktrace_entry& x) {
    std::cout << x << std::endl;
  }):
}

void f() {
  g();
}

int main() {
  f();
}
```
* st.crbegin()[color ff0000]
* st.crend()[link crend.md]
* current()[link current.md]
* std::stacktrace_entry[link /reference/stacktrace/stacktrace_entry.md]

### 出力
```
main.cpp:17
main.cpp:13
main.cpp:6
```


## バージョン
### 言語
- C++23

### 処理系
- [Clang](/implementation.md#clang): ??
- [GCC](/implementation.md#gcc): ??
- [Visual C++](/implementation.md#visual_cpp): ??
