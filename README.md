#  Jade Tools C++ 工具合集 
## 更新时间 
2026-05-06 09:57:00 
# 更新日志

## v2.4.6

* 修复rand无法在linux上编译的问题
* Dockerfile 中CUDA11.8中严格按照计算能力编译
* 加密狗控制器,传参支持HaspAdapterDevice类型
* 新增字符串支持按照\n分隔, 用于解析配置文件中的多行字符串
* 退出信号使用Info日志级别, 用于提示用户程序退出信号
* 修改参数重连时间, 单位秒
* 新增getSectionParameters方法, 用于获取section中所有参数, 统一返回string类型, 客户端需要根据string类型,手动转换为int或long或bool或string类型
* 解决在32位系统上,图像无法clone的bug
* 定义一个Mat 数据转换成BGR格式的方法
* Json解析如果字符串为空,返回默认字符串
* JStringProcessor添加判断IPV4地址的方法
* 新增JFloatProcessor添加浮点数保留小数位数的方法
* CrashHandle支持返回crash dump文件路径
* 解决日志退出不正常的bug
* 奔溃不在处理日志文件，只返回crash dump文件路径
* JImage不能随便增加函数,不然需要重新编译Inference库,会导致虚表错误
* 分离ConvertBGR函数,使用单独的类来进行管理
* 修复Soap服务端,在Python端使用suds,不能被正常调用的问题,需要正确处理Host头,生成Wsdl Location地址
* 奔溃单例新增测试奔溃的函数
* 修复文件路径在Windows上,创建中文路径的问题
* jade::j_sqlite3::getInteger 默认返回-1
* Sqlite3Helper新增close方法, 用于关闭数据库连接
* 修复Sqlite3中int64_t类型, 无法正确绑定的问题
* Sqlite3数据使用强同步的方式
* 修复创建日期路径的bug
* 日志按照日期进行轮转

---