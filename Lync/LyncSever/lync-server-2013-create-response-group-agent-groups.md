---
title: Lync Server 2013：创建响应组代理组
TOCTitle: 创建响应组代理组
ms:assetid: 2a80de17-ead0-46e8-8a27-7a4e233dbde0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520969(v=OCS.15)
ms:contentKeyID: 49312333
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建响应组代理组

 

_**上一次修改主题：** 2012-09-12_

创建代理组时要选择分配给该组的代理并指定其他组设置，如路由方法以及代理能否登录到组和从组注销。

必须登录到组和从组注销（与登录到 Lync Server 或从中注销不同）的代理称为 *正式代理* 。正式代理必须登录到组，然后才能接收路由至该组的呼叫。这对于以兼职形式应答组中的呼叫的代理很有用。正式代理通过单击 Lync 2013 中的菜单项打开 Windows Internet Explorer Internet 浏览器并显示网页控制台，以登录到组或从组注销。

不登录到组或从组注销的代理称为 *非正式代理* 。非正式代理登录到 Lync Server 后，将自动登录到组，但无法从组注销。

> [!NOTE]  
> 仅本地用户可成为代理。如果一个代理从本地移至联机，则 响应组呼叫将不会被路由到该代理。



## 本部分内容

[在 Lync Server 2013 中创建或修改代理组](lync-server-2013-create-or-modify-an-agent-group.md)

