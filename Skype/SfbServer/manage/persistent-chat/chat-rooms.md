---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器内的聊天室
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7b2e1302-280c-4efe-9ec8-787687b414da
description: 摘要： 了解如何管理 Persistent Chat Server 聊天室中 Skype for Business Server 2015。
ms.openlocfilehash: 25d13b8b44e16d476191fdae337eb72d73e77dbc
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973773"
---
# <a name="manage-chat-rooms-in-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理持久聊天服务器内的聊天室
 
**摘要：** 了解如何为业务服务器 2015年管理持久聊天服务器中 Skype 的聊天室。
  
通过正确使用类别，创建和管理聊天室的过程可以大大简化。 类别定义谁可以创建或加入聊天室。 您尝试管理聊天室之前，请务必阅读[持久聊天类别、 聊天室和用户角色中的业务服务器 2015 Skype](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)和[管理类别中的业务服务器 2015 Skype Persistent Chat Server 中](categories.md)。
  
> [!NOTE]
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。 

您可以配置和管理聊天室，通过使用 Windows PowerShell 命令行界面，或通过使用 Skype for Business 客户端，如果您是聊天室的成员。 本主题介绍了如何使用 Windows PowerShell 命令行界面管理聊天室。 如果您想要使用 Skype 业务客户端管理聊天室，请参阅客户端帮助。 
  
聊天室可以是两种类型之一： 普通和大会堂。 Normal 聊天室允许所有成员发布和阅读消息。 Auditorium 聊天室仅允许演示者发布消息，但所有人都可以阅读消息。
  
可访问和管理聊天室的人员取决于用户角色，如下所示：
  
- 用户必须是聊天室的成员才能发布和阅读消息。
    
- 演示者可以向 Auditorium 聊天室发布消息。
    
- 管理员可删除任何聊天室的旧内容（例如，特定日期前发布的内容）以保持数据库的大小不会极大地增加。 管理员也可以删除或替换认为对特定聊天室不合适的消息。
    
- 最终用户（包括消息作者）无法删除任何聊天室的内容。
    
- 聊天室管理者可以对所有聊天室属性进行更改，包括禁用聊天室。 但管理者无法删除聊天室或更改聊天室的类别。 
    
- 聊天室创建后，仅管理员可删除它。
    
您可以使用以下 Windows PowerShell cmdlet 配置和管理聊天室：
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-cspersistentchatroom  <br/> |新建聊天室  <br/> |
|Set-cspersistentchatroom  <br/> |配置现有聊天室的设置；向聊天室分配用户和用户组  <br/> |
|Get-cspersistentchatroom  <br/> |检索有关聊天室的信息  <br/> |
|Clear-cspersistentchatroom  <br/> |清除聊天室或清除聊天室中的消息  <br/> |
|即 Remove-cspersistentchatroom  <br/> |删除聊天室  <br/> |
|删除 CsPersistentChatMessage  <br/> |从聊天室删除消息  <br/> |
   
使用 **New-CsPersistentChatRoom** cmdlet 来创建聊天室，使用 **Set-CsPersistentChatRoom** cmdlet 来配置现有聊天室，包括向聊天室添加用户。 您可以配置聊天室的以下参数：
  
- Disabled。 允许您禁用或启用聊天室。 
    
- Invitations。 允许您禁用或启用聊天室邀请，在用户被添加为聊天室成员时，可使用邀请来通知用户。 将继承默认邀请设置，这导致聊天室会采用在其所属的类别上配置的邀请设置。 在聊天室级别将邀请设置配置为 false 可覆盖类别设置。 
    
- Privacy。 使您可以指定聊天室是“开放式”、“封闭式”还是“机密”。 任何人都可以搜索和访问“开放式”聊天室。 任何人都可以搜索“封闭式”聊天室，但只有成员才能访问。 只有聊天室的成员才能搜索和访问“机密”聊天室。 默认情况下，每个新聊天室最初都会配置为“封闭式”。
    
- Type。 允许您指定聊天室是否正常的室内，接受任何成员，或大会堂聊天室，其接受只能由演示者张贴的消息张贴的消息。
    
- Addin。 让您可以将之前配置的外接程序与聊天室关联，从而允许成员在加入时查看 URL 内容。
    
除了上述参数， **Set-cspersistentchatroom** cmdlet 可以将用户分配到聊天室，如下所示：
  
- Members。 配置聊天室的成员关系。 您可以通过指定用户的 SIP 地址，使用单个 cmdlet 添加或删除单个或多个成员。 要允许批量添加用户，也可指定 Active Directory 组织单位或通讯组。
    
- Managers。 让您可以向聊天室分配管理者。 管理者有权定义聊天室的成员关系和其他设置。
    
- Presenters。让您可以向 Auditorium 聊天室分配演示者。 
    
 有关语法，包括所有参数的详细信息，请参阅[Skype 的业务服务器 2015年命令行管理程序](../management-shell.md)。
  
## <a name="create-a-new-room"></a>创建新聊天室

您可以使用 **New-CsPersistentChatRoom** cmdlet 创建新聊天室。 例如，以下命令可在池 atl-cs-001.contoso.com 上创建名为 ITChatRoom 的新聊天室。 在此示例中，聊天室被添加到 IT 类别：
  
```
New-CsPersistentChatRoom -Name "ITChatRoom" -PersistentChatPoolFqdn "atl-cs-001.contoso.com"-Category "IT"
```

**注意：** 如果下列选项之一为 true，则不需要 PersistentChatPoolFqdn: 
  
- 没有只有一个持久聊天服务器池。
    
- 您为类别提供了一个池 FQDN。
    
- 您提供了一个池 Fqdn 以添加聊天室。
    
## <a name="configure-an-existing-room"></a>配置现有聊天室

您可以使用**Set-cspersistentchatroom** cmdlet 配置现有的聊天室。 例如，以下命令分配作为成员和演示者的 user1 和 user2 作为经理，testCat 大会堂聊天室的：
  
```
Set-CsPersistentChatRoom -Identity testCat -Members @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}
Set-CsPersistentChatRoom -Identity testCat -Presenters @{Add="sip:user1@contoso.com"}
Set-CsPersistentChatRoom -Identity testCat -Managers @{Add="sip:user2@contoso.com"}
```

 下一个示例将 Active Directoryor 中 NorthAmericaUsers OU 中的所有用户添加到 NorthAmerica 聊天室：
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="OU=NorthAmericaUsers,DC=contoso,DC=com"}
```

下一个示例将 Finance 通讯组中的所有成员添加到相同的聊天室：
  
```
Set-CsPersistentChatRoom -PersistentChatPoolFqdn "atl-cs-001.contoso.com\NorthAmerica" -Members @{Add="CN=Finance,OU=ExternalUsers,DC=contoso,DC=com"}
```

## <a name="disable-or-enable-a-room"></a>禁用或启用聊天室

如果持久聊天聊天室的主题不再重要，您可以使聊天室内不可用对用户禁用它。 禁用聊天室时，所有成员将立即从聊天室断开。 禁用聊天室后，用户无法重新加入或在聊天室搜索中找到该聊天室。
  
如果聊天室的历史记录仍然存在，请禁用聊天室时，将保留内容。 但是，在该聊天室处于禁用状态时，该内容不会显示在搜索中。 如果随后启用该聊天室，则用户可以搜索禁用该聊天室之前发布的消息。 有关配置聊天室的历史记录的信息，请参阅[中的业务服务器 2015 Skype Persistent Chat Server 中管理类别](categories.md)。 
  
如果聊天室被禁用，其成员关系列表和其他设置将被保留。 作为管理员，您可以启用被禁用的聊天室，您无需手动重新创建设置。
  
您可以通过使用**Set-cspersistentchatroom** cmdlet 并禁用参数设置为 true 时，禁用聊天室：
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $True
```

要启用聊天室，请将 Disabled 参数设置为 False：
  
```
Set-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -Disabled $False
```

## <a name="get-information-about-rooms"></a>获取有关聊天室的信息

要获取有关您的组织中配置使用的聊天室的信息，可以使用 **Get-CsPersistentChatRoom** cmdlet。
  
以下命令返回有关配置为在组织中使用的所有聊天室的信息：
  
```
Get-CsPersistentChatRoom
```

## <a name="remove-all-content-from-a-room"></a>从聊天室删除所有内容

您可以使用 **Clear-CsPersistentChatRoom** cmdlet 从聊天室删除内容。例如，以下命令可从持久聊天室 ITChatRoom 中删除 2015 年 3 月 1 日或之前添加到聊天室的所有内容：
  
```
Clear-CsPersistentChatRoom -Identity "atl-cs-001.contoso.com\ITChatRoom" -EndDate "3/1/2015"
```

## <a name="remove-a-message-from-a-room"></a>从聊天室删除消息

您可以使用 **Remove-CsPersistentChatMessage** cmdlet 删除持久聊天数据库中的一条或多条消息，并且可以选择将消息替换为默认消息或管理员提供的消息。例如，以下命令可从 ITChatRoom 聊天室删除用户 kenmyer@contoso.com 发布的所有消息：
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com"
```

在下一个示例中，任何已删除的消息都将替换为说明消息已不再可用的通知：
  
```
Remove-CsPersistentChatMessage -Identity "atl-persistentchat-001.contoso.com\ITChatRoom" -UserUri "sip:kenmyer@contoso.com" -ReplaceMessage "This message is no longer available."
```

## <a name="remove-a-room"></a>删除聊天室

您可以通过使用 **Remove-CsPersistentChatRoom** cmdlet 来删除聊天室。
  
例如，以下命令可删除聊天室 RedmondChatRoom：
  
```
Remove-CsPersistentChatRoom -Identity "atl-gc-001.contoso.com\RedmondChatRoom"
```

## <a name="move-a-room-from-one-category-to-another"></a>将聊天室从一个类别移动到另一个类别

如果聊天室管理员在其他类别中具有  **Creator** 特权，则他/她可以将聊天室从一个类别移动到另一个类别。将不会删除和重新创建该聊天室。这是数据库中的关联的更改。
  
应该尽量不要或者谨慎更改聊天室类别。类别用于确定聊天室允许的成员身份，因此当聊天室移动到另一个类别时，新类别不再支持的所有系统访问控制列表 (SACL) 都将清除。例如，如果用户是聊天室的成员，且不再是新类别中的许可成员，则系统会修改聊天室成员身份，并将用户从聊天室中删除。
  

