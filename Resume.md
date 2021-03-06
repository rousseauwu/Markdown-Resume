
 <html>
    <table style="margin-left: auto; margin-right: auto;">
        <tr>
            <td>
                 <center>
     <h1>伍家宏</h1>
     <div>
         <span>
             <img src="assets/phone-solid.svg" width="15px">
             15521006279
         </span>
         ·
         <span>
             <img src="assets/envelope-solid.svg" width="16px">
             wu657983699@gmail.com
         </span>
     </div>
 </center>
            </td>
            <td>
            <center>
     <div>
         <span>
             <img src="assets/profile.png" width="100px">
         </span>
     </div>
 </center>
            </td>
        </tr>
    </table>
</html>

 ## <img src="assets/info-circle-solid.svg" width="20px"> 个人信息

 - 男，1994 年出生
 - 求职意向：Java 研发工程师
 - 工作经验：2.5 年

## <img src="assets/graduation-cap-solid.svg" width="20px"> 教育经历

- 学士：广东工业大学，物联网工程，2014.9~2018.7
- 通过了 CET4 英语等级考试

## <img src="assets/briefcase-solid.svg" width="20px"> 工作经历

- 平安科技深圳有限公司，集团系统开发一部，开发工程师，2018.7~至今

## <img src="assets/tools-solid.svg" width="20px"> 技能清单
- ★★★ 熟悉JVM内存管理、多线程、锁、集合等基础框架
- ★★★ 熟悉掌握Spring、SringMvc、Mybatis、Dubbo等主流开发框架
- ★★★ 熟悉关系型数据库Oracle、Postgresql，有大量sql优化经验
- ★★☆ 熟悉Redis、Kafka、ZooKeeper等中间件的使用和原理，掌握Elasticsearch的使用方法
- ★★☆ 熟悉Nginx部署，了解Kubernetes相关概念
- ★★★ 熟悉Maven、git等项目管理工具

## <img src="assets/project-diagram-solid.svg" width="20px"> 项目经历

- **考勤系统升级改造**

  *技术栈*：SSM、Dubbo、Kafka、Redis、多线程、Oracle

  - 项目描述：旧有考勤打卡系统采用面对数据库编程的架构，并发量和吞吐量都很低，用户使用感受差，投诉不断。通过缓存、消息队列等技术对后端接口进行改造，保证打卡记录不丢失，高峰期能支持800QPS；在网关层增加限流及熔断功能，控制接口并发量，避免下游系统崩溃。项目改造完成后，考勤功能故障从月均5次降至几乎为0，用户满意度上升。同时，系统提供考勤监控功能，向管理层发送考勤报表。
  - 涉及技术：
    - 基于Dubbo、多线程等技术，获取用户信息并处理业务逻辑
    - 使用Redis漏斗限流功能，实现简单的用户请求限流
    - 基于Kafka消息队列功能缓存起用户的请求数据，同时保证个人的考勤记录是连续的
    - 使用nginx做负载均衡与面对接口的请求限流
  - 主要任务：
    - 分析业务流程，优化业务逻辑，业务需求分析
    - 负责打卡请假接口优化
    - 负责其他考勤系统常规需求
<!-- kafka消息补偿机制
    客户端有那些获取请求的模式？
    Pull模式的另外一个好处是consumer可以自主决定是否批量的从broker拉取数据。Push模式必须在不知道下游consumer消费能力和消费策略的情况下决定是立即推送每条消息还是缓存之后批量推送。如果为了避免consumer崩溃而采用较低的推送速率，将可能导致一次只推送较少的消息而造成浪费。

    为什么使用kafka？持久化数据，sync模式，顺序写

      多线程编程技术

    使用redis hash结构，存储漏斗的各个状态信息。取出来计算，再放回去。但这套动作在redis中不是原子操作。redis-cell，限流模块。提供了原子的限流指令。
        CL.THROTTLE test 100 400 60 3     以上命令表示从一个初始值为100的令牌桶中取3个令牌，该令牌桶的速率限制为400次/60秒。
        令牌桶算法的原理是定义一个按一定速率产生token的桶，每次去桶中申请token，若桶中没有足够的token则申请失败，否则成功。在请求不多的情况下，桶中的token基本会饱和，此时若流量激增，并不会马上拒绝请求，所以这种算法允许一定的流量激增。
     -->

