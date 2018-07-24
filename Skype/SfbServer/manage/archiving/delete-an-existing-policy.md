---
title: 删除现有的业务服务器存档策略中 Skype
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8b88bed9-2b37-4caf-b119-48688076e06a
description: 摘要： 了解如何删除存档策略的 Skype 业务服务器。
ms.openlocfilehash: 0446999923b462311f941b6653157b41000b1f43
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20973099"
---
# <a name="delete-an-existing-archiving-policy-in-skype-for-business-server"></a>删除现有的业务服务器存档策略中 Skype

**摘要：** 了解如何删除存档策略的 Skype 业务服务器。
  
可以删除用户策略或站点策略，但无法删除全局策略。 如果您删除全局策略，Skype 业务服务器自动将策略重置为默认值。
  
## <a name="delete-a-policy-by-using-the-control-panel"></a>使用控制面板删除策略

1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“**监控和存档**”，然后单击“**存档策略**”。
    
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

有关详细信息，请参阅[Remove-csarchivingpolicy](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingpolicy?view=skype-ps) cmdlet 的帮助主题。