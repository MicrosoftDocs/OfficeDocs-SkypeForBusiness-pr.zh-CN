---
title: 持久聊天外接程序
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 您可以使用"持久聊天"页的"外接程序"部分将 URL 与持久聊天室关联。 这些 URL 显示在对话可扩展性窗格的聊天室的客户端中。 管理员必须将外接程序添加到已注册的外接程序列表中，并且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序关联，用户才能在客户端中查看此升级。
ms.openlocfilehash: 4eaaf9f82fb820813fe2d9721193b7b93dc43da2
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60853266"
---
# <a name="persistent-chat-add-in"></a>持久聊天外接程序

您可以使用" **持久聊天"** 页的"外接程序" **部分将** URL 与持久聊天室关联。 这些 URL 显示在对话可扩展性窗格的聊天室的客户端中。 管理员必须将外接程序添加到已注册的外接程序列表中，并且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序关联，用户才能在客户端中查看此升级。

外接程序用于扩展聊天室内体验。 典型的外接程序可能包括一个指向 Silverlight 应用程序的 URL，该应用程序在将股票代码张贴到聊天室时截获，在可扩展性窗格中显示股票历史记录。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，例如“第一个想到的品牌”(Top of mind) 或“今日主题”(Topic of the day)。

若要为持久聊天室创建外接程序，请参阅 Configure [add-ins for Persistent Chat rooms in Skype for Business Server 2015。](../../manage/persistent-chat/configure-add-ins.md) 如果您是持久聊天管理员，可以使用控制面板或 cmdlet 创建Windows PowerShell外接程序。

## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在“外接程序”页上执行以下任务：

- [Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>配置聊天室外接程序

下表介绍了该页上的菜单、命令、字段和属性。

1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。

2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。 有关可用于启动控制面板的不同方法的详细信息，请参阅 [Open Lync Server Administrative Tools](/previous-versions/office/lync-server-2013/lync-server-2013-open-lync-server-administrative-tools)。

3. 在左侧导航栏中，单击“持久聊天”，然后单击“外接程序”。

    对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。

4. 在“外接程序”页上，单击“新建”。

5. 在 **"选择服务**"中，选择与需要创建外接程序的持久聊天服务器池对应的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。

6. 在“新建外接程序”中，执行下列操作：

   - 在“名称”中，指定新外接程序的名称。

   - 在“URL”中，指定与外接程序关联的 URL。URL 限制为 http 和 https 协议。

7. 单击“提交”。

## <a name="see-also"></a>另请参阅

有关持久聊天服务器特性和功能的详细信息，请参阅 Plan [for Persistent Chat Server in Skype for Business Server 2015、Deploy](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md) [Persistent Chat Server in Skype for Business Server 2015](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和 Manage Persistent Chat Server in [Skype for Business Server2015](../../manage/persistent-chat/persistent-chat.md)。