# 复杂度来源:低成本,安全,规模

#### 低成本

低成本给架构设计带来的主要复杂度体现在 , 往往只有"创新"才能达到低成本目标 . 这里的创新既包括开创一个全新的技术领域 , 当然这很难实现 , 也包括引入新技术 , 如果没有找到能够解决自己问题的新技术 , 那么就真的需要自己创造新技术了 . 

**类似的新技术例子很多 : **

* NoSQL\(Memcache , Redis等\)的出现是为了解决关系型数据库无法应对的高并发访问带来的访问压力 . 
* 全文搜索引擎\(Sphinx , Elasticsearch , Solr\)的出现是为了解决关系型数据库like搜索的低效的问题 . 
* Hadoop的出现是为了解决传统文件系统无法应对海量数据存储和计算的问题 . 

**其他业界列子 : **

* Facebook为了解决PHP的低效问题 , 刚开始的解决方式是HipHop PHP , 可以将PHP语言翻译为C++语言执行 , 后来改为HHVM , 将PHP翻译为字节码然后由虚拟机执行 , 和Java的JVM类似 . 
* 新浪微博将传统的Redis/MC + MySQL方式 , 扩展为Redis/MC + SSD Cache + MySQL 方式 , SSD Cache 作为 L2 缓存使用 , 既解决了MC/Redis成本过高 , 容量小的问题 , 也解决了穿透DB带来的数据库访问压力 . 
  * 可以看看相关文章 : 新浪微博架构
  * https://www.infoq.cn/article/weibo-platform-archieture/

* Linkedin为了处理每天5千亿的事件 , 开发了高效的Kafka消息系统 . 

* 其他类似将Ruby On Rails改为Java , Lua + redis改为Go语言实现的例子还有很多 . 

无论引入新技术 , 还是自己创造新技术 , 都是一件复杂的事情 . 小公司引入新技术 , 大公司创造新技术. 



