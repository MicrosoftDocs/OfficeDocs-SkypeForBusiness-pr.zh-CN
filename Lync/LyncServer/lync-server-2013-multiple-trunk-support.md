---
title: Lync Server 2013：多个中继支持
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
ms.openlocfilehash: 9d13ca1a28fd28a6d280ddf3a18e57e09376e668
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="multiple-trunk-support-in-lync-server-2013"></a>Lync Server 2013 中的多个中继支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-11-01_

Lync Server 2013 功能支持网关和中介服务器之间的多个关联。 这些关联通过定义主干（这是中介服务器池和公共交换电话网络（PSTN）网关、会话边界控制器（SBC）或 ip-pbx）之间的逻辑关联来进行。 使用拓扑生成器将网关与中介服务器相关联（即中继）。

  - 若要在 Lync Server 2013 中分配或删除主干，必须首先在拓扑生成器中定义一个主干。 主干包含以下关联：中介服务器完全限定的域名（FQDN）、中介服务器侦听端口、网关 FQDN 和网关侦听端口。

  - 若要配置多个中继，可以在同一网关和中介服务器之间创建多个关联。 这将为企业语音基础结构提供额外的复原，这在专用分支 exchange （PBX） interoperational 方案中尤其有用。

定义中继，必须将其与路由关联。 若要将主干关联到路由，请为拓扑生成器中的主干定义一个简单名称。 此简单名称用作 Lync Server 控制面板中的主干名称，其中中继可以与路由相关联。 简单主干名称用作 Lync Server 命令行管理程序中的网关名称。

    New-CsVoiceRoute -Identity <RouteId> -NumberPattern <String> -PstnUsages @{add="<UsageString>"} -PstnGatewayList @{add="<TrunkSimpleName>"}

管理员必须选择与中介服务器关联的默认中继。 从拓扑生成器中，右键单击关联的中介服务器，然后单击 "**属性**"。 指定中介服务器的默认网关。

下图显示了为每个中介服务器和网关定义的多个中继。

**M-N 中继路由**

![多个中继分配。](images/JJ205127.c61cd9a7-d8d9-4e02-83b9-ab62519a48c4(OCS.15).jpg "多个中继分配。")

</div>

<span> </span>

</div>

</div>

</div>

