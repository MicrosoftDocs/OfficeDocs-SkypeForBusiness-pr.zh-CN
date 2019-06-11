---
title: Lync Server 2013：关于网络区域、站点和子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ef6601a0baafd1226f4e283d62a8cbdb410064ff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837979"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>关于 Lync Server 2013 中的网络区域、站点和子网

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-24_

本部分中所述的高级企业语音功能共享网络区域、网络站点和子网的某些配置要求。 例如, 所有三个高级功能都要求拓扑中的每个子网都与特定*网络站点*相关联, 并且每个网络站点必须与一个*网络区域*相关联。

<div>


> [!IMPORTANT]  
> 在开始呼叫许可控制、E9-1 或媒体绕过的网络配置之前, 请确保你查看了有关<A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的高级企业语音功能的网络设置</A>中的网络设置的其他信息计划文档中的主题。 有关网络配置的详细信息, 主要介绍呼叫许可控制, 请参阅规划文档中的<A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 中的 "定义呼叫许可控制要求</A>"。



</div>

呼叫允许控制和 E9-1-1 对网络站点具有其他配置要求：

  - 呼叫允许控制要求为由 WAN 带宽限制限定的每个站点指定*带宽策略配置文件*。 如果你计划部署呼叫许可控制, 则必须先[在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md), 然后再配置你的网络站点。

  - E9-1-1 要求为每个站点指定*位置策略*。 如果你计划部署 E9-1, 则必须先[在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md), 然后才能配置你的网络网站。

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>创建或修改网络区域、网络站点和子网

以下主题提供创建或修改网络区域和网络站点以及将子网与网络站点相关联的步骤。 这些主题并非特定于任何特定的高级企业语音功能。

  - [在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)

  - [在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)

  - [在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

