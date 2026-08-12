#  Jade Tools C++ 工具合集 
## 更新时间 
2026-08-12 16:44:12 
# 更新日志


## v2.5.4

* health接口自定义参数,支持用来显示更新时间
* 更新日志模块支持多个Logger实例
* 优化console日志输出的颜色
* EIO连接支持手动连接,定义打开和关闭的方法，回调直接返回所有的状态
* 修复手动打开第二次无法监听的bug
* 解决华为小站视频录制内存溢出的问题
* 删除Ascend上不必要的代码
* 新增Copy方法, 用于复制文件或目录到指定路径
* 修复CRITICAL日志级别程序不退出的bug
* 优化Ascend资源释放的方式, 避免资源泄漏的问题
* 优化Modbus的重连机制,重连时,先关闭当前连接,再重新打开连接,避免连接失败,导致资源泄漏的问题
* compress方法如果压缩后的宽度大于768,强行设置为768, 避免图像宽度超过最大限制,高度也相同比例缩放
* JImage支持返回Context和ImageProc
* 优化crop函数,优化裁剪逻辑,避免重新创建ImageProc对象
* Image Read 才需要创建ImageProc对象,其他操作都直接使用ImageProc对象即可
* 修复HaspAdapter的info内存泄漏问题
* Ascend read Image 需要自动释放ImageProc和Context
* health接口支持显示更新时间和版本号,以及启动时间

---