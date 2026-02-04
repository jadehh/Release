#  Jade Tools C++ 工具合集 
## 更新时间 
2026-02-04 09:02:29 
# 更新日志

## v2.1.9
* JLogger支持从字符串获取日志级别的方法, 可以根据字符串来设置日志级别, 方便在运行时动态设置日志级别
* 工厂代码内部不使用std::unique_ptr, 统一使用std::shared_ptr
* fix 日志关闭时，重复输出日志的bug
* fix 日志不初始化的报错,如果logger没有初始化, 则默认使用appName为App,不会写入日志文件
* 日志文件初始化的时候先关闭之前的日志文件, 避免日志文件重复输出
* j_string 添加字符串转大写的方法, 用于将字符串转换为大写, 方便在比较字符串时忽略大小写
* JIniReader支持直接返回RtspInfo对象, 方便在使用时直接获取相机的信息
* 调整ini_reader目录结构, 新增rz_ini_reader目录, 因为使用了rtsp_info,所以必须排在ini_reader目录后面
* 图像统一处理的回调函数新增user_data参数, 用于在回调函数中传递用户数据, 方便在回调函数中使用用户数据,图像抓拍的回调函数返回image使用指针, 方便在回调函数中使用图像, 防止出现图像被释放的情况
* 新增获取内存地址的方法, 用于获取对象的内存地址, 方便在调试时查看对象的内存地址,不使用模板创建,直接使用void*指针
* Ascend上支持多线程的图像保存,创建图像的时候都需要指定上下文,减少image_proc的创建次数,创建image的时候直接将image_proc传递进去
* Ascend上如果需要做图像处理需要转换成cv::Mat,转换之后的图像在转换成Ascend NPU上的图像,这里使用的是jpeg的编码方法,传统的NV12ToMat的效率要更高
* 保存图像统一使用线程保存,统一使用jpeg的图像编码格式,避免在主线程中保存图像,导致主线程阻塞
* 实现Rtsp协议中的用户名密码解密功能.传入的参数都是加密过后的字符串
* JCryptoUtil类新增字符串加密解密的方法,加密返回的是Base64编码的字符串,解密返回的是原始字符串,解密需要对先进行Base64解码,再进行解密
* 如果线程退出程序，需要通过主线程来请求退出程序, 否则会导致程序无法退出
* 测试h265的流在CUDA和Ascend上是否正常
* 华为小站可以自动切换H264和H265编码, 不需要手动切换编码
* 扩展JiniReader类, 新增从字符串获取RtspInfo对象的方法, 方便在使用时直接获取相机的信息
* Image的save方法更改参数统一使用const std::string&
* BaseConfig初始化时，创建路径, 确保路径存在, 否则创建失败
* JFileProcessor创建文件夹,创建失败如文件夹已存在,也返回true, 避免在创建文件夹时,因为文件夹已存在而导致创建失败,通过error_code来判断是否创建成功
* SafeQueue类新增clear方法和full方法, 用于清空队列和检查队列是否已满, 方便在使用时动态调整队列的大小,并且支持先进先出和后进先出两种模式
* jade::JImageFactory::destroy() ,1.5f销毁前需要判断图像保存的线程是否已经退出，如果没有线程没有完成，直接退出，会导致图像保存异常;
* JCommand类程序退出时,需要将所有执行的命令都退出,否则会导致程序退出时,命令还在执行,windows上输出中文
* JString 支持 gbk转utf-8方法
* 新增JBaseConfig父类,用于初始化配置文件,日志模块,崩溃处理模块,以及其他一些公共的配置,子类必须实现initConfig方法
* 所有种类的图像保存都使用可控的线程池
* CvCudaVideoCapture类,支持图像从BGRA格式转换为BGR格式
* 文本定位的结果,水平方向和垂直方向顺序不一样,所以需要先判断文本框是否垂直,垂直方向透视变化与水平方向不同,需要特殊处理,旋转了180度
* HaspAdapter 类不在使用默认的析构函数释放加密狗资源,必须使用手动调用stop方法释放加密狗资源
* JBaseConfig类新增getImageSaveDays和getVideoSaveDays方法, 用于获取图片保存天数和视频保存天数
* Image 调用save方法时,文件名可以没有后缀, 会自动添加后缀,强制添加后缀为jpg
* RtspInfo类支持本地视频文件, 可以直接使用本地视频文件来创建RtspInfo对象
* JadeVideoCapture类,判断是否为本地文件,如果是本地文件,需要模拟fps,否则会导致视频播放过快,影响测试
* JImageCrop类,还是根据宽高比将图像逆时针旋转90度
* 视频流地址如果是本地,getCameraInfo只返回相机名称
* Image类新增save方法, 用于保存图像,并可以返回保存路径,通过传参的方式返回,而不是通过返回值的方式返回
* Image类save方法只有info不为空时,才会打印正常日志
* 使用cpprestsdk库开发SOAP服务端, 可以接收SOAP请求,并返回SOAP响应，使用JHttpFactory创建，使用registerHandle的方法注册事件
* cpu和cuda版本支持modbus库, 可以在cpu和cuda版本中使用modbus库
* JHttpServer类导出,支持继承JHttpServer类,也支持使用JHttpFactory创建这个类
* cpprestSdk,Windows上无法监听所有IP,只能监听localhost,弃用,使用httplib库开发SOAP服务端
* 使用pugixml库解析WSDL文档, 可以方便地获取WSDL文档中的信息
* 由子类控制是否需要锁,确保同时只能处理一个请求,WebService不影响Get请求,Get请求可以并发处理
---