---
title: Lync Server 2013：为分支用户创建 VoIP 路由策略
TOCTitle: 为分支用户创建 VoIP 路由策略
ms:assetid: 10deca9f-f870-4a42-b25d-e4fc53108658
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398196(v=OCS.15)
ms:contentKeyID: 49312032
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中为分支用户创建 VoIP 路由策略

 

_**上一次修改主题：** 2012-09-23_

建议为分支站点的用户创建单独的 IP 语音 (VoIP) 策略。此策略应包含从 Survivable Branch Appliance 网关或 Survivable Branch Server 外部网关发出的路由以及从中央站点的网关发出的备份路由。无论是在 Survivable Branch Appliance 或 Survivable Branch Server 的注册器上，还是在中央站点的备份注册器群集上注册用户，该用户的 VoIP 策略始终有效。

## 为分支用户配置 VoIP 路由策略

1.  创建用户级拨号计划并将其分配给分支用户。（请参阅操作文档中的 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。）

2.  在该站点上分配与用户的拨号习惯相对应的规范化规则。如果 Survivable Branch Appliance 或 Survivable Branch Server 用户故障转移到中央站点的备份注册器池，则相同的拨号计划将生效。（请参阅操作文档中的 [在 Lync Server 2013 中创建拨号计划](lync-server-2013-create-a-dial-plan.md)。）

3.  配置从 Survivable Branch Appliance 网关或 Survivable Branch Server 外部网关发出的语音路由。（请参阅操作文档中的 [在 Lync Server 2013 中创建语音路由](lync-server-2013-create-a-voice-route.md)。）

4.  在 Survivable Branch Appliance 或 Survivable Branch Server 网关上设置备份呼叫路由以指向中央站点的备份注册器池（与中介服务器并置）。（请参阅 Survivable Branch Appliance 或 Survivable Branch Server 供应商文档。）
    
    > [!NOTE]  
    > 此备份呼叫路由设置可帮助确保在 Survivable Branch Appliance 或 Survivable Branch Server 不可用（如正在停机维护中）时，能够对分支用户进行入站呼叫。如果 Survivable Branch Appliance 或 Survivable Branch Server 上的注册器和中介服务器不可用，并且用户是使用中央站点的备份注册器池注册的，入站呼叫仍可路由到该用户。
    


**下一步**：[在 Lync Server 2013 中配置语音邮件重新路由设置](lync-server-2013-configure-voice-mail-rerouting-settings.md)

