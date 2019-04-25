---
title: Skype 管理业务 Online 组织 （英文）
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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 和 Get CsTenant 和 Get CsTenantLicensingConfiguration cmdlet 来获取有关您 Skype 业务 Online 租户的信息。
ms.openlocfilehash: b71c89967ab34909fa461f71fc5f67c1cf99a408
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32224442"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="a227d-103">Skype 管理业务 Online 组织 （英文）</span><span class="sxs-lookup"><span data-stu-id="a227d-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="a227d-104">您可以通过使用**Get-CsTenant**和**Get CsTenantLicensingConfiguration** cmdlet 查找有关您的业务 Online 租户的 Skype 的信息。</span><span class="sxs-lookup"><span data-stu-id="a227d-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="a227d-105">Skype 管理业务 Online 租户 （英文）</span><span class="sxs-lookup"><span data-stu-id="a227d-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="a227d-106">若要返回有关您 Skype 业务 Online 租户的信息，请调用不带任何其他参数的[Get CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a227d-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="a227d-107">要返回仅租户名称和 ID，使用此命令。</span><span class="sxs-lookup"><span data-stu-id="a227d-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="a227d-108">运行 cmdlet[设置 CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)等[设置 CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)时需要_TenantID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="a227d-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="a227d-109">要查找有关是否为指定租户的许可信息为业务 Online 管理中心的 Skype 中提供的信息，请使用[Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="a227d-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="a227d-110">相关主题</span><span class="sxs-lookup"><span data-stu-id="a227d-110">Related topics</span></span>
[<span data-ttu-id="a227d-111">设置您的计算机的业务联机管理使用 Windows PowerShell 的 Skype</span><span class="sxs-lookup"><span data-stu-id="a227d-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
