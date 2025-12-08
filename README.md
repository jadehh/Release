#  Jade Tools C++ 工具合集 
## 更新时间 
2025-12-08 14:10:45 
# 更新日志

## v2.1.0
* 解密支持解密到内存中, 新增decryptDataToMemory方法
* 取消JCryptoUtilsFactory的工厂模式，直接使用JCryptoUtils的instance方法构造，方便调用,key和iv参数改为const std::string&类型
* 新增随机字符串生成函数jade::j_string::random, 用于生成随机字符串
---