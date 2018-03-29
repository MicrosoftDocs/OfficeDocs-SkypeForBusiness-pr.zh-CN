---
title: 在 Skype for Business Server 2015 中配置持久聊天室的加载项
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c1037909-0750-411a-98c1-3a327eed4ae8
description: 摘要： 了解如何在 Skype 为业务服务器 2015年配置加载项持久聊天服务器聊天室。
ms.openlocfilehash: dbd1eba6cf73783d02b502930f271ada93e28145
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-add-ins-for-persistent-chat-rooms-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置持久聊天室的加载项
 
**摘要：**了解如何在 Skype 为业务服务器 2015年配置加载项持久聊天服务器聊天室。
  
外接程序用于扩展聊天室内体验，方式是将 URL 与聊天室关联。 这些 URL 显示在客户端对话可扩展性窗格中。 一个典型的加载项可能包括指向截获股票行情自动收录器过帐到聊天室，和扩展性窗格中显示的股票的历史记录时的 Silverlight 应用程序的 URL。 其他示例包括将 OneNote 2013 URL 作为外接程序嵌入聊天室，以包括一些共享上下文，如“指导思想”或“今日主题”。
  
 您必须首先将外接程序添加到已注册外接程序列表，同时聊天室管理者或创建者需要将聊天室与外接程序关联，然后用户才能在客户端中看到外接程序。
  
## <a name="configure-add-ins-for-chat-rooms-by-using-the-control-panel"></a>使用控制面板配置聊天室的外接程序

要使用控制面板配置聊天室的外接程序：
  
1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**外接程序**”。
    
    对于多个持久性聊天服务器池部署，从下拉列表中选择适当的池。
    
4. 在“**外接程序**”页上，单击“**新建**”。
    
5. 中**选择一个服务**，请选择对应于您需要创建外接程序的持久的聊天服务器池的服务。 外接程序无法从一个池移到另一个池，或者在不同池之间共享。
    
6. 在“**新建外接程序**”中，执行下列操作：
    
  - 在“**名称**”中，指定新外接程序的名称。
    
  - 在“**URL**”中，指定与外接程序关联的 URL。URL 将限制为 http 和 https 协议。
    
7. 单击“**提交**”。
    
## <a name="configure-add-ins-by-using-windows-powershell"></a>使用 Windows PowerShell 配置外接程序

您可以使用以下 Windows PowerShell cmdlet 配置聊天室的外接程序。 有关语法，包括所有的可用参数的详细信息请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。
  
| |
|**Cmdlet**|**说明**|
|:-----|:-----|
|新 CsPersistentChatAddin  <br/> |创建新的外接程序  <br/> |
|一组 CsPersistentChatAddin  <br/> |配置现有外接程序的设置  <br/> |
|获得 CsPersistentChatAddin  <br/> |检索有关外接程序的信息  <br/> |
|删除 CsPersistentChatAddin  <br/> |删除外接程序  <br/> |
   
### <a name="create-a-new-add-in"></a>创建新的外接程序

您可以创建新的外接使用**New CsPersistentChatAddin** cmdlet。
  
例如，以下命令将创建一个新外接 （与 ITPersistentChatAddin 的名称） 为池 atl cs 001.contoso.com。URL 参数和参数值http://atl-cs-001.contoso.com/itchat指定位置的外接程序的网页：
  
```
New-CsPersistentChatAddin -Name "ITPersistentChatAddin" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -Url "http://atl-cs-001.contoso.com/itchat"
```

### <a name="configure-settings-for-an-existing-add-in"></a>配置现有外接程序的设置

您可以使用 **Set-CsPersistentChatAddIn** cmdlet 配置现有外接程序的设置。 例如，以下命令可修改分配给持久聊天外接程序 ITPersistentChatAddin 的URL。 在这种情况下，URL 更改为http://atl-cs-001.contoso.com/itchat2:
  
```
Set-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITPersistentChatAddin" -Url "http://atl-cs-001.contoso.com/itchat2"
```

### <a name="retrieve-information-about-add-ins"></a>检索有关外接程序的信息

您可以使用 **Get-CsPersistentChatAddin** cmdlet 获取有关外接程序的信息。例如，以下命令将为组织中配置使用的所有持久聊天外接程序返回相关信息：
  
```
Get-CsPersistentChatAddin
```

### <a name="remove-an-add-in"></a>删除外接程序

您可以通过**删除 CsPersistentChatAddIn** cmdlet 删除外接程序。 例如，以下命令可删除池 atl-cs-001.contoso.com 中的持久聊天外接程序 ITChatAddin：
  
```
Remove-CsPersistentChatAddin -Identity "atl-cs-001.contoso.com\ITChatAddin"
```


