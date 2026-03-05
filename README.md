#  Inference C++ 推理框架 
## 更新时间 
2026-03-05 23:38:56 
# 更新日志
## v1.0.7
* 单例模式使用局部静态变量,避免了多线程环境下的线程安全问题
* NVLogger使用代理模式, The logger passed into createInferRuntime differs from one already provided for an existing builder, runtime, or refitter. Uses of the global logger, returned by nvinfer1::getLogger(), will return the existing value.
* 更改Tensorrt Inference 析构函数的释放顺序,先释放推理上下文,然后释放引擎,最后释放运行时
* 解决预处理存在的显存和内存泄漏的bug,std和mean只需要初始化一次,不需要在推理前每次初始化
* 优化Inference库日志输出
* 只有在主线程中构建模型的时候,才能退出,其他的在线程中无法退出,只能返回false,给主线程处理
* 代码项目结构重构
* NNRtRTInference 类,支持CPU上的图像推理
----