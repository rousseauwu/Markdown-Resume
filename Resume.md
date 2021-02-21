
 <html>
    <table style="margin-left: auto; margin-right: auto;">
        <tr>
            <td>
                 <center>
     <h1>伍家宏</h1>
     <div>
         <span>
             <img src="assets/phone-solid.svg" width="18px">
             155210006279
         </span>
         ·
         <span>
             <img src="assets/envelope-solid.svg" width="18px">
             wu657983699@gmail.com
         </span>
     </div>
 </center>
            </td>
            <td>
            <center>
     <div>
         <span>
             <img src="assets/profile.png" width="120px">
         </span>
     </div>
 </center>
            </td>
        </tr>
    </table>
</html>

 ## <img src="assets/info-circle-solid.svg" width="30px"> 个人信息

 - 男，1994 年出生
 - 求职意向：Java 研发工程师
 - 工作经验：3 年
 - 期望薪资：0k

## <img src="assets/graduation-cap-solid.svg" width="30px"> 教育经历

- 学士：广东工业大学，物联网工程，2014.9~2018.7
- 绩点：***，年级前 100%
- 通过了 CET4/6 英语等级考试

## <img src="assets/briefcase-solid.svg" width="30px"> 工作经历

- 平安科技深圳有限公司，集团系统开发一部，开发工程师，2018.7~至今

## <img src="assets/briefcase-solid.svg" width="30px"> 个人成就
- 每年绩效达头部30%，30人团队主力开发
- 高并发web应用架构设计落地经验
- 从0到1学习PeopleSoft语言，手撕Cobol语言
- 对 coding 有热情，在项目迭代，性能优化，疑难问题排查等方面都有可靠的攻坚能力

## <img src="assets/project-diagram-solid.svg" width="30px"> 项目经历

- **PEOPLESOFT人事系统数据迁移与回写**

  *技术栈*：PeopleSoft，Oracle

  - 项目描述：PS系统是平安集团使用了10年以上的人力资源管理系统，业务包括人员信息管理、组织岗位管理、职务管理、考勤、算薪及报表。
  - 主要任务：梳理人岗架业务及表结构；新旧系统数据交互设计；数据回写流程设计与落地；回写任务状态监控；数据落地准确性监控。
  - 涉及技术：
    - 数据库表索引优化
  <!--
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

- **考勤系统升级改造**

  *技术栈*：Java，Kafka，Redis，多线程

  - 项目描述：旧有考勤打卡系统采用面对数据库编程的架构，并发量和吞吐量都很低，用户使用感受差，投诉不断。通过一系列改造，考勤移动系统用户满意度提升，高峰期轻易支持500QPS，用户量也节节上升
  - 主要任务：提高系统并发量和吞吐量，提升系统响应速度，提升用户满意度
    - 涉及技术：
    - 抛弃面对数据库编程
    - 基于Dubbo、多线程等技术，获取用户信息并处理业务逻辑
    - 使用Redis漏斗限流功能，实现简单的用户请求限流
    - 基于Kafka消息队列功能缓存起用户的请求数据，客户端使用poll模式请求，起到削峰作用；另外，Kafka也能保证顺序写数据
    - 使用nginx做负载均衡与面对接口的请求限流
<!-- kafka消息补偿机制
    客户端有那些获取请求的模式？
    Pull模式的另外一个好处是consumer可以自主决定是否批量的从broker拉取数据。Push模式必须在不知道下游consumer消费能力和消费策略的情况下决定是立即推送每条消息还是缓存之后批量推送。如果为了避免consumer崩溃而采用较低的推送速率，将可能导致一次只推送较少的消息而造成浪费。

    为什么使用kafka？持久化数据，sync模式，顺序写

      多线程编程技术

    使用redis hash结构，存储漏斗的各个状态信息。取出来计算，再放回去。但这套动作在redis中不是原子操作。redis-cell，限流模块。提供了原子的限流指令。
        CL.THROTTLE test 100 400 60 3     以上命令表示从一个初始值为100的令牌桶中取3个令牌，该令牌桶的速率限制为400次/60秒。
        令牌桶算法的原理是定义一个按一定速率产生token的桶，每次去桶中申请token，若桶中没有足够的token则申请失败，否则成功。在请求不多的情况下，桶中的token基本会饱和，此时若流量激增，并不会马上拒绝请求，所以这种算法允许一定的流量激增。
     -->

- **bi智能报表-热图**

  *技术栈*：Spring、Elasticsearch、Redis

  - 项目描述：薪酬大宽表列数多，mmp型数据库对于关系型

  <!-- redis缓存数据，穿透，雪崩，解决方案 -->

- **标签工厂**

  *技术栈*：spring、Elasticsearch、Redis

- **to b薪酬模块**

  *技术栈*：spring、Elasticsearch、Redis、ElasticJob

- **算薪源码翻译**

  *技术栈*：Cobol，Java

## <img src="assets/tools-solid.svg" width="30px"> 技能清单

- ★★★ Java
- ★★☆ Spring、SpringBoot、Dubbo
- ★★★ Oracle、Postgresql
- ★★★ Redis、Kafka、Elasticsearch、ZooKeeper
- ★★☆ Nginx、tomcat、k8s
