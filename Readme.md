# Webassembly
[w3c](https://www.w3.org/community/webassembly/); WebAssembly 是一门不同于 JavaScript 的语言，但是，它不是用来取代 JavaScript 的。相反，它被设计为和 JavaScript 一起协同工作，从而使得网络开发者能够利用两种语言的优势

## 关键概念
* 模块: 一个已经被浏览器编译为可执行机器码的 WebAssembly 二进制代码。
  * 模块是无状态的，并且像一个二进制大对象（Blob）一样.
  * 能够被缓存到 IndexedDB中或者在 windows 和 workers 之间进行共享（通过postMessage() (en-US)函数）
* 内存: ArrayBuffer，大小可变。
  * 本质上是连续的字节数组，WebAssembly 的低级内存存取指令可以对它进行读写操作。
* 表格: 带类型数组，大小可变。
  * 表格中的项存储了不能作为原始字节存储在内存里的对象的引用。
* 实例: 一个模块及其在运行时使用的所有状态，包括内存、表格和一系列导入值。
  * 一个实例就像一个已经被加载到一个拥有一组特定导入的特定的全局变量的 ES2015 模块。

## 安装
https://emscripten.org/docs/getting_started/downloads.html

## 使用
### 编译
```
  emcc hello.c
  emcc hello.c -o hello.html
  emcc hello_world_file.cpp -o hello.html --preload-file hello_world_file.txt
```
### 启动服务
```
  python3 -m http.server 8001
```