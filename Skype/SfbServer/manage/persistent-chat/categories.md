---
title: 在 Skype for Business Server 2015 中管理持久聊天服务器中的类别
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 1/31/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b0c834b9-b5c8-41d5-865b-c8b180e76d13
description: 摘要：了解如何在 Skype for Business Server 2015 中管理持久聊天服务器类别。
ms.openlocfilehash: 648629e42994c59f5d6ba5ee5592729f4dff0bbe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815122"
---
# <a name="manage-categories-in-persistent-chat-server-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中管理持久聊天服务器中的类别
 
**摘要：** 了解如何在 Skype for Business Server 2015 中管理持久聊天服务器类别。
  
类别是组织聊天室的逻辑结构。 类别定义一组默认的访问控制列表 (ACL) 用于控制可以创建或加入聊天室的用户和用户组。 聊天室类别包含聊天室，但不包含其他类别。 每个类别使用名称 和描述 等元数据描述其内容。 类别具有可设置以控制属于该类别的聊天室的行为的属性;例如，聊天室是否允许邀请或文件上载，或包含聊天历史记录。 
  
正确使用类别可更轻松地创建和管理聊天室。 作为持久聊天服务器管理员，您可以为每个类别定义 AllowedMembers 和 Creators，还可以定义将应用于类别中创建的所有聊天室的默认聊天室设置和行为。 例如，如果将类别的 AllowedMembers 设置为 contoso.com，您可以将 Contoso 的任何组或用户作为成员添加到该类别中的聊天室。 如果将类别中的"允许的成员"设置为"销售"，则只有此通讯组列表中的组和用户才能作为成员添加到该类别中的聊天室。 Creators 属性使您能够控制可在该类别中创建聊天室的人。 创建聊天室后，可以将 AllowedMembers 组中的任何人指定为对聊天室执行持续管理 (例如，成员身份更改和审批) 。
  
为类别定义 AllowedMembers 和 Creators 有以下好处：
  
- 该类别中的所有聊天室都绑定了在类别级别设置的限制。您可以使用此限制，根据业务需求和访问策略隔离聊天室。
    
- Creators 列表中的用户可在该类别中创建新聊天室。 如果要实现一个系统，在该系统中，组织中有限数量的人员可以创建聊天室，此控制可用于满足该要求。 
    
标识为 (创建者的用户、组织单位) 和用户组是唯一被允许在类别中创建聊天室的个人和组。 创建类别后，可以从类别的 AllowedMembers 列表中选择用户、US 和用户组作为聊天室管理员和成员来管理和参与聊天室。 
  
在配置类别之前，请务必阅读 [Skype for Business Server 2015](../../plan-your-deployment/persistent-chat-server/categories-chat-rooms-and-user-roles.md)中的持久聊天类别、聊天室和用户角色。
  
可以使用控制面板或 cmdlet 配置和管理Windows PowerShell类别。

> [!NOTE]
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。 
  
## <a name="configure-categories-by-using-the-control-panel"></a>使用控制面板配置类别

1. 使用分配给 CsPersistentChatAdministrator 或 CsAdministrator 角色的用户帐户登录到您的本地部署中的任一计算机。
    
2. 从 **"开始** "菜单中，选择 Skype for Business Server 控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“持久聊天”，然后单击“类别”。
    
    对于多个持久聊天服务器池部署，请从下拉列表中选择相应的池。
    
4. 在“类别”页上，单击“新建”或“编辑”。
    
5. 在 **"选择服务**"中，选择与需要创建类别的持久聊天服务器池对应的服务。 该服务是持久聊天客户端用来标识类别所属的池的持久聊天服务器池。 类别只能属于一个持久聊天服务器池，并且不能移动到另一个池或与另一个池共享。
    
6. 在“新建类别”中，执行下列操作：
    
   - 在“名称”中，指定新聊天室类别的名称。
    
   - 在“描述”中，提供有关聊天室类别（例如 Contoso 聊天室类别）的详细描述。
    
   - 若要控制是否能为属于此类别的聊天室启用邀请，请选中或清除“启用邀请”复选框。 如果选中，此类别中的聊天室将可以打开或关闭邀请；如果清除，则不允许该类别中的聊天室执行邀请操作。 如果聊天室有邀请，当向聊天室中添加一名新成员时，他（她）会收到其持久聊天客户端中新聊天室的通知。
    
   - 若要控制属于此类别的聊天室中的文件上载，请选中或清除“启用文件上载”复选框。如果选中，该类别的聊天室可以启用或禁用文件上载；如果清除，则不允许该类别的聊天室执行文件上载操作。
    
   - 若要控制聊天历史记录，请选中或清除" **启用聊天历史记录"** 复选框。 如果选中，聊天室聊天内容将是持久的；否则，聊天消息将不是持久的。 如果启用了合规性，将合规保存聊天室聊天内容，但用户无法访问较早的消息。 此选项可用于指定为不需要保留聊天历史记录实时临时协作的聊天室。
    
