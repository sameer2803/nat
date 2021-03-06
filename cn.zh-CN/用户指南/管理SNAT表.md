# 管理SNAT表 {#concept_pnw_cdl_32b .concept}

NAT网关提供SNAT功能，为VPC内无公网IP的ECS实例提供访问互联网的代理服务。

## SNAT条目 {#section_qnw_cdl_32b .section}

NAT网关将SNAT功能的配置，抽象为一张SNAT列表。您可以通过配置SNAT列表中的SNAT条目，实现SNAT功能的配置。

每个SNAT条目由交换机和公网IP组成。交换机为专有网络ECS实例所属的交换机，公网IP为NAT网关绑定的弹性公网IP（EIP），如下表所示。

**说明：** 对于2018年1月26日之前账户下存在NAT带宽包的用户，SNAT条目中的公网IP为NAT带宽包提供的公网IP。

|交换机|公网IP|
|:--|:---|
|vsw-184ipsxxx|139.224.xx.xx|
|vsw-11qht5xxx|139.224.xx.xx|

配置SNAT条目后，当指定交换机下的ECS实例发起互联网访问请求时，NAT网关会为其提供SNAT服务（代理上网服务），且使用的公网IP地址为指定的公网IP。默认情况下交换机下的所有ECS实例都可以使用配置的公网IP发起互联网访问。

**说明：** 若某台持有公网IP的ECS实例（比如已经绑定了EIP）发起互联网访问时，会优先使用其持有的公网IP，而不会使用NAT网关的SNAT功能。

## 添加SNAT条目 {#section_unw_cdl_32b .section}

完成以下操作，添加SNAT条目：

1.  登录[VPC管理控制台](https://vpcnext.console.aliyun.com/nat/)。
2.  在左侧导航栏，单击**NAT网关**。
3.  选择NAT网关的地域。
4.  单击目标NAT网关的实例ID。
5.  在左侧导航栏，单击**SNAT列表**，然后单击**创建SNAT条目**。
6.  根据以下信息，配置SNAT条目。

    |配置|说明|
    |:-|:-|
    |**交换机**| 选择VPC中的交换机。该交换机下所有的ECS实例都将可以通过SNAT功能进行公网访问。

 **说明：** 如果某台持有公网IP的ECS实例（比如已经绑定了EIP）发起互联网访问时，会优先使用其持有的公网IP，而不会使用NAT网关的SNAT功能。

 |
    |**交换机网段**|显示该交换机的网段。|
    |**公网IP**| 选择用来提供互联网访问的公网IP。

 **说明：** 用于创建DNAT条目的公网IP地址不能再用来创建SNAT条目。

 |


## 编辑SNAT条目 {#section_b4w_cdl_32b .section}

完成以下操作，编辑SNAT条目：

1.  登录[VPC管理控制台](https://vpcnext.console.aliyun.com/nat/)。
2.  在左侧导航栏，单击**NAT网关**。
3.  选择NAT网关的地域。
4.  单击目标NAT网关的**设置SNAT**选项。
5.  单击目标SNAT条目的**编辑**，更新SNAT条目配置。

## 删除SNAT条目 {#section_d4w_cdl_32b .section}

完成以下操作，删除SNAT条目：

1.  登录[VPC管理控制台](https://vpcnext.console.aliyun.com/nat/)。
2.  在左侧导航栏，单击**NAT网关**。
3.  选择NAT网关的地域。
4.  单击目标NAT网关的**设置SNAT**选项。
5.  单击目标SNAT条目的**移除**，然后单击**确定**。

