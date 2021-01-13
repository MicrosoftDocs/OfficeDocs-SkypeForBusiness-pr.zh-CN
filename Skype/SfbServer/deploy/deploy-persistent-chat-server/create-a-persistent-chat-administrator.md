---
title: 在 Skype for Business Server 2015 中创建持久聊天管理员
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 摘要：阅读本主题，了解如何创建持久聊天服务器管理员角色，以在 Skype for Business Server 2015 中启用持久聊天服务的初始配置和管理。
ms.openlocfilehash: eea989b0284353e193ebf99a0be99b2d0811e532
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802092"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建持久聊天管理员
 
**摘要：** 阅读本主题，了解如何创建持久聊天服务器管理员角色，以在 Skype for Business Server 2015 中启用持久聊天服务的初始配置和管理。
  
在 Skype for Business Server 中，必须将执行特定任务的用户分配为一个或多个特定组的成员。 Role-Based访问控制 (RBAC) 用于通过向预定义的 Skype for Business Server 管理角色分配用户来授予权限。 这些角色对应于 Active Directory 域服务中的通用安全组。 持久聊天管理员安全组 CsPersistentChatAdministrator 的成员被授予对持久聊天服务器 cmdlet 的访问权限，这些 cmdlet 可以使用 Skype for Business Server 命令行管理程序或 Skype for Business Server 控制面板执行。
  
在配置和管理持久聊天服务器之前，请确保相应的用户权限已就位，并且将充当持久聊天管理员的任何用户添加到持久聊天管理员安全组。
  
> [!NOTE] 
> 持久聊天在 Skype for Business Server 2015 中可用，但在 Skype for Business Server 2019 中不再受支持。 Teams 中也提供相同的功能。 有关详细信息，请参阅 [Microsoft Teams](/microsoftteams/upgrade-start-here)升级入门。 如果你需要使用持久聊天，你的选择是：将需要此功能的用户迁移到 Teams，或者继续使用 Skype for Business Server 2015。

## <a name="create-a-persistent-chat-administrator"></a>创建持久聊天管理员

若要将用户添加到持久聊天管理员安全组 CsPersistentChatAdministrator，请执行以下步骤：
  
1. 使用有权修改 Active Directory 组成员身份的帐户登录到安装了 Active Directory 用户和计算机的计算机。
    
2. 单击"开始"，单击"所有程序"，再单击"管理工具"，然后单击"Active Directory 用户和计算机"。
    
3. 在"Active Directory 用户和计算机"中，展开域的名称，然后单击"用户"容器。
    
4. 右键单击安全组 CsPersistentChatAdministrator，然后单击"属性"。
    
5. 在"属性"对话框中的"成员"选项卡上，单击"添加"。
    
6. 在"选择用户、计算机、联系人或组"对话框中，在"输入要选择的对象名称"框中键入要添加到组的用户的用户名或 显示名称，然后单击"确定"。
    
7. 在“属性”对话框中，单击“确定”。
    

