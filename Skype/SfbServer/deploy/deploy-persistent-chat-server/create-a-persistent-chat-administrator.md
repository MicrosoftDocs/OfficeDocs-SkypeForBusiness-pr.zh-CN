---
title: 在 Skype for Business Server 2015 中创建持久聊天管理员
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/28/2016
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5c3892e4-ebae-453e-8107-f42ec0436ea2
description: '摘要: 阅读本主题, 了解如何创建持久聊天服务器管理员角色, 以便在 Skype for Business Server 2015 中启用持久聊天服务的初始配置和管理。'
ms.openlocfilehash: 1b593f1de776f1896d43bab35a15af7b6bcf7245
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34273880"
---
# <a name="create-a-persistent-chat-administrator-in-skype-for-business-server-2015"></a>在 Skype for Business Server 2015 中创建持久聊天管理员
 
**摘要:** 阅读本主题, 了解如何创建持久聊天服务器管理员角色, 以便在 Skype for Business Server 2015 中启用持久聊天服务的初始配置和管理。
  
在 Skype for Business 服务器中, 执行特定任务的用户必须分配为一个或多个特定组的成员。 基于角色的访问控制 (RBAC) 用于通过将用户分配给预定义的 Skype for business 服务器管理角色来授予权限。 这些角色对应 Active Directory 域服务中的通用安全组。 永久性聊天管理员安全组的成员 CsPersistentChatAdministrator 授予访问持久聊天服务器 cmdlet 的权限, 可以使用 Skype for Business 服务器管理外壳或 Skype for business 执行此 cmdlet"服务器控制面板"。
  
在配置和管理持久聊天服务器之前，请确保已分配相应的用户权限，并将充当持久聊天管理员的任何用户添加到持久聊天管理员安全组中。
  
> [!NOTE] 
> Skype for business Server 2015 中提供了持久聊天, 但 Skype for business Server 2019 不再支持此功能。 团队中提供了相同的功能。 有关详细信息, 请参阅[从 Skype For Business 迁移到 Microsoft 团队](/microsoftteams/journey-skypeforbusiness-teams)。 如果需要使用持久聊天, 您可以选择将需要此功能的用户迁移到团队, 或继续使用 Skype for Business Server 2015。

## <a name="create-a-persistent-chat-administrator"></a>Create a Persistent Chat administrator

若要将用户添加到持久聊天管理员安全组, 请 CsPersistentChatAdministrator, 请执行以下步骤:
  
1. 使用具有修改 Active Directory 组成员身份权限的帐户，登录到已安装“Active Directory 用户和计算机”的计算机。
    
2. 依次单击“开始”、“所有程序”、“管理工具”，然后单击“Active Directory 用户和计算机”。
    
3. 在“Active Directory 用户和计算机”中，展开域名并单击“用户”容器。
    
4. 右键单击安全组 CsPersistentChatAdministrator，然后单击“属性”。
    
5. 在“属性”对话框的“成员”选项卡上，单击“添加”。
    
6. 在“选择用户、计算机、联系人或组”对话框的“输入要选择的对象名称”框中，键入要添加到组的用户的用户名或显示名称，然后单击“确定”。
    
7. 在“属性”对话框中，单击“确定”。
    

