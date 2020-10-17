---
title: 使用租户参数的 Skype for Business Online 中的 cmdlet
description: Skype for Business Online 中使用租户参数的 cmdlet。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ff2b8053dd855a854fa26699770d3dafaa0dcbd7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546798"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="74a17-103">使用租户参数的 Skype for Business Online 中的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="74a17-103">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="74a17-104">修改公共提供商设置时，始终需要提供租户标识;即使只有一个租户，也是如此。</span><span class="sxs-lookup"><span data-stu-id="74a17-104">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="74a17-105">例如，此命令将 Windows Live 设置为允许用户与之通信的唯一公共提供程序：</span><span class="sxs-lookup"><span data-stu-id="74a17-105">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="74a17-106">幸运的是，在每次运行这些 cmdlet 时，都不需要键入租户 ID (例如，bf19b7db-6960-41e5-a139-2aa373474354) 。</span><span class="sxs-lookup"><span data-stu-id="74a17-106">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="74a17-107">相反，您可以通过运行 [get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet，将租户 id 存储在一个变量中，然后在调用其他 cmdlet 之一时使用该变量来检索租户 id。</span><span class="sxs-lookup"><span data-stu-id="74a17-107">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="74a17-108">例如：</span><span class="sxs-lookup"><span data-stu-id="74a17-108">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="74a17-109">或者，您可以在单个命令中执行此操作，方法是检索租户 ID，然后将该值通过管道传递给 Set-CsTenantPublicProvider cmdlet：</span><span class="sxs-lookup"><span data-stu-id="74a17-109">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="74a17-110">调用 **get-cstenant** cmdlet 时无需指定租户 ID。</span><span class="sxs-lookup"><span data-stu-id="74a17-110">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="74a17-111">此命令将返回有关你的租户的信息：</span><span class="sxs-lookup"><span data-stu-id="74a17-111">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="74a17-112">以下 cmdlet 接受租户标识。</span><span class="sxs-lookup"><span data-stu-id="74a17-112">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="74a17-113">但是，在这些情况下，参数是可选的，并且在调用 cmdlet 时不需要输入。</span><span class="sxs-lookup"><span data-stu-id="74a17-113">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="74a17-114">相反，Windows PowerShell 将根据你当前连接到的 Skype for Business Online 租户有效地为你输入租户标识：</span><span class="sxs-lookup"><span data-stu-id="74a17-114">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="74a17-115">[Get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74a17-115">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74a17-116">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74a17-116">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74a17-117">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74a17-117">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74a17-118">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74a17-118">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74a17-119">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74a17-119">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="74a17-120">[Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74a17-120">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="74a17-121">例如，可以使用以下命令调用 **CsTenantFederationConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="74a17-121">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="74a17-122">尽管不是必需的，但您可以在调用 Get-CsTenantFederationConfiguration 时包含租户参数：</span><span class="sxs-lookup"><span data-stu-id="74a17-122">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="74a17-123">另请参阅</span><span class="sxs-lookup"><span data-stu-id="74a17-123">See Also</span></span>


[<span data-ttu-id="74a17-124">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="74a17-124">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="74a17-125">[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="74a17-125">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

