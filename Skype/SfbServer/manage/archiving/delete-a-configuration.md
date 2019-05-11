---
title: 删除存档配置中 Skype 业务服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fed12cb5-2c80-476a-af3b-d55b450c5fbc
description: 摘要： 了解如何删除存档配置中 Skype 业务服务器。
ms.openlocfilehash: 3b6f79247a03beae4abc917d38a6844d67324082
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33884973"
---
# <a name="delete-an-archiving-configuration-in-skype-for-business-server"></a>删除存档配置中 Skype 业务服务器

**摘要：** 了解如何删除存档配置中 Skype 业务服务器。
  
可以删除站点配置或池配置，但无法删除全局配置。如果删除全局配置，该配置将自动重置为默认值。
  
## <a name="delete-an-archiving-configuration-by-using-the-control-panel"></a>使用控制面板删除存档配置

要使用控制面板删除存档配置
  
1. 使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。 
    
2. 打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。 
    
3. 在左侧导航栏中，单击“监控和存档”****，然后单击“存档配置”****。
    
4. 在存档配置的列表中，单击要删除的站点或池配置，单击“**编辑**”，然后单击“**删除**”。
    
    > [!NOTE]
    > 您也可以单击全局配置，但仅在希望将全局配置重置为默认值时选择此选项。 
  
5. 单击“**提交**”。
    
## <a name="delete-an-archiving-configuration-by-using-windows-powershell"></a>使用 Windows PowerShell 删除存档配置

您还可以使用**Remove-csarchivingconfiguration** cmdlet 删除存档配置。
  
例如，以下命令可删除应用于 Redmond 站点的存档配置设置。删除在站点范围内配置的策略后，先前受站点策略管理的用户将自动受到全局存档策略的管理：
  
```
Remove-CsArchivingConfiguration -Identity "site:Redmond"
```

以下命令会删除应用到服务范围的所有存档配置设置：
  
```
Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration
```

下一条命令会删除在其中已禁用 Exchange 存档的所有存档配置设置：
  
```
Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration
```

您也可以使用 **Remove-CsArchivingConfiguration** cmdlet 将全局设置重置为默认值。 例如，假设您已在全局级别启用 IM 会话存档；以下命令会将该值重置为默认值 None，这将在全局级别禁用存档：
  
```
Remove-CsArchivingConfiguration -Identity global
```

有关详细信息，请参阅[Remove-csarchivingconfiguration](https://docs.microsoft.com/powershell/module/skype/remove-csarchivingconfiguration?view=skype-ps) cmdlet 的帮助主题。