- **中旅薪酬板块设计实现及智能报表优化**

  *技术栈*：SSM、Dubbo、Elasticsearch、Redis、PostgreSql

  - 项目描述：PS薪酬功能是核心模块，但ps提供的webservice接口性能差且开发灵活度低，严重浪费了薪酬数据的价值。为了满足各种查询需求，团队决定采用数仓加工配合ElasticSearch作搜索引擎的系统架构。使用redis缓存热点数据，降低数据库压力。经过一系列改造后，薪酬报表模块最差响应时间从20秒到100毫秒，薪酬报表模块实质性地赋能薪酬管理岗，方便用户填报查询薪酬信息。另外，还帮助中旅集团实现薪酬模块的移动化，主要实现了个人保税申报、薪资福利查询等功能。
  - 涉及技术：
    - 基于Es开发数据批量导入及查询接口
    - 基于Redis缓存优化请求响应
    - 基于左右值无限极分类实现薪酬科目树
    - 基于Elastic Job实现同步数据任务
  - 主要任务：
    - 负责Es相关接口开发
    - 负责薪酬科目树的实现
    - 负责优化查询sql

  <!-- redis缓存数据，穿透，雪崩，解决方案 redis分布式锁：setnx ex,lua 脚步，redlock-->
  <!-- es快速查询，更多时间处理业务计算，相关性搜索。部门架构岗位姓名 -->
  <!-- Yellowbrick Data is a US-based database company delivering massively parallel processing (MPP) data warehouse and SQL analytics products. -->

- **PEOPLESOFT人事系统数据迁移与回写**

  *技术栈*：PeopleSoft、Oracle

  - 项目描述：平安PS系统经过10年迭代，应用性能逐渐满足不了业务需求。业务方要求借鉴ps优秀的人力资源管理理念并尽量保留其人力资源数据，设计出一套类似ps的Web系统，并引用新的管理方法。经过5个月的努力，新系统顺利上线。数据迁移回写组件在不断优化下，回写时间粒度从小时到分钟。监控模块屡次发次重要警告，避免大规模算薪错误。
  - 涉及技术：
    - Oracle、PeopleSoft、Application Engine
  - 主要任务：
    - 梳理人岗架三大核心模块业务逻辑，阅读源码，整理表结构
    - 新旧系统数据交互设计
    - 数据回写流程设计与落地
    - 数据监控程序开发：回写任务状态监控，数据落地准确性监控

  <!--
  PS系统是平安集团使用了10年以上的人力资源管理系统，业务包括人员信息管理、组织岗位管理、职务管理、考勤、算薪及各类报表。
  1、接近100张表，数据模型创建管理ezdml
  2、两个应用数据库使用同一数据库，分批次出数据，分批次回写数据
  3、主任务监控源系统运行情况，数据量等，根据数据量启动相应数量的回写任务个数
  4、回写任务失败发邮件；定时任务使用sql对比两个系统的相关模块数据，去除正在回写数据，并发出警告邮件；
  业务逻辑繁多，优化业务逻辑，去掉无用功能
  经过测试发现，用户重复保存数据产生大量重复流水数据，改为半小时内的最终结果
  单条数据回写慢，改为批处理，优化表索引，优化sql，事务处理，归档处理
  索引：b数索引，列基数大
  位索引，列基数小
  https://blog.csdn.net/WuLex/article/details/79394072
  回写可能存在失败，加上重试机制（失败3次则视为最终失败）;回写任务失败邮件监控;回写数据准确性监控;数据阻塞临时处理页面
  -->

- **其他项目**
  - *标签工厂*：用户在人员信息、岗位、架构三大类信息中选择多个纬度配置标签，并实时或者离线给用户权限范围内的人打上标签。离线打标由数仓加工得出；在线打标由java生成脚本，从数据库查询得出结果。
  - *算薪源码翻译*：集团整体规划脱离PeopleSoft系统，并按照其中的算薪功能复制出一套功能。此算薪功能是使用COBOL语言实现的。实现方案是使用Antlr半自动翻译COBOL，剩下的具体实现需人工翻译。最后项目由于公司决定要自研而停止。