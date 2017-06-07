# BoostTcpServerTest
1.需要配合boost的asio使用
    教程：
        1).安装boost 添加环境变量
            添加 BoostDir = C:\czlin\dep\boost_1_64_0
        2).编译asio库 进入 BoostDir 运行bootstrap 生成  bjam b2
            命令 bjam --with-system --with-thread --with-date_time --with-regex --with-serialization stage
        3).给使用工程 项目 属性 c/c++ 常规 附加包含目录
            添加 $(BoostDir)
        4).给使用工程 项目 属性 链接器 常规  附加库目录 
            添加 $(BoostDir)\stage\lib\
        5).给使用工程 项目 属性 链接器 输入 附加依赖项 更具debug release 分别添加
            Debug:
                libboost_system-vc140-mt-gd-1_64.lib
                libboost_date_time-vc140-mt-gd-1_64.lib
                libboost_regex-vc140-mt-gd-1_64.lib
                libboost_thread-vc140-mt-gd-1_64.lib
                
            Release:
                libboost_system-vc140-mt-1_64.lib
                libboost_date_time-vc140-mt-1_64.lib
                libboost_regex-vc140-mt-1_64.lib
                libboost_thread-vc140-mt-1_64.lib
                
        其他平台同理
        完毕
2.提供同步启动和异步启动两种方式（比如纯命令行测试用同步启动，嵌入cocos异步启动）


使用方法
startAsyncTcpServer("51234");