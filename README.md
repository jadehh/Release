#  Jade Tools C++ 工具合集 
## 更新时间 
2025-12-09 16:26:48 
# 更新日志

## v2.1.1
* 新增JSharedMemoryFactory类, 用于创建JSharedMemory对象, 支持不同平台下的共享内存创建，注意Windows下是创建临时文件, 其他平台下是创建匿名共享内存
* 解决Sqlite3和SocketServer的异常退出事件
----