---
title: 删除存档配置Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要：了解如何删除存档配置Skype for Business Server。
ms.openlocfilehash: defd9377453234e400dbf75a7d0261c52904adda
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/08/2021
ms.locfileid: "60851025"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>删除存档配置Skype for Business Server

**摘要：** 了解如何删除存档配置Skype for Business Server。
  
可以删除站点配置或池配置，但无法删除全局配置。 如果删除全局配置，该配置将自动重置为默认值。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>使用控制面板删除存档配置

使用控制面板删除存档配置：
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开浏览器窗口，然后输入管理 URL 以打开Skype for Business Server控制面板。 
    
3. 在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档配置”**。
    
4. 在存档配置列表中，单击要删除的站点或池配置，再单击"编辑"，然后单击"删除 **"。**
    
    > [!NOTE]
    > 还可以单击"全局"配置，但仅在希望将"全局"配置重置为默认值时选择此选项。 
  
5. 单击“提交”。
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>使用配置删除存档Windows PowerShell

您还可以使用 **Remove-CsArchivingConfiguration** cmdlet 删除存档配置。
  
例如，以下命令可删除应用于 Redmond 站点的存档配置设置。 删除在站点范围配置的策略后，之前由站点策略管理的用户将自动受到全局存档策略的管理：
  
```PowerShell
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

以下命令删除应用于服务范围的所有存档配置设置：
  
```PowerShell
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

下一个命令将删除已禁用存档Exchange的所有存档配置设置：
  
```PowerShell
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

您还可以使用 **Remove-CsArchivingConfiguration** cmdlet 将全局设置重置为默认值。 例如，假设您在全局级别启用了 IM 会话存档;以下命令将该值重置为默认值 None，这将在全局级别禁用存档：
  
```PowerShell
Remove-CsArchivingConfiguration -Identity global
```

有关详细信息，请参阅 [Remove-CsArchivingConfiguration](/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。