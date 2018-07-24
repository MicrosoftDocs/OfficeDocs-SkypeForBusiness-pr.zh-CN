---
title: 配置 Skype for Business Server 2015 中的持久聊天用户策略
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5862480-95f8-4d76-a2b5-940cd995e93c
description: 摘要： 阅读本主题可了解如何为业务服务器 2015 Persistent Chat Server in Skype 创建初始用户策略。 持久聊天用户策略确定允许用户访问聊天室。
ms.openlocfilehash: 186611977a1a9dfa77549e8f0c5df6b863718eee
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "21000834"
---
# <a name="configure-persistent-chat-user-policies-in-skype-for-business-server-2015"></a>配置 Skype for Business Server 2015 中的持久聊天用户策略
 
**摘要：** 阅读本主题可了解如何为业务服务器 2015 Persistent Chat Server in Skype 创建初始用户策略。 持久聊天用户策略确定允许用户访问聊天室。
  
您可以管理持久聊天服务器在以下级别的用户策略： 全局、 站点或用户。 最初，您配置全局策略以为部署中的所有用户启用持久聊天设置，然后创建其他用户和站点策略以控制是否为特定用户和站点打开持久聊天。
  
本主题包括以下部分：
  
- 配置全局策略
    
- 创建站点策略
    
- 创建用户策略
    
- 将策略应用于用户或用户组
    
> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。

## <a name="configure-the-global-policy"></a>配置全局策略

要配置全局策略：
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在业务 Server Control Panel 的 Skype，单击**持久聊天**，，然后单击**持久聊天策略**。
    
4. 单击策略列表中的“**全局**”，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在“**编辑持久聊天策略 - 全局**”中，执行下列操作： 
    
   - 在“**名称**”中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。
    
   - 在**说明**框中，提供有关用户策略内容 （例如， _centralsitename_的全局策略） 的详细信息。
    
   - 若要控制的所有站点和未通过站点策略或用户策略明确控制的用户的持久聊天，请选中或清除**启用持久聊天**复选框。
    
6. 单击“**提交**”。
    
## <a name="create-a-site-policy"></a>创建站点策略

对于已部署的每个站点，您可以创建特定于站点的持久聊天策略。 站点策略中的配置可覆盖全局策略，但仅适用于站点策略所涵盖的特定站点。 要创建站点策略：
  
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
    
## <a name="create-a-user-policy"></a>创建用户策略

您可以创建特定于用户的策略，该策略可覆盖用户所属的全局策略和任何站点策略。 要创建用户策略：
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“**持久聊天**”，然后单击“**持久聊天策略**”。
    
4. 单击“**新建**”，然后单击“**用户策略**”。
    
5. 在“**新建持久聊天策略**”中，执行下列操作之一：
    
   - 在“**名称**”中，指定新用户策略的名称。
    
   - 在**说明**框中，提供有关用户策略内容 （例如，为特定用户的持久聊天策略） 的详细信息。
    
   - 若要控制未专门通过用户策略控制的所有用户的持久聊天，请选中或清除**启用持久聊天**复选框。
    
6. 单击“**提交**”。
    
## <a name="apply-a-policy-to-a-user-account"></a>向用户组应用策略

创建策略后，您可以将策略应用于用户账户，如下所示：
  
1. 从分配给 CsPersistentChatAdministrator、CsAdministrator 或 CsUserAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。
    
2. 从**开始**菜单上，选择业务 Server Control Panel Skype 或打开一个浏览器窗口中，，然后输入管理 URL。
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在**持久聊天策略**下**的企业服务器用户编辑 Skype** ，选择要应用的持久聊天用户策略。
    
    > [!NOTE]
    > **\<自动\>** 设置应用默认有效策略。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    

