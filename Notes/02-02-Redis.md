#  Question1
1. 数据存在内存里：内存读写比硬盘快几百倍。
1. 单线程模型：避免多线程上下文切换和锁竞争。
2. IO 多路复用：一个线程管理大量连接，不浪费线程等网络。
3. 数据结构优化：压缩列表等都是为速度专门设计的。

一句话：Redis 快，是因为数据全放内存，单线程避免竞争，IO 多路复用管连接，数据结构专门优化过。
# Question2
1. 方式一：字符串（String）
把整行数据序列化成 JSON，作为一个字符串存。
2. 方式二：哈希（Hash）
把每个字段存成 Hash 里的一个 field。
# Question3
1. 方式一：Jedis（最底层，类似 JDBC）
2. 方式二：Lettuce（Spring Boot 默认，支持异步）
3. 方式三：Spring Data Redis（Spring 项目最常用）

基本逻辑为：
1. 连上Redis
2. 执行命令（set/get/delete等）
3. 处理返回结果