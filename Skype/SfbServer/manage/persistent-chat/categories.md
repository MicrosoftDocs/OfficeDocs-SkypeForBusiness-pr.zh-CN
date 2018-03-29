---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器内的类别
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 1/31/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 摘要： 了解如何管理业务服务器 2015 Skype 的持久聊天服务器类别。
ms.openlocfilehash: e24beb1c4e1ebe7bb541a7bd6226f098c1bcb58b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理持久聊天服务器内的类别
 
**摘要：**了解如何管理业务服务器 2015 Skype 的持久聊天服务器类别。
  
类别是用于组织聊天室的逻辑结构。 类别定义了一套默认的访问控制列表 (ACL) 以控制可以创建或加入聊天室的用户和用户组。 聊天室类别包含聊天室，但不包含其他类别。 每个类别说明了其内容及元数据，比如名称和说明。 类别拥有各种属性，可设置这些属性来控制属于该类别的聊天室的行为；例如，聊天室是否允许邀请或文件上载，或包含聊天历史记录。 
  
通过正确使用类别，创建和管理聊天室的过程可以大大简化。 持久聊天服务器管理员可以定义每个类别的 AllowedMembers 和  Creators，还可以定义将应用于在该类别中创建的所有聊天室的默认聊天室设置和行为。 例如，如果 contoso.com 设置类别的 AllowedMembers，您可以添加任何组或用户 contoso 作为成员向该类别中的聊天室。 如果将某个类别上的 Allowed Members 设置为 Sales，则只能将此通讯组列表中的组和用户添加为该类别中的聊天室的成员。 同样，利用 Creators 属性，您可以控制可在该类别中创建聊天室的人员。 创建聊天室后，可将 AllowedMembers 组中的任何人指定为聊天室中正在进行的管理操作（例如，成员身份更改和审批）的管理者。
  
为类别定义  AllowedMembers  和  Creators  有以下好处：
  
- 该类别中的所有聊天室都绑定了在类别级别设置的限制。 您可以使用此限制，根据业务需求和访问策略隔离聊天室。
    
- Creators 列表中的用户可在该类别中创建新聊天室。如果要实现这样一个系统 - 组织中有限数量的人员可创建聊天室，那么可使用此控制来满足要求。 
    
标识为类别创建者的用户、组织单位 (OU) 和用户组是仅有的被允许在类别中创建聊天室的个人和组。 创建类别后，您可以从类别的  AllowedMembers  列表中选择用户、OU 和用户组作为聊天室的管理员和成员来管理和参与聊天室。 
  
配置类别之前，请务必阅读[持久交谈类别、 聊天室和在业务服务器 2015年的 Skype 的用户角色](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)。
  
您可以使用控制面板或 Windows PowerShell cmdlet 配置和管理类别。
  
## <a name="configure-categories-by-using-the-control-panel"></a>使用控制面板配置类别

1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录您的本地部署中的任一计算机。
    
2. 从**开始**菜单中，选择 Skype 业务服务器的控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**类别**”。
    
    对于多个持久性聊天服务器池部署，从下拉列表中选择适当的池。
    
4. 在“**类别**”页上，单击“**新建**”或“**编辑**”。
    
5. 中**选择一个服务**，请选择对应于持久的聊天服务器池需要创建类别的服务。 该服务是持久聊天服务器池持续聊天客户端用来标识该池类别属于。 类别可以属于一个持久聊天服务器池，并无法移动，或与另一个池共享。
    
6. 在“**新建类别**”中，执行下列操作：
    
   - 在“**名称**”中，指定新聊天室类别的名称。
    
   - 在“**描述**”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。
    
   - 要控制是否为属于此类别的聊天室启用邀请，请选中或清除“**启用邀请**”复选框。 如果选中，则此类别的聊天室将打开或关闭邀请；如果清除，则不允许此类别的聊天室具有邀请。 如果一个房间上时将新成员添加到文件室的邀请，他或她将收到一条通知其持久聊天客户端中新建文件室。
    
   - 要控制属于此类别的聊天室中的文件上载，请选中或清除“**启用文件上载**”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。
    
   - 若要控制聊天历史记录，请选中或清除**启用聊天历史记录**复选框。 如果选中，则聊天室聊天内容将变成持久的；否则，将不会保留聊天消息。 如果启用了合规性，则将按合规性保存聊天室聊天内容，但用户无法访问较早的消息。 此选项可用于指定以进行实时地点对点协作不需要聊天历史记录，以保持房间。
    
7. 在“**编辑类别**”中，执行下列操作：
    
   - 在中的**成员资格**，**允许的成员**部分中，添加或删除用户，并允许被添加为成员的聊天室其他 Active Directory 域服务主体 （用户、 通讯组、 组织单位，等）属于该类别。 类别允许的主体可搜索此类别的聊天室（除非隐藏了聊天室，在这种情况下，仅聊天室的成员可在此目录中搜索聊天室）。
    
   - 在中的**成员资格**，**拒绝的成员**部分中，添加或删除用户和其他 Active Directory 主体与被拒绝从文件室的成员。
    
   - 在中的**成员资格**，**创建者**部分中，添加或删除用户和其他 Active Directory 主体与创建者的类别相关联。 创建者是有权创建聊天室并指定聊天室管理员和成员的用户。
    
8. 单击“**提交**”。
    
## <a name="configure-categories-by-using-windows-powershell"></a>使用 Windows PowerShell 配置类别

您可以使用以下 Windows PowerShell cmdlet 配置类别：
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|新 CsPersistentChatCategory  <br/> |创建新类别  <br/> |
|一组 CsPersistentChatCategory  <br/> |配置现有类别的设置  <br/> |
|获得 CsPersistentChatCategory  <br/> |检索有关类别的信息  <br/> |
|删除 CsPersistentChatCategory  <br/> |删除类别  <br/> |
   
可以为类别配置以下参数：
  
- EnableFileUpload。允许类别中的聊天室具有文件上载功能。
    
- EnableInvitations。 为类别启用邀请。 AllowedMembers 列表中的用户将在创建新聊天室后自动收到加入该聊天室的邀请。
    
- ChatHistory。启用或禁用聊天室历史记录功能。
    
- Creators。 指定允许在类别中创建聊天室的用户。
    
- AllowedMembers。 指定允许访问类别中的聊天室的用户。
    
- DeniedMembers。列出不允许访问类别中的聊天室的用户。
    
完成有关 cmdlet 的语法中，包括所有参数，请参阅[业务服务器 2015年管理外壳的 Skype](../management-shell.md)。
  
### <a name="create-a-new-category"></a>创建新类别

您可以使用 **New-CsPersistentChatCategory** cmdlet 创建新类别。 例如，以下命令将创建新的类别上池 atl cs 001.contoso.com 名为帮助台。在此示例中，将启用文件上载：
  
```
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>配置现有类别

您可以使用 **Set-CsPersistentCategory** cmdlet 配置现有类别。
  
例如，以下命令指定该用户 1 是 AllowedMember 和创建者，而用户 2 将被拒绝访问该类别中的教室：
  
```
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>获取有关类别的信息

您可以使用 **Get-CsPersistentChatCategory** cmdlet 获取有关类别的信息。例如，以下命令将为组织中的所有持久聊天类别返回信息：
  
```
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>删除类别

您可以使用 **Remove-CsPersistentChatCategory** cmdlet 删除类别。删除类别前，您必须首先删除类别下的所有聊天室，或将聊天室移至新类别。例如，以下命令可删除具有 Identity“atl-cs-001.contoso.com\helpdesk”的类别：
  
```
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```


