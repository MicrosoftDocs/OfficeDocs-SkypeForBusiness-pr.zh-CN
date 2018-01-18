---
title: "管理 Skype 的在线业务组织"
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 12/15/2017
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
ms.appliesto: Skype for Business
localization_priority: Normal
ROBOTS: None
f1keywords: None
ms.custom: PowerShell
description: "使用 Windows PowerShell 和 Get CsTenant 和 Get CsTenantLicensingConfiguration cmdlet 以获取有关您的在线业务的租户的 Skype 的信息。"
ms.openlocfilehash: cab693fa153eae99ac605981112a30ec09f49920
ms.sourcegitcommit: 8f2e49bc813125137c90de997fb7a6dd74e6d1d5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/15/2017
---
# <a name="manage-skype-for-business-online-organizations"></a>管理 Skype 的在线业务组织

您可以使用**Get CsTenant**和**Get CsTenantLicensingConfiguration** cmdlet 有关您 Skype 的在线商业租户找到信息。
  
## <a name="manage-skype-for-business-online-tenants"></a>管理 Skype 的在线业务的承租人

若要返回您 Skype 的在线商业租户有关的信息，请调用不带任何附加参数[获取 CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet。
  
```
Get-CsTenant
```

返回只是租户，名称和 ID，请使用此命令。
  
```
Get-CsTenant | Select-Object Name, TenantID
```

运行[设置 CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[一组 CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)等的 cmdlet 时需要_TenantID_参数的值。
  
若要查找有关授权指定的租户信息是否可用在 Skype 的在线业务管理中心信息，使用[Get CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。
  
## <a name="related-topics"></a>相关主题
[设置计算机上的 Skype 业务在线管理使用 Windows PowerShell](set-up-your-computer-for-windows-powershell.md)
