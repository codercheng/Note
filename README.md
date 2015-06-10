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
