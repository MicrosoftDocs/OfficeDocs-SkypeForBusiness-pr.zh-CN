---
title: Lync Server 2013：多中继支持
description: Lync Server 2013：支持多个中继。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Multiple trunk support
ms:assetid: a1309c09-ad9a-4c54-9650-4e3f5b2a4a00
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205127(v=OCS.15)
ms:contentKeyID: 48184948
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3bbabb90405b3fdae47a59ba8a0798743943216d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48552418"
---
# <a name="multiple-trunk-support-in-lync-server-2013"></a>Lync Server 2013 中的多中继支持

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-11-01_

Lync Server 2013 功能支持网关和中介服务器之间的多个关联。 这些关联通过定义中继进行，这是中介服务器池与公开交换电话网络之间的逻辑关联 (PSTN) 网关、会话边界控制器 (SBC) 或 ip-pbx。 使用拓扑生成器将网关与中介服务器关联 (即中继) 。

  - 若要在 Lync Server 2013 中分配或删除中继，必须首先在拓扑生成器中定义一个中继。 中继包含以下关联：中介服务器完全限定的域名 (FQDN) 、中介服务器侦听端口、网关 FQDN 和网关侦听端口。

  - 若要配置多个中继，可以在同一个网关和中介服务器之间创建多个关联。 这为企业语音基础结构提供了额外的恢复能力，这在专用分支 exchange (PBX) interoperational 方案中尤其有用。

定义中继，必须将其与路由关联。 若要将中继与路由关联，请在拓扑生成器中定义中继的简单名称。 此简单名称在 Lync Server 控制面板中用作中继名称，其中中继可与路由关联。 简单中继名称将用作 Lync Server 命令行管理程序中的网关名称。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

管理员必须选择与中介服务器关联的默认中继。 在拓扑生成器中，右键单击关联的中介服务器，然后单击 " **属性**"。 指定中介服务器的默认网关。

下图说明了为每个中介服务器和网关定义的多个中继。

**M-N 中继路由**

![多个中继分配。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多个中继分配。")

</div>

<span> </span>

</div>

</div>

</div>

