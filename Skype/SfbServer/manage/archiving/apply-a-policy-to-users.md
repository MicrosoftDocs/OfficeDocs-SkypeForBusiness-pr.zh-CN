---
title: 将存档策略应用于 Skype for Business 服务器中的用户
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: bebd45d1-93c3-4e80-8933-755b699b2209
description: 摘要：了解如何为 Skype for Business Server 中的用户分配存档策略。
ms.openlocfilehash: 5dbd1624813b187e8c0981aa1a84b6096b79e86a
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992779"
---
# <a name="apply-an-archiving-policy-to-users-in-skype-for-business-server"></a>将存档策略应用于 Skype for Business 服务器中的用户

**摘要：** 了解如何为 Skype for Business Server 中的用户分配存档策略。
  
如果已为驻留在 Skype for business Server 上的用户创建了一个或多个用户策略，则可以通过向这些用户或用户组应用相应的策略来实现对特定用户的存档支持。 例如，如果创建了支持内部通信存档的策略，则可以将其应用到至少一个用户或用户组以支持用户的 Skype for Business 服务器通信的存档。
  
> [!NOTE]
> 如果为你的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管在 Exchange 上的用户启用存档，并将其邮箱置于原地保留。 有关详细信息，请参阅[在 skype for Business 服务器中规划存档](../../plan-your-deployment/archiving/archiving.md)和[配置与 Skype for Business 服务器的 Exchange 存储的集成](../../deploy/deploy-archiving/configure-integration-with-exchange-storage.md)。 
  
## <a name="apply-a-user-policy-by-using-the-control-panel"></a>使用控制面板应用用户策略

使用控制面板应用用户策略：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“**用户**”，然后搜索要配置的用户帐户。 
    
4. 在列出搜索结果的表中，单击相应的用户帐户，再单击“**编辑**”，然后单击“**显示详细信息**”。
    
5. 在 "在**存档策略**中**编辑 Lync 服务器用户**" 下，选择要应用的存档用户策略。
    
    > [!NOTE]
    > " ** \<自动\> **设置" 应用默认服务器安装设置。 服务器将自动应用这些设置。
  
6. 单击“**提交**”。
    
## <a name="apply-a-user-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 应用用户策略

你还可以使用 Windows PowerShell**授权 CsArchivingPolicy** cmdlet 应用用户策略。
  
以下命令向用户 Ken Myer 分配每用户存档策略 RedmondArchivingPolicy。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName "RedmondArchivingPolicy"
```

此命令向帐户驻留在注册器池 atl-cs-001.contoso.com 的所有用户分配每用户存档策略 RedmondArchivingPolicy。 有关此命令中使用的筛选器参数的详细信息，请参阅[move-csuser](https://docs.microsoft.com/powershell/module/skype/get-csuser?view=skype-ps) cmdlet 文档。
  
```PowerShell
Get-CsUser -Filter {RegistrarPool -eq "atl-cs-001.contoso.com"} | Grant-CsArchivingPolicy -PolicyName "RedmondArchivingPolicy"
```

以下命令可删除之前已分配给 Ken Myer 的所有每用户存档策略。在删除每用户策略后，将自动使用全局策略或本地站点策略（如果有）管理 Ken Myer。站点策略优先于全局策略。
  
```PowerShell
Grant-CsArchivingPolicy -Identity "Ken Myer" -PolicyName $Null
```

有关详细信息，请参阅[CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/grant-csarchivingpolicy?view=skype-ps) cmdlet 文档。
  

