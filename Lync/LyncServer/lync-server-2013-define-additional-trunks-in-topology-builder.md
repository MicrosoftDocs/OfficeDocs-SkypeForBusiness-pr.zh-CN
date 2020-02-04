---
title: Lync Server 2013：定义拓扑生成器中的其他中继
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
ms.openlocfilehash: c55e8073bd1ad1bb2db69096e4e58aa2b148e775
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728482"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="define-additional-trunks-in-topology-builder-in-lync-server-2013"></a>在 Lync Server 2013 的拓扑生成器中定义其他中继

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-04_

按照以下步骤使用拓扑生成器定义可将*对等*与中介服务器相关联的其他主干。 对等用户可通过连接到公共交换电话网络（PSTN）来为企业语音启用企业语音。 对等方可以是用于 Internet 电话服务提供商 (ITSP) 的 PSTN 网关、IP-PBX 或会话边界控制器 (SBC)。 主干在中介服务器和对等之间定义此连接。 可以为每个中介服务器定义多个中继。 中介服务器可以与多个对等方关联。

主干是中介服务器与元组唯一标识的网关之间的逻辑连接：

{中介服务器 FQDN、中介服务器侦听端口（TLS 或 TCP）：网关 IP 和 FQDN，网关侦听端口}

<div>


> [!NOTE]  
> 本主题假定你已使用至少一个 collocated 或独立中介服务器或池设置 PSTN 网关和根中继，如在部署文档的<A href="lync-server-2013-define-a-gateway-in-topology-builder.md">Lync Server 2013 中的 "拓扑生成器" 中定义的网关</A>中所述。



</div>

<div>


> [!NOTE]  
> 本主题假定你至少在一个中心网站中设置了一个前端池或标准版服务器，如在<A href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">Lync server 2013 中定义和配置前端池或标准版服务器</A>中所述，在部署文档中的<A href="lync-server-2013-publish-the-topology.md">lync Server 2013 中发布拓扑</A>。



</div>

<div>

## <a name="to-define-an-additional-trunk-between-a-mediation-server-and-a-gateway-peer"></a>在中介服务器和网关对等之间定义其他主干

1.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在 "Lync Server 2013" 下，选择 "网站名称"、"**共享组件**"，右键单击**中继**节点，然后单击 "**新建主干**"。
    
    ![Lync Server 拓扑生成器文件结构屏幕](images/JJ721915.90d5b349-aa1e-407a-87ed-fa112f478560(OCS.15).png "Lync Server 拓扑生成器文件结构屏幕")

3.  在“定义新的 Trunk”**** 中，指定唯一标识中继的友好名称。 您不得有两个具有相同名称的中继。
    
    <div>
    

    > [!NOTE]  
    > 如果将传输层安全性（TLS）指定为传输类型，则必须指定 FQDN，而不是中介服务器对等的 IP 地址。

    
    </div>

4.  在“关联的 PSTN 网关”**** 下，选择 PSTN 对等网关以与此中继相关联。
    
    ![用于干线的 PSTN 网关对等的属性设置](images/JJ721915.7c3fe8ee-8f4c-4413-8462-8347228e61bb(OCS.15).png "用于干线的 PSTN 网关对等的属性设置")

5.  在 " **PSTN 网关的侦听端口**" 下，键入对等（PSTN 网关、IP PBX 或 SBC）将从要与该主干关联的中介服务器接收 SIP 消息的侦听端口。 对于传输控制协议 (TCP) 来说，默认对等端口为 5066，对于传输层安全性 (TLS)，默认端口为 5067。 默认的 Survivable 分支装置端口为用于 TLS 的 TCP 和5082的5081。

6.  在“SIP 传输协议”**** 下，单击对等方使用的传输类型。
    
    <div>
    

    > [!NOTE]  
    > 出于安全原因，强烈建议你将对等部署到可以使用 TLS 的中介服务器。

    
    </div>

7.  在 "**关联的中介服务器**" 下，选择要与此对等方的根中继相关联的中介服务器池

8.  在 "**关联的中介服务器端口**" 下，键入中介服务器将从对等方接收 SIP 消息的侦听端口。
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中有多个中继支持，具有不同中继名称的两个中继不能配置为与<STRONG>IP/PSTN 网关</STRONG>相同的<STRONG>关联中介服务器端口</STRONG>和侦听端口

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > 在 Lync Server 2013 中有多个中继支持，可以在中介服务器上定义多个 SIP 信号端口，以便与多个对等方通信。 定义主干时，关联的<STRONG>中介服务器端口</STRONG>号必须位于中介服务器允许的各个协议的侦听端口范围内。 此端口范围在 Lync Server 2013 和中介服务器池下定义。 右键单击相关的中介服务器池，然后选择 "<STRONG>编辑属性</STRONG>"。 Specify the port range in the <STRONG>Listening ports</STRONG> field.

    
    </div>

9.  单击“**确定**”。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中的拓扑生成器中修改主干](lync-server-2013-modify-a-trunk-in-topology-builder.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

