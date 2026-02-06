#  Inference C++ 推理框架 
## 更新时间 
2026-02-06 13:41:10 
# 更新日志

## v1.0.6
* 使用最新的jade_tools库,必须升级,因为更改了JTextBox库的接口改为了JQuad库
* 修改项目名称为inference
* 使用JInferenceUtils 转换void*指针,防止内存泄漏
* 模型转换日志输出只有在Trace级别下才会输出,其他级别下不会输出
* 修复如果AlgorithmConfig被外部释放,导致inference内部悬空指针问题
* 使用最新版本的jade_tools库,必须升级,因为更改了Logger库的接口
* Inference对外暴露模型构建(build)和模型初始化(init)的方法,build不支持多线程,init函数支持多线程
* NNRT Inference 模型加载失败,输出失败的原因,不在删除模型文件,支持一个线程中运行多个模型,解决了一个线程中只能运行一个模型的问题
* DBPostProcess 四个点的顺序是左上角,右上角,右下角,左下角，这四个点是按照顺时针方向排列的
----