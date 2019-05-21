---
title: 在 Skype for Business 服务器中删除现有存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: '摘要: 了解如何删除 Skype for business 服务器的存档策略。'
ms.openlocfilehash: 04ea9db10a2f95ba5010471f262d58c269c173d1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34278410"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>在 Skype for Business 服务器中删除现有存档策略

**摘要:** 了解如何删除 Skype for business 服务器的存档策略。
  
可以删除用户策略或站点策略，但无法删除全局策略。 如果您删除全局策略, 则 Skype for Business 服务器会自动将策略重置为默认值。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>使用控制面板删除策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口, 然后输入管理员 URL 以打开 Skype for Business 服务器控制面板。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档策略”****。
    
4. 在存档策略列表中，单击要删除的用户策略或站点策略，再单击“**编辑**”，然后单击“**删除**”。
    
5. 单击“**提交**”。
    
## <a name="delete-a-policy-by-using-windows-powershell"></a>使用 Windows PowerShell 删除策略

您也可以使用 **Remove-CsArchivingPolicy** cmdlet 删除存档策略。
  
例如，以下命令可删除具有 Identity site:Redmond 的策略。删除在站点级别配置的策略后，先前受站点策略管理的用户将自动受到全局存档策略的管理：
  
```
Remove-CsArchivingPolicy -Identity site:Redmond
```

此命令将删除所有适用于每用户级别的存档策略：
  
```
Get-CsArchivingPolicy -Filter "tag:*" | Remove-CsArchivingPolicy
```

此命令将删除其中禁用了内部存档的所有存档策略：
  
```
Get-CsArchivingPolicy | Where-Object {$_.ArchiveInternal -eq $False} | Remove-CsArchivingPolicy
```

有关详细信息, 请参阅[CsArchivingPolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。
