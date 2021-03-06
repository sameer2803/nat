# NAT网关规格 {#concept_nlc_s1z_ydb .concept}

NAT网关提供不同的规格。NAT网关的规格会影响SNAT功能的最大连接数和每秒新建连接数，但不会影响数据吞吐量。

NAT网关提供如下规格。

|规格|SNAT最大连接数|SNAT每秒新建连接数|
|:-|:--------|:----------|
|小型|1万|1千|
|中型|5万|5千|
|大型|20万|1万|
|超大型-1|100万|3万|

在选择NAT规格时，请注意：

-   NAT网关的规格仅对SNAT的性能有影响，对DNAT没有限制。

-   NAT网关的规格与共享带宽包的带宽大小、IP个数之间没有相互制约关系。

-   NAT网关在云监控控制台只提供最大连接数监控，不提供每秒新建连接数。

-   NAT网关SNAT的连接超时时间为900秒。

-   为避免网络拥塞、公网抖动可能造成的SNAT连接超时，请确保您的业务应用有自动重连机制，这样可以提供更高的可用性。

-   NAT网关暂不支持报文分片。

-   当VPC内无公网IP的ECS实例通过NAT网关访问公网上同一个目的IP和端口的带宽超过5Gbps时，建议您为NAT网关绑定多个公网IP并[构建SNAT IP池](https://yq.aliyun.com/articles/533821?spm=a2c4e.11155435.0.0.5e2d49f0MGgXFw)，避免单个公网IP的端口数量限制可能产生的丢包。

