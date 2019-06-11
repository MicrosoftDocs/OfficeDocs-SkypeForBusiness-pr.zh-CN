---
title: Skype for Business Online 中使用租户参数的 cmdlet
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Cmdlets that use the Tenant parameter
ms:assetid: e7fe7c12-fbe0-49c1-9e8c-eef6958f27d0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn362850(v=OCS.15)
ms:contentKeyID: 56558865
ms.date: 05/04/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: aa3b09e6f419c7425332427ccf4a4ff664b9e395
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837089"
---
# <a name="cmdlets-in-skype-for-business-online-that-use-the-tenant-parameter"></a><span data-ttu-id="4562e-102">Skype for Business Online 中使用租户参数的 cmdlet</span><span class="sxs-lookup"><span data-stu-id="4562e-102">Cmdlets in Skype for Business Online that use the Tenant parameter</span></span>

 


<span data-ttu-id="4562e-103">修改公共提供程序设置时, 你始终需要提供租户标识;即使只有单个租户, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="4562e-103">When modifying your public provider settings, you always need to supply a Tenant identity; this is true even if you only have a single tenant.</span></span> <span data-ttu-id="4562e-104">例如, 此命令将 Windows Live 设置为允许用户与之通信的唯一公共提供程序:</span><span class="sxs-lookup"><span data-stu-id="4562e-104">For example, this command sets Windows Live as the only public provider your users are allowed to communicate with:</span></span>

    Set-CsTenantPublicProvider -Tenant "bf19b7db-6960-41e5-a139-2aa373474354" -Provider "WindowsLive"

<span data-ttu-id="4562e-105">幸运的是, 每次运行其中一个 cmdlet 时无需键入租户 ID (例如, bf19b7db-6960-41e5-a139-2aa373474354)。</span><span class="sxs-lookup"><span data-stu-id="4562e-105">Fortunately, you do not need to type the Tenant ID (for example, bf19b7db-6960-41e5-a139-2aa373474354) each time you run one of these cmdlets.</span></span> <span data-ttu-id="4562e-106">相反, 你可以通过运行[CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet 来检索租户 id, 将租户 id 存储在一个变量中, 然后在调用其他 cmdlet 之一时使用该变量。</span><span class="sxs-lookup"><span data-stu-id="4562e-106">Instead, you can retrieve the Tenant ID by running the [Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\)) cmdlet, storing the Tenant ID in a variable, and then using that variable when you call one of the other cmdlets.</span></span> <span data-ttu-id="4562e-107">例如：</span><span class="sxs-lookup"><span data-stu-id="4562e-107">For example:</span></span>

    $x = (Get-CsTenant).TenantId
    Set-CsTenantPublicProvider -Tenant $x -Provider "WindowsLive"

<span data-ttu-id="4562e-108">或者, 你可以在单个命令中执行此操作, 方法是检索租户 ID, 然后将该值管道 CsTenantPublicProvider cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4562e-108">Alternatively, you can do this in a single command by retrieving the Tenant ID and then piping that value to the Set-CsTenantPublicProvider cmdlet:</span></span>

    Get-CsTenant | Select-Object TenantId | ForEach-Object {Set-CsTenantPublicProvider -Tenant $_.TenantId -Provider "WindowsLive"}

<span data-ttu-id="4562e-109">在调用**CsTenant** cmdlet 时, 无需指定租户 ID。</span><span class="sxs-lookup"><span data-stu-id="4562e-109">You do not need to specify the tenant ID when calling the **Get-CsTenant** cmdlet.</span></span> <span data-ttu-id="4562e-110">此命令将返回有关租户的信息:</span><span class="sxs-lookup"><span data-stu-id="4562e-110">This command returns information about your tenant:</span></span>

    Get-CsTenant

<span data-ttu-id="4562e-111">以下 cmdlet 接受租户标识。</span><span class="sxs-lookup"><span data-stu-id="4562e-111">The following cmdlets accept a tenant identity.</span></span> <span data-ttu-id="4562e-112">但是, 在这些情况下, 该参数是可选的, 并且无需在调用 cmdlet 时输入。</span><span class="sxs-lookup"><span data-stu-id="4562e-112">However, in these cases, the parameter is optional and does not need to be entered when calling the cmdlet.</span></span> <span data-ttu-id="4562e-113">因此, Windows PowerShell 将根据您当前连接到的 Skype for business Online 租户有效地为您输入租户标识:</span><span class="sxs-lookup"><span data-stu-id="4562e-113">Instead, Windows PowerShell will effectively enter the tenant identity for you based on the Skype for Business Online tenant you are currently connected to:</span></span>

  - <span data-ttu-id="4562e-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4562e-114">[Get-CsTenant](https://technet.microsoft.com/en-us/library/jj994044\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4562e-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4562e-115">[Set-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994080\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4562e-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4562e-116">[Set-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994046\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4562e-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4562e-117">[Get-CsTenantFederationConfiguration](https://technet.microsoft.com/en-us/library/jj994072\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4562e-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4562e-118">[Get-CsTenantHybridConfiguration](https://technet.microsoft.com/en-us/library/jj994034\(v=ocs.15\))</span></span>

  - <span data-ttu-id="4562e-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4562e-119">[Get-CsTenantLicensingConfiguration](https://technet.microsoft.com/en-us/library/dn362770\(v=ocs.15\))</span></span>

<span data-ttu-id="4562e-120">例如, 可以使用以下命令调用**CsTenantFederationConfiguration** cmdlet:</span><span class="sxs-lookup"><span data-stu-id="4562e-120">For example, the **Get-CsTenantFederationConfiguration** cmdlet can be called by using this command:</span></span>

    Get-CsTenantFederationConfiguration

<span data-ttu-id="4562e-121">尽管不是必需的, 但你可以在调用 CsTenantFederationConfiguration 时包含租户参数:</span><span class="sxs-lookup"><span data-stu-id="4562e-121">Although not required, you can include the Tenant parameter when calling Get-CsTenantFederationConfiguration :</span></span>

    Get-CsTenantFederationConfiguration -Tenant "bf19b7db-6960-41e5-a139-2aa373474354"

## <a name="see-also"></a><span data-ttu-id="4562e-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4562e-122">See Also</span></span>


[<span data-ttu-id="4562e-123">Skype for Business Online 中的身份、范围和租户</span><span class="sxs-lookup"><span data-stu-id="4562e-123">Identities, scopes, and tenants in Skype for Business Online</span></span>](identities-scopes-and-tenants-in-skype-for-business-online.md)  
<span data-ttu-id="4562e-124">[Lync Online Cmdlet](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span><span class="sxs-lookup"><span data-stu-id="4562e-124">[The Skype for Business Online cmdlets](https://technet.microsoft.com/en-us/library/dn362817\(v=ocs.15\))</span></span>

