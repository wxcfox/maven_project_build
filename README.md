# maven_project_build
Simply use Maven to build a project
使用maven搭建工程
1.搭建
yk-parent：父工程，打包方式pom，管理jar包版本号。项目中所有工程都应该继承父工程。
|--yk-common：通用的工具类、通用的pojo。打包方式jar。
|--yk-manager：聚合工程。打包方式pom。依赖common
|--yk-manager-pojo：打包方式jar，
|--yk-manager-dao：打包方式jar，依赖pojo、mybatis、mysql、连接池。
|--yk-manager-interface：打包方式jar，依赖pojo。
|--yk-manager-service：打包方式：jar，依赖dao、interface、spring相关。
    |--yk-manager-web：表现层工程，打包方式war，依赖service、jsp相关。
补全目录结构，添加欢迎页。
2.测试
在yk-manager 的pom工程中，配置tomcat插件。启动的端口号，和工程名称。
按顺序对yk-parent和yk-common执行maven install，然后对yk-manager执行clean tomcat:run。
