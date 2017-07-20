# Qt 学习笔记

- 路径不要用中文。
- Windows环境 MinGW编译
  1. 进入 Qt 自己的命令行工具，后进入源码文件夹。
  2. qmake -project "QT += widgets"  #生成 .pro 后缀文件（平台无关文件的项目文件）
  3. qmake #生成 Makefile 文件，与平台相关的构建文件。可通过 qmake 及其相关参数 来转换工程文件成其它工程文件。
  4. mingw32-make
- Mac、Linux环境 编译
  1. qmake -project "QT += widgets"
  2. qmake
  3. make
- 