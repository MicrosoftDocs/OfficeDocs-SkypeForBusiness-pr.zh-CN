---
title: 'Lync Server 2013: 混合和拆分域-自动发现'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hybrid and split-domain - Autodiscover
ms:assetid: c855bcc5-b656-4d2d-92d6-f016f2797d3a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945652(v=OCS.15)
ms:contentKeyID: 51541520
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 389288a695f7e8ed96ab72d16f612ffd92a7b013
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830044"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hybrid-and-split-domain---autodiscover-in-lync-server-2013"></a>Lync Server 2013 中的混合和拆分域自动发现

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-14_

共享 SIP 地址空间 (也称为*拆分域*部署或*混合*部署) 是在内部部署和联机环境中部署用户的配置。 所需的结果是让用户无论其主服务器位于何处 (内部部署还是联机), 登录到部署并被重定向到其主服务器位置。 为了实现此目的, Lync Server 2013 的自动发现功能用于将联机用户重定向到联机拓扑。 你可以通过使用 Lync Server Management Shell、 **CsHostingProvider** Cmdlet 和**CsHostingProvider** cmdlet 配置自动发现统一资源定位器 (URL) 来执行此操作。

<div>

## <a name="mobility-for-the-split-domain-deployment"></a>拆分域部署的移动性

你将需要收集和记录以下已部署的属性:

  - 从 Lync Server 命令行管理程序中, 键入
    
        Get-CsHostingProvider

  - 在结果中, 查找具有属性**ProxyFQDN**的联机提供程序。 例如, sipfed.online.lync.com。

  - 记录 ProxyFQDN 的值。

  - 在本地 Lync Server "控制面板" 中启用联盟, 从而允许与联机提供程序进行联盟。

  - 为联机提供程序启用联盟。 默认情况下, 将为域联盟启用所有联机用户, 并且可以与所有域通信。

  - 如果你要定义阻止的域和允许的域, 请确定你将明确允许或显式阻止的域。

  - 对于联机联盟, 你必须为防火墙例外、证书和 DNS 主机 (如果使用 IPv6) 记录制定计划。 此外, 必须配置联合身份验证策略。 有关详细信息, 请参阅[规划 Lync Server 2013 和 Office 通信服务器联合身份验证](lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

