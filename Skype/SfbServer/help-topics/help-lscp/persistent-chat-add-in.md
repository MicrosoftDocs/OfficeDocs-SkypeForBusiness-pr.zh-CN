---
title: 持久聊天外接程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 持久聊天页的外接程序部分可用于将 Url 与持久聊天聊天室相关联。 这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。 管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。
ms.openlocfilehash: b1a601ab1ecfa1b188f291534af914daef1037c3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33910530"
---
# <a name="persistent-chat-add-in"></a>持久聊天外接程序

**持久聊天**页的**外接程序**部分可用于将 Url 与持久聊天聊天室相关联。 这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。 管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。

外接程序用于扩展聊天室内体验。 典型的加载项可能包含指向截获当股票代码张贴到聊天室，并将扩展性窗格中显示库存的历史记录的 Silverlight 应用程序的 URL。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。

若要创建的持久聊天聊天室加载项，请参阅[配置外接程序中的业务服务器 2015 Skype 的持久聊天聊天室](../../manage/persistent-chat/configure-add-ins.md)。 如果您是 a Persistent Chat Administrator，您可以使用控制面板或 Windows PowerShell cmdlet 创建加载项。

## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在“**外接程序**”页上执行以下任务：

- [在 Skype for Business Server 2015 中配置持久聊天室的加载项](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>配置聊天室外接程序

下表介绍了该页上的菜单、命令、字段和属性。

1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。

2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。 有关可用于启动控制面板的不同方法的详细信息，请参阅[Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)。

3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。

    对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。

4. 在“**外接程序**”页上，单击“**新建**”。

5. 在**选择服务**，选择对应于需要创建外接程序的持久聊天服务器池的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。

6. 在“**新建外接程序**”中，执行下列操作：

   - 在“**名称**”中，指定新外接程序的名称。

   - 在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。

7. 单击“**提交**”。

## <a name="see-also"></a>另请参阅

有关详细信息 Persistent Chat Server 特性和功能，请参阅[Plan for Persistent Chat Server in 业务服务器 2015年的 Skype](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[部署持久聊天服务器中的 Business Server 2015 Skype](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和[管理持久聊天服务器在业务服务器 2015 Skype](../../manage/persistent-chat/persistent-chat.md)。


