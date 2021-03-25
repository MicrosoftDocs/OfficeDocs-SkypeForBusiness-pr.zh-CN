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
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="1041b-103">管理 Skype for Business Online 组织</span><span class="sxs-lookup"><span data-stu-id="1041b-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="1041b-104">最新的 [Teams PowerShell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/) 与 Skype for Business Online 连接器集成，为 Teams PowerShell 管理提供单个模块。</span><span class="sxs-lookup"><span data-stu-id="1041b-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="1041b-105">可以使用 **Get-CsTenant** 和 **Get-CsTenantLicensingConfiguration** cmdlet 查找有关 Skype for Business Online 租户的信息。</span><span class="sxs-lookup"><span data-stu-id="1041b-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="1041b-106">管理 Skype for Business Online 租户</span><span class="sxs-lookup"><span data-stu-id="1041b-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="1041b-107">若要返回有关 Skype for Business Online 租户的信息，请不带任何其他参数调用 [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1041b-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](/powershell/module/skype/Get-CsTenant) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="1041b-108">若要仅返回租户名称和 ID，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="1041b-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="1041b-109">运行 [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider)和 [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration)等 cmdlet 时，需要 _TenantID_ 参数的值。</span><span class="sxs-lookup"><span data-stu-id="1041b-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](/powershell/module/skype/Set-CsTenantPublicProvider) and [Set-CsTenantFederationConfiguration](/powershell/module/skype/Set-CsTenantFederationConfiguration).</span></span>
  
<span data-ttu-id="1041b-110">若要查找有关指定租户的许可信息在 Skype for Business Online 管理中心中是否可用的信息，请使用 [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="1041b-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](/powershell/module/skype/Get-CsTenantLicensingConfiguration) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="1041b-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="1041b-111">Related topics</span></span>
[<span data-ttu-id="1041b-112">使用 skype for business Online 管理设置计算机Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1041b-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
