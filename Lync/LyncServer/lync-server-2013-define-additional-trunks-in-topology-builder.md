---
title: Lync Server 2013：在拓扑生成器中定义其他中继
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Define additional trunks in Topology Builder
ms:assetid: e68b8377-50a2-452a-bf5c-910929e34236
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721915(v=OCS.15)
ms:contentKeyID: 49733849
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f88a292b11e617d1ae0d20f603ad53b2b2847e7f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038134"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓扑生成器中定义其他中继

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-04_

按照以下步骤使用拓扑生成器定义可将*对等方*与中介服务器关联的其他中继。 对等方为启用了到公用电话交换网（PSTN）连接的企业语音启用了用户。 对等方可以是用于 Internet 电话服务提供商电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。 中继定义中介服务器与对等方之间的连接。 可以为每个中介服务器定义多个中继。 中介服务器可以与多个对等方相关联。

中继是中介服务器和元组唯一标识的网关之间的逻辑连接：

{中介服务器 FQDN、中介服务器侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}

<div>


> [!NOTE]  
> 本主题假定您已使用至少一个并置或独立中介服务器或池设置了 PSTN 网关和根中继，如在部署文档中的 "在<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">拓扑生成器中定义一个网关</A>" 中所述，在 "Lync server 2013" 中定义一个网关。



</div>

<div>


> [!NOTE]  
> 本主题假定您已至少在一个中心站点中设置了一个前端池或 Standard Edition 服务器，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或 Standard edition server</A>以及部署文档中的<A href="lync-server-2013-publish-the-topology.md">"在 lync Server 2013 中发布拓扑"</A>中所述。



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在中介服务器和网关对等方之间定义其他中继

1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在 "Lync Server 2013" 下，右键单击 "**共享组件**"，右键单击 "**中继**" 节点，然后单击 "**新建中继**"。
    
    ![Lync Server 拓扑生成器文件结构屏幕](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓扑生成器文件结构屏幕")

3.  在“定义新的 Trunk”**** 中，指定唯一标识中继的友好名称。 您不得有两个具有相同名称的中继。
    
    <div>
    

    > [!NOTE]  
    > 如果将传输层安全性（TLS）指定为传输类型，则必须指定 FQDN，而不是中介服务器的对等方的 IP 地址。

    
    </div>

4.  在“关联的 PSTN 网关”**** 下，选择 PSTN 对等网关以与此中继相关联。
    
    ![用于中继的 PSTN 网关对等的属性设置](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "用于中继的 PSTN 网关对等的属性设置")

5.  在 "**用于 PSTN 网关的侦听端口**" 下，键入对等方（PSTN 网关、IP-PBX 或 SBC）将从要与此中继关联的中介服务器接收 SIP 消息的侦听端口。 对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。 默认的 Survivable 分支装置端口是用于 TLS 的 TCP 和5082的5081。

6.  在“SIP 传输协议”**** 下，单击对等方使用的传输类型。
    
    <div>
    

    > [!NOTE]  
    > 出于安全考虑，强烈建议您将对等部署到可以使用 TLS 的中介服务器。

    
    </div>

7.  在 "**关联的中介服务器**" 下，选择要与此对等方的根中继相关联的中介服务器池

8.  在 "**关联的中介服务器端口**" 下，键入中介服务器将从对等方接收 SIP 消息的侦听端口。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中有多个中继支持，不能为具有不同中继名称的两个中继配置<STRONG>IP/PSTN 网关</STRONG>的相同<STRONG>关联中介服务器端口</STRONG>和侦听端口

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中有多个中继支持，可以在中介服务器上定义多个 SIP 信号端口，以便与多个对等方通信。 在定义中继时，<STRONG>关联的中介服务器端口</STRONG>号必须位于中介服务器允许的各个协议的侦听端口范围内。 此端口范围在 "Lync Server 2013" 和 "中介服务器池" 中定义。 右键单击相关中介服务器池，然后选择 "<STRONG>编辑属性</STRONG>"。 在“侦听端口”<STRONG></STRONG>字段中指定端口范围。

    
    </div>

9.  单击“确定”****。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中修改拓扑生成器中的中继](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

