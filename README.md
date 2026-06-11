#  Jade Tools C++ 工具合集 
## 更新时间 
2026-06-11 10:44:45 
# 更新日志

## v2.4.9

* 修复Ascend初始化问题
* 修复Sqlite3Cleaner 无法停止运行的问题
* 修复VencVideoWriter无法录制第二个视频的bug
* VencVideoWriter使用硬编码,结合H264VideoWriter写入mp4文件,解决播放器无法播放的bug,将h264裸流,转换为mp4文件,浏览器可以直接播放
* Venc由于不支持多线程,所以现在还是恢复到NV12VideoWriter使用CPU进行解码
* JStringProcesser支持按照指定字符切割字符串, 用于解析字符串中的多个字段
* 使用VencEncoder作为进程编码图片后,再用H264VideoWriter写入mp4文件,解决VENC无法再多线程中创建的bug,使用多进程操作
* ImageSender 与 VencEncoder 进程通信, 用于发送图片数据, 与 VencEncoder 进程通信, 用于接收处理结果
* 使用Opencv进行CPU录制的时候,使用avi格式,降低CPU占用,但是这样会导致视频文件的大小增加, 浏览器上也无法直接播放
* 修复corrupted size vs. prev_size的问题

---