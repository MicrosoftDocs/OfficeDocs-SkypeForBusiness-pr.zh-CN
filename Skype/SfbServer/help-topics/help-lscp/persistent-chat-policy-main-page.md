---
title: 持久聊天策略主页
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/27/2015
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicyMain
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0dc18d5c-82d6-4d39-afb1-efdb3ae6d2c7
description: 您可以使用“持久聊天”组的“持久聊天策略”页来管理全局级、池级、站点级或用户级的策略，包括为部署配置默认全局策略以及创建一个或多个其他用户和站点策略。 如果用户按策略启用了持久聊天服务器, 则持久聊天服务器环境将显示在其客户端中。
ms.openlocfilehash: ed4e8bbcb0856156148f459435b5cec857e9e223
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294170"
---
# <a name="persistent-chat-policy-main-page"></a>持久聊天策略主页
 
您可以使用“**持久聊天**”组的“**持久聊天策略**”页来管理全局级、池级、站点级或用户级的策略，包括为部署配置默认全局策略以及创建一个或多个其他用户和站点策略。 如果用户按策略启用了持久聊天服务器, 则持久聊天服务器环境将显示在其客户端中。
  
> [!NOTE]
> 在拓扑中, 持久聊天服务器网站策略适用于全局、每个用户的池、每个用户的网站或每个用户。 
  
全局策略是在部署持久聊天服务器时自动创建的, 并且可以配置, 但不能删除。 由于全局策略适用于所有用户, 因此无需为每个用户设置。
  
你可以创建和配置多个网站和用户策略, 这些策略与全局策略一起为持久聊天服务器启用用户。 池和网站持久聊天服务器策略替代全局持久聊天服务器策略, 但仅适用于该网站的用户。 用户策略将覆盖分配有用户策略的用户的全局、池和站点策略。
  
> [!NOTE]
> 若要配置和使用持久聊天服务器, 必须首先使用拓扑生成器向拓扑添加持久聊天服务器支持, 然后发布拓扑。 有关详细信息, 请参阅[将持久聊天服务器添加到 Skype for Business server 2015 拓扑](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。 
  
## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在**持久聊天策略**页上执行以下任务：启用和管理“持久聊天服务器”策略。
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>配置永久聊天的全局策略

1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从 "**开始**" 菜单中, 选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口, 然后输入管理员 URL。
    
3. 在 "Skype for Business 服务器控制面板" 中, 单击 "**持久聊天**", 然后单击 "**持久聊天策略**"。
    
4. 单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑持久聊天策略 - 全局**”中，执行下列操作：
    
   - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
   - 在 "**说明**" 中, 提供有关用户策略的详细信息 (例如, _centralSiteName_的全局策略)。
    
   - 若要为未通过网站策略或用户策略明确控制的所有网站和用户控制持久聊天, 请选中或清除 "**启用持久聊天**" 复选框。
    
6. 单击“**提交**”。
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>为网站创建持久聊天策略

对于已部署的每个网站, 你可以创建特定于站点的持久聊天策略。
  
站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从 "**开始**" 菜单中, 选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口, 然后输入管理员 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。
    
4. 单击“**新建**”，然后单击“**站点策略**”。
    
5. 在“**选择站点**”中，单击要应用此策略的站点。
    
6. 在“**新建持久聊天策略**”中，执行下列操作之一：
    
   - 在“**名称**”中，指定新站点策略的名称（例如，Redmond）。
    
   - 在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。
    
   - 若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。
    
7. 单击“**提交**”。
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>创建持久聊天的用户策略

在 Skype for Business 服务器控制面板中, 你可以定义可分配给**用户**中用户的用户策略。
  
用户策略将覆盖全局策略和站点策略，但是仅限于为其分配了该用户策略的特定用户。
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从 "**开始**" 菜单中, 选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口, 然后输入管理员 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。
    
4. 单击“**新建**”，然后单击“**用户策略**”。
    
5. 在“**新建持久聊天策略**”中，执行下列操作之一：
    
   - 在“**名称**”中，指定新用户策略的名称。
    
   - 在 "**说明**" 中, 提供有关用户策略的详细信息 (例如, 针对特定用户的持久聊天策略)。
    
   - 若要为未通过用户策略明确控制的所有用户控制持久聊天, 请选中或清除 "**启用持久聊天**" 复选框。
    
6. 单击“**提交**”。
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>将持久聊天用户策略应用于用户帐户

如果用户已启用 Skype for business, 则可将相应策略应用于特定用户, 以便为永久聊天服务器启用或禁用它们。
  
使用本主题中的过程将以前创建的持久聊天用户策略应用于一个或多个用户帐户或用户组。
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从 "**开始**" 菜单中, 选择 "Skype For business 服务器" 控制面板或打开一个浏览器窗口, 然后输入管理员 URL。
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在 "**永久聊天策略**" 下的 "**编辑 Lync Server 用户**" 中, 选择要应用的持久聊天用户策略。
    
    > [!NOTE]
    > " ** \<自动\> **设置" 应用默认有效策略。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    

