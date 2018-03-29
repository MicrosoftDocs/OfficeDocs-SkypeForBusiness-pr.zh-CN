---
title: 在 Skype for Business Server 2015 中创建持久聊天管理员
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: 摘要： 阅读本主题，以了解如何创建启用初始配置和管理的持久聊天服务 Skype 业务服务器 2015年的持久聊天服务器管理员角色。
ms.openlocfilehash: 4efe5dff2821784a24f51712b8a19dad83e47c3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建持久聊天管理员
 
**摘要：**阅读本主题，以了解如何创建启用初始配置和管理的持久聊天服务 Skype 业务服务器 2015年的持久聊天服务器管理员角色。
  
在 Skype 业务服务器，必须为一个或多个特定组的成员分配用户执行特定任务。 使用基于角色的访问控制 (RBAC) 是通过将用户分配到预定义的 Skype 业务服务器管理角色授予的权限。 这些角色对应 Active Directory 域服务中的通用安全组。 持续聊天管理员安全组，CsPersistentChatAdministrator 的成员会被授予访问持久聊天服务器的 cmdlet，可以为企业使用的业务服务器管理外壳 Skype 或 Skype 执行服务器的控制面板。
  
在配置和管理持久聊天服务器之前，请确保已分配相应的用户权限，并将充当持久聊天管理员的任何用户添加到持久聊天管理员安全组中。
  
## <a name="create-a-persistent-chat-administrator"></a>创建持久聊天管理员

若要将用户添加到的持续聊天管理员安全组中，CsPersistentChatAdministrator，请执行以下步骤：
  
1. 使用具有修改 Active Directory 组成员身份权限的帐户，登录到已安装“Active Directory 用户和计算机”的计算机。
    
2. 依次单击“开始”、“所有程序”、“管理工具”，然后单击“Active Directory 用户和计算机”。
    
3. 在“Active Directory 用户和计算机”中，展开域名并单击“用户”容器。
    
4. 右键单击安全组 CsPersistentChatAdministrator，然后单击“属性”。
    
5. 在“属性”对话框的“成员”选项卡上，单击“添加”。
    
6. 在“选择用户、计算机、联系人或组”对话框的“输入要选择的对象名称”框中，键入要添加到组的用户的用户名或显示名称，然后单击“确定”。
    
7. 在“属性”对话框中，单击“确定”。
    

