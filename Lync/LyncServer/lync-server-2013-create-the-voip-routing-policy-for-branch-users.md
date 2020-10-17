---
title: Lync Server 2013：为分支用户创建 VoIP 路由策略
description: Lync Server 2013：为分支用户创建 VoIP 路由策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create the VoIP routing policy for branch users
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398196(v=OCS.15)
ms:contentKeyID: 48183435
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c39cff86d9ede957fa99e7955d8a87172380f963
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48551078"
---
# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>在 Lync Server 2013 中为分支用户创建 VoIP 路由策略

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-23_

建议为分支站点的用户创建单独的 IP 语音 (VoIP) 策略。 此策略应包含来自 Survivable 分支装置网关或 Survivable 分支服务器外部网关的传出的路由，以及从中央站点的网关传出的备份路由。 无论用户是在 Survivable 分支机构或 Survivable 分支服务器上的注册器上或在中央站点的备份注册器群集上注册的，用户的 VoIP 策略始终有效。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>为分支用户配置 VoIP 路由策略

1.  创建用户级别拨号计划并将其分配给分支用户。  (请参阅操作文档中的在 [Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md) 。 ) 

2.  分配与该网站用户的拨号习惯相对应的规范化规则。 如果 Survivable 分支装置或 Survivable 分支服务器用户故障转移到中央站点的备份注册器池，则相同的拨号计划将生效。  (请参阅操作文档中的在 [Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md) 。 ) 

3.  配置发出来自 Survivable 分支装置网关或 Survivable 分支服务器外部网关的语音路由。  (请参阅操作文档中的在 [Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md) 。 ) 

4.  在 Survivable 分支装置或 Survivable Branch Server gateway 上设置一个备份呼叫路由，以指向在中央站点上使用中介服务器) 的备份注册器池 (并置。  (请参阅 Survivable Branch 装置或 Survivable Branch Server 供应商文档。 ) 
    
    <div>
    

    > [!NOTE]  
    > 此备份呼叫路由设置有助于确保在 Survivable 分支设备或 Survivable 分支服务器不可用时，分支用户的入站呼叫将正常工作 (例如，如果它处于关闭状态以供维护) 。 如果 Survivable 分支设备或 Survivable 分支服务器上的注册器和中介服务器不可用，并且用户注册到中央站点的备份注册器池，则仍可以将入站呼叫路由到用户。

    
    </div>

**下一步**： [在 Lync Server 2013 中配置语音邮件重新路由设置](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

