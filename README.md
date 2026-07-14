#  Jade Tools C++ 工具合集 
## 更新时间 
2026-07-14 09:27:37 
# 更新日志

## v2.5.2

* 新增JStringProcesser的removeChars方法, 用于删除字符串中的指定字符, 用于删除版本号中的V字符
* 修改JStringProcesser的versionToInt方法, 用于将版本号转换为整数, 用于比较版本号,异常情况返回0, 用于处理无效的版本号字符串
* 优化相机异常的日志输出
* 解决在Ascend上相机重连的bug,是Aclite库的问题,需要升级到最新版本

---