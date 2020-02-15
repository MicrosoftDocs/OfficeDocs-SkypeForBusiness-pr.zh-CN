---
title: Lync Server 2013：定义企业语音要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Defining your organization's requirements for Enterprise Voice
ms:assetid: 3310f78e-c658-4557-95fa-159ce3c22953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425826(v=OCS.15)
ms:contentKeyID: 48183816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d88a70796282fe09941ce7632d8c13258defc515
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42032154"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="defining-your-requirements-for-enterprise-voice-in-lync-server-2013"></a>在 Lync Server 2013 中定义对企业语音的要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-08-07_

本主题概述了您需要对拓扑中的区域、网站和链接之间的注意事项以及在部署企业语音时这些网站的重要性。 有关帮助您做出这些决策的详细信息，请参阅规划文档中的[Lync Server 2013 中的 "高级企业语音功能的网络设置](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)"。

<div>

## <a name="sites-and-regions"></a>站点和区域

首先，确定您的拓扑中的网站，您将在其中部署企业语音和这些网站所属的网络区域。 特别是，考虑如何将公用电话交换网 (PSTN) 连接到每个站点。 由于可管理性和物流方面的原因，这些站点所属的区域可能是一个决定性因素。 确定在本地部署网关的位置，将在其中部署 Survivable 分支机构（Sba），并且可以在哪里配置 SIP 中继（本地或在中央站点）到 Internet 电话服务提供商（ITSP）。

</div>

<div>

## <a name="network-links-between-sites"></a>站点之间的网络链路

您还需要考虑您在中央站点与其分支站点之间的网络链接上所需的带宽使用率。 如果您有或计划在站点之间部署弹性 WAN 链接，我们建议您在每个分支站点部署一个网关，以便为这些站点上的用户提供本地的直接向内拨号（已）终端。 如果具有可恢复 WAN 链路，但 WAN 链路上的带宽可能被限定，则需要为该链路配置呼叫允许控制。 如果没有可恢复的 WAN 链路，请在分支站点上托管少于1000个用户，并且没有本地训练有素的 Lync Server 管理员，我们建议您在分支站点部署 Survivable 分支设备。 如果你在分支站点上托管1000和5000用户，缺少弹性 WAN 连接，并且已培训的 Lync Server 管理员可用，我们建议您在分支站点上部署具有小型网关的 Survivable 分支服务器。 如果具有支持媒体旁路功能的对等网关，则也可以考虑在限定链路上启用媒体旁路功能。

</div>

<div>

## <a name="see-also"></a>另请参阅


[Lync Server 2013 中的高级企业语音功能的网络设置](lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

