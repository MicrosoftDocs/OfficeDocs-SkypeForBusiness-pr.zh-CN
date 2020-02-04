---
title: 持久聊天外接程序
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.PersistentChatAddin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 66124a70-67e8-4bda-9da5-8ab13afccf49
description: 你可以使用持久聊天页面的加载项部分将 Url 与持久聊天室相关联。 这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。 管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。
ms.openlocfilehash: da971a43c8e113dc1fff8ee9dc600f55a2fea955
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41686215"
---
# <a name="persistent-chat-add-in"></a>持久聊天外接程序

你可以使用**持久聊天**页面的**加载项**部分将 url 与持久聊天室相关联。 这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。 管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。

外接程序用于扩展聊天室内体验。 典型外接程序可能包含指向 Silverlight 应用程序的 URL，该应用程序在将股票行情滚动到聊天室时进行截获，并在 "扩展性" 窗格中显示股票历史记录。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。

若要为持久聊天室创建外接程序，请参阅[在 Skype for Business Server 2015 中配置持久聊天室的加载项](../../manage/persistent-chat/configure-add-ins.md)。 如果您是持久的聊天管理员，则可以使用控制面板或 Windows PowerShell cmdlet 创建外接程序。

## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在“**外接程序**”页上执行以下任务：

- [在 Skype for Business Server 2015 中配置持久聊天室的加载项](../../manage/persistent-chat/configure-add-ins.md)

## <a name="to-configure-add-ins-for-chat-rooms"></a>配置聊天室外接程序

下表介绍了该页上的菜单、命令、字段和属性。

1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。

2. 从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。 有关可用于启动控制面板的不同方法的详细信息，请参阅[Open Lync Server Administrative Tools](https://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)。

3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。

    对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。

4. 在“**外接程序**”页上，单击“**新建**”。

5. 在 "**选择服务**" 中，选择与需要在其中创建外接程序的持久聊天服务器池对应的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。

6. 在“**新建外接程序**”中，执行下列操作：

   - 在“**名称**”中，指定新外接程序的名称。

   - 在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。

7. 单击“**提交**”。

## <a name="see-also"></a>另请参阅

有关持久聊天服务器功能和功能的详细信息，请参阅在 skype for business [server 2015 中规划持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、在 skype For business [server 2015 中部署持久](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)聊天服务器以及[在 skype For Business Server 2015 中管理持久聊天服务器](../../manage/persistent-chat/persistent-chat.md)。


