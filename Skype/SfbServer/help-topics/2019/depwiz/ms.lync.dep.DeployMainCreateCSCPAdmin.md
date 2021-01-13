---
title: 创建 Skype for Business Server 控制面板管理员
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
f1.keywords:
- CSH
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 若要授予对 Skype for Business Server 的访问权限，请执行下列操作：
ms.openlocfilehash: cb1449aa4fcca534e01b4d8a47a7ac9c39cd64c7
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49824962"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>创建 Skype for Business Server 控制面板管理员
 
若要授予对 Skype for Business Server 的访问权限，请执行下列操作：
  
1. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
2. 打开“Active Directory 用户和计算机”，展开域，并右键单击“用户”容器，然后单击“属性”。
    
3. 在“CSAdministrator 属性”中，单击“成员”选项卡。
    
4. 在“成员”选项卡上，单击“添加”。在“选择用户、联系人、计算机、服务帐户或组”中，找到“输入要选择的对象名称”。键入要添加到 CSAdministrators 组的用户名或组名。单击“确定”。
    
5. 在“成员”选项卡上，确认所选的用户或组存在。单击“确定”。
    
> [!TIP]
> Skype for Business Server 控制面板是基于角色的访问控制工具。 CsAdministrator 组的成员身份为使用 Skype for Business Server 控制面板的用户提供了所有可用配置功能的完全控制权限。 为特定功能提供了其他专门的角色。 用户不需要启用 Skype for Business Server，就成为管理组的成员。 
  
其他角色包括：
  
- **CsArchiving：** 此组的成员可以执行所有存档功能，例如配置和管理存档服务器角色。
    
- **CsHelpDesk：** 该组的成员可以查看配置和部署，包括用户属性和策略。成员还可以执行特定的故障排除任务。
    
- **CsLocationAdministrator：** 成员具有与管理增强型 9-1-1 (E9-1-1) 相关的最低用户权限。他们可以在部署中创建 E9-1-1 位置和网络标识符并关联它们。
    
- **CsResponseGroupAdministrator：** 成员可以管理和配置响应组服务
    
- **CsServerAdministrator：** 成员可以管理、监视所有运行 Skype for Business Server 的服务器并排除故障。
    
- **CsUserAdministrator：** 成员可以管理、启用和禁用用户，以及将现有策略分配给用户。
    
- **CsViewOnlyAdministrator：** 成员可以查看服务器信息的部署和配置。 此成员身份使成员能够监视运行 Skype for Business Server 的服务器运行状况。
    
- **CsVoiceAdministrator：** 成员可以在 Skype for Business Server 中创建、配置和管理与语音相关的设置。
    
若要帮助保留安全性和基于角色的访问控制完整性，请向组添加用户，这些组定义了用户在 Skype for Business Server 部署管理中执行的角色。
  

