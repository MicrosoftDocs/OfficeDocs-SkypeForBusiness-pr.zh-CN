---
title: Lync Server 2013：关于网络区域、站点和子网
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: About network regions, sites, and subnets
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398467(v=OCS.15)
ms:contentKeyID: 48184335
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4fe7b93f00ce7af6354fa8a1bc94c104f3af14f
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523209"
---
# <a name="about-network-regions-sites-and-subnets-in-lync-server-2013"></a>关于 Lync Server 2013 中的网络区域、站点和子网

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-24_

本节所述的高级企业语音功能共享了网络区域、网络站点和子网的某些配置要求。例如，三种高级功能都要求拓扑中的每个子网与特定*网络站点* 关联，而每个网络站点必须与*网络区域* 关联。

<div>


> [!IMPORTANT]  
> 在为呼叫允许控制、E9-1-1 或媒体旁路配置网络配置之前，请务必阅读规划文档中的 " <A href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中的高级企业语音功能的网络设置</A> " 中的 "网络设置" 中的其他信息。 有关主要有关呼叫允许控制的网络配置的详细信息，请参阅规划文档中的在 <A href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">Lync Server 2013 中定义呼叫允许控制的要求</A> 。



</div>

呼叫允许控制和 E9-1-1 对网络站点具有其他配置要求：

  - 呼叫允许控制要求为由 WAN 带宽限制限定的每个站点指定*带宽策略配置文件*。 如果您计划部署呼叫允许控制，则必须在配置网络站点之前 [在 Lync Server 2013 中创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md) 。

  - E9-1-1 要求为每个站点指定*位置策略*。 如果您计划部署 E9-1-1，则必须在配置网络站点之前 [在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md) 。

<div>

## <a name="create-or-modify-network-regions-network-sites-and-subnets"></a>创建或修改网络区域、网络站点和子网

以下主题提供有关创建或修改网络区域和网络站点，以及将子网与网络站点关联的步骤。这些主题不特定于任何特定高级企业语音功能。

  - [在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)

  - [在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)

  - [在 Lync Server 2013 中将子网与网络站点关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

