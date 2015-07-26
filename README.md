Leo
=====

接口自动化测试框架 1.0.7-SNAPSHOT

1.0.7-SNAPSHOT 更新内容
-----------------------------------------------------
1.增加对cookie的接口依赖;在预期结果中增加${cookie},会将cookie做为变量传递到其它参数中;
2.增加httpClient线程池管理，解决多线程请求时“[ERROR] CasesUtils - Invalid use of BasicClientConnManager: connection still allocated.”的问题;
3.修复多线程时更新请求参数时资源同步问题;(现在业务类方法不需要继承casesUtils)



1.0.6 更新内容
-------------------------------
1. 增加接口依赖，以${}标示，预期结果中支持多个相同参数以下划线加后缀进行区分，eg:${key_01}; 
2. 请求参数中支持依赖参数部分替换;eg:value${key_01}value 只会替换${}中的内容;
3. 修复当有多个数据库连接操作时，只能实例化一个数据库连接;


1.0.5 更新内容
-------------------------------
1. 解决生成javadoc时WARNING;
2. 当预期结果为int类型时，对实际结果为0进行判断(0为int结果匹配中的特殊值,0不包含在关键词int中);
3. 支持用例多线程方式，提高运行效率;
4. 支持对Sheet中的多用例进行多线程(即：methods方式);可对多个Sheet页进行多线程执行（即：tests方式）;
5. 可自定义线程数;
6. 支持实际结果为json数组的处理;相同的key，value用数组表示,预期结果可写成数组行完全匹配，也可以写单个值进行包含匹配;



1.0.4 更新内容：
-------------------------------
1. 增加设置预期结果中"date"关键词dateFormat样式，可自定义关键词date样式;
2. 预期结果中增加对int关键词的支持，匹配结果中int类型动态值,支持单个和多个实际结果（key=int或key=int^int）;
3. 增加Host关键字及全局配置;
4. 增加Header全局配置;
5. 修改注解;


1.0.3 更新内容：
-------------------------------
1. pom.xml中增加邮件包依赖;  
2. 增加https请求处理（支持证书认证与非证书认证两种方式）
3. 修改解析xml时一个key对应多个值时，实际结果值与预期结果值无法进行比较（key=[value1,value2]）
4. CompareResult.trimActres 修改为public类型提供业务处理使用;
5. 修改代理默认值bug;