---
title: Lync Server 2013：配置语音邮件重新路由设置
description: Lync Server 2013：配置语音邮件重新路由设置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure voice mail rerouting settings
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398606(v=OCS.15)
ms:contentKeyID: 48184593
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 669ea5585f9e732b6a49d9749b8939c14b4e0d9f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566728"
---
# <a name="configure-voice-mail-rerouting-settings-in-lync-server-2013"></a>在 Lync Server 2013 中配置语音邮件重新路由设置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-18_

Survivable 分支机构和 Survivable 分支服务器可在 WAN 中断期间为分支用户提供语音邮件留存能力（如果 Exchange 统一消息 (UM) 安装在中央站点，并且部署了 Exchange UM 邮件自动助理 (AA) 。 建议 Exchange 管理员将 AA 配置为仅接受消息，禁用其他常规功能，例如转接到用户或接线员的功能。 此外，也可以使用常规 AA 或为路由呼叫而自定义的 AA。

有关详细信息，请参阅规划文档中的 [Lync Server 2013 分支站点恢复要求](lync-server-2013-branch-site-resiliency-requirements.md) 一节中的 "准备语音邮件留存性" 一节。

<div>

## <a name="to-configure-voice-mail-survivability"></a>配置语音邮件生存能力

1.  请求 Exchange 管理员将 AA 配置为仅接受 Exchange 命令行管理器中 (的以下 cmdlet 使用以下 cmdlet： **get-umautoattendant \<AA name\> -CallSomeoneEnabled $false**。 默认情况下，指定允许留言的参数 (*SendVoiceMsgEnabled*) 为 true。

2.  在 Lync Server 命令行管理程序中，使用 **CSVoiceMailReroutingConfiguration** CMDLET 将 AA 电话号码设置为 Survivable 分支设备或 Survivable 分支服务器上的语音邮件重新路由配置中的 Exchange UM 自动助理电话号码。
    
    <div>
    

    > [!NOTE]  
    > 如果以后需要修改语音邮件重新路由设置，请使用 <STRONG>Set-CsVoiceMailReRoutingConfiguration</STRONG> cmdlet 执行相应的操作。 有关 <STRONG>New-</STRONG> 和 <STRONG>Set-CSVoiceMailReroutingConfiguration</STRONG> 的详细信息，请参阅相应的 Shell 帮助主题。

    
    </div>

3.  将与分支用户的 Exchange UM 拨号计划对应的 Exchange UM 订阅者访问号码设置为 Survivable 分支设备或 Survivable 分支服务器上的语音邮件重新路由配置中的 Exchange UM 订阅者访问号码。
    
    <div>
    

    > [!NOTE]  
    > 配置 Exchange UM 用户的拨号计划，以便在 WAN 中断期间需要访问 "获取语音邮件" 功能的所有分支用户都有一个与之关联的拨号计划。

    
    </div>

Survivable 分支装置或 Survivable 分支服务器的**下一步**：[在 Lync Server 2013 中的 Survivable 分支装置或服务器上的家庭用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

