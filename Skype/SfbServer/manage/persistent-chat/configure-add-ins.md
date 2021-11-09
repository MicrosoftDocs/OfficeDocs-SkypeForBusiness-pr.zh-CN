---
title: Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要：了解如何在 Skype for Business Server 2015 中为持久聊天服务器聊天室配置外接程序。
ms.openlocfilehash: c23a0dd11d51bbfa1c49d8a910decda5be0ac48f
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60854296"
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>Configure add-ins for Persistent Chat rooms in Skype for Business Server 2015
 
**摘要：** 了解如何在 Skype for Business Server 2015 中为持久聊天服务器聊天室配置外接程序。
  
外接程序用于通过将 URL 与聊天室关联来扩展聊天室内体验。 这些 URL 显示在客户端对话扩展性窗格中。 典型的外接程序可能包括一个指向 Silverlight 应用程序的 URL，该应用程序在将股票代码张贴到聊天室时截获，在可扩展性窗格中显示股票历史记录。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，例如“第一个想到的品牌”(Top of mind) 或“今日主题”(Topic of the day)。
  
 用户必须先将加载项添加到已注册加载项列表中，然后聊天室管理员或创建者需要将聊天室与加载项关联，用户才能在客户端中查看加载项。
  
> [!NOTE]
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，则选择将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 

## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>使用控制面板配置聊天室的外接程序

使用控制面板配置聊天室的外接程序：
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“持久聊天”，然后单击“外接程序”。
    
    对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。
    
4. 在“外接程序”页上，单击“新建”。
    
5. 在 **"选择服务**"中，选择与需要创建外接程序的持久聊天服务器池对应的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。
    
6. 在“新建外接程序”中，执行下列操作：
    
   - 在“名称”中，指定新外接程序的名称。
    
   - 在“URL”中，指定与外接程序关联的 URL。 URL 仅限于 http 和 https 协议。
    
7. 单击“提交”。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>使用加载项配置Windows PowerShell

您可以使用以下 cmdlet 配置聊天室的Windows PowerShell。 有关语法的详细信息，包括所有可用参数，请参阅 Skype for Business Server [2015 Management Shell](../management-shell.md)。
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-CsPersistentChatAddin  <br/> |创建新的外接程序  <br/> |
|Set-CsPersistentChatAddin  <br/> |配置现有外接程序的设置  <br/> |
|Get-CsPersistentChatAddin  <br/> |检索有关外接程序的信息  <br/> |
|Remove-CsPersistentChatAddin  <br/> |删除加载项  <br/> |
   
### <a name="create-a-new-add-in"></a>创建新的外接程序

您可以使用 **New-CsPersistentChatAddin** cmdlet 创建新的外接程序。
  
例如，以下命令创建一个新的外接程序 (名称为 ITPersistentChatAddin) 池 `atl-cs-001.contoso.com` 。 URL 参数和参数值指定 `http://atl-cs-001.contoso.com/itchat` 外接程序网页的位置：
  
```PowerShell
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>配置现有外接程序的设置

您可以使用 **Set-CsPersistentChatAddIn** cmdlet 配置现有外接程序的设置。 例如，以下命令修改分配给持久聊天外接程序 ITPersistentChatAddin 的 URL。 在这种情况下，URL 更改为 `http://atl-cs-001.contoso.com/itchat2` ：
  
```PowerShell
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>检索有关外接程序的信息

您可以使用 **Get-CsPersistentChatAddin** cmdlet 获取有关外接程序的信息。 例如，以下命令返回有关配置为在组织使用的所有持久聊天外接程序的信息：
  
```PowerShell
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>删除加载项

您可以使用 **Remove-CsPersistentChatAddIn** cmdlet 删除外接程序。 例如，以下命令删除在池上找到的持久聊天外接程序 ITChatAddin： `atl-cs-001.contoso.com`
  
```PowerShell
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


