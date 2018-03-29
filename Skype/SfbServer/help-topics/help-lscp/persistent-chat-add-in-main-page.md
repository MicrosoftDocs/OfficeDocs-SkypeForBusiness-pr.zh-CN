---
title: 持久聊天外接程序主页
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatAddinMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0c0ecf64-258d-4b43-8fac-fa5ffa4e7646
description: 持续聊天页的加载项部分可用于持续聊天房间与相关联的 Url。 这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。 管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。
ms.openlocfilehash: 701a128095cd2d9e001109fb6623659d189b2fbb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="persistent-chat-add-in-main-page"></a>持久聊天外接程序主页
 
**持续聊天**页的**加载项**部分可用于持续聊天房间与相关联的 Url。 这些 URL 将显示在对话可扩展性窗格的聊天室中的客户端中。 管理员必须将外接程序添加到注册的外接程序列表中，且聊天室管理员/创建者必须将聊天室与其中一个注册的外接程序相关联，这样用户才能在其客户端中看到此升级。
  
外接程序用于扩展聊天室内体验。 一个典型的加载项可能包括指向截获股票行情自动收录器过帐到聊天室，和扩展性窗格中显示的股票的历史记录时的 Silverlight 应用程序的 URL。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。
  
要为持久的聊天房间创建外接程序，请参阅[配置外接程序为持久聊天 Skype 业务服务器 2015年的客房](../../manage/persistent-chat/configure-add-ins.md)。 如果您持续的聊天管理员，可以使用控制面板或 Windows PowerShell cmdlet 来创建外接程序。
  
## <a name="tasks-you-can-perform"></a>可执行的任务

您可以在“**外接程序**”页上执行以下任务：
  
- [配置加载项持久聊天房间在 Skype 业务服务器 2015](../../manage/persistent-chat/configure-add-ins.md)
    
## <a name="to-configure-add-ins-for-chat-rooms"></a>配置聊天室外接程序

下表介绍了该页上的菜单、命令、字段和属性。
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。 您可以使用启动控制面板的不同方法的详细信息，请参阅[打开 Lync 服务器管理工具](http://technet.microsoft.com/library/8c58de94-9e0a-4368-9e14-9afcaa1142d0.aspx)。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。
    
    对于多个持久性聊天服务器池部署，从下拉列表中选择适当的池。
    
4. 在“**外接程序**”页上，单击“**新建**”。
    
5. 中**选择一个服务**，请选择对应于您需要创建外接程序的持久的聊天服务器池的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。
    
6. 在“**新建外接程序**”中，执行下列操作：
    
  - 在“**名称**”中，指定新外接程序的名称。
    
  - 在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。
    
7. 单击“**提交**”。
    
### 

有关持久聊天服务器特性和功能，详细信息请参阅[规划业务服务器 2015年的 Skype 的持久聊天服务器](../../plan-your-deployment/persistent-chat-server/persistent-chat-server.md)、[业务服务器 2015 Skype 在部署持续聊天服务器](../../deploy/deploy-persistent-chat-server/deploy-persistent-chat-server.md)和[管理持续聊天服务器在 Skype 业务服务器 2015年](../../manage/persistent-chat/persistent-chat.md)。
  

