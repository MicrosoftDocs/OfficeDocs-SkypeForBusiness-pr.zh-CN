---
title: 持久聊天策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 您可以使用持久聊天组的"持久聊天策略"页来管理全局、池、站点或用户级别的策略，包括配置默认全局策略和为部署创建一个或多个其他用户和站点策略。 如果策略为用户启用了持久聊天服务器，则持久聊天服务器环境将显示在其客户端中。
ms.openlocfilehash: 6145740717ca4e240cde767535c91040c336cb90
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/26/2021
ms.locfileid: "58621388"
---
# <a name="persistent-chat-policy"></a>持久聊天策略
 
您可以使用持久聊天组的"持久聊天策略"页来管理全局、池、站点或用户级别的策略，包括配置默认全局策略和为部署创建一个或多个其他用户和站点策略。 如果策略为用户启用了持久聊天服务器，则持久聊天服务器环境将显示在其客户端中。
  
全局策略是在部署持久聊天服务器时自动创建的，可以配置全局策略，但不能将其删除。 由于全局策略适用于所有用户，因此不必按用户进行设置。
  
可以创建和配置多个站点和用户策略，这些策略与全局策略一起为用户启用持久聊天服务器。 池和站点持久聊天服务器策略会覆盖全局持久聊天服务器策略，但仅适用于该站点的用户。 用户策略将覆盖分配有用户策略的用户的全局、池和网站策略。
  
> [!NOTE]
> 若要配置和使用持久聊天服务器，必须先使用拓扑生成器向拓扑中添加持久聊天服务器支持，然后发布拓扑。 有关详细信息，请参阅[Add Persistent Chat Server to your Skype for Business Server 2015 topology](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。 
  
## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在"持久聊天策略"页上执行以下任务：启用持久聊天服务器策略;管理持久聊天服务器策略。
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>配置持久聊天的全局策略

1. 使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在Skype for Business Server控制面板"中，单击"**持久聊天**"，然后单击"**持久聊天策略"。**
    
4. 单击策略列表中的“全局”，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在“编辑持久聊天策略 - 全局”中，执行下列操作：
    
   - 在“名称”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
   - 在 **"说明**"中，提供有关用户策略 (例如  _centralSiteName_ 策略的全局策略) 。
    
   - 若要控制未通过站点策略或用户策略明确控制的所有站点和用户的持久聊天，请选中或清除" **启用持久聊天** "复选框。
    
6. 单击“提交”。
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>为站点创建持久聊天策略

对于已部署的每个站点，可以创建特定于站点的持久聊天策略。
  
站点策略中的配置将覆盖全局策略，但仅适用于站点策略覆盖的指定站点。
  
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
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>为持久聊天创建用户策略

在Skype for Business Server控制面板中，定义可分配给 Users 中的用户 **的用户策略**。
  
用户策略将覆盖全局策略和站点策略，但仅适用于分配了该用户策略的特定用户。
  
1. 使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“持久聊天”，然后单击“持久聊天策略”。
    
4. 单击“新建”，然后单击“用户策略”。
    
5. 在“新建持久聊天策略”中，执行下列操作之一：
    
   - 在“名称”中，指定新用户策略的名称。
    
   - 在 **"说明**"中，提供有关用户策略 (例如，特定用户的持久聊天策略) 。
    
   - 若要控制未通过用户策略明确控制的所有用户的持久聊天，请选中或清除" **启用持久聊天** "复选框。
    
6. 单击“提交”。
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>将持久聊天用户策略应用于用户帐户

如果为用户启用了Skype for Business Server，您可以将相应的策略应用于特定用户，以启用或禁用持久聊天服务器。
  
使用本主题中的过程将以前创建的持久聊天用户策略应用于一个或多个用户帐户或用户组。
  
1. 使用分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从"**开始**"菜单中，Skype for Business Server控制面板或打开浏览器窗口，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“用户”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”，然后单击“显示详细信息”。
    
5. 在 **"编辑 Lync Server 用户"** 中的" **持久聊天** 策略"下，选择要应用持久聊天用户策略。
    
    > [!NOTE]
    > 设置 **\<Automatic\>** 将应用默认的有效策略。 服务器将自动应用这些设置。
  
6. 单击“提交”。
    

