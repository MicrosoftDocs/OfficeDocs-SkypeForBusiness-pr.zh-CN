---
title: 创建 Skype for Business Server 控制面板管理员
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 2/8/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
ms.localizationpriority: medium
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 若要授予对 Skype for Business Server 2015 的访问权限，请执行下列操作：
ms.openlocfilehash: ef975e064d33473d87e44c4e14725b58b28bce27
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2021
ms.locfileid: "60744868"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>创建 Skype for Business Server 控制面板管理员
 
若要授予对 Skype for Business Server 2015 的访问权限，请执行下列操作：
  
1. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
2. 打开“Active Directory 用户和计算机”，展开域，并右键单击“用户”容器，然后单击“属性”。
    
3. 在“CSAdministrator 属性”中，单击“成员”选项卡。
    
4. 在“成员”选项卡上，单击“添加”。在“选择用户、联系人、计算机、服务帐户或组”中，找到“输入要选择的对象名称”。键入要添加到 CSAdministrators 组的用户名或组名。单击“确定”。
    
5. 在“成员”选项卡上，确认所选的用户或组存在。单击“确定”。
    
> [!TIP]
> 该Skype for Business Server控制面板是基于角色的访问控制工具。 CsAdministrator 组的成员身份为使用 Skype for Business Server 控制面板的用户提供了对所有可用配置功能的完全控制权限。 为特定功能提供了其他专门的角色。 用户不需要启用Skype for Business Server，就成为管理组的成员。 
  
其他角色包括：
  
- **CsArchiving：** 此组的成员可以执行所有存档功能，例如配置和管理存档服务器角色。
    
- **CsHelpDesk：** 该组的成员可以查看配置和部署，包括用户属性和策略。成员还可以执行特定的故障排除任务。
    
- **CsLocationAdministrator：** 成员具有与管理增强型 9-1-1 (E9-1-1) 相关的最低用户权限。他们可以在部署中创建 E9-1-1 位置和网络标识符并关联它们。
    
- **CsResponseGroupAdministrator：** 成员可以管理和配置响应组服务
    
- **CsServerAdministrator：** 成员可以管理、监视所有运行 Skype for Business Server 的服务器并排除Skype for Business Server。
    
- **CsUserAdministrator：** 成员可以管理、启用和禁用用户，以及将现有策略分配给用户。
    
- **CsViewOnlyAdministrator：** 成员可以查看服务器信息的部署和配置。 此成员身份使成员能够监视运行 2015 年 2015 Skype for Business Server的运行状况。
    
- **CsVoiceAdministrator：** 成员可以在用户环境中创建、配置和管理与语音Skype for Business Server。
    
为了帮助保留安全性和基于角色的访问控制完整性，将用户添加到组，这些组定义了用户在管理 Skype for Business Server 的角色。
  