7. 在“编辑类别”中，执行下列操作：
    
   - 在 **"** 成员身份"中，在"允许的成员"部分，添加或删除用户和其他 Active Directory 域服务主体 (用户、通讯组、组织单位等) 允许添加为属于该类别的聊天室的成员。 类别允许的主体可以搜索该类别中的聊天室（除非聊天室处于隐藏状态，在这种情况下只有聊天室的成员才能在目录中搜索它）。
    
   - 在 **"成员身份**"中的"拒绝的成员"部分，添加或删除与聊天室中被拒绝的成员关联的用户和其他 Active Directory 主体。
    
   - 在 **"成员身份**"中的" **创建者** "部分，添加或删除与类别的创建者关联的用户和其他 Active Directory 主体。 创建者是有权创建聊天室并指定聊天室管理员和成员的用户。
    
8. 单击“提交”。
    
## <a name="configure-categories-by-using-windows-powershell"></a>使用自定义配置Windows PowerShell

可以使用以下 cmdlet 配置Windows PowerShell：
  

|**Cmdlet**|**说明**|
|:-----|:-----|
|New-CsPersistentChatCategory  <br/> |创建新类别  <br/> |
|Set-CsPersistentChatCategory  <br/> |配置现有类别的设置  <br/> |
|Get-CsPersistentChatCategory  <br/> |检索有关类别的信息  <br/> |
|Remove-CsPersistentChatCategory  <br/> |删除类别  <br/> |
   
您可以为类别配置以下参数：
  
- EnableFileUpload。 允许将文件上载到类别中的聊天室。
    
- EnableInvitations。 启用类别邀请。 AllowedMembers 列表中的用户在新建聊天室时将自动收到加入新聊天室的邀请。
    
- ChatHistory。 启用或禁用聊天历史记录功能。
    
- 创建者。 指定允许在类别中创建聊天室的用户。
    
- AllowedMembers。 指定允许访问类别中的聊天室的用户。
    
- DeniedMembers。 列出不允许访问类别中的聊天室的用户。
    
有关 cmdlet 语法的完整信息（包括所有参数），请参阅[Skype for Business Server 2015 Management Shell。](../management-shell.md)
  
### <a name="create-a-new-category"></a>创建新类别

您可以使用 **New-CsPersistentChatCategory** cmdlet 创建新类别。 例如，以下命令在池池上创建一个名为 HelpDesk 的新atl-cs-001.contoso.com。 本示例中启用文件上载：
  
```PowerShell
New-CsPersistentChatCategory -Name "HelpDesk" -PersistentChatPoolFqdn "atl-cs-001.contoso.com" -EnableFileUpload 
```

### <a name="configure-an-existing-category"></a>配置现有类别

可以使用 **Set-CsPersistentCategory** cmdlet 配置现有类别。
  
例如，以下命令指定 user1 是 AllowedMember 和 Creator，而 user2 被拒绝访问类别中的聊天室：
  
```PowerShell
Set-CsPersistentChatCategory -Identity testCat -AllowedMembers @{Add="sip:user1@contoso.com", "CN=container,DC=contoso,DC=com"}  -DeniedMembers @{Add="sip:user2@contoso.com"}
Set-CsPersistentChatCategory -Identity testCat -Creators @{Add="sip:user1@contoso.com"}
```

### <a name="get-information-about-categories"></a>获取有关类别的信息

您可以使用 **Get-CsPersistentChatCategory** cmdlet 获取有关类别的信息。 例如，以下命令返回组织中所有持久聊天类别的信息：
  
```PowerShell
Get-CsPersistentChatCategory
```

### <a name="remove-a-category"></a>删除类别

您可以使用 **Remove-CsPersistentChatCategory** cmdlet 删除类别。 在删除类别之前，必须先删除类别下的所有聊天室，或将聊天室移动到新类别。 例如，以下命令删除 Identity 为"atl-cs-001.contoso.com\helpdesk"的类别：
  
```PowerShell
Remove-CsPersistentChatCategory -Identity "atl-cs-001.contoso.com\helpdesk"
```
