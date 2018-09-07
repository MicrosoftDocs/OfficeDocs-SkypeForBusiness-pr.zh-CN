---
title: Skype 管理业务 Online 组织 （英文）
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 和 Get CsTenant 和 Get CsTenantLicensingConfiguration cmdlet 来获取有关您 Skype 业务 Online 租户的信息。
ms.openlocfilehash: 279f9431c69605377fcc0070bf9c81a027cb4064
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23863330"
---
# <a name="manage-skype-for-business-online-organizations"></a>Skype 管理业务 Online 组织 （英文）

您可以通过使用**Get-CsTenant**和**Get CsTenantLicensingConfiguration** cmdlet 查找有关您的业务 Online 租户的 Skype 的信息。
  
## <a name="manage-skype-for-business-online-tenants"></a>Skype 管理业务 Online 租户 （英文）

若要返回有关您 Skype 业务 Online 租户的信息，请调用不带任何其他参数的[Get CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet。
  
```
Get-CsTenant
```

要返回仅租户名称和 ID，使用此命令。
  
```
Get-CsTenant | Select-Object Name, TenantID
```

运行 cmdlet[设置 CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)等[设置 CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)时需要_TenantID_参数的值。
  
要查找有关是否为指定租户的许可信息为业务 Online 管理中心的 Skype 中提供的信息，请使用[Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。
  
## <a name="related-topics"></a>相关主题
[设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype](set-up-your-computer-for-windows-powershell.md)

  
 