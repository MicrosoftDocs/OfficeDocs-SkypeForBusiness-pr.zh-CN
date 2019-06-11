---
title: Lync Server 2013：对用于 XMPP 联盟的边缘池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 551774c070ebafd25376d220b20acccc8c573af2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830161"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-10-19_

在你的组织中, 有一个边界池指定为用于 XMPP 联合身份验证的池。 如果此池停止运行, 则必须故障转移 XMPP 联合身份验证才能使用其他边缘池, 然后 XMPP 联盟才能再次工作。

当你首次安装 Edge 池并启用 XMPP 联合身份验证时, 你可以通过为 XMPP 联盟的所有边缘池设置外部 DNS SRV 记录 (而不是仅一个) 来简化灾难恢复过程。 其中每个 SRV 记录都必须具有不同的优先级集。 所有 XMPP 联盟流量都将经历具有最高优先级的 SRV 记录的池。 有关启用和设置 XMPP 联合身份验证的详细信息, 请参阅[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)。

在以下过程中, EdgePool1 是最初托管 XMPP 联盟的池, EdgePool2 是池, 它现在将托管 XMPP 联合。

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>故障切换用于 XMPP 联盟的边缘池

1.  如果尚未部署另一个边缘池 (除了当前已关闭的), 请部署该池。 有关详细信息, 请参阅[在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

2.  在现在将托管 XMPP 联合身份验证 (EdgePool2) 的新边缘池中的每个边缘服务器上, 运行以下 cmdlet:
    
        Stop-CsWindowsService

3.  运行以下 cmdlet 以将 XMPP 联盟路由 repoint 到 EdgePool2:
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在此示例中, Site2 是包含边缘池的网站, 它现在将托管 XMPP 联合路由, EdgeServer2.contoso.com 是该池中的边缘服务器的 FQDN。

4.  在外部 DNS 服务器上, 将 XMPP 联合的 DNS A 记录更改为指向 EdgeServer2.contoso.com。

5.  如果你还没有可解析为 XMPP 联合的 DNS SRV 记录, 并且该记录将托管到将托管 XMPP 联合的边缘池, 则必须添加它, 如下例所示。 此 SRV 记录必须具有端口值5269。
    
        _xmpp-server._tcp.contoso.com

6.  验证现在将托管 XMPP 联合身份验证的边缘池是否具有端口5269在外部打开。

7.  在边缘池中的所有边缘服务器上启动服务, 现在将托管 XMPP 联合身份验证:
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

