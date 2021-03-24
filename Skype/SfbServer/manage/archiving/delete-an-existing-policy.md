---
title: 删除 Skype for Business Server 中的现有存档策略
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 摘要：了解如何删除 Skype for Business Server 的存档策略。
ms.openlocfilehash: 2baad7d862b1b6739019a4459492bfb3b67e04cc
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095386"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>删除 Skype for Business Server 中的现有存档策略

**摘要：** 了解如何删除 Skype for Business Server 的存档策略。
  
可以删除用户策略或站点策略，但不能删除全局策略。 如果删除全局策略，Skype for Business Server 会自动将策略重置为默认值。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>使用控制面板删除策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开 Skype for Business Server 控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。
    
4. 在存档策略列表中，单击要删除的用户策略或站点策略，再单击“编辑”，然后单击“删除”。
    
5. 单击“提交”。
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>使用策略删除Windows PowerShell

您还可以使用 **Remove-CsArchivingPolicy** cmdlet 删除存档策略。
  
例如，以下命令删除 Identity 为 site：Redmond 的策略。 删除在站点级别配置的策略后，之前由站点策略管理的用户将自动受到全局存档策略的管理：
  
```PowerShell
Remove-CsArchivingPolicy -Identity site:Redmond
```

此命令删除应用于每用户级别的所有存档策略：
  
```PowerShell
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

此命令将删除其中禁用了内部存档的所有存档策略：
  
```PowerShell
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

有关详细信息，请参阅 [Remove-CsArchivingPolicy](/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。