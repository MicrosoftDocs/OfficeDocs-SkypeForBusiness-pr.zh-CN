---
title: 管理 Skype 的在线业务组织
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.date: 01/22/2018
ms.topic: article
ms.assetid: c71f0d4d-5b6b-40ac-bc4a-6b97c05a121a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- PowerShell
description: 使用 Windows PowerShell 和 Get CsTenant 和 Get CsTenantLicensingConfiguration cmdlet 以获取有关您的在线业务的租户的 Skype 的信息。
ms.openlocfilehash: 53043fbf623ce2cc7342bf5ac7b32c363927def5
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/03/2018
---
# <a name="manage-skype-for-business-online-organizations"></a><span data-ttu-id="26cd0-103">管理 Skype 的在线业务组织</span><span class="sxs-lookup"><span data-stu-id="26cd0-103">Manage Skype for Business Online organizations</span></span>

<span data-ttu-id="26cd0-104">您可以使用**Get CsTenant**和**Get CsTenantLicensingConfiguration** cmdlet 有关您 Skype 的在线商业租户找到信息。</span><span class="sxs-lookup"><span data-stu-id="26cd0-104">You can find information about your Skype for Business Online tenant by using the **Get-CsTenant** and **Get-CsTenantLicensingConfiguration** cmdlets.</span></span>
  
## <a name="manage-skype-for-business-online-tenants"></a><span data-ttu-id="26cd0-105">管理 Skype 的在线业务的承租人</span><span class="sxs-lookup"><span data-stu-id="26cd0-105">Manage Skype for Business Online tenants</span></span>

<span data-ttu-id="26cd0-106">若要返回您 Skype 的在线商业租户有关的信息，请调用不带任何附加参数[获取 CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="26cd0-106">To return information about your Skype for Business Online tenant, call the [Get-CsTenant](https://go.microsoft.com/fwlink/p/?linkid=849599) cmdlet without any additional parameters.</span></span>
  
```
Get-CsTenant
```

<span data-ttu-id="26cd0-107">返回只是租户，名称和 ID，请使用此命令。</span><span class="sxs-lookup"><span data-stu-id="26cd0-107">To return just the tenant name and ID, use this command.</span></span>
  
```
Get-CsTenant | Select-Object Name, TenantID
```

<span data-ttu-id="26cd0-108">运行[设置 CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602)和[一组 CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx)等的 cmdlet 时需要_TenantID_参数的值。</span><span class="sxs-lookup"><span data-stu-id="26cd0-108">The value of the  _TenantID_ parameter is required when running cmdlets such as [Set-CsTenantPublicProvider](https://go.microsoft.com/fwlink/p/?linkid=849602) and [Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080.aspx).</span></span>
  
<span data-ttu-id="26cd0-109">若要查找有关授权指定的租户信息是否可用在 Skype 的在线业务管理中心信息，使用[Get CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="26cd0-109">To find information about whether licensing information for the specified tenant is available in the Skype for Business Online admin center, use the [Get-CsTenantLicensingConfiguration](https://go.microsoft.com/fwlink/p/?linkid=849606) cmdlet.</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="26cd0-110">相关主题</span><span class="sxs-lookup"><span data-stu-id="26cd0-110">Related topics</span></span>
[<span data-ttu-id="26cd0-111">设置计算机上的 Skype 业务在线管理使用 Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="26cd0-111">Set up your computer for skype for business online management using Windows PowerShell</span></span>](set-up-your-computer-for-windows-powershell.md)

  
 