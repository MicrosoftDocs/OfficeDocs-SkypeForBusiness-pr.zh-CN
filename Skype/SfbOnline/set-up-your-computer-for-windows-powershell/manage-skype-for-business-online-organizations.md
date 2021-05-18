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
ms.openlocfilehash: 2fa95bf8997dd0aff7271b1383c69d9b27c4f4a9
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52238782"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="8de02-103">管理 Skype for Business Online 组织</span><span class="sxs-lookup"><span data-stu-id="8de02-103">Manage Skype for Business Online organizations</span></span>

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]
> [!NOTE]
> <span data-ttu-id="8de02-104">PowerShell [Teams](https://www.powershellgallery.com/packages/MicrosoftTeams/)预览版的最新版与 Skype for Business Online 连接器集成，为 PowerShell 管理Teams模块。</span><span class="sxs-lookup"><span data-stu-id="8de02-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="8de02-105">可以使用 **Get-CsTenant** 和 **Get-CsTenantLicensingConfiguration** cmdlet 查找有关 Skype for Business Online 租户的信息。</span><span class="sxs-lookup"><span data-stu-id="8de02-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="8de02-106">管理 Skype for Business Online 租户</span><span class="sxs-lookup"><span data-stu-id="8de02-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="8de02-107">若要返回有关 Skype for Business Online 租户的信息，请调用不带任何其他参数的[Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8de02-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="8de02-108">若要仅返回租户名称和 ID，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="8de02-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="8de02-109">运行 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)等 cmdlet 时，需要 _TenantID_ 参数的值。</span><span class="sxs-lookup"><span data-stu-id="8de02-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="8de02-110">若要查找有关指定租户的许可信息在 Skype for Business Online 管理中心中是否可用的信息，请使用[Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="8de02-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="8de02-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="8de02-111">Related topics</span></span>
[<span data-ttu-id="8de02-112">使用 Skype for business Online 管理设置计算机Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8de02-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
