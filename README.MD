# market_web_server
## 包介绍
* comm    各项配置及通用类
* dao     该包主要放置操作数据库的类
* dto     数据传输对象，与接口开发指引的业务要素基本对应
* entity  持久化对象，与数据库对应的实体类
* service 业务接口及实现 如果有事务操作，在此层做
## 配置资源
* mappers mybatis ORM映射
* application.properties 配置入口
* log4j.properties 日志配置

## 使用手册 参照示例：CfetsSystemlogMapper

### 通用查询：单表的CRUD操作配置
* 第一步：
    可以手动填写与数据库对应的实体类（也可以使用mybatis反向生成工具生成实体类）放置包com.croot.asset.web.entity下。
* 第二步：
    找到com.croot.asset.web.dao包下建立一个与之对应的mapper操作接口，接口继承MyMapper<T>，T为数据库对应的实体类。

### 自定义查询：自定义查询 ，有些业务复杂需要多表链接查询 可以使用自定义查询
* 第一步：在通用的Mapper接口上定义自己的方法selectByPre2，返回值，参数，方法名。
* 第二步：需要在/resources/mappers文件下创建mybatis的xml文件。
* 第三部：配置好xml文件中对应的namespace，方法名(selectByPre2)等信息。

### Test测试
* 相关测试用例参考：ApplicationTest类下的testService2，testA,testB方法。

### 相关参考文档：
1、https://blog.csdn.net/ypp91zr/article/details/89006493  
2、https://blog.csdn.net/qq_28988969/article/details/78606066  
3、https://blog.csdn.net/gdift/article/details/78987162



    