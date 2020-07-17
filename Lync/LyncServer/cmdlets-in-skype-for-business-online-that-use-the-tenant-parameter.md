---
title: 使用租户参数的 Skype for Business Online 中的 cmdlet
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
ms.openlocfilehash: 352a33fcff5db306b62535c28fb4a2b2dd766bea
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755038"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="068e1-102">使用租户参数的 Skype for Business Online 中的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="068e1-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="068e1-103">修改公共提供商设置时，始终需要提供租户标识;即使只有一个租户，也是如此。</span><span class="sxs-lookup"><span data-stu-id="068e1-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="068e1-104">例如，此命令将 Windows Live 设置为允许用户与之通信的唯一公共提供程序：</span><span class="sxs-lookup"><span data-stu-id="068e1-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="068e1-105">幸运的是，每次运行这些 cmdlet 时，不需要键入租户 ID （例如，bf19b7db-6960-41e5-a139-2aa373474354）。</span><span class="sxs-lookup"><span data-stu-id="068e1-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="068e1-106">相反，您可以通过运行[get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet，将租户 id 存储在一个变量中，然后在调用其他 cmdlet 之一时使用该变量来检索租户 id。</span><span class="sxs-lookup"><span data-stu-id="068e1-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="068e1-107">例如：</span><span class="sxs-lookup"><span data-stu-id="068e1-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="068e1-108">或者，您可以在单个命令中执行此操作，方法是检索租户 ID，然后通过管道将此值 Set-cstenantpublicprovider cmdlet：</span><span class="sxs-lookup"><span data-stu-id="068e1-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="068e1-109">调用**get-cstenant** cmdlet 时无需指定租户 ID。</span><span class="sxs-lookup"><span data-stu-id="068e1-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="068e1-110">此命令将返回有关你的租户的信息：</span><span class="sxs-lookup"><span data-stu-id="068e1-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="068e1-111">以下 cmdlet 接受租户标识。</span><span class="sxs-lookup"><span data-stu-id="068e1-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="068e1-112">但是，在这些情况下，参数是可选的，并且在调用 cmdlet 时不需要输入。</span><span class="sxs-lookup"><span data-stu-id="068e1-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="068e1-113">相反，Windows PowerShell 将根据你当前连接到的 Skype for Business Online 租户有效地为你输入租户标识：</span><span class="sxs-lookup"><span data-stu-id="068e1-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="068e1-114">[Get-cstenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="068e1-114">[Get-CsTenant](https://technet.microsoft.com/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="068e1-115">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="068e1-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="068e1-116">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="068e1-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="068e1-117">[CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="068e1-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="068e1-118">[CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="068e1-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="068e1-119">[Get-cstenantlicensingconfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="068e1-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="068e1-120">例如，可以使用以下命令调用**CsTenantFederationConfiguration** cmdlet：</span><span class="sxs-lookup"><span data-stu-id="068e1-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="068e1-121">尽管不是必需的，但您可以在调用 CsTenantFederationConfiguration 时包含租户参数：</span><span class="sxs-lookup"><span data-stu-id="068e1-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="068e1-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="068e1-122">See Also</span></span>


[<span data-ttu-id="068e1-123">Skype for Business Online 中的标识、范围和租户</span><span class="sxs-lookup"><span data-stu-id="068e1-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="068e1-124">[Skype for Business Online cmdlet](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="068e1-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/library/dn362817\(v=ocs.15\))</span></span>

