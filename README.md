# Note
a note in alibaba


### 提取rpm包
* 如下命令，不用安装，直接列出所有的文件
```
  rpm2cpio test.rpm  | cpio -div
```
* 提取debuginfo
```
  objcopy --only-keep-debug test test.debug
```
* 删除debug相关段
```
  strip -g test
```
* 添加debug link
```
  objcopy --add-gnu-debuglink=test.debug test
```

### 参考
* [Debugging Information in Separate Files](https://sourceware.org/gdb/onlinedocs/gdb/Separate-Debug-Files.html)
* [ELF格式文件符号表分析](http://guizhongyun.elastos.org/2013/03/27/elf%E6%A0%BC%E5%BC%8F%E6%96%87%E4%BB%B6%E7%AC%A6%E5%8F%B7%E8%A1%A8%E5%88%86%E6%9E%90/)
