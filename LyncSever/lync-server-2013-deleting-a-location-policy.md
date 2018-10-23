---
title: 删除位置策略
TOCTitle: 删除位置策略
ms:assetid: 8ca9ba10-f45f-435a-b39c-519d251e9085
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688125(v=OCS.15)
ms:contentKeyID: 49888500
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除位置策略

 

_**上一次修改主题：** 2012-10-10_

在 Lync Server 2013 中，您可以使用位置策略应用与增强型 9-1-1 (E9-1-1) 功能相关和与用户或联系人的位置设置相关的设置。位置策略可确定用户是否启用了 E9-1-1，以及在启用了该服务时紧急呼叫的行为。例如，您可以使用位置策略定义哪些数字构成紧急呼叫（例如，美国的 911）、是否应自动通知企业安全人员以及应如何路由该呼叫。

您可以在 Lync Server 2013 控制面板中的“网络配置”组中配置位置策略。在 Lync Server 控制面板中，您可以查看、创建、修改或删除位置策略。使用以下过程删除位置策略。有关创建或修改位置策略的详细信息，请参阅[创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)。

## 删除位置策略

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“位置策略”。

4.  在“位置策略”页上，选择要删除的位置策略。
    
    > [!NOTE]  
    > 可一次性删除多个位置策略。要执行此操作，请按住 Ctrl 键，同时选择多个策略。或者，要选中全部策略，请单击“编辑”菜单中的“全选”。
    


5.  在“编辑”菜单上，单击“删除”。

6.  单击“确定”。
    
    > [!IMPORTANT]
    > 无法删除“全局”位置策略。如果尝试删除“全局”策略，您将收到一条警告消息，而该策略将重置为其默认值。


## 另请参阅

#### 任务

[创建或修改位置策略](lync-server-2013-creating-or-modifying-a-location-policy.md)  
[查看位置策略信息](lync-server-2013-viewing-location-policy-information.md)

