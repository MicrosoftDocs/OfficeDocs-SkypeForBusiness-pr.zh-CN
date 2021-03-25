---
title: 管理 Skype for Business Online 组织
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 和 Get-CsTenant Get-CsTenantLicensingConfiguration cmdlet 获取有关 Skype for Business Online 租户的信息。
ms.openlocfilehash: ed15d062bf4f2e5f2ad0f47169ac0626d2c59d20
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51113178"
---
# <a name="manage-skype-for-business-online-organizations"></a>管理 Skype for Business Online 组织
> [!NOTE]
> 最新的 [Teams PowerShell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/) 与 Skype for Business Online 连接器集成，为 Teams PowerShell 管理提供单个模块。

可以使用 **Get-CsTenant** 和 **Get-CsTenantLicensingConfiguration** cmdlet 查找有关 Skype for Business Online 租户的信息。
  
## <a name="manage-skype-for-business-online-tenants"></a>管理 Skype for Business Online 租户

若要返回有关 Skype for Business Online 租户的信息，请不带任何其他参数调用 [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet。
  
```PowerShell
Get-CsTenant
```

若要仅返回租户名称和 ID，请使用此命令。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

运行 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)等 cmdlet 时，需要 _TenantID_ 参数的值。
  
若要查找有关指定租户的许可信息在 Skype for Business Online 管理中心中是否可用的信息，请使用 [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet。
  
## <a name="related-topics"></a>相关主题
[使用 skype for business Online 管理设置计算机Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
