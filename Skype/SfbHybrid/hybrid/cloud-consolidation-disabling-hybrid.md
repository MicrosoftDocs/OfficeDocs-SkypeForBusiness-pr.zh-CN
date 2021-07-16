---
title: 禁用混合以完成仅Teams迁移
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.prod: skype-for-business-itpro
search.appverid: MET150
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
audience: ITPro
f1.keywords:
- NOCSH
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本文包括禁用混合功能的详细步骤，作为云解决方案和Teams Skype for Business。
ms.openlocfilehash: 87bd1f6e0dcabed067174972dd0f0fc51149beb0
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453641"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="8c30b-103">禁用混合配置以完成仅Teams迁移</span><span class="sxs-lookup"><span data-stu-id="8c30b-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="8c30b-104">本文介绍如何在停用本地部署环境之前禁用Skype for Business配置。</span><span class="sxs-lookup"><span data-stu-id="8c30b-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="8c30b-105">这是停止使用本地环境的以下步骤的第 2 步：</span><span class="sxs-lookup"><span data-stu-id="8c30b-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="8c30b-106">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="8c30b-106">Step 1.</span></span> <span data-ttu-id="8c30b-107">[将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="8c30b-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="8c30b-108">**步骤 2.禁用混合配置。**</span><span class="sxs-lookup"><span data-stu-id="8c30b-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="8c30b-109"> (本文) </span><span class="sxs-lookup"><span data-stu-id="8c30b-109">(This article)</span></span>

- <span data-ttu-id="8c30b-110">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="8c30b-110">Step 3.</span></span> <span data-ttu-id="8c30b-111">[将混合应用程序终结点从本地迁移到联机](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="8c30b-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="8c30b-112">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="8c30b-112">Step 4.</span></span> <span data-ttu-id="8c30b-113">[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="8c30b-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="8c30b-114">步骤 2 和步骤 3 应在同一维护窗口中完成，因为任何现有的混合应用程序终结点在步骤 2 和步骤 3 完成之间将不可发现。</span><span class="sxs-lookup"><span data-stu-id="8c30b-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>


## <a name="summary"></a><span data-ttu-id="8c30b-115">摘要</span><span class="sxs-lookup"><span data-stu-id="8c30b-115">Summary</span></span>

<span data-ttu-id="8c30b-116">在将所有用户从本地Skype for Business升级到Teams仅在 Microsoft 365 中，可以停用内部部署Skype for Business部署。</span><span class="sxs-lookup"><span data-stu-id="8c30b-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span>

<span data-ttu-id="8c30b-117">在停用内部部署部署Skype for Business删除任何硬件之前，必须通过禁用混合在逻辑上将本地部署与Microsoft 365分开。</span><span class="sxs-lookup"><span data-stu-id="8c30b-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="8c30b-118">禁用混合包括以下四个步骤：</span><span class="sxs-lookup"><span data-stu-id="8c30b-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="8c30b-119">[更新 DNS 记录以指向Microsoft 365。](#update-dns-to-point-to-microsoft-365)</span><span class="sxs-lookup"><span data-stu-id="8c30b-119">[Update DNS records to point to Microsoft 365](#update-dns-to-point-to-microsoft-365).</span></span>

2. <span data-ttu-id="8c30b-120">[将组织的共存模式更改为"仅Teams"。](#change-the-coexistence-mode-for-your-organization-to-teams-only)</span><span class="sxs-lookup"><span data-stu-id="8c30b-120">[Change the coexistence mode for your organization to Teams Only](#change-the-coexistence-mode-for-your-organization-to-teams-only).</span></span>

3. <span data-ttu-id="8c30b-121">在组织 (共享 sip 地址空间[) "拆分Microsoft 365共享 sip 地址空间](#disable-shared-sip-address-space-in-microsoft-365-organization)。</span><span class="sxs-lookup"><span data-stu-id="8c30b-121">[Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization](#disable-shared-sip-address-space-in-microsoft-365-organization).</span></span>

4. [<span data-ttu-id="8c30b-122">禁用内部部署和内部部署之间的Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c30b-122">Disable communication between on-premises and Microsoft 365</span></span>](#disable-communication-between-on-premises-and-microsoft-365)

<span data-ttu-id="8c30b-123">这些步骤在逻辑上将本地部署的 Skype for Business Server 与 Microsoft 365，并确保你的组织完全Teams Only。</span><span class="sxs-lookup"><span data-stu-id="8c30b-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="8c30b-124">完成这些步骤后，可以使用 Decide [how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md)中引用的两种方法之一停用内部部署 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="8c30b-124">After you've completed these steps, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

> [!Important] 
> <span data-ttu-id="8c30b-125">完成此逻辑分离后，本地 Active Directory 中的 msRTCSIP 属性仍具有值，并且将继续通过 Azure AD 连接同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="8c30b-125">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="8c30b-126">如何停用内部部署环境取决于是打算保留这些属性，还是先从本地 Active Directory 中清除它们。</span><span class="sxs-lookup"><span data-stu-id="8c30b-126">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="8c30b-127">请注意，从本地迁移后清除本地 msRTCSIP 属性可能会导致用户服务丢失！</span><span class="sxs-lookup"><span data-stu-id="8c30b-127">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="8c30b-128">在决定在停用后如何管理属性中介绍了这两种停用方法 [的详细信息和权衡](cloud-consolidation-managing-attributes.md)。</span><span class="sxs-lookup"><span data-stu-id="8c30b-128">Details and tradeoffs of the two decommissioning approaches are described in [Decide how to manage attributes after decommissioning](cloud-consolidation-managing-attributes.md).</span></span>

## <a name="update-dns-to-point-to-microsoft-365"></a><span data-ttu-id="8c30b-129">更新 DNS 以指向Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c30b-129">Update DNS to point to Microsoft 365</span></span>

<span data-ttu-id="8c30b-130">需要更新内部部署组织的组织外部 DNS，以便Skype for Business记录指向Microsoft 365部署。。</span><span class="sxs-lookup"><span data-stu-id="8c30b-130">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> 

<span data-ttu-id="8c30b-131">此外，会议或拨入的 CNAME 记录 (如果存在) 可以删除。</span><span class="sxs-lookup"><span data-stu-id="8c30b-131">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="8c30b-132">最后，应删除Skype for Business网络的任何 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="8c30b-132">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

<span data-ttu-id="8c30b-133">有关更新 DNS 记录的详细信息，请参阅[更新 DNS](decommission-manage-dns-entries.md)条目以使你的组织能够全部Teams记录。</span><span class="sxs-lookup"><span data-stu-id="8c30b-133">For details about updating DNS records, see [Update DNS entries to enable your organization to be all Teams Only](decommission-manage-dns-entries.md).</span></span>

## <a name="change-the-coexistence-mode-for-your-organization-to-teams-only"></a><span data-ttu-id="8c30b-134">将组织的共存模式更改为"仅Teams"</span><span class="sxs-lookup"><span data-stu-id="8c30b-134">Change the coexistence mode for your organization to Teams Only</span></span>

<span data-ttu-id="8c30b-135">此步骤可确保将组织的任何新用户始终创建为仅Teams用户。</span><span class="sxs-lookup"><span data-stu-id="8c30b-135">This step ensures that any new user in your organization is always created as a Teams Only user.</span></span> 

<span data-ttu-id="8c30b-136">尝试将租户模式更改为 Teams Only 将自动检查是否存在步骤 1 中可能遗漏的任何本地 DNS 记录，并会在输出中标识这些记录。</span><span class="sxs-lookup"><span data-stu-id="8c30b-136">Attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span> <span data-ttu-id="8c30b-137">将租户模式Teams只有更新组织的所有 DNS 记录后才会成功。</span><span class="sxs-lookup"><span data-stu-id="8c30b-137">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organization are updated.</span></span> 

<span data-ttu-id="8c30b-138">若要将租户模式更改为 Teams请仅从 PowerShell 窗口Teams以下命令。</span><span class="sxs-lookup"><span data-stu-id="8c30b-138">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
```

<span data-ttu-id="8c30b-139">或者，可以使用 Teams 管理中心将租户共存模式更改为 TeamsOnly，在"组织范围的设置"->"Teams升级"下。</span><span class="sxs-lookup"><span data-stu-id="8c30b-139">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    

## <a name="disable-shared-sip-address-space-in-microsoft-365-organization"></a><span data-ttu-id="8c30b-140">禁用组织中共享的 sip 地址Microsoft 365空间</span><span class="sxs-lookup"><span data-stu-id="8c30b-140">Disable shared sip address space in Microsoft 365 organization</span></span>
    
<span data-ttu-id="8c30b-141">若要禁用共享 sip 地址空间，请从 PowerShell Teams运行以下命令。</span><span class="sxs-lookup"><span data-stu-id="8c30b-141">To disable shared sip address space, run the following command from a Teams PowerShell window.</span></span>

```PowerShell
Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
```
 
## <a name="disable-communication-between-on-premises-and-microsoft-365"></a><span data-ttu-id="8c30b-142">禁用内部部署和内部部署之间的Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8c30b-142">Disable communication between on-premises and Microsoft 365</span></span>

<span data-ttu-id="8c30b-143">若要禁用本地环境和 Microsoft 365之间的通信，请从本地 PowerShell 窗口运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8c30b-143">To disable communication between the on-premises environment and Microsoft 365, run the following command from an on-premises PowerShell window:</span></span>

```PowerShell
Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```


## <a name="see-also"></a><span data-ttu-id="8c30b-144">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c30b-144">See also</span></span>

- [<span data-ttu-id="8c30b-145">云解决方案Teams Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8c30b-145">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="8c30b-146">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="8c30b-146">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

