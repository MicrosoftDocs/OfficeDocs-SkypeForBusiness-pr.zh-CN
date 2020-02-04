---
title: Lync Server 2013：对用于 Lync Server 联盟的边缘池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for Lync Server federation
ms:assetid: 5c9da0f2-7429-40bb-bb3c-5cc4ecb5a13d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688071(v=OCS.15)
ms:contentKeyID: 49733665
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f144def3d3a8df9cc63221342a85666eb3c28913
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765190"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-lync-server-federation-in-lync-server-2013"></a>在 Lync Server 2013 中对用于 Lync Server 联盟的边缘池进行故障转移

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-17_

如果您的 Lync Server 联合身份验证配置所在的边缘池已关闭，则必须将联合身份更改为使用其他边缘池才能正常工作。

<div>

## <a name="failing-over-the-edge-pool-used-for-lync-server-federation"></a>故障切换用于 Lync Server 联合身份验证的边缘池

1.  在前端服务器上，打开拓扑生成器。 展开 "**边缘池**"，然后右键单击当前为联盟配置的边缘服务器或边缘服务器池。 选择 "**编辑属性**"。

2.  在 "**编辑属性**" 下的 "**常规**" 下，清除 "**为此边缘池启用联盟（端口5061）**"。 单击“**确定**”。

3.  展开 "**边缘池**"，然后右键单击要用于联盟的边缘服务器或边缘服务器池。 选择 "**编辑属性**"。

4.  在 "**常规**" 下的 "**编辑属性**" 下，选择 "**为此边缘池启用联盟（端口5061）**"。 单击“**确定**”。

5.  单击 "**操作**"，选择 "**拓扑**"，选择 "**发布**"。 当系统提示**发布拓扑**时，单击 "**下一步**"。 发布完成后，单击 "**完成**"。

6.  在边缘服务器上，打开 "Lync Server 部署向导"。 单击 "**安装或更新 Lync 服务器系统**"，然后单击 "**设置" 或 "删除 lync server 组件**"。 再次单击 "**运行**"。

7.  在 "安装 Lync 服务器组件" 中，单击 "**下一步**"。 "摘要" 屏幕将显示执行时的操作。 部署完成后，单击 "**查看日志**" 以查看可用的日志文件。 单击 "**完成**" 以完成部署。
    
    如果包含失败的 Edge 池的网站包含仍在运行的前端服务器，则必须更新这些前端池上的 Web 会议服务和 A/V 会议服务，才能使用仍在运行的远程网站中的边缘池。 有关详细信息，请参阅[在 Lync Server 2013 中更改与前端池关联的边缘池](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md)  
[在 Lync Server 2013 中对用于 Lync Server 联盟或 XMPP 联盟的边缘池进行故障回复](lync-server-2013-failing-back-the-edge-pool-used-for-lync-server-federation-or-xmpp-federation.md)  


[Lync Server 2013 中的边缘服务器灾难恢复](lync-server-2013-edge-server-disaster-recovery.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

