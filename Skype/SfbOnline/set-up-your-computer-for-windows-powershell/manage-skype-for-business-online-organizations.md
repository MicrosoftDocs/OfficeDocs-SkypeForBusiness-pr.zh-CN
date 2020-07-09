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
ms.openlocfilehash: 06597447edaf095be3df26b58e6210bb919ee0bd
ms.sourcegitcommit: 90939ad992e65f840e4c2e7a6d18d821621319b4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2020
ms.locfileid: "45085688"
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="c70a8-103">管理 Skype for Business Online 组织</span><span class="sxs-lookup"><span data-stu-id="c70a8-103">Manage Skype for Business Online organizations</span></span>
> [!NOTE]
> <span data-ttu-id="c70a8-104">最新的[团队 powershell 公共预览版](https://www.powershellgallery.com/packages/MicrosoftTeams/)已与 Skype For Business Online 连接器集成，为团队 PowerShell 管理提供单个模块。</span><span class="sxs-lookup"><span data-stu-id="c70a8-104">The latest [Teams PowerShell public preview release](https://www.powershellgallery.com/packages/MicrosoftTeams/) is integrated with Skype for Business Online Connector, providing a single module for Teams PowerShell management.</span></span>

<span data-ttu-id="c70a8-105">你可以使用**CsTenant**和**CsTenantLicensingConfiguration** cmdlet 查找有关 Skype for business Online 租户的信息。</span><span class="sxs-lookup"><span data-stu-id="c70a8-105">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="c70a8-106">管理 Skype for Business Online 租户</span><span class="sxs-lookup"><span data-stu-id="c70a8-106">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="c70a8-107">若要返回有关 Skype for Business Online 租户的信息，请调用[CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet，无需任何其他参数。</span><span class="sxs-lookup"><span data-stu-id="c70a8-107">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```PowerShell
Get-CsTenant
```

<span data-ttu-id="c70a8-108">若要仅返回租户名称和 ID，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="c70a8-108">To return just the tenant name and ID, use this command.</span></span>
  
```PowerShell
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="c70a8-109">在运行[CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx)等 cmdlet 时，必须输入_TenantID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="c70a8-109">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="c70a8-110">若要查找有关指定租户的授权信息是否在 Skype for Business Online 管理中心中可用的信息，请使用[CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c70a8-110">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c70a8-111">相关主题</span><span class="sxs-lookup"><span data-stu-id="c70a8-111">Related topics</span></span>
[<span data-ttu-id="c70a8-112">使用 Windows PowerShell 为 skype for business online 管理设置计算机</span><span class="sxs-lookup"><span data-stu-id="c70a8-112">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 
