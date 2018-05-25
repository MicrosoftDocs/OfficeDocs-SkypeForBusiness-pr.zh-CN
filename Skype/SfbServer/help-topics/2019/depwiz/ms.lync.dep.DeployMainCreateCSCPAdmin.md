---
title: 创建 Skype for Business Server 控制面板管理员
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/8/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
description: 向 Skype 授予访问权限的业务服务器 2015年，执行以下操作：
ms.openlocfilehash: db781611e2df2abf23c071673d3dfe0570f5700b
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>创建 Skype for Business Server 控制面板管理员
 
向 Skype 授予访问权限的业务服务器 2015年，执行以下操作：
  
1. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
2. 打开“**Active Directory 用户和计算机**”，展开域，并右键单击“**用户**”容器，然后单击“**属性**”。
    
3. 在“**CSAdministrator 属性**”中，单击“**成员**”选项卡。
    
4. 在“成员”选项卡上，单击“**添加**”。在“**选择用户、联系人、计算机、服务帐户或组**”中，找到“**输入要选择的对象名称**”。键入要添加到 CSAdministrators 组的用户名或组名。单击“**确定**”。
    
5. 在“成员”选项卡上，确认所选的用户或组存在。单击“**确定**”。
    
> [!TIP]
> 为业务 Server Control Panel Skype 是一个基于角色的访问控制工具。 CsAdministrator 组的成员提供的业务 Server Control Panel 完全控制的所有可用的配置函数使用 Skype 的用户。 为特定功能提供了其他专门的角色。 用户没有要启用 Skype 业务服务器才能成为管理组的成员。 
  
其他角色包括：
  
- **CsArchiving:** 此组的成员可以执行所有存档功能，如配置和管理存档服务器角色。
    
- **CsHelpDesk：** 该组的成员可以查看配置和部署，包括用户属性和策略。成员还可以执行特定的故障排除任务。
    
- **CsLocationAdministrator：** 成员具有与管理增强型 9-1-1 (E9-1-1) 相关的最低用户权限。他们可以在部署中创建 E9-1-1 位置和网络标识符并关联它们。
    
- **CsResponseGroupAdministrator：** 成员可以管理和配置响应组服务。
    
- **CsServerAdministrator:** 成员可以管理、 监视和解决业务服务器运行 Skype 的所有服务器。
    
- **CsUserAdministrator：** 成员可以管理、启用和禁用用户，以及将现有策略分配给用户。
    
- **CsViewOnlyAdministrator:** 成员可以查看部署和配置服务器信息。 此成员资格使成员 to monitor the health 的业务服务器 2015年运行 Skype 的服务器。
    
- **CsVoiceAdministrator:** 成员可以创建、 配置和管理 Skype 中的业务服务器的语音相关的设置。
    
若要帮助保留安全性和基于角色的访问控制完整性，请将用户添加到定义了用户执行的业务服务器部署 Skype 的管理角色组。
  

