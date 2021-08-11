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
ms.openlocfilehash: 733d7e30bc25f15bcf05c2746ef1eb2cb8aa5cfd8e7e780356c4a972ef97a183
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "54298742"
---
# <a name="manage-skype-for-business-online-organizations"></a>管理 Skype for Business Online 组织

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> PowerShell [Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)预览版的最新版与 Skype for Business Online 连接器集成，为 PowerShell 管理Teams模块。

可以使用 **Get-CsTenant** 和 **Get-CsTenantLicensingConfiguration** cmdlet 查找有关 Skype for Business Online 租户的信息。
  
## <a name="manage-skype-for-business-online-tenants"></a>管理 Skype for Business Online 租户

若要返回有关 Skype for Business Online 租户的信息，请调用不带任何其他参数的[Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet。
  
```PowerShell
Get-CsTenant
```

若要仅返回租户名称和 ID，请使用此命令。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

运行 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)等 cmdlet 时，需要 _TenantID_ 参数的值。
  
若要查找有关指定租户的许可信息在 Skype for Business Online 管理中心中是否可用的信息，请使用[Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet。
  
## <a name="related-topics"></a>相关主题
[使用 Skype for business Online 管理设置计算机Windows PowerShell](set-up-your-computer-for-windows-powershell.md)

  
