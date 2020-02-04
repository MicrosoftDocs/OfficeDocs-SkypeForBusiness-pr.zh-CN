---
title: 创建 Skype for Business Server 控制面板管理员
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.dep.DeployMainCreateCSCPAdmin
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3312926a-4671-4030-bb92-90ac24c778dd
ROBOTS: NOINDEX, NOFOLLOW
description: 若要向 Skype for Business 服务器授予访问权限，请执行下列操作：
ms.openlocfilehash: 79b1c4bd181c18ee48f4172fd232467a77f21714
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41705449"
---
# <a name="create-skype-for-business-server-control-panel-administrators"></a>创建 Skype for Business Server 控制面板管理员
 
若要向 Skype for Business 服务器授予访问权限，请执行下列操作：
  
1. 以 Domain Admins 组或 RTCUniversalServerAdmins 组成员的身份登录。
    
2. 打开“**Active Directory 用户和计算机**”，展开域，并右键单击“**用户**”容器，然后单击“**属性**”。
    
3. 在“**CSAdministrator 属性**”中，单击“**成员**”选项卡。
    
4. 在“成员”选项卡上，单击“**添加**”。在“**选择用户、联系人、计算机、服务帐户或组**”中，找到“**输入要选择的对象名称**”。键入要添加到 CSAdministrators 组的用户名或组名。单击“**确定**”。
    
5. 在“成员”选项卡上，确认所选的用户或组存在。单击“**确定**”。
    
> [!TIP]
> Skype for Business Server "控制面板" 是基于角色的访问控制工具。 CsAdministrator 组中的成员身份为所有可用的配置函数提供了使用 Skype for Business Server 控制面板的 "完全控制" 的用户。 还有其他为特定功能设计的专门角色可用。 无需为 Skype for business 服务器启用用户，即可成为管理组的成员。 
  
其他角色包括：
  
- **CsArchiving：** 本组成员可以执行所有存档功能，例如配置和管理存档服务器角色。
    
- **CsHelpDesk：** 该组的成员可以查看配置和部署，包括用户属性和策略。成员还可以执行特定的故障排除任务。
    
- **CsLocationAdministrator：** 成员具有与管理增强型 9-1-1 (E9-1-1) 相关的最低用户权限。他们可以在部署中创建 E9-1-1 位置和网络标识符并关联它们。
    
- **CsResponseGroupAdministrator：** 成员可以管理和配置响应组服务。
    
- **CsServerAdministrator：** 成员可以管理、监视和解决运行 Skype for Business 服务器的所有服务器。
    
- **CsUserAdministrator：** 成员可以管理、启用和禁用用户，以及将现有策略分配给用户。
    
- **CsViewOnlyAdministrator：** 成员可以查看服务器信息的部署和配置。 此成员身份使成员能够监视运行 Skype for Business 服务器的服务器的运行状况。
    
- **CsVoiceAdministrator：** 成员可以在 Skype for Business Server 中创建、配置和管理语音相关设置。
    
若要帮助保留安全和基于角色的访问控制完整性，请将用户添加到定义用户在管理 Skype for Business 服务器部署时所执行的角色的组。
  

