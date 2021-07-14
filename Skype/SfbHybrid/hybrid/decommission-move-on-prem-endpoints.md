---
title: 将混合应用程序终结点迁移到云
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
description: 在停用本地环境之前迁移Skype for Business应用程序终结点。
ms.openlocfilehash: 7315ee807bb79b9186cd92ccc19074021b2fcfa1
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420797"
---
# <a name="migrate-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="57a00-103">在停用本地环境之前迁移混合应用程序终结点</span><span class="sxs-lookup"><span data-stu-id="57a00-103">Migrate hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="57a00-104">本文介绍如何在停用本地部署环境之前，将所需的混合应用程序终结点Skype for Business Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="57a00-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="57a00-105">这是停止使用本地环境的以下步骤的第 3 步：</span><span class="sxs-lookup"><span data-stu-id="57a00-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="57a00-106">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="57a00-106">Step 1.</span></span> [<span data-ttu-id="57a00-107">将所有所需的用户从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="57a00-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="57a00-108">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="57a00-108">Step 2.</span></span> <span data-ttu-id="57a00-109">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="57a00-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="57a00-110">**步骤 3.将混合应用程序终结点从本地迁移到联机。**</span><span class="sxs-lookup"><span data-stu-id="57a00-110">**Step 3. Migrate hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="57a00-111"> (本文) </span><span class="sxs-lookup"><span data-stu-id="57a00-111">(This article)</span></span>

- <span data-ttu-id="57a00-112">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="57a00-112">Step 4.</span></span> <span data-ttu-id="57a00-113">[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="57a00-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="migrate-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="57a00-114">将所有必需的混合应用程序终结点从本地迁移到联机</span><span class="sxs-lookup"><span data-stu-id="57a00-114">Migrate all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="57a00-115">在可以将这些终结点移动到联机状态之前，必须确保已更新 DNS 记录，以指向Microsoft 365所使用的所有 sip 域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="57a00-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="57a00-116">请注意，一旦将 DNS 更新为指向Microsoft 365，在您完成此步骤之前，任何现有的混合应用程序终结点将无法再被发现。</span><span class="sxs-lookup"><span data-stu-id="57a00-116">Be aware that once you update DNS to point to Microsoft 365, any existing hybrid application endpoints will no longer be discoverable until you complete this step.</span></span> <span data-ttu-id="57a00-117">由于此步骤 (如果 DNS 记录指向本地) ，则不能创建联机资源帐户，因此您应计划在同一维护窗口中执行步骤 2 和步骤 3。</span><span class="sxs-lookup"><span data-stu-id="57a00-117">Since this step (creating online Resource Accounts) is not possible if DNS records point to on-premises you should plan to do both steps 2 and 3 in the same maintenance window.</span></span> <span data-ttu-id="57a00-118">有关详细信息，请参阅 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="57a00-118">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="57a00-119">通过执行以下本地部署和 PowerShell 命令检索和导出Skype for Business Server应用程序终结点设置：</span><span class="sxs-lookup"><span data-stu-id="57a00-119">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="57a00-120">在资源中心[创建](/microsoftteams/manage-resource-accounts)和Microsoft 365资源帐户，以替换现有的本地混合应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="57a00-120">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="57a00-121">将新的资源帐户与现有的混合应用程序终结点关联。</span><span class="sxs-lookup"><span data-stu-id="57a00-121">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="57a00-122">通过执行以下 PowerShell 命令本地混合应用程序终结点中定义Skype for Business Server电话号码：</span><span class="sxs-lookup"><span data-stu-id="57a00-122">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="57a00-123">由于这些帐户的电话号码有可能在 Microsoft 365 而非本地管理，因此在 Skype for Business PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="57a00-123">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="57a00-124">将电话号码分配给在步骤 2 中创建的新资源帐户。</span><span class="sxs-lookup"><span data-stu-id="57a00-124">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="57a00-125">若要详细了解如何将电话号码分配给资源帐户，请参阅以下文章： [分配服务号码](/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="57a00-125">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="57a00-126">通过执行 PowerShell 命令Skype for Business Server本地终结点：</span><span class="sxs-lookup"><span data-stu-id="57a00-126">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="57a00-127">现在，你已准备好[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="57a00-127">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="57a00-128">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57a00-128">See also</span></span>

- [<span data-ttu-id="57a00-129">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="57a00-129">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="57a00-130">将所有所需的用户从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="57a00-130">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="57a00-131">禁用混合配置</span><span class="sxs-lookup"><span data-stu-id="57a00-131">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="57a00-132">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="57a00-132">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




