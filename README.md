#  Jade Tools C++ 工具合集 
## 更新时间 
2025-12-23 23:04:56 
# 更新日志

## v2.1.7
* 注意编码方式,Opencv录制视频是MPEG-4编码, CPU占用率低, 但是压缩比不高, 生成的文件大小较大
* Ascend 使用ffmpeg录制，直接写入JPEG编码过后的视频文件, 避免了Ascend视频录制时, CPU占用率高的问题
* JFileProcessor新增writeBinary方法, 用于写入二进制数据到文件中
* Opencv 使用GPU编码,注意在低版本的Opencv中不支持GPU编码如4.3.0,还是需要放在CPU中编码存储视频文件
* 录制视频统一使用队列来做, 避免视频写入时, 出现视频卡顿的问题
* 最新的Opencv可以使用GPU encode的方法写入视频, 旧版本的Opencv只能回退到CPU方式写入视频
* 4.12.0 Opencv 支持GPU编码,但是写入视频文件失败, 提示错误信息为: `Error: Failed to write frame to file` 升级至最新的Opencv可以解决这个bug
* 使用GPU编码与CPU编码视频的区别，CPU编码视频文件大小较大, 压缩比不高, 而GPU编码视频文件大小较小, 压缩比较高, 减少磁盘占用空间
* j_file 创建文件夹支持按照日期删除过期文件夹,按照过期时间删除文件夹。
* j_time 新增isDateOlderThan方法, 用于判断日期是否过期, 支持自定义日期格式
* 新增添加图像检测框功能, 可以在图像中添加矩形框, 用于标识检测到的目标，支持Opencv图像和Ascend图像,返回结果统一返回jpeg内存,后续可以直接写入图像文件
* 升级Opencv到最新版本, Linux上修复Failed to write frame问题,但是在Windows版本还是存在这个问题,因为windows调用的是opencv_videoio_ffmpeg.dll,无法修改这个dll
* 修复在Cuda10上的bug
* 加速设备新增AUTO类型, 用于自动判断是否使用GPU加速,或NPU加速, 默认为AUTO, Rtsp流默认使用auto 类型.
* 视频重连线程,添加条件变量, 用于等待视频源重新连接, 避免线程无法退出的问题,导致内存泄漏
---