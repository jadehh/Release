#  Jade Tools C++ 工具合集 
## 更新时间 
2025-12-23 18:03:03 
# 更新日志

## v2.1.8
* 新增添加图像检测框功能, 可以在图像中添加矩形框, 用于标识检测到的目标，支持Opencv图像和Ascend图像,返回结果统一返回jpeg内存,后续可以直接写入图像文件
* 升级Opencv到最新版本, Linux上修复Failed to write frame问题,但是在Windows版本还是存在这个问题,因为windows调用的是opencv_videoio_ffmpeg.dll,无法修改这个dll
---