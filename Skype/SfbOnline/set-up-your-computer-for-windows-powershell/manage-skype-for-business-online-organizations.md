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
f1keywords: None
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 和 CsTenant 和 CsTenantLicensingConfiguration cmdlet 获取有关 Skype for Business Online 租户的信息。
ms.openlocfilehash: 340ef9de0e793cbbed7d471754ebca715eb7eaf7
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40989227"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="81c01-103">管理 Skype for Business Online 组织</span><span class="sxs-lookup"><span data-stu-id="81c01-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="81c01-104">你可以使用**CsTenant**和**CsTenantLicensingConfiguration** cmdlet 查找有关 Skype for business Online 租户的信息。</span><span class="sxs-lookup"><span data-stu-id="81c01-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="81c01-105">管理 Skype for Business Online 租户</span><span class="sxs-lookup"><span data-stu-id="81c01-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="81c01-106">若要返回有关 Skype for Business Online 租户的信息，请调用[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet，无需任何其他参数。</span><span class="sxs-lookup"><span data-stu-id="81c01-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="81c01-107">若要仅返回租户名称和 ID，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="81c01-107">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="81c01-108">在运行[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)等 cmdlet 时，必须输入_TenantID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="81c01-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="81c01-109">若要查找有关指定租户的授权信息是否在 Skype for Business Online 管理中心中可用的信息，请使用[CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="81c01-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="81c01-110">相关主题</span><span class="sxs-lookup"><span data-stu-id="81c01-110">Related topics</span></span>
[<span data-ttu-id="81c01-111">使用 Windows PowerShell 为 skype for business online 管理设置计算机</span><span class="sxs-lookup"><span data-stu-id="81c01-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
