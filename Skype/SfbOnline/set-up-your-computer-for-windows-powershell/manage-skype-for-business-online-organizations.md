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
description: 使用 Windows PowerShell 和 CsTenant 和 CsTenantLicensingConfiguration cmdlet 获取有关 Skype for Business Online 租户的信息。
ms.openlocfilehash: 3c4a8f72caca634b208de5cf4aa555b88518f4da
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41706247"
---
# <a name="manage-skype-for-business-online-organizations"></a>管理 Skype for Business Online 组织

你可以使用**CsTenant**和**CsTenantLicensingConfiguration** cmdlet 查找有关 Skype for business Online 租户的信息。
  
## <a name="manage-skype-for-business-online-tenants"></a>管理 Skype for Business Online 租户

若要返回有关 Skype for Business Online 租户的信息，请调用[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet，无需任何其他参数。
  
```PowerShell
Get-CsTenant
```

若要仅返回租户名称和 ID，请使用此命令。
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

在运行[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)等 cmdlet 时，必须输入_TenantID_参数的值。
  
若要查找有关指定租户的授权信息是否在 Skype for Business Online 管理中心中可用的信息，请使用[CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。
  
## <a name="related-topics"></a>相关主题
[使用 Windows PowerShell 为 skype for business online 管理设置计算机](set-up-your-computer-for-windows-powershell.md)

  
 
