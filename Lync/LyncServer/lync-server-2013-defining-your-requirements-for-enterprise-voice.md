---
title: Lync Server 2013：定义企业语音要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f0ce05c39e3433ff949d82f583207aebfba871fc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830682"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中定义企业语音要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-08-07_

本主题概述了在你的拓扑中对网站之间的区域、网站和链接以及这些内容在你部署企业语音时的重要因素。 有关有助于做出这些决策的详细信息, 请参阅规划文档中[Lync Server 2013 中的高级企业语音功能的网络设置](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)。

<div>

## <a name="sites-and-regions"></a>网站和区域

首先, 确定你的拓扑中的网站, 你将在这些网站中部署企业语音和这些网站所属的网络区域。 特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。 由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。 确定本地部署网关的位置 (将部署 Survivable 分支装置 (SBAs)), 以及你可以在哪里将 SIP 中继 (本地或中央网站) 配置为 Internet 电话服务提供商 (ITSP)。

</div>

<div>

## <a name="network-links-between-sites"></a>网站之间的网络链接

您还需要考虑您的中心站点与其分支站点之间网络链接所期望的带宽使用情况。 如果你拥有或计划在网站之间部署弹性 WAN 链接, 我们建议你在每个分支站点上部署网关, 以便为用户在这些网站上提供本地直接向内拨号 (已) 终止。 如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。 如果您没有弹性 WAN 链接, 在您的分支站点上托管的用户少于1000个用户, 并且没有本地训练有素的 Lync 服务器管理员可用, 我们建议您在分支站点部署 Survivable 分支装置。 如果你在分支站点上的1000和5000用户之间托管, 缺少弹性 WAN 连接, 并且有经过培训的 Lync 服务器管理员可用, 我们建议你在分支站点上使用小型网关部署 Survivable 分支服务器。 如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Network settings for the advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

