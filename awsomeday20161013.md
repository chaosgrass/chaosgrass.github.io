AWSome Day 介绍
==============

简介
---
    AWSome day是亚马逊推出的免费培训课程，简要介绍了AWS的各种服务。
    去年是1.0版，主要围绕服务介绍适用的场景，今年改版后的2.0版，突出了场景，围绕了5个场景介绍AWS服务的各项能力。
    云计算中最重要的存储，所以S3(Simple Storage Service)也是AWS最早推出的服务，几乎可以认为是存储空间无限，带宽无限的对象存储（添加/删除/替换？）。
    存储的安全，AWS提供了区域+可用区（AZ）的概念来解决，区域保证就近，可用区提供灾备。

场景1：Web站点
--------------

    云计算的典型场景是大规模高并发的Web站点，AWS对此的解决方案是以下服务的组合配置：
	1. S3存储静态内容+CloudFront CDN服务；
	2. EC2提供虚拟机服务，或者是Lambda + API Gateway的Serverless HTTP服务；
	3. EC2需要配合Elastic Load Balancing + Auto Scaling + Cloud Watch完成负载均衡，弹性伸缩容；
	4. VPC提供虚拟私有子网；
	5. RDS提供关系数据库服务，有各种数据库引擎选择，跨AZ部署，主从分离，只读副本；
	6. Elastic Cache提供高速缓存，减少主库压力（Redis/Memcached）；
	7. Route 53提供DNS服务（配合CDN服务？）；

场景2：云友好的Web应用
---------------------

    空谈的架构师容易，难点在于开发云友好的应用，所以对AWS的建议：
	1. 『无状态的应用』
	2. EC2无状态，则故障出现时，EC2实例随时可以重启或重建；
	3. 用户会话状态建议存储到数据库中；
	4. AWS提供丰富的开发包=REST API + SDK + 命令行 + GUI控制台；
	5. 可以自动扩容的服务，例如DynamoDB，EBS，实时数据流；
	6. 无需关心扩容的服务，Lambda，免费额度；
	7. 深度依赖云服务的Web应用如何调试？

场景3：运维
-----------
    自动化运维服务：
	1. 弹性IP、CloudFormation、OpsWorks，CodeCommit、CodePipeline
	2. Service Catalog + ECS/ECR；
	3. CloudTrace 记录API调用；
	4. 洋葱先生，每天100个版本，持续交付
		在线持续集成系统（全自动化版本发布页面）；
		系统级的监控；
		故障应急处置；
		突发流量应急处置；
		成本控制系统；

场景4：大数据
-------------
    云中大数据：
	收集、分析、可视化
	海量数据的管道：Kinesis，弹幕Demo；
	海量数据分析：EMR（Hadoop）
			CoreNode with HDFS
			TaskNode without HDFS，可弹性伸缩
		Hive数据仓库
		BI工具可直接读取AWS数据（Tableau）
		Redishift，在百万数据级别秒杀PostgressSQL

场景5：云中企业应用
------------------

提供资源：
---------
    AWS的资源：
	微博、微信
	视频课程：http://aws.amazon.bokecc.com
	awsomeday.cn
	awsomeday.cn/advanced
	amazonaws.com 中国区
	http://china.qwiklab.com 快速上手实验室
