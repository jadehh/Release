#  Jade Tools C++ 工具合集 
## 更新时间 
2026-02-14 00:50:44 
# 更新日志

## v2.2.0
* 修改JText_boxes为JQuad
* 指针优化,使用智能指针管理内存,避免内存泄漏
* JImageCrop和JImageDrawing 都不能在使用std::vector<void*>类型的数据,需要明确指定数据类型
* 单例模式全局使用静态局部变量, 避免多线程环境下的重复创建问题,和内存泄漏的问题
* IniReader支持获取Int数据类型
* 完全手动控制JImage类,需要手动调用release方法释放内存
* 解决CPU和Slim上的代码错误
* JImageFactory导出为动态库
* 更改jade_tools生成补办模板格式,jade_tools头文件删除不必要的include语句
* SharedMemoryFile 内存泄漏的问题解决
* 图像保存线程分离,不需要控制线程的生命周期, 可以在任意时间调用save方法保存图像
* Sqlite3Helper 新增绑定参数的方法, 用于绑定查询语句的参数, 避免SQL注入攻击
* Sqlite3Helper 新增查询方法, 用于查询数据库, 并返回查询结果
* JImageFactory创建Ascend Image时 image_proc和context优化
* 解决手动修改DB文件时候,出现空值的问题
* Sqlite3Helper新增一个安全取值的方法, 用于从Sqlite3Value中安全取值, 避免取值时出现空值的问题
* 解决查询时数据类型不一致的bug
* 确保取值的数据类型也一致
* 添加文件转base64的方法, 用于将文件内容转换为base64字符串, 方便在网络传输时使用
* 解决SoapServer的内存泄漏问题
* 如果录制视频过程变慢,手动清除队列中的数据, 避免队列满了导致内存溢出
* RtspInfo 支持设置GPU idID,解码的时候可以指定使用哪个GPU
* 规范Jtime的使用,新增std::time_t转字符串的方法, 用于将时间戳转换为时间字符串
* 最多支持毫秒级级别的时间字符串转换,支持字符串时间戳转换成std::time_t时间点
* JImage添加压缩的方法,用于改变图像的分辨率,达到压缩的目的。
* JImageFactory在Ascend上创建图像时,多线程安全, 可以在多个线程中同时创建图像
* 统一各种数据类型转换为字符串的方法, 方便在使用时直接调用toString方法, 避免记忆不同的转换方法
* 使用Path类管理所有的路径, 包括bin路径, config路径, log路径等
* 视频录制支持录制传参相机名称,返回相机名称和录制视频的路径
* 修复第二次视频录制无法录制的问题
---