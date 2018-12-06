---
title: 禁用网络媒体旁路
TOCTitle: 禁用网络媒体旁路
ms:assetid: 936d2678-d712-4589-b172-b5793013652f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688141(v=OCS.15)
ms:contentKeyID: 49888517
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 禁用网络媒体旁路

 

_**上一次修改主题：** 2012-10-15_

媒体旁路设置会全局应用到整个 Microsoft Lync Server 2013 部署。媒体旁路功能允许呼叫绕过中介服务器。有关何时使用媒体旁路的详细信息，请参阅“规划”一节中的[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)。可以通过 Lync Server 控制面板禁用媒体旁路。有关启用和配置媒体旁路的详细信息，请参阅[启用网络媒体绕过](lync-server-2013-enabling-network-media-bypass.md)

## 禁用媒体旁路

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“网络配置”，然后单击“全局”。

4.  在“全局”页上，单击“全局”配置。始终只有一个配置，且始终命名为“全局”。

5.  在“编辑”菜单上，单击“查看详细信息”。

6.  在“编辑全局设置”页上，清除“启用媒体旁路”复选框。

7.  单击“提交”保存所做的更改。

## 另请参阅

#### 任务

[启用网络媒体绕过](lync-server-2013-enabling-network-media-bypass.md)

