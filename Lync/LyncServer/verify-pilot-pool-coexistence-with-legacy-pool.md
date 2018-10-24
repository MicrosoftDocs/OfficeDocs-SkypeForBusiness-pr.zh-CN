---
title: 验证试点池与旧池的共存情况
TOCTitle: 验证试点池与旧池的共存情况
ms:assetid: fe7e14bb-c7eb-4719-b154-009e99360520
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205420(v=OCS.15)
ms:contentKeyID: 49314860
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 验证试点池与旧池的共存情况

 

_**上一次修改主题：** 2012-09-29_

部署试点池之后，需要使用管理工具查看池信息来验证两个池是否共存。对于 Lync Server 2013 池和旧版池，您必须使用 Lync Server 2013 控制面板和拓扑生成器工具。

## 确认已启动 Lync Server 2013 服务

1.  从 Lync Server 2013 前端服务器导航到管理员工具\\Services 小程序。

2.  确认以下服务正在前端服务器上运行：

**Lync Server 2013 服务**

![启动的 Lync Server 服务的列表](images/JJ205420.cfff9385-6bf6-461c-982c-e727c9f20b70(OCS.15).png "启动的 Lync Server 服务的列表")

## 打开 Lync Server 2013 控制面板

从 Lync Server 2013 部署中的前端服务器中，打开 Lync Server 2013 控制面板，然后选择 Lync Server 2010 池。重复此过程可打开 Lync Server 2013 池。

**打开 Lync Server 2013 控制面板**

![“选择 URL”对话框](images/JJ205420.b1f8e650-9c3c-4563-a403-5069f198342f(OCS.15).png "“选择 URL”对话框")

> [!IMPORTANT]
> 在 Lync Server 2013 上，必须先将 Silverlight 升级到 Silverlight 版本 5，然后才能使用 Lync Server 控制面板。


此拓扑现在包含 Lync Server 2010 和 Lync Server 2013 服务器角色。

**“Lync Server 2013 控制面板拓扑”页**

![Lync Server 控制面板 - “拓扑”页](images/JJ205420.4ed1cc7a-cb3e-42f6-82e2-6d4d71d19352(OCS.15).jpg "Lync Server 控制面板 - “拓扑”页")

## 请勿尝试使用 Lync Server 2010 拓扑生成器打开拓扑

如果您尝试使用 Lync Server 2010 拓扑生成器打开拓扑，则将遇到以下错误。拓扑只能使用 Lync Server 2013 拓扑生成器进行查看。 Lync Server 2013 拓扑生成器必须用于为 Lync Server 2013 和 Lync Server 2010 创建池。

**Lync Server 2010 拓扑生成器错误消息**

![Lync Server - 拓扑生成器 MMC 单元错误](images/JJ205420.f6666343-c348-4d81-ae0e-6ba5a44e16c4(OCS.15).png "Lync Server - 拓扑生成器 MMC 单元错误")

