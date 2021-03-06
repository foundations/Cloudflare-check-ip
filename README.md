# CF自选节点
通过脚本选取当前地点最优的clouddflare cdn节点
本项目由`@犯罪高手` 制作，有`Windows` `Linux`双版本
## Windows
#### 使用方法
##### 推荐使用半自动方式查找

**可以发给不同地区的网站用户帮忙进行测速**

* 执行`1-自动查找100个丢包最少的IP.bat`
设置对`IP`丢包测试`PING`的次数，默认`100`次，可手动设定，推荐`50`次以上。运行完毕后命令行窗口会自动关闭再进行下一步操作<br>
* 执行`2-对100个丢包最少的IP测速.bat`
此过程是利用`curl`下载托管于cloudflare的大文件，默认每个`IP`下载时间为 10 秒钟。下载结束后到`temp`文件夹根据文件大小排序查看下载文件的大小。文件越大，代表单位时间内传输的数据越多，速度就越快。其中文件名是以`IP`地址的名称命名的。如果想要对`IP`单线程测速，可参考第三步。如果第三步找不到好用的`IP`，可重新执行第二步，再此完整测速分析<br>
* 执行`3-单IP测速.bat`输入第二步筛选出来的`IP`地址，回车后进行文件下载速度测试<br>

###### 如果觉得上述过程过于繁琐 请参照最后一步<br>
* 懒人版全自动处理 执行`自动查找最优CF节点-懒人专用.bat`等待运行完毕后自动弹出`IP`速度从大到小的排名文本文件 该测试的结果不一定能达到预期的效果，等待执行完成，会输出一个`速度排行.txt`，那个第一个`ip`即为最优`ip`

## Linux
**需要`curl`支持**

0. 下载未编译的`源码`
1. 解压`fping-4.2.tar.gz`
2. 执行`./configure`
3. 执行`make`
4. 进入`/src`目录执行`./cf.sh`
等待执行完成，会输出一个`ip.txt`，那个文件数值最大的即为最优`ip`

### 本项目实时更新
