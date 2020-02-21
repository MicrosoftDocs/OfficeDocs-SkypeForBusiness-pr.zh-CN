---
title: Lync Server 2013：为分支用户创建 VoIP 路由策略
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
ms.openlocfilehash: 7cc958e5f643a18c45989d5835fd786c001899db
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42179709"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-the-voip-routing-policy-for-branch-users-in-lync-server-2013"></a>在 Lync Server 2013 中为分支用户创建 VoIP 路由策略

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-23_

建议为分支站点的用户创建单独的 IP 语音 (VoIP) 策略。 此策略应包含来自 Survivable 分支装置网关或 Survivable 分支服务器外部网关的传出的路由，以及从中央站点的网关传出的备份路由。 无论用户是在 Survivable 分支机构或 Survivable 分支服务器上的注册器上或在中央站点的备份注册器群集上注册的，用户的 VoIP 策略始终有效。

<div>

## <a name="to-configure-the-voip-routing-policy-for-branch-users"></a>为分支用户配置 VoIP 路由策略

1.  创建用户级别拨号计划并将其分配给分支用户。 （请参阅操作文档中的在[Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。）

2.  分配与该网站用户的拨号习惯相对应的规范化规则。 如果 Survivable 分支装置或 Survivable 分支服务器用户故障转移到中央站点的备份注册器池，则相同的拨号计划将生效。 （请参阅操作文档中的在[Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。）

3.  配置发出来自 Survivable 分支装置网关或 Survivable 分支服务器外部网关的语音路由。 （请参阅操作文档中的在[Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。）

4.  将 Survivable 分支装置或 Survivable 分支服务器网关上的备份呼叫路由设置为指向中央站点的备份注册器池（并置 with 中介服务器）。 （请参阅 Survivable Branch 设备或 Survivable Branch Server 供应商文档。）
    
    <div>
    

    > [!NOTE]  
    > 此备份呼叫路由设置有助于确保在 Survivable 分支设备或 Survivable 分支服务器不可用时，分支用户的入站呼叫将正常运行（例如，如果在维护时关闭）。 如果 Survivable 分支设备或 Survivable 分支服务器上的注册器和中介服务器不可用，并且用户注册到中央站点的备份注册器池，则仍可以将入站呼叫路由到用户。

    
    </div>

**下一步**：[在 Lync Server 2013 中配置语音邮件重新路由设置](lync-server-2013-configure-voice-mail-rerouting-settings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

