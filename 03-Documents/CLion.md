## CLion Settings

本文记录了使用CLion编写C语言代码时，所遇到问题的一些解决方式。


## 初次使用

### 下载安装

1. 官网地址：[CLion - JetBrains](https://www.jetbrains.com/clion/)
2. 运行安装程序，一步一步安装至完成即可

> 注意：最新版的CLion中自带MinGW，所以不用再额外安装C语言的编译器


### 新建项目

1. 打开CLion，选择 `新建项目/New Project` 选项
2. 选择 `C 可执行文件/C Executable` 选项并创建
3. 项目的其他设置选择 **默认设置** 即可
4. 运行刚创建项目中的 `main.c` 文件

> 提示：能正常运行 `main.c` 文件，说明IDE已经可以正常使用了


### 安装插件

1. 双击键盘的 `Shift` 按键
2. 在弹出的搜索框中输入 `plugins` ，在结果中选择 `Manage plugins` 选项
3. 在插件管理页面，选择 `Marketplace` 选项卡
4. 在Marketplace的搜索框中，使用关键字查询想要安装的插件

以下为推荐安装的插件：
- [Chinese Language Pack](https://plugins.jetbrains.com/plugin/13710-chinese-simplified-language-pack----)
- [One Dark theme](https://plugins.jetbrains.com/plugin/11938-one-dark-theme)
- [C/C++ Single File Execution](https://plugins.jetbrains.com/plugin/8352-c-c--single-file-execution)


### 其他设置

1. 文件 -> 设置 -> 外观与行为 -> 外观：字体大小设置为 **`14`**
2. 文件 -> 设置 -> 按键映射：设置为 `Sublime Text`
3. 文件 -> 设置 -> 编辑器 -> 常规：勾选 `使用Ctrl + 鼠标滚轮更改字号`
4. 文件 -> 设置 -> 编辑器 -> 字体：大小设为 **`18`**
5. 文件 -> 设置 -> 编辑器 -> 文件和代码模板：删除 `include` -> `C File Header` 文件中的内容
    > 注意：不是删除 `C File Header` 文件，而是删除 `C File Header` 文件中的内容（删除整个文件后，后面每次新建c文件都会报错）


## 运行单个C文件

### 使用插件

1. 下载插件 `C/C++ Single File Execution`
    - 插件官网：[C/C++ Single File Execution](https://plugins.jetbrains.com/plugin/8352-c-c--single-file-execution)
2. 在文件中，右键选择 `Add executable for single c/c++ file` 即可
    - 快捷键： `Ctrl + Shift + Alt + E`

> 注意：Cmake项目还需要将文件添加到 `CMakeLists.txt` 中（CLion中会有提示）  
> 建议：先右键使用插件添加文件，然后再添加文件到 `CMakeLists.txt` 中


### CMakeLists.txt

初始的 `CMakeLists.txt` 文件内容备份

```cmake
cmake_minimum_required(VERSION 3.24)
project(C_Coding C)

set(CMAKE_C_STANDARD 11)

add_executable(C_Coding main.c)
```


