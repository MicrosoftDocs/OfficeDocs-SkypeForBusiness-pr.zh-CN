---
title: 在 Skype for Business Server 2015 中配置持久聊天室的加载项
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要：了解如何在 Skype for business Server 2015 中为持久聊天服务器聊天室配置外接程序。
ms.openlocfilehash: c7243184f273704335dda3c8709de17e767f6b51
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992107"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置持久聊天室的加载项
 
**摘要：** 了解如何在 Skype for business Server 2015 中为持久聊天服务器聊天室配置外接程序。
  
外接程序用于扩展聊天室内体验，方式是将 URL 与聊天室关联。 这些 URL 显示在客户端对话可扩展性窗格中。 典型外接程序可能包含指向 Silverlight 应用程序的 URL，该应用程序在将股票行情滚动到聊天室时进行截获，并在 "扩展性" 窗格中显示股票历史记录。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。
  
 您必须首先将外接程序添加到已注册外接程序列表，同时聊天室管理者或创建者需要将聊天室与外接程序关联，然后用户才能在客户端中看到外接程序。
  
> [!NOTE]
> Skype for business Server 2015 中提供了持久聊天，但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息，请参阅[Microsoft 团队升级](/microsoftteams/upgrade-start-here)入门。 如果需要使用持久聊天，您可以选择将需要此功能的用户迁移到团队，或继续使用 Skype for Business Server 2015。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>使用控制面板配置聊天室的外接程序

要使用控制面板配置聊天室的外接程序：
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从 "**开始**" 菜单中，选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口，然后输入管理员 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。
    
    对于多个持久聊天服务器池部署，从下拉列表中选择相应的池。
    
4. 在“**外接程序**”页上，单击“**新建**”。
    
5. 在 "**选择服务**" 中，选择与需要在其中创建外接程序的持久聊天服务器池对应的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。
    
6. 在“**新建外接程序**”中，执行下列操作：
    
   - 在“**名称**”中，指定新外接程序的名称。
    
   - 在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。
    
7. 单击“**提交**”。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>使用 Windows PowerShell 配置外接程序

您可以使用以下 Windows PowerShell cmdlet 配置聊天室的外接程序。有关语法的详细信息，包括所有可用参数，请参阅[Skype for Business Server 2015 Management Shell](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |创建新的外接程序  <br/> |
|Set-CsPersistentChatAddin  <br/> |配置现有外接程序的设置  <br/> |
|Get-CsPersistentChatAddin  <br/> |检索有关外接程序的信息  <br/> |
|Remove-CsPersistentChatAddin  <br/> |删除外接程序  <br/> |
   
### <a name="create-a-new-add-in"></a>创建新的外接程序

你可以使用**CsPersistentChatAddin** cmdlet 创建新外接程序。
  
例如，以下命令将为 pool atl-cs-001.contoso.com 创建一个新的外接程序（名称为 ITPersistentChatAddin）。 URL 参数和参数值http://atl-cs-001.contoso.com/itchat指定外接程序的网页的位置：
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>配置现有外接程序的设置

您可以使用 **Set-CsPersistentChatAddIn** cmdlet 配置现有外接程序的设置。 例如，以下命令可修改分配给持久聊天外接程序 ITPersistentChatAddin 的URL。 在这种情况下，URL 将更改为http://atl-cs-001.contoso.com/itchat2:
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>检索有关外接程序的信息

您可以使用 **Get-CsPersistentChatAddin** cmdlet 获取有关外接程序的信息。例如，以下命令将为组织中配置使用的所有持久聊天外接程序返回相关信息：
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>删除外接程序

你可以使用**CsPersistentChatAddIn** Cmdlet 删除外接程序。 例如，以下命令可删除池 atl-cs-001.contoso.com 中的持久聊天外接程序 ITChatAddin：
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


