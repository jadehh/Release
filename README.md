#  Jade Tools C++ 工具合集 
## 更新时间 
2025-12-03 10:58:49 
# 更新日志

## v2.0.9
* 统一定义SOCKET_TYPE, 不同平台下的socket类型不同, 如Windows下区分32位和64位
* 新增jade::opencv::utils::handleOpencvError函数, 用于处理Opencv的错误, 并打印错误信息到日志中
---