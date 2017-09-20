> # Linux 常用命令

##### 1. cd -可以在最近工作的两个目录间切换
``` linux
cd desktop
```
##### 2. pwd 输出当前工作目录
##### 3. ls  列出目标目录中所有的子目录和文件
``` linux
ls -a 列出目录下的所有文件，包括以 . 开头的隐含文件
```
##### 4. mkdir 创建文件夹
``` linux
mkdir ~/temp 在home目录下创建一个名为temp的目录
```
##### 5. rm 删除文件
``` linux
rm -r example 递归删除文件夹下所有文件，并删除该文件夹
```
##### 6. cp 拷贝文件
``` linux
cp -p file1 file2 拷贝文件1到文件2，并保持文件的权限、属主和时间戳
cp -i file1 file2 拷贝file1到file2，如果file2存在会提示是否覆盖
```
##### 7. mv 重命名文件
``` linux
mv -i file1 file2 将文件名file1重命名为file2，如果file2存在则提示是否覆盖
```
##### 8. cat 查看文件内容