---
title: 在 Skype for Business Server 2015 中创建持久聊天管理员
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 摘要： 阅读本主题可了解如何创建启用初始配置和管理业务服务器 2015年持久聊天中的 services Skype 的持久聊天服务器管理员角色。
ms.openlocfilehash: fb8a222f65f6fe579d3600df15a53bb84f65de66
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32225340"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建持久聊天管理员
 
**摘要：** 阅读本主题可了解如何创建启用初始配置和管理业务服务器 2015年持久聊天中的 services Skype 的持久聊天服务器管理员角色。
  
在 Skype 业务服务器，必须将执行特定任务的用户分配为一个或多个特定组的成员。 基于角色的访问控制 (RBAC) 用于通过向预定义 Skype 业务服务器管理角色分配用户授予权限。 这些角色对应 Active Directory 域服务中的通用安全组。 CsPersistentChatAdministrator，Persistent Chat Administrator 安全组的成员会被授予访问可用于业务业务 Server 命令行管理程序 Skype 或 Skype 执行的持久聊天服务器 cmdletServer Control Panel。
  
在配置和管理持久聊天服务器之前，请确保已分配相应的用户权限，并将充当持久聊天管理员的任何用户添加到持久聊天管理员安全组中。
  
> [!NOTE] 
> 持久聊天中的业务服务器 2015 Skype 可用但业务服务器 2019年不再支持在 Skype。 中团队提供了相同的功能。 有关详细信息，请参阅[从企业对 Microsoft 团队的 Skype 旅程](/microsoftteams/journey-skypeforbusiness-teams)。 如果您需要使用持久聊天，您的选择是也迁移要求给团队，此功能的用户或继续对业务服务器 2015年使用 Skype。

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

若要将用户添加到持久聊天管理员安全组，CsPersistentChatAdministrator，执行以下步骤：
  
1. 使用具有修改 Active Directory 组成员身份权限的帐户，登录到已安装“Active Directory 用户和计算机”的计算机。
    
2. 依次单击“开始”、“所有程序”、“管理工具”，然后单击“Active Directory 用户和计算机”。
    
3. 在“Active Directory 用户和计算机”中，展开域名并单击“用户”容器。
    
4. 右键单击安全组 CsPersistentChatAdministrator，然后单击“属性”。
    
5. 在“属性”对话框的“成员”选项卡上，单击“添加”。
    
6. 在“选择用户、计算机、联系人或组”对话框的“输入要选择的对象名称”框中，键入要添加到组的用户的用户名或显示名称，然后单击“确定”。
    
7. 在“属性”对话框中，单击“确定”。
    

