---
title: 持久聊天策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/27/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.PersistentChatPolicy
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: eb9e95b9-f69d-4545-970f-9dfdd93b0eff
description: 您可以使用“持久聊天”组的“持久聊天策略”页来管理全局级、池级、站点级或用户级的策略，包括为部署配置默认全局策略以及创建一个或多个其他用户和站点策略。 如果策略为用户启用了持久聊天服务器，然后持久聊天服务器环境中将显示他们的客户端。
ms.openlocfilehash: 95020a24cc8f68c33028977cc5e4c3569423b219
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375781"
---
# <a name="persistent-chat-policy"></a>持久聊天策略
 
您可以使用“**持久聊天**”组的“**持久聊天策略**”页来管理全局级、池级、站点级或用户级的策略，包括为部署配置默认全局策略以及创建一个或多个其他用户和站点策略。 如果策略为用户启用了持久聊天服务器，然后持久聊天服务器环境中将显示他们的客户端。
  
当部署持久聊天服务器，并可以配置，但不是删除时，将自动创建的全局策略。 全局策略应用于所有用户，因为它不具有每个用户设置。
  
您可以创建和配置多个站点和用户策略的全局策略，以及为用户启用持久聊天服务器。 池和站点的持久聊天服务器策略将覆盖全局持久聊天服务器策略，但仅对该网站的用户。 用户策略将覆盖分配有用户策略的用户的全局、池和站点策略。
  
> [!NOTE]
> 配置和使用持久聊天服务器，必须首先使用拓扑生成器向持久聊天服务器支持的拓扑，添加，然后发布该拓扑。 有关详细信息，请参阅[将持久聊天服务器添加到您的业务服务器 2015年拓扑的 Skype](../../deploy/deploy-persistent-chat-server/add-persistent-chat-server.md)。 
  
## <a name="tasks-that-you-can-perform"></a>可执行的任务

您可以在**持久聊天策略**页上执行以下任务：启用“持久聊天服务器”策略；管理“持久聊天服务器”策略。
  
## <a name="to-configure-the-global-policy-for-persistent-chat"></a>为持久聊天配置全局策略

1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在业务 Server Control Panel 的 Skype，单击**持久聊天**，，然后单击**持久聊天策略**。
    
4. 单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑持久聊天策略 - 全局**”中，执行下列操作：
    
   - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
   - 在**说明**框中，提供有关用户策略内容 （例如， _centralsitename_的全局策略） 的详细信息。
    
   - 若要控制的所有站点和未通过站点策略或用户策略明确控制的用户的持久聊天，请选中或清除**启用持久聊天**复选框。
    
6. 单击“**提交**”。
    
## <a name="to-create-a-persistent-chat-policy-for-a-site"></a>若要创建站点的持久聊天策略

对于已部署的每个站点，您可以创建特定于站点的持久聊天策略。
  
站点策略中的配置将覆盖全局策略，但是仅限于站点策略所涉及的特定站点。
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。
    
4. 单击“**新建**”，然后单击“**站点策略**”。
    
5. 在“**选择站点**”中，单击要应用此策略的站点。
    
6. 在“**新建持久聊天策略**”中，执行下列操作之一：
    
   - 在“**名称**”中，指定新站点策略的名称（例如，Redmond）。
    
   - 在“**说明**”中，提供有关该站点策略内容的详细信息（例如，Redmond 的聊天室策略）。
    
   - 若要控制未通过站点策略明确控制的所有站点的持久聊天，请选中或清除“**启用持久聊天**”复选框。
    
7. 单击“**提交**”。
    
## <a name="to-create-a-user-policy-for-persistent-chat"></a>为持久聊天创建用户策略

在业务 Server 控制面板的 Skype，定义可分配给**用户**中的用户的用户策略。
  
用户策略将覆盖全局策略和站点策略，但是仅限于为其分配了该用户策略的特定用户。
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。
    
4. 单击“**新建**”，然后单击“**用户策略**”。
    
5. 在“**新建持久聊天策略**”中，执行下列操作之一：
    
   - 在“**名称**”中，指定新用户策略的名称。
    
   - 在**说明**框中，提供有关用户策略内容 （例如，为特定用户的持久聊天策略） 的详细信息。
    
   - 若要控制未专门通过用户策略控制的所有用户的持久聊天，请选中或清除**启用持久聊天**复选框。
    
6. 单击“**提交**”。
    
## <a name="to-apply-a-persistent-chat-user-policy-to-a-user-account"></a>将持久聊天用户策略应用于用户帐户

如果用户已启用的 Skype 业务服务器，则可以向特定用户启用或禁用这些 for Persistent Chat Server 应用适当的策略。
  
使用本主题中的过程将以前创建持久聊天用户策略应用于一个或多个用户帐户或用户组。
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在**编辑 Lync Server 用户****持久聊天策略**下，选择要应用的持久聊天用户策略。
    
    > [!NOTE]
    > **\<自动\>** 设置应用默认有效策略。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    

