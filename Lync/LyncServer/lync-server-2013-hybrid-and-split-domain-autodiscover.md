---
title: Lync Server 2013：混合和拆分域-自动发现
description: Lync Server 2013：混合和拆分域自动发现。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 972233fd10d2b68a002d2d3a203f61bb0bd29574
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554878"
---
# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的混合和拆分域自动发现

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-14_

共享 SIP 地址空间（也称为 *拆分域* 部署或 *混合* 部署）是在本地部署和联机环境中部署用户的配置。 所需的结果是，无论用户的主服务器位于何处 (本地或联机) ，都会登录到部署并重定向到其主服务器位置。 为实现此目的，Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。 为此，可以通过使用 Lync Server 命令行管理程序、 **CsHostingProvider** Cmdlet 和 **CsHostingProvider** Cmdlet 来配置自动发现统一资源定位器 (URL) 。

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>拆分域部署的移动性

您需要收集和记录下列部署的属性：

  - 在 Lync Server 命令行管理程序中，键入
    
        Get-CsHostingProvider

  - 在结果中，查找具有属性 **ProxyFQDN** 的在线提供商。 例如，sipfed.online.lync.com。

  - 记录 ProxyFQDN 的值。

  - 在内部部署 Lync Server 控制面板中启用联合，以允许与联机提供程序进行联盟。

  - 为在线提供商启用联盟。 默认情况下，所有联机用户都启用了域联盟，并且可以与所有域进行通信。

  - 如果要定义阻止和允许的域，请确定您将明确允许或显式阻止的域。

  - 对于联机联盟，如果使用 IPv6) 记录，则必须规划防火墙例外、证书和 DNS 主机 (A 或 AAAA。 此外，您还必须配置联盟策略。 有关详细信息，请参阅 [规划 Lync Server 2013 和 Office 通信服务器联合](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

