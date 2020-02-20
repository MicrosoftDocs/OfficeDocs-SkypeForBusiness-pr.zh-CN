---
title: Lync Server 2013：对用于 XMPP 联盟的边缘池进行故障转移
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Failing over the Edge pool used for XMPP federation
ms:assetid: 587e7829-a26b-46f8-8aad-b78a7b325b55
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688065(v=OCS.15)
ms:contentKeyID: 49733659
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 182bc427c7b4faf3bd937bd58af8ca1d4d9c7d77
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145821"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="failing-over-the-edge-pool-used-for-xmpp-federation-in-lync-server-2013"></a>在 Lync Server 2013 中对用于 XMPP 联盟的边缘池进行故障转移

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-19_

在您的组织中，已将一个边缘池指定为用于 XMPP 联盟的池。如果该池出现故障，您必须先对 XMPP 联盟进行故障转移以使用其他边缘池，直到 XMPP 联盟可重新正常工作。

在您首次安装边缘池并启用 XMPP 联盟时，您可以通过为 XMPP 联盟的所有（而不只是一个）边缘池设置外部 DNS SRV 记录来简化灾难恢复过程。 所有这些 SRV 记录都必须具有不同的优先级设置。 所有 XMPP 联盟流量将通过具有优先级最高的 SRV 记录的池。 有关启用和设置 XMPP 联盟的详细信息，请参阅[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)。

在以下过程中，EdgePool1 是最初承载 XMPP 联盟的池，EdgePool2 是现在承载 XMPP 联盟的池。

<div>

## <a name="failing-over-the-edge-pool-used-for-xmpp-federation"></a>对用于 XMPP 联盟的边缘池进行故障转移

1.  如果您尚未部署另一个边缘池（当前出现故障的边缘池之外的池），请部署该池。 有关详细信息，请参阅[在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)。

2.  在现在承载 XMPP 联盟的新边缘池 (EdgePool2) 中的每个边缘服务器上，运行以下 cmdlet：
    
        Stop-CsWindowsService

3.  运行以下 cmdlet 可将 XMPP 联盟路由重新指向 EdgePool2：
    
        Set-CsSite Site2 -XmppExternalFederationRoute EdgeServer2.contoso.com
    
    在此示例中，Site2 是包括现在承载 XMPP 联盟路由的边缘池的站点，EdgeServer2.contoso.com 是该池中某个边缘服务器的 FQDN。

4.  在外部 DNS 服务器上，将 XMPP 联盟的 DNS A 记录更改为指向 EdgeServer2.contoso.com。

5.  如果您尚不具有解析为现在承载 XMPP 联盟的边缘池的 XMPP 联盟的 DNS SRV 记录，则必须添加它，如以下示例中所示。此 SRV 记录的端口值必须为 5269。
    
        _xmpp-server._tcp.contoso.com

6.  确认现在承载 XMPP 联盟的边缘池具有已外部打开的端口 5269。

7.  在现在承载 XMPP 联盟的边缘池中的所有边缘服务器上启动服务：
    
        Start-CsWindowsService

</div>

</div>

<span> </span>

</div>

</div>

</div>

