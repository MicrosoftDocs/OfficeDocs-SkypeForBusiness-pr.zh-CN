---
title: 查看受信任应用程序列表
TOCTitle: 查看受信任应用程序列表
ms:assetid: f09300b3-67cf-4e70-a51a-23d62479b913
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182604(v=OCS.15)
ms:contentKeyID: 49314691
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看受信任应用程序列表

 

_**上一次修改主题：** 2012-09-21_

可以使用 Lync Server 2013 控制面板查看在 Lync Server 2013 环境中部署的受信任应用程序列表。受信任应用程序是基于 Microsoft 统一通信托管 API (UCMA) 3.0 核心 SDK 且受 Lync Server 2013 信任的应用程序。以下列表概述了此信任关系：

  - Lync Server 不会要求对受信任应用程序进行身份验证。

  - Lync Server 不会限制受信任应用程序进行 SIP 事务、连接或传出 IP 语音 (VoIP) 呼叫。

  - 受信任应用程序可模拟任何用户，并能在不出现在名单中的情况下参加会议。

  - 受信任应用程序具有高可用性和恢复能力。

在 Lync Server 控制面板中，可以看到这些应用程序的名称、它们运行时所在的池以及它们使用的端口。

## 查看受信任应用程序列表

1.  使用分配给 CsServerAdministrator、CsAdministrator、CsHelpDesk 或 CsViewOnlyAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。有关 Lync Server 2013 中提供的预定义管理角色的详细信息，请参阅[在 Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“拓扑”，然后单击“受信任应用程序”。

4.  在“受信任应用程序”页上，单击某个列标题对应用程序进行排序（如果需要）。

## 另请参阅

#### 其他资源

[管理 Lync Server 2013 拓扑](lync-server-2013-managing-the-lync-server-topology.md)

