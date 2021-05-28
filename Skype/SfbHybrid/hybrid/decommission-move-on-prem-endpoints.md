---
title: 将混合应用程序终结点移动到云
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
description: 在停用本地环境之前移动Skype for Business应用程序终结点。
ms.openlocfilehash: 959a3ed47993f431636fe3c99b8502cf9aa634fe
ms.sourcegitcommit: 36924dc54fe7b09607b07d7543fe7e39eb4d2483
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52684379"
---
# <a name="move-hybrid-application-endpoints-before-decommissioning-your-on-premises-environment"></a><span data-ttu-id="60f0d-103">在停用本地环境之前移动混合应用程序终结点</span><span class="sxs-lookup"><span data-stu-id="60f0d-103">Move hybrid application endpoints before decommissioning your on-premises environment</span></span>

<span data-ttu-id="60f0d-104">本文介绍如何在停用本地部署环境之前，将所需的混合应用程序终结点Skype for Business Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="60f0d-104">This article describes how to move required hybrid application endpoints to the Microsoft cloud before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="60f0d-105">这是停止使用本地环境的以下步骤的第 3 步：</span><span class="sxs-lookup"><span data-stu-id="60f0d-105">This is step 3 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="60f0d-106">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="60f0d-106">Step 1.</span></span> [<span data-ttu-id="60f0d-107">将所有所需的用户从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="60f0d-107">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- <span data-ttu-id="60f0d-108">步骤 2.</span><span class="sxs-lookup"><span data-stu-id="60f0d-108">Step 2.</span></span> <span data-ttu-id="60f0d-109">[禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="60f0d-109">[Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

- <span data-ttu-id="60f0d-110">**步骤 3.将混合应用程序终结点从本地移动到联机。**</span><span class="sxs-lookup"><span data-stu-id="60f0d-110">**Step 3. Move hybrid application endpoints from on-premises to online.**</span></span> <span data-ttu-id="60f0d-111"> (本文) </span><span class="sxs-lookup"><span data-stu-id="60f0d-111">(This article)</span></span>

- <span data-ttu-id="60f0d-112">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="60f0d-112">Step 4.</span></span> <span data-ttu-id="60f0d-113">[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="60f0d-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>


## <a name="move-all-required-hybrid-application-endpoints-from-on-premises-to-online"></a><span data-ttu-id="60f0d-114">将所有必需的混合应用程序终结点从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="60f0d-114">Move all required hybrid application endpoints from on-premises to online</span></span>

<span data-ttu-id="60f0d-115">在可以将这些终结点移动到联机状态之前，必须确保已更新 DNS 记录，以指向Microsoft 365所使用的所有 sip 域的 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="60f0d-115">Before you can move these endpoints to online, you must ensure you have updated DNS records to point to Microsoft 365 for all sip domains used by the endpoints.</span></span> <span data-ttu-id="60f0d-116">如果 DNS 记录指向本地，则不能创建联机资源帐户。</span><span class="sxs-lookup"><span data-stu-id="60f0d-116">It is not possible to create online Resource Accounts if DNS records point to on-premises.</span></span> <span data-ttu-id="60f0d-117">有关详细信息，请参阅 [禁用混合配置](cloud-consolidation-disabling-hybrid.md)。</span><span class="sxs-lookup"><span data-stu-id="60f0d-117">For more information, see [Disable your hybrid configuration](cloud-consolidation-disabling-hybrid.md).</span></span>

1. <span data-ttu-id="60f0d-118">通过执行以下本地部署和 PowerShell 命令检索和导出Skype for Business Server应用程序终结点设置：</span><span class="sxs-lookup"><span data-stu-id="60f0d-118">Retrieve and export on-premises hybrid application endpoint settings by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint|select Sipaddress, DisplayName, ApplicationID, LineUri |Export-Csv -Path "c:\backup\HybridEndpoints.csv"
   ```
2. <span data-ttu-id="60f0d-119">在资源中心[创建](/microsoftteams/manage-resource-accounts)和Microsoft 365资源帐户，以替换现有的本地混合应用程序终结点。</span><span class="sxs-lookup"><span data-stu-id="60f0d-119">Create and license new [Resource Accounts](/microsoftteams/manage-resource-accounts) in Microsoft 365 to replace the existing on-premises hybrid application endpoints.</span></span>

3. <span data-ttu-id="60f0d-120">将新的资源帐户与现有的混合应用程序终结点关联。</span><span class="sxs-lookup"><span data-stu-id="60f0d-120">Associate the new Resource Accounts with the existing hybrid application endpoints.</span></span>

4. <span data-ttu-id="60f0d-121">通过执行以下 PowerShell 命令本地混合应用程序终结点中定义Skype for Business Server电话号码：</span><span class="sxs-lookup"><span data-stu-id="60f0d-121">Remove phone numbers defined in the on-premises hybrid application endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint -Filter {LineURI -ne $null} | Set-CsHybridApplicationEndpoint -LineURI ""
   ```
5. <span data-ttu-id="60f0d-122">由于这些帐户的电话号码有可能在 Microsoft 365 而非本地管理，因此在 Skype for Business PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="60f0d-122">Because it's possible that phone numbers for these accounts were managed in Microsoft 365 instead of on-premises, run the following command in Skype for Business Online PowerShell:</span></span>

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

6. <span data-ttu-id="60f0d-123">将电话号码分配给在步骤 2 中创建的新资源帐户。</span><span class="sxs-lookup"><span data-stu-id="60f0d-123">Assign phone numbers to the new Resource Accounts created in Step 2.</span></span> <span data-ttu-id="60f0d-124">若要详细了解如何将电话号码分配给资源帐户，请参阅以下文章： [分配服务号码](/microsoftteams/manage-resource-accounts#assign-a-service-number)。</span><span class="sxs-lookup"><span data-stu-id="60f0d-124">For more information about how to assign a phone number to a resource account, see the following article: [Assign a service number](/microsoftteams/manage-resource-accounts#assign-a-service-number).</span></span>

7. <span data-ttu-id="60f0d-125">通过执行 PowerShell 命令Skype for Business Server本地终结点：</span><span class="sxs-lookup"><span data-stu-id="60f0d-125">Delete the on-premises endpoints by executing the following on-premises Skype for Business Server PowerShell command:</span></span>

   ```PowerShell
   Get-CsHybridApplicationEndpoint | Remove-CsHybridApplicationEndpoint
   ```
<span data-ttu-id="60f0d-126">现在，你已准备好[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="60f0d-126">You are now ready to [remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="60f0d-127">另请参阅</span><span class="sxs-lookup"><span data-stu-id="60f0d-127">See also</span></span>

- [<span data-ttu-id="60f0d-128">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="60f0d-128">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

- [<span data-ttu-id="60f0d-129">将所有所需的用户从本地移动到联机</span><span class="sxs-lookup"><span data-stu-id="60f0d-129">Move all required users from on-premises to online</span></span>](decommission-move-on-prem-users.md)

- [<span data-ttu-id="60f0d-130">禁用混合配置</span><span class="sxs-lookup"><span data-stu-id="60f0d-130">Disable your hybrid configuration</span></span>](cloud-consolidation-disabling-hybrid.md)

- [<span data-ttu-id="60f0d-131">删除本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="60f0d-131">Remove your on-premises Skype for Business deployment</span></span>](decommission-remove-on-prem.md)




