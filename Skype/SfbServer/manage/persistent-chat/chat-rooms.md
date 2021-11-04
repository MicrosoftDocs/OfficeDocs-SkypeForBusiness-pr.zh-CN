---
title: Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器聊天室。
ms.openlocfilehash: 5eb69b3f852ce8e093947cdd04cc00b6bfdc19e3
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60746878"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>Manage chat rooms in Persistent Chat Server in Skype for Business Server 2015
 
**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器聊天室。
  
正确使用类别可更轻松地创建和管理聊天室。 类别定义可以创建或加入聊天室的人。 在尝试管理聊天室之前，请务必阅读[Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)中的持久聊天类别、聊天室和用户角色和在[Skype for Business Server 2015](categories.md)中管理持久聊天服务器中的类别。
  
> [!NOTE]
> 持久聊天在 2015 Skype for Business Server可用，但在 2019 年 2 月不再Skype for Business Server支持。 相同的功能在 Teams 中可用。 有关详细信息，请参阅开始[升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。 

您可以使用命令行界面或 Windows PowerShell（如果您是聊天室的成员）使用 Skype for Business 客户端配置和管理聊天室。 本主题介绍如何使用命令行界面Windows PowerShell聊天室。 如果要使用客户端管理聊天室Skype for Business，请参阅客户端帮助。 
  
聊天室可以是以下两种类型之一：Normal 和 Auditorium。 Normal 聊天室允许所有成员发布和阅读消息。 Auditorium 是一种聊天室，只有演示者可以发布消息，但每个人都可以阅读。
  
Who聊天室的用户角色取决于用户角色，如下所示：
  
- 用户必须是聊天室的成员才能发布和阅读消息。
    
- 演示者被允许在大会堂聊天室发布帖子。
    
- 管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。 管理员还可以删除或替换认为不适合特定聊天室的消息。
    
- 最终用户（包括消息作者）无法删除任何聊天室的内容。
    
- 聊天室管理员可更改所有聊天室属性，包括禁用聊天室。 但是，经理不能删除聊天室或更改聊天室的类别。 
    
- 只有管理员才能在聊天室创建后删除该聊天室。
    
您可以使用以下 cmdlet 配置和管理Windows PowerShell聊天室：
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-CsPersistentChatRoom  <br/> |创建新的聊天室  <br/> |
|Set-CsPersistentChatRoom  <br/> |配置现有聊天室的设置;将用户和用户组分配给聊天室  <br/> |
|Get-CsPersistentChatRoom  <br/> |检索有关聊天室的信息  <br/> |
|Clear-CsPersistentChatRoom  <br/> |清除聊天室或聊天室的消息  <br/> |
|Remove-CsPersistentChatRoom  <br/> |删除聊天室  <br/> |
|Remove-CsPersistentChatMessage  <br/> |从聊天室中删除邮件  <br/> |
   
您可以使用 **New-CsPersistentChatRoom** cmdlet 创建聊天室，使用 **Set-CsPersistentChatRoom** cmdlet 配置现有聊天室，包括向聊天室添加用户。 您可以为聊天室配置以下参数：
  
- 已禁用。 允许您禁用或启用聊天室。 
    
- 邀请。 允许您启用或禁用聊天室邀请，这些邀请用于在用户被添加为聊天室成员时通知用户。 继承邀请的默认设置，导致聊天室采用在所属类别上配置的邀请设置。 在聊天室级别将邀请设置配置为 false 可覆盖类别设置。 
    
- 隐私。 允许您指定聊天室是"打开"、"关闭"还是"机密"。 任何人都可以搜索和访问开放式聊天室。 任何人都可以搜索封闭式聊天室，但只有成员才能访问。 只能由聊天室的成员搜索和访问机密聊天室。 默认情况下，每个新会议室最初配置为"已关闭"。
    
- 类型。 允许您指定聊天室是普通聊天室（接受任何成员发布的消息）还是 Auditorium 聊天室（仅接受演示者发布的消息）。
    
- 加载项。 允许您将以前配置的外接程序与聊天室关联，这样成员可以在参与时查看 URL 内容。
    
除了上述参数之外 **，Set-CsPersistentChatRoom** cmdlet 还允许您将用户分配到聊天室，如下所示：
  
- 成员。 配置聊天室的成员身份。 通过指定用户的 SIP 地址，可以使用单个 cmdlet 添加或删除单个或多个成员。 若要允许批量添加用户，还可以指定 Active Directory 组织单位或通讯组。
    
- 经理。 允许您将管理员分配到聊天室。 管理员有权定义聊天室成员身份以及其他设置。
    
- 演示者。 允许你将演示者分配到 Auditorium 聊天室。 
    
  有关语法的详细信息，包括所有参数，请参阅 Skype for Business Server [2015 Management Shell](../management-shell.md)。
  
## <a name="create-a-new-room"></a>创建新聊天室

您可以使用 **New-CsPersistentChatRoom** cmdlet 创建新聊天室。 例如，以下命令在池池上创建一个名为 ITChatRoom 的新 atl-cs-001.contoso.com。 此示例将聊天室添加到 IT 类别：
  
```PowerShell
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**注意：** 如果下列情况之一为 true，则不需要 PersistentChatPoolFqdn： 
  
- 只有一个持久聊天服务器池。
    
- 您为类别提供了一个池 FQDN。
    
- 您提供了一个池 Fqdn 以添加聊天室。
    
## <a name="configure-an-existing-room"></a>配置现有聊天室

您可以使用 **Set-CsPersistentChatRoom** cmdlet 配置现有聊天室。 例如，以下命令将 user1 分配为 testCat Auditorium 会议室的成员和演示者，并将 user2 分配为管理者：
  
```PowerShell
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 下一个示例将 Active Directory 中 NorthAmericaUsers OU 的所有用户添加到 NorthAmerica 聊天室：
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

下一个示例将 Finance 通讯组的所有成员添加到同一聊天室：
  
```PowerShell
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>禁用或启用聊天室

如果持久聊天室的主题不再相关，您可以通过禁用该聊天室来使用户无法使用该聊天室。 禁用聊天室后，所有成员将立即与聊天室断开连接。 禁用聊天室后，用户将无法重新加入该聊天室或在聊天室搜索中查找该聊天室。
  
如果聊天室的历史记录仍然存在，则禁用该聊天室时将保留该内容。 但是，在聊天室保持禁用状态期间，该内容不会显示在搜索中。 如果稍后启用该聊天室，则用户可以搜索在禁用聊天室之前发布的消息。 有关配置聊天室历史记录的信息，请参阅 Manage [categories in Persistent Chat Server in Skype for Business Server 2015。](categories.md) 
  
禁用某聊天室时，将保留其成员身份列表和其他设置。 作为管理员，您可以启用已禁用的聊天室，并且不需要手动重新创建设置。
  
您可以使用 **Set-CsPersistentChatRoom** cmdlet 将 Disabled 参数设置为 True 来禁用聊天室：
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

若要启用聊天室，将 Disabled 参数设置为 False：
  
```PowerShell
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>获取有关聊天室的信息

若要获取有关配置为在组织使用的聊天室的信息，可以使用 **Get-CsPersistentChatRoom** cmdlet。
  
以下命令返回有关配置为在组织使用的所有聊天室的信息：
  
```PowerShell
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>从聊天室中删除所有内容

您可以使用 **Clear-CsPersistentChatRoom** cmdlet 从聊天室中删除内容。 例如，以下命令从持久聊天室 ITChatRoom 中删除在 2015 年 3 月 1 日或之前添加到聊天室的所有内容：
  
```PowerShell
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>从聊天室中删除邮件

您可以使用 **Remove-CsPersistentChatMessage** cmdlet 删除持久聊天数据库中的一条或多条消息，也可以选择将该消息替换为默认消息或管理员提供的消息。 例如，以下命令从 ITChatRoom 聊天室中删除用户发布的所有 kenmyer@contoso.com：
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

下一个示例将删除的邮件替换为该邮件不再可用的注释：
  
```PowerShell
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>删除聊天室

您可以使用 **Remove-CsPersistentChatRoom** cmdlet 删除聊天室。
  
例如，以下命令可删除聊天室 RedmondChatRoom：
  
```PowerShell
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>将聊天室从一个类别移动到另一个类别

如果聊天室管理员具有其他 **类别中的 Creator** 权限，则他/她可以将聊天室从一个类别移动到另一个类别。 将不会删除和重新创建该聊天室。 这是数据库中的关联的更改。
  
更改聊天室类别应很少且谨慎。 类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。 例如，如果用户是聊天室的成员，并且不再是新类别中的允许成员，则聊天室成员身份将被修改，并且该用户将从聊天室中删除。
  

