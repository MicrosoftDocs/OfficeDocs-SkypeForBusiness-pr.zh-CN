---
title: 在 Skype for Business Server 2015 中配置持久聊天用户策略
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要：阅读本主题，了解如何在 Skype for Business Server 2015 中为持久聊天服务器创建初始用户策略。 持久聊天用户策略确定是否允许用户访问聊天室。
---

# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中配置持久聊天用户策略
 
**摘要：** 阅读本主题，了解如何在 Skype for Business Server 2015 中为持久聊天服务器创建初始用户策略。 持久聊天用户策略确定是否允许用户访问聊天室。
  
您可以在以下级别管理持久聊天服务器用户策略：全局、站点或用户。 最初，将全局策略配置为为部署中的所有用户启用持久聊天设置，然后创建其他用户和站点策略以控制是否对特定用户和站点启用持久聊天。
  
本主题包含以下各部分：
  
- 配置全局策略
    
- 创建站点策略
    
- 创建用户策略
    
- 将策略应用于用户或用户组
    
> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 2019 年 2 Skype for Business Server不再受支持。 相同的功能在 Teams。 有关详细信息，请参阅[开始升级Microsoft Teams升级](/microsoftteams/upgrade-start-here)。 如果您需要使用持久聊天，您的选择是迁移需要此功能的用户以Teams或继续使用 Skype for Business Server 2015。

## <a name="configure-the-global-policy"></a>配置全局策略

配置全局策略：
  
1. 使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在Skype for Business Server控制面板"中，单击"**持久聊天**"，然后单击"**持久聊天策略"**。
    
4. 单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑持久聊天策略 - 全局”中，执行下列操作： 
    
   - 在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
   - 在 **"说明**"中，提供有关用户策略 (例如  _centralSiteName_ 策略的全局策略) 。
    
   - 若要控制未通过站点策略或用户策略明确控制的所有站点和用户的持久聊天，请选中或清除" **启用持久聊天** "复选框。
    
6. 单击“提交”。
    
## <a name="create-a-site-policy"></a>创建站点策略

对于已部署的每个站点，可以创建特定于站点的持久聊天策略。 站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。 创建站点策略：
  
1. 使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。
    
4. 单击“新建”，然后单击“站点策略”。
    
5. 在“选择站点”中，单击要应用此策略的站点。
    
6. 在“新建持久聊天策略”中，执行下列操作之一：
    
   - 在“名称”中，指定新站点策略的名称（例如，Redmond）。
    
   - 在“说明”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。
    
   - 若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“启用持久聊天”复选框。
    
7. 单击“提交”。
    
## <a name="create-a-user-policy"></a>创建用户策略

可以创建特定于用户的策略，以覆盖全局策略和用户所属的任何站点策略。 创建用户策略：
  
1. 使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。
    
4. 单击“新建”，然后单击“用户策略”。
    
5. 在“新建持久聊天策略”中，执行下列操作之一：
    
   - 在“名称”中，指定新用户策略的名称。
    
   - 在 **"** 说明"中，提供有关用户策略 (例如，特定用户的持久聊天策略) 。
    
   - 若要控制未通过用户策略明确控制的所有用户的持久聊天，请选中或清除" **启用持久聊天** "复选框。
    
6. 单击“提交”。
    
## <a name="apply-a-policy-to-a-user-account"></a>将策略应用于用户帐户

创建策略后，可以将其应用到用户帐户，如下所示：
  
1. 使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在 **"Skype for Business Server** 聊天策略"下的"编辑用户 **"** 中，选择要应用持久聊天用户策略。
    
    > [!NOTE]
    > 设置 **\<Automatic\>** 将应用默认的有效策略。 服务器将自动应用这些设置。
  
6. 单击“提交”。
    

