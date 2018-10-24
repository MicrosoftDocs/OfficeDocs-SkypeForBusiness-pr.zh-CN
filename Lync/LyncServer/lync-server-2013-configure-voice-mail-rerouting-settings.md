---
title: Lync Server 2013：配置语音邮件重新路由设置
TOCTitle: 配置语音邮件重新路由设置
ms:assetid: 7ab6be28-eabb-4a79-a796-648887d71b83
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398606(v=OCS.15)
ms:contentKeyID: 49313356
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置语音邮件重新路由设置

 

_**上一次修改主题：** 2012-10-18_

如果在中央站点安装了 Exchange 统一消息 (UM)，并且部署了 Exchange UM 消息自动助理 (AA)，则 Survivable Branch Appliance 和 Survivable Branch Server 可以在 WAN 中断期间为分支用户提供语音邮件生存能力。建议 Exchange 管理员将 AA 配置为仅接受消息，禁用其他常规功能，例如转接到用户或接线员的功能。此外，也可以使用常规 AA 或为路由呼叫而自定义的 AA。

有关详细信息，请参阅规划文档中的[Lync Server 2013 的分支站点恢复能力要求](lync-server-2013-branch-site-resiliency-requirements.md)的“准备语音邮件生存能力”一节。

## 配置语音邮件生存能力

1.  要求 Exchange 管理员将 AA 配置为仅接受消息（在 Exchange Shell 中，使用以下 cmdlet： **Set-UMAutoAttendant \<AA name\> -CallSomeoneEnabled $false**）。默认情况下，指定允许留言的参数 ( *SendVoiceMsgEnabled*) 为 true。

2.  在 Lync Server 命令行管理程序 中，使用 **New-CSVoiceMailReroutingConfiguration** cmdlet 将 AA 电话号码设置为 Survivable Branch Appliance 或 Survivable Branch Server 上语音邮件重新路由配置中的 Exchange UM 自动助理电话号码。
    
    > [!NOTE]  
    > 如果以后需要修改语音邮件重新路由设置，请使用 <strong>Set-CsVoiceMailReRoutingConfiguration</strong> cmdlet 执行相应的操作。有关 <strong>New-</strong> 和 <strong>Set-CSVoiceMailReroutingConfiguration</strong> 的详细信息，请参阅相应的 Shell 帮助主题。
    


3.  将对应于分支用户的 Exchange UM 拨号计划的 Exchange UM 订阅者访问号码设置为 Survivable Branch Appliance 或 Survivable Branch Server 上语音邮件重新路由配置中的 Exchange UM 订阅者访问号码。
    
    > [!NOTE]  
    > 对 Exchange UM 用户的拨号计划进行配置，以便只有一个拨号计划与 WAN 中断期间需要访问“获取语音邮件”功能的所有分支用户相关联。
    


Survivable Branch Appliance 或 Survivable Branch Server 的 **后续步骤** ： [在 Lync Server 2013 中在 Survivable Branch Appliance 或 Survivable Branch Server 上承载用户](lync-server-2013-home-users-on-a-survivable-branch-appliance-or-server.md)。

