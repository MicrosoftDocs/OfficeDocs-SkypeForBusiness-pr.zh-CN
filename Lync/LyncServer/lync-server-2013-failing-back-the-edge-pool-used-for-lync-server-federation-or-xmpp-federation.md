---
title: 对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing back the Edge pool used for Lync Server federation or XMPP federation
ms:assetid: d40097a1-1bed-44dc-aeb6-0871927ab2b9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721897(v=OCS.15)
ms:contentKeyID: 49733831
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75e4dbe8265050d30620b0ecbdd1992b480106e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830186"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-11-01_

将用于托管联合身份验证的边缘池恢复为联机状态后, 请使用此过程将 Lync Server 联合身份验证路由和/或 XMPP 联盟路由重新故障, 以再次使用此还原的边缘池。

<div>

## <a name="failing-back-federation-to-a-restored-edge-pool"></a>向还原的边缘池回切联合

1.  在现在再次可用的 Edge 池中, 启动 Edge 服务。

2.  如果你希望恢复 Lync Server 联合身份验证路由以使用还原的边缘服务器, 请执行以下操作:
    
      - 在前端服务器上, 打开拓扑生成器。 展开 "**边缘池**", 然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。 选择 "**编辑属性**"。
    
      - 在 "**编辑属性**" 下的 "**常规**" 下, 清除 "**为此边缘池启用联盟 (端口 5061)**"。 单击“**确定**”。
    
      - 展开 "**边缘池**", 然后右键单击要用于联盟的原始边缘服务器或边缘服务器池。 选择 "**编辑属性**"。
    
      - 在 "**常规**" 下的 "**编辑属性**" 下, 选择 "**为此边缘池启用联盟 (端口 5061)**"。 单击“**确定**”。
    
      - 单击 "**操作**", 选择 "**拓扑**", 选择 "**发布**"。 当系统提示**发布拓扑**时, 单击 "**下一步**"。 发布完成后, 单击 "**完成**"。
    
      - 在边缘服务器上, 打开 "Lync Server 部署向导"。 单击 "**安装或更新 Lync 服务器系统**", 然后单击 "**设置" 或 "删除 lync server 组件**"。 再次单击 "**运行**"。
    
      - 在 "安装 Lync 服务器组件" 中, 单击 "**下一步**"。 "摘要" 屏幕将显示执行时的操作。 部署完成后, 单击 "**查看日志**" 以查看可用的日志文件。 单击 "**完成**" 以完成部署。

3.  如果想要恢复 XMPP 联盟路由以使用还原的边缘服务器, 请执行以下操作:
    
      - 运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到边缘池, 该池现在将托管 XMPP 联合身份验证 (在此示例中, EdgeServer1):
        
            Set-CsSite Site1 -XmppExternalFederationRoute EdgeServer1.contoso.com
        
        在此示例中, Site1 是包含边缘池的网站, 它现在将托管 XMPP 联合路由, EdgeServer1.contoso.com 是该池中的边缘服务器的 FQDN。
    
      - 如果你还没有可解析为 XMPP 联合的 DNS SRV 记录, 并且该记录将托管到将托管 XMPP 联合的边缘池, 则必须添加它, 如下例所示。 此 SRV 记录必须具有端口值5269。
        
            _xmpp-server._tcp.contoso.com
    
      - 在外部 DNS 服务器上, 将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。
    
      - 验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。

4.  如果前端池仍在包含发生故障且已还原的边缘池的网站中运行, 则应在这些前端池上更新 Web 会议服务和 A/V 会议服务, 再次使用其本地网站上的边缘池。 有关详细信息, 请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

5.  如果与失败的 Edge 池位于同一站点的前端池也失败, 您现在可以使用 Invoke-CsPoolFailback 来故障回复前端池。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)  
[在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  


[Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

