---
title: Lync Server 2013：为分支用户创建 VoIP 路由策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4f53e69069bc1f39f84c057f1e90882d5ae0d65d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830763"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>在 Lync Server 2013 中为分支用户创建 VoIP 路由策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-23_

我们建议为分支站点上的用户创建单独的 IP 语音 (VoIP) 策略。 此策略应包含来自 Survivable 分支装置网关的传出的路由或 Survivable 分支服务器外部网关以及从中心站点的网关传出的传出的备份路由。 无论用户在何处注册, 都可以在 Survivable 分支装置或 Survivable 分支服务器上的注册机构或中心站点的备份注册机构群集上使用, 用户的 VoIP 策略始终有效。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>为分支用户配置 VoIP 路由策略

1.  创建用户级拨号计划, 并将其分配给分支用户。 (请参阅操作文档中的[Lync Server 2013 中的 "创建拨号计划](lync-server-2013-create-a-dial-plan.md)"。)

2.  分配与在该网站上的用户的拨号习惯相对应的规范化规则。 如果 Survivable 分支装置或 Survivable 分支服务器用户故障转移到中心站点的备份注册机构池, 则相同的拨号计划将生效。 (请参阅操作文档中的[Lync Server 2013 中的 "创建拨号计划](lync-server-2013-create-a-dial-plan.md)"。)

3.  配置从 Survivable 分支装置网关或 Survivable 分支服务器外部网关 egresses 的语音路由。 (请参阅在操作文档中在[Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。)

4.  在 Survivable 分支装置或 Survivable 分支服务器网关上设置备份呼叫路由, 以指向中心站点上的备份注册机构池 (collocated 与中介服务器)。 (请参阅 Survivable 分支装置或 Survivable 分支服务器供应商文档。)
    
    <div>
    

    > [!NOTE]  
    > 此备份呼叫路由设置帮助确保在 Survivable 分支设备或 Survivable 分支服务器不可用时, 对分支用户的入站调用将正常工作 (例如, 如果它已关闭)。 如果 Survivable 分支设备或 Survivable 分支服务器上的注册机构和中介服务器不可用, 并且用户已向中心站点上的备份注册机构池注册, 则入站呼叫仍可路由到用户。

    
    </div>

**下一步**:[在 Lync Server 2013 中配置语音邮件重新路由设置](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

