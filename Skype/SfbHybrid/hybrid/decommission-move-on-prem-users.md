---
title: 将用户和终结点移动到云
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 在停用 Skype for Business 本地环境之前移动用户和终结点。
ms.openlocfilehash: 130f276d07dd33be33d3c038c2ead20c7a887e6b
ms.sourcegitcommit: f223b5f3735f165d46bb611a52fcdfb0f4b88f66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2021
ms.locfileid: "51593879"
---
# <a name="move-required-users-and-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="293b9-103">在停用本地环境之前移动所需的用户和终结点</span><span class="sxs-lookup"><span data-stu-id="293b9-103">Move required users and endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="293b9-104">本文介绍如何在停用本地 Skype for Business 环境之前，将所需的用户和应用程序终结点移动到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="293b9-104">This article describes how to move required users and application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="293b9-105">这是停止使用本地环境的以下步骤的第 1 步：</span><span class="sxs-lookup"><span data-stu-id="293b9-105">This is step 1 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="293b9-106">**步骤 1.将所有必需的用户和应用程序终结点从本地移动到联机。**</span><span class="sxs-lookup"><span data-stu-id="293b9-106">**Step 1. Move all required users and application endpoints from on-premises to online.**</span></span> <span data-ttu-id="293b9-107"> (本文.) </span><span class="sxs-lookup"><span data-stu-id="293b9-107">(This article.)</span></span>

- <span data-ttu-id="293b9-108">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="293b9-108">Step 2.</span></span> <span data-ttu-id="293b9-109">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="293b9-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="293b9-110">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="293b9-110">Step 3.</span></span> <span data-ttu-id="293b9-111">[删除本地 Skype for Business 部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="293b9-111">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="293b9-112">将所有所需的用户从本地移动到云</span><span class="sxs-lookup"><span data-stu-id="293b9-112">Move all required users from on-premises to the cloud</span></span>

<span data-ttu-id="293b9-113">完成迁移后将继续使用的任何用户必须先从本地迁移到云。</span><span class="sxs-lookup"><span data-stu-id="293b9-113">Any users that you will continue to use after completing the migration must first be moved from on-premises to the cloud.</span></span> <span data-ttu-id="293b9-114">使用本地管理工具移动用户。</span><span class="sxs-lookup"><span data-stu-id="293b9-114">You move users by using the on-premises administration tools.</span></span> <span data-ttu-id="293b9-115">有关详细信息，请参阅在内部 [部署和云之间移动用户](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="293b9-115">For details, see [Move users between on-premises and cloud](move-users-between-on-premises-and-cloud.md).</span></span>

<span data-ttu-id="293b9-116">尽管拥有本地 Skype for Business Server 帐户的用户可以使用 Teams，但是这些用户没有 Teams 的全部功能。</span><span class="sxs-lookup"><span data-stu-id="293b9-116">Although it is possible for users with on-premises Skype for Business Server accounts to use Teams, these users do not have the full functionality of Teams.</span></span> <span data-ttu-id="293b9-117">这些用户无法与仍在使用 Skype for Business (用户进行互操作或联合，无论是联机还是本地) 。</span><span class="sxs-lookup"><span data-stu-id="293b9-117">These users cannot interoperate or federate with any other user still using Skype for Business (whether online or on-premises).</span></span> <span data-ttu-id="293b9-118">这些用户也无法在 Teams 客户端中接收 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="293b9-118">Nor can these users receive PSTN calls in their Teams client.</span></span> <span data-ttu-id="293b9-119">因此，必须将这些用户移至联机。</span><span class="sxs-lookup"><span data-stu-id="293b9-119">Therefore, you must move these users to online.</span></span> <span data-ttu-id="293b9-120">此步骤还可确保在 Skype for Business Server 中创建的任何联系人或会议都迁移到 Teams。</span><span class="sxs-lookup"><span data-stu-id="293b9-120">This step also ensures any contacts or meetings created in Skype for Business Server are migrated to Teams.</span></span>

<span data-ttu-id="293b9-121">若要检查本地部署中是否有剩余用户，请在 Skype for Business Server PowerShell 窗口中运行以下 cmdlet。</span><span class="sxs-lookup"><span data-stu-id="293b9-121">To check if there are any remaining users in your on-premises deployment, run the following cmdlet in a Skype for Business Server PowerShell window.</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"}
```

<span data-ttu-id="293b9-122">如果返回了任何用户，请查看输出以确定是否必须将任何帐户移动到云，对于此类用户，请按照此处 [的步骤操作](move-users-between-on-premises-and-cloud.md)。</span><span class="sxs-lookup"><span data-stu-id="293b9-122">If any users are returned, review the output to determine if any accounts must be moved to the cloud, and, for any such users, follow the steps [here](move-users-between-on-premises-and-cloud.md).</span></span> <span data-ttu-id="293b9-123">对于不再需要的用户帐户，请运行以下 Skype for Business Server PowerShell cmdlet：</span><span class="sxs-lookup"><span data-stu-id="293b9-123">For user accounts that are no longer needed, run the following Skype for Business Server PowerShell cmdlet:</span></span>

```PowerShell
Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Disable-CsUser
```

> [!NOTE]
> <span data-ttu-id="293b9-124">运行Disable-CsUser将删除满足筛选条件的所有用户的所有 Skype for Business 属性。</span><span class="sxs-lookup"><span data-stu-id="293b9-124">Running Disable-CsUser will remove all Skype for Business attributes for all users meeting the filter criteria.</span></span> <span data-ttu-id="293b9-125">在继续之前，请确认今后不再需要这些帐户。</span><span class="sxs-lookup"><span data-stu-id="293b9-125">Before proceeding, confirm that these accounts are no longer needed going forward.</span></span>

## <a name="move-on-premises-hybrid-application-endpoints-to-microsoft-365"></a><span data-ttu-id="293b9-126">将本地混合应用程序终结点移动到 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="293b9-126">Move on-premises hybrid application endpoints to Microsoft 365</span></span>

1. <span data-ttu-id="293b9-127">通过执行以下本地 Skype for Business Server PowerShell 命令检索和导出本地混合应用程序终结点设置：</span><span class="sxs-lookup"><span data-stu-id="293b9-127">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="293b9-128">在 Microsoft [](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) 365 中新建资源帐户并授予许可，以替换现有的本地混合应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="293b9-128">Create and license new [Resource Accounts](https://docs.microsoft.com/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="293b9-129">将新的资源帐户与现有的混合应用程序终结点关联。</span><span class="sxs-lookup"><span data-stu-id="293b9-129">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="293b9-130">通过执行以下本地 Skype for Business Server PowerShell 命令删除在本地混合应用程序终结点中定义的电话号码：</span><span class="sxs-lookup"><span data-stu-id="293b9-130">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="293b9-131">由于这些帐户的电话号码有可能在 Microsoft 365 而非本地管理，因此在 Skype for Business Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="293b9-131">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

   ```PowerShell
   $endpoints = import-csv "c:\backup\HybridEndpoints.csv"
   foreach ($endpoint in $endpoints)
   {
   if($endpoint.LineUri)
       {
           $upn = $endpoint.SipAddress.Replace("sip:","")
           $ra=Get-CsOnlineApplicationInstance | where UserPrincipalName -eq $upn 
           Set-CsOnlineApplicationInstance -Identity $ra.Objectid -OnpremPhoneNumber ""
       }
   }
   ```

6. <span data-ttu-id="293b9-132">将电话号码分配给在步骤 2 中创建的新资源帐户。</span><span class="sxs-lookup"><span data-stu-id="293b9-132">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="293b9-133">若要详细了解如何将电话号码分配给资源帐户，请参阅以下文章： [分配服务号码](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="293b9-133">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](https://docs.microsoft.com/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="293b9-134">通过执行以下本地 Skype for Business Server PowerShell 命令删除本地终结点：</span><span class="sxs-lookup"><span data-stu-id="293b9-134">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="293b9-135">现在，你已准备好 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="293b9-135">You are now ready to [disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="293b9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="293b9-136">See also</span></span>

- [<span data-ttu-id="293b9-137">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="293b9-137">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="293b9-138">禁用混合配置</span><span class="sxs-lookup"><span data-stu-id="293b9-138">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="293b9-139">删除本地 Skype for Business 部署</span><span class="sxs-lookup"><span data-stu-id="293b9-139">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




