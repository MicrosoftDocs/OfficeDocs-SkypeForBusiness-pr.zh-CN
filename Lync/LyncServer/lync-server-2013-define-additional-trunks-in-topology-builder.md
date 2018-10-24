---
title: Lync Server 2013：在拓扑生成器中定义其他中继
TOCTitle: 在拓扑生成器中定义其他中继
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49888653
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 拓扑生成器中定义其他中继

 

_**上一次修改主题：** 2012-10-04_

按照以下步骤可使用 拓扑生成器定义其他中继，对此可将 *对等方* 与 中介服务器进行关联。对等方向启用 企业语音的用户提供到公用电话交换网 (PSTN) 的连接。对等方可以是用于 Internet 电话服务提供商电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。该中继可定义 中介服务器和对等方之间的此连接。每个 中介服务器可定义多个中继。一个 中介服务器可与多个对等方关联。

中继是元组唯一标识的 中介服务器 和网关之间的全局连接：

{ 中介服务器 FQDN，中介服务器 侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}

> [!NOTE]  
> 本主题假定您已设置至少带有一个关联或独立的 中介服务器 或池的 PSTN 网关和根中继 ，如部署文档的 <a href="lync-server-2013-define-a-gateway-in-topology-builder.md">在 Lync Server 2013 拓扑生成器中定义网关</a>中所述。



> [!NOTE]  
> 本主题假定您已经在至少一个中央站点中设置到至少一个 前端池或 Standard Edition Server，如部署文档的 <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器</a>和 <a href="lync-server-2013-publish-the-topology.md">在 Lync Server 2013 中发布拓扑</a>中所述。



## 在 中介服务器 和对等网关之间定义其他中继

1.  启动拓扑生成器：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 拓扑生成器”。

2.  在 Lync Server 2013、您的站点名称和“共享组件”下，右键单击“Trunk”节点，然后单击“新建 Trunk”。
    
    ![显示 Lync Server 拓扑生成器文件结构的屏幕](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "显示 Lync Server 拓扑生成器文件结构的屏幕")

3.  在“定义新的 Trunk”中，指定唯一标识中继的友好名称。您不得有两个具有相同名称的中继。
    
    > [!NOTE]  
    > 如果您作为传输类型指定传输层安全性 (TLS)，则必须指定 FQDN，而不是 中介服务器 对等的 IP 地址。
    


4.  在“关联的 PSTN 网关”下，选择 PSTN 对等网关以与此中继相关联。
    
    ![中继的 PSTN 网关对等方的属性设置](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "中继的 PSTN 网关对等方的属性设置")

5.  在“PSTN 网关的侦听端口”下，键入对等方（PSTN 网关、IP-PBX 或 SBC）侦听端口将从要与此中继关联的 中介服务器 接收 SIP 消息。对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。对于 TCP 来说，默认 Survivable Branch Appliance 端口为 5081，对于 TLS，则默认端口为 5082。

6.  在“SIP 传输协议”下，单击对等方使用的传输类型。
    
    > [!NOTE]  
    > 为了安全起见，我们强烈建议您部署可使用 TLS 的 中介服务器的对等方。
    


7.  在“关联的中介服务器”下，选择 中介服务器池以与此对等方的根中继相关联

8.  在“关联的中介服务器端口”下，键入 中介服务器将从对等方接收 SIP 消息的侦听端口。
    
    > [!NOTE]  
    > 借助 Lync Server 2013 中的多个中继支持，具有不同中继名称的两个中继无法使用具有相同的“中介服务器 端口”和“IP/PSTN 网关的侦听端口”进行配置
    
    
    > [!NOTE]  
    > 借助 Lync Server 2013 中的多个中继支持，可在 中介服务器上配置多个与多个对等方通信的 SIP 信号端口。当定义中继时，对于由 中介服务器允许的相应协议，“关联的 中介服务器端口”号必须在侦听端口的范围内。此端口范围在 Lync Server 2013 和 中介服务器池 范围下定义。右键单击相应的 中介服务器池，并选择“编辑属性”。在“侦听端口”字段中指定端口范围。
    


9.  单击“确定”。

## 另请参阅

#### 任务

[在 Lync Server 2013 中修改拓扑生成器中的中继](lync-server-2013-modify-a-trunk-in-topology-builder.md)

