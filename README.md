### 说明
在阿里的工作相关临时记录

------------------------

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

-------------

###临时两台机传送文件
* server
```
  nc -l 9898 >out.file
```
* client
```
  nc -n xx.xx.xx.xx 9898 < in.file
```

###实用命令查询替换
* 搜索本目录下所有包含xxxx的文件，列出文件名
```
  grep xxxx -rl ./
```
* 搜索本目录所有包含xxxx的文件，列出文件名和具体行（慢）
```
  grep xxxx -ri ./
```

* 替换本目录下所有文件中得xxx为yyy
```
  sed -i "s/xxx/yyy/g" `grep xxx -rl ./`
```
