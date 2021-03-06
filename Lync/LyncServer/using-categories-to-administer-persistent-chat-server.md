﻿---
title: 使用类别管理持久聊天服务器
TOCTitle: 使用类别管理持久聊天服务器
ms:assetid: dfcb3ad1-da90-467e-b08c-f4e68673b7b5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398988(v=OCS.15)
ms:contentKeyID: 49314490
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 使用类别管理持久聊天服务器

 

_**上一次修改主题：** 2013-10-01_

持久聊天服务器部署可以托管许多并发 持久聊天聊天室。聊天室可以组织到服务器上的一组类别中。每个聊天室属于一个类别，并继承该类别的一些设置。这种组织方式可创建一种非常有用的结构以基于对话的业务目的识别对话，并有助于委托管理和简化控制。

> [!NOTE]  
> 尽管聊天室的许多管理功能在运行 持久聊天（ Lync 客户端）的计算机上对于用户都可用，但 持久聊天管理员（ <strong>cspersistentchatadministrator</strong> 角色中）必须使用 Lync Server 控制面板或 Windows PowerShell cmdlet 创建或管理类别。


持久聊天管理员使用 Lync Server 控制面板或 Windows PowerShell cmdlet 创建和管理类别，并为组织中的用户设计聊天室的访问权限。

持久聊天 室管理员能够管理一个或多个聊天室，可以使用 Lync 客户端启动聊天室管理 Web 应用程序创建和管理聊天室（或者客户可以创建自定义解决方案和要调用的工作流）。 持久聊天管理员还可以使用 Lync Server 控制面板或 Windows PowerShell cmdlet 创建和管理聊天室。

> [!NOTE]  
> 持久聊天 聊天室的名称不能与 持久聊天 类别相同。


除了更改聊天室类别之外，聊天室管理员还可以更改所有聊天室属性。不能限制其执行以下操作：

  - 禁用聊天室

  - 更改聊天室名称

  - 更改聊天室说明

  - 更改聊天室类型（大会堂还是普通）

  - 更改聊天室隐私（开放、关闭还是秘密）

  - 添加或删除成员

  - 添加或删除聊天室管理者

  - 添加或删除加载项

  - 更改邀请之类的设置（根据类别允许的内容）

## 委托管理

通过正确使用类别，可以更轻松地创建和管理 持久聊天聊天室。 持久聊天管理员可以定义每个类别的 **AllowedMembers** 和 **Creators**，还可以定义将应用于在该类别中创建的所有聊天室的默认聊天室设置和行为。 持久聊天管理员可以通过使用 Lync Server 控制面板或 Windows PowerShell cmdlet 来创建和管理类别。

标识为类别创建者的用户、组织单位 (OU) 和用户组是仅有的被允许在类别中创建聊天室的个人和组。创建类别后，他们可以从类别的 **AllowedMembers** 列表中选择用户、OU 和用户组作为聊天室的管理员和成员来管理和参与聊天室。

在类别中创建的聊天室应遵守该类别强制的策略和设置（如谁可以是聊天室的成员、谁可以管理聊天室、是否允许文件上载、是否发送邀请等等）。

