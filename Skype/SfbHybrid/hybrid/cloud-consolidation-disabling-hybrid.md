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
ms.openlocfilehash: 97681f4e9306336874ba4d9428a273b1d31519db
ms.sourcegitcommit: f39484688800a3d22f361e660d0eeba974a44fb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420837"
---
# <a name="disable-your-hybrid-configuration-to-complete-migration-to-teams-only"></a><span data-ttu-id="7d9fc-103">禁用混合配置以完成仅Teams迁移</span><span class="sxs-lookup"><span data-stu-id="7d9fc-103">Disable your hybrid configuration to complete migration to Teams Only</span></span> 

<span data-ttu-id="7d9fc-104">本文介绍如何在停用本地部署环境之前禁用Skype for Business配置。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-104">This article describes how to disable your hybrid configuration before decommissioning your on-premises Skype for Business environment.</span></span> <span data-ttu-id="7d9fc-105">这是停止使用本地环境的以下步骤的第 2 步：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-105">This is step 2 of the following steps to decommission your on-premises environment:</span></span>

- <span data-ttu-id="7d9fc-106">步骤 1.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-106">Step 1.</span></span> <span data-ttu-id="7d9fc-107">[将所有所需的用户从本地移动到联机](decommission-move-on-prem-users.md)。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-107">[Move all required users from on-premises to online](decommission-move-on-prem-users.md).</span></span>

- <span data-ttu-id="7d9fc-108">**步骤 2.禁用混合配置。**</span><span class="sxs-lookup"><span data-stu-id="7d9fc-108">**Step 2. Disable your hybrid configuration.**</span></span> <span data-ttu-id="7d9fc-109"> (本文) </span><span class="sxs-lookup"><span data-stu-id="7d9fc-109">(This article)</span></span>

- <span data-ttu-id="7d9fc-110">步骤 3.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-110">Step 3.</span></span> <span data-ttu-id="7d9fc-111">[将混合应用程序终结点从本地迁移到联机](decommission-move-on-prem-endpoints.md)。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-111">[Migrate hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md).</span></span>

- <span data-ttu-id="7d9fc-112">步骤 4.</span><span class="sxs-lookup"><span data-stu-id="7d9fc-112">Step 4.</span></span> <span data-ttu-id="7d9fc-113">[删除本地部署Skype for Business部署](decommission-remove-on-prem.md)。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-113">[Remove your on-premises Skype for Business deployment](decommission-remove-on-prem.md).</span></span>

> [!NOTE]
> <span data-ttu-id="7d9fc-114">步骤 2 和步骤 3 应在同一维护窗口中完成，因为任何现有的混合应用程序终结点在步骤 2 和步骤 3 完成之间将不可发现。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-114">Steps 2 and 3 should be done in the same maintenance window because any existing hybrid application endpoints will not be discoverable between steps 2 and completion of step 3.</span></span>

## <a name="overview"></a><span data-ttu-id="7d9fc-115">概述</span><span class="sxs-lookup"><span data-stu-id="7d9fc-115">Overview</span></span>

<span data-ttu-id="7d9fc-116">在将所有用户从本地Skype for Business升级到Teams仅在 Microsoft 365 中，可以停用内部部署Skype for Business部署。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-116">After you have upgraded all users from Skype for Business on-premises to Teams Only in Microsoft 365, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="7d9fc-117">在停用内部部署部署Skype for Business删除任何硬件之前，必须通过禁用混合在逻辑上将本地部署与Microsoft 365分开。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-117">Before you decommission the on-premises Skype for Business deployment and remove any hardware, you must logically separate the on-premises deployment from Microsoft 365 by disabling hybrid.</span></span> <span data-ttu-id="7d9fc-118">禁用混合包括以下四个步骤：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-118">Disabling hybrid consists of the following four steps:</span></span>

1. <span data-ttu-id="7d9fc-119">将 DNS 记录更新为指向 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-119">Update DNS records to point to Microsoft 365.</span></span>

2. <span data-ttu-id="7d9fc-120">将组织的共存模式更改为"仅Teams"。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-120">Change the coexistence mode for your organization to Teams Only.</span></span>

3. <span data-ttu-id="7d9fc-121">在组织 (禁用共享 sip 地址) 也称为"拆分Microsoft 365空间。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-121">Disable shared sip address space (also known as "split domain") in the Microsoft 365 organization.</span></span>

4. <span data-ttu-id="7d9fc-122">在本地禁用与用户通信Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-122">Disable the ability in on-premises to communicate with Microsoft 365.</span></span>

<span data-ttu-id="7d9fc-123">这些步骤在逻辑上将本地部署的 Skype for Business Server 与 Microsoft 365，并确保你的组织完全Teams Only。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-123">These steps logically separate your on-premises deployment of Skype for Business Server from Microsoft 365 and ensure your organization is fully Teams Only.</span></span> <span data-ttu-id="7d9fc-124">本文提供了每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-124">Details for each step are provided in this article.</span></span> <span data-ttu-id="7d9fc-125">完成后，可以使用下面引用的两种方法Skype for Business停用内部部署部署。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-125">Once that is complete, you can decommission your on-premises Skype for Business deployment by using one of two methods referenced below.</span></span>

> [!Important] 
> <span data-ttu-id="7d9fc-126">完成此逻辑分离后，本地 Active Directory 中的 msRTCSIP 属性仍具有值，并且将继续通过 Azure AD 连接同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-126">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="7d9fc-127">如何停用内部部署环境取决于是打算保留这些属性，还是先从本地 Active Directory 中清除它们。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-127">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="7d9fc-128">请注意，从本地迁移后清除本地 msRTCSIP 属性可能会导致用户服务丢失！</span><span class="sxs-lookup"><span data-stu-id="7d9fc-128">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="7d9fc-129">稍后将介绍这两种停用方法的详细信息和权衡。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-129">Details and tradeoffs of the two decommissioning approaches are described later.</span></span>

## <a name="detailed-steps"></a><span data-ttu-id="7d9fc-130">详细步骤</span><span class="sxs-lookup"><span data-stu-id="7d9fc-130">Detailed Steps</span></span>

1. <span data-ttu-id="7d9fc-131">*更新 DNS 以指向Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="7d9fc-131">*Update DNS to point to Microsoft 365.*</span></span> <span data-ttu-id="7d9fc-132">需要更新内部部署组织的组织外部 DNS，以便Skype for Business记录指向Microsoft 365部署。。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-132">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="7d9fc-133">具体来说：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-133">Specifically:</span></span>

    |<span data-ttu-id="7d9fc-134">记录类型</span><span class="sxs-lookup"><span data-stu-id="7d9fc-134">Record type</span></span>|<span data-ttu-id="7d9fc-135">名称</span><span class="sxs-lookup"><span data-stu-id="7d9fc-135">Name</span></span>|<span data-ttu-id="7d9fc-136">TTL</span><span class="sxs-lookup"><span data-stu-id="7d9fc-136">TTL</span></span>|<span data-ttu-id="7d9fc-137">优先级</span><span class="sxs-lookup"><span data-stu-id="7d9fc-137">Priority</span></span>|<span data-ttu-id="7d9fc-138">粗细</span><span class="sxs-lookup"><span data-stu-id="7d9fc-138">Weight</span></span>|<span data-ttu-id="7d9fc-139">端口</span><span class="sxs-lookup"><span data-stu-id="7d9fc-139">Port</span></span>|<span data-ttu-id="7d9fc-140">值</span><span class="sxs-lookup"><span data-stu-id="7d9fc-140">Value</span></span>|
    |---|---|---|---|---|---|---|
    |<span data-ttu-id="7d9fc-141">SRV</span><span class="sxs-lookup"><span data-stu-id="7d9fc-141">SRV</span></span>|<span data-ttu-id="7d9fc-142">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="7d9fc-142">_sipfederationtls._tcp</span></span>|<span data-ttu-id="7d9fc-143">3600</span><span class="sxs-lookup"><span data-stu-id="7d9fc-143">3600</span></span>|<span data-ttu-id="7d9fc-144">100</span><span class="sxs-lookup"><span data-stu-id="7d9fc-144">100</span></span>|<span data-ttu-id="7d9fc-145">1</span><span class="sxs-lookup"><span data-stu-id="7d9fc-145">1</span></span>|<span data-ttu-id="7d9fc-146">5061</span><span class="sxs-lookup"><span data-stu-id="7d9fc-146">5061</span></span>|<span data-ttu-id="7d9fc-147">sipfed.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="7d9fc-147">sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7d9fc-148">SRV</span><span class="sxs-lookup"><span data-stu-id="7d9fc-148">SRV</span></span>|<span data-ttu-id="7d9fc-149">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="7d9fc-149">_sip._tls</span></span>|<span data-ttu-id="7d9fc-150">3600</span><span class="sxs-lookup"><span data-stu-id="7d9fc-150">3600</span></span>|<span data-ttu-id="7d9fc-151">100</span><span class="sxs-lookup"><span data-stu-id="7d9fc-151">100</span></span>|<span data-ttu-id="7d9fc-152">1</span><span class="sxs-lookup"><span data-stu-id="7d9fc-152">1</span></span>|<span data-ttu-id="7d9fc-153">443</span><span class="sxs-lookup"><span data-stu-id="7d9fc-153">443</span></span>|<span data-ttu-id="7d9fc-154">sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="7d9fc-154">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7d9fc-155">CNAME</span><span class="sxs-lookup"><span data-stu-id="7d9fc-155">CNAME</span></span>| <span data-ttu-id="7d9fc-156">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="7d9fc-156">lyncdiscover</span></span>|   <span data-ttu-id="7d9fc-157">3600</span><span class="sxs-lookup"><span data-stu-id="7d9fc-157">3600</span></span>| | | |<span data-ttu-id="7d9fc-158">webdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="7d9fc-158">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="7d9fc-159">CNAME</span><span class="sxs-lookup"><span data-stu-id="7d9fc-159">CNAME</span></span>| <span data-ttu-id="7d9fc-160">sip</span><span class="sxs-lookup"><span data-stu-id="7d9fc-160">sip</span></span>|    <span data-ttu-id="7d9fc-161">3600</span><span class="sxs-lookup"><span data-stu-id="7d9fc-161">3600</span></span>| | | | <span data-ttu-id="7d9fc-162">sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="7d9fc-162">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="7d9fc-163">此外，会议或拨入的 CNAME 记录 (如果存在) 可以删除。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-163">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="7d9fc-164">最后，应删除Skype for Business网络的任何 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-164">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="7d9fc-165">在极少数情况下，将组织的 DNS 从本地指向Microsoft 365可能会导致与其他一些组织的联盟停止工作，直到其他组织更新其联盟配置：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-165">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="7d9fc-166">任何使用旧直接联盟模型 (也称为允许的合作伙伴服务器) 的联合组织都需要更新其组织的允许域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-166">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="7d9fc-167">此旧联盟模型不基于 DNS SRV 记录，因此，一旦组织移动到云，此类配置将过期。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-167">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="7d9fc-168">没有启用 sipfed.online.lync 的宿主提供商的任何联盟组织。 <span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-168">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="7d9fc-169">这种情况只有在联盟组织完全在本地且从未与任何混合或联机租户联盟时才能实现。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-169">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="7d9fc-170">在这种情况下，在启用其宿主提供商之前，与这些组织的联盟将不起作用。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-170">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="7d9fc-171">如果您怀疑您的任何联盟伙伴可能正在使用直接联盟，或者未与任何联机或混合组织联盟，我们建议您在准备完成迁移到云时发送有关此内容的通信。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-171">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="7d9fc-172">*将组织的共存模式更改为"仅Teams"。*</span><span class="sxs-lookup"><span data-stu-id="7d9fc-172">*Change the coexistence mode for your organization to Teams Only.*</span></span> <span data-ttu-id="7d9fc-173">这可确保将组织的任何新用户始终创建为仅Teams用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-173">This ensures that any new user in your organization is always created as a Teams Only user.</span></span> <span data-ttu-id="7d9fc-174">此外，尝试将租户模式更改为 Teams Only 将自动检查是否存在步骤 1 中可能遗漏的任何本地 DNS 记录，并识别输出中的这些记录。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-174">In addition,  attempting to change the tenant mode to Teams Only will automatically check for existence of any on-premises DNS records that may have been missed in step 1 and identify these records in the output.</span></span>  <span data-ttu-id="7d9fc-175">在更新组织的所有 DNS 记录Teams仅租户模式不会成功。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-175">Changing the tenant mode to Teams Only will not succeed until all DNS records for your organizaiton are updated.</span></span> <span data-ttu-id="7d9fc-176">若要将租户模式更改为 Teams请仅从 PowerShell 窗口Teams以下命令。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-176">To change the tenant mode to Teams Only run the following command from a Teams PowerShell window.</span></span>

     ```PowerShell
     Grant-CsTeamsUpgradePolicy -PolicyName UpgradeToTeams -Global
     ```
<span data-ttu-id="7d9fc-177">或者，可以使用 Teams 管理中心将租户共存模式更改为 TeamsOnly，在"组织范围的设置"->"Teams升级"下。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-177">Alternatively, you can use the Teams Admin Center to change the tenant coexistence mode to TeamsOnly, under "Org-wide settings" -> "Teams Upgrade."</span></span>    
    
3.  <span data-ttu-id="7d9fc-178">*在组织中禁用共享 sip Microsoft 365空间。*</span><span class="sxs-lookup"><span data-stu-id="7d9fc-178">*Disable shared sip address space in Microsoft 365 organization.*</span></span> <span data-ttu-id="7d9fc-179">以下命令需要从 PowerShell 窗口Teams完成。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-179">The command below needs to be done from a Teams PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
4.  <span data-ttu-id="7d9fc-180">*在本地禁用与用户通信Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="7d9fc-180">*Disable the ability in on-premises to communicate with Microsoft 365.*</span></span> <span data-ttu-id="7d9fc-181">以下命令需要在内部部署 PowerShell 窗口中完成：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-181">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="7d9fc-182">将用户从本地迁移到云后管理属性</span><span class="sxs-lookup"><span data-stu-id="7d9fc-182">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="7d9fc-183">默认情况下，之前已启用 Skype for Business Server随后移动到云的所有用户仍在本地 Active Directory 中配置 msRTCSIP 属性。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-183">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="7d9fc-184">这些属性（尤其是 sip 地址 (msRTCSIP-PrimaryUserAddress) 以及可能的电话号码 (msRTCSIP-Line) ）将继续同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-184">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="7d9fc-185">如果需要更改任何 msRTCSIP 属性，则必须在本地 Active Directory 中进行更改，然后同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-185">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="7d9fc-186">但是，Skype for Business Server部署后，Skype for Business Server工具将不能管理这些属性。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-186">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="7d9fc-187">有两个选项可用于处理这种情况：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-187">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="7d9fc-188">将启用的用户保留为 Skype for Business 帐户，然后使用 Active Directory 工具管理 msRTCSIP 属性。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-188">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="7d9fc-189">这可确保迁移用户不会丢失服务，并允许你通过消除 (（例如擦除) 服务器）轻松删除 Skype for Business Server 部署，而无需完全停用。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-189">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="7d9fc-190">但是，新授权的用户不会在本地 Active Directory 中填充这些属性，并且需要联机管理。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-190">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="7d9fc-191">清除本地 Active Directory 中迁移用户的所有 msRTCSIP 属性，然后使用联机工具管理这些属性。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-191">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="7d9fc-192">此方法允许现有用户和新用户采用一致的管理方法，但可能会导致本地停用过程中暂时丢失服务。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-192">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="7d9fc-193">方法 1 - 在 Active Directory 中管理用户的 sip 地址和电话号码</span><span class="sxs-lookup"><span data-stu-id="7d9fc-193">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="7d9fc-194">管理员可管理以前从本地部署Skype for Business Server移动到云的用户，即使内部部署已停用。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-194">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="7d9fc-195">如果要更改用户的 sip 地址或用户的电话号码 (并且 sip 地址或电话号码在本地 Active Directory) 中已有值，则必须在本地 Active Directory 中这样做，让值 (s) 流向 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-195">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="7d9fc-196">这不需要本地Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-196">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="7d9fc-197">相反，您可以直接在本地 Active Directory 中修改这些属性，使用 Active Directory 用户和计算机 MMC 管理单元 (如下) 所示，或者使用 PowerShell 修改这些属性。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-197">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="7d9fc-198">如果使用的是 MMC 管理单元，请打开用户的属性页，单击"属性编辑器"选项卡，并查找要修改的适当属性：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-198">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="7d9fc-199">若要修改用户的 sip 地址，请修改 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-199">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7d9fc-200">如果 `ProxyAddresses` 属性包含 sip 地址，则作为最佳实践更新该值。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-200">If the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="7d9fc-201">尽管已填充的 O365 将忽略 中的 sip 地址，但其他本地组件 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 可能会使用。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-201">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="7d9fc-202">若要修改用户的电话号码，请 `msRTCSIP-Line` *修改（如果已具有值*）。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-202">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="7d9fc-204">如果用户在移动之前最初没有本地值，您可以使用 `msRTCSIP-Line` Skype for Business Online PowerShell 模块中 `onpremLineUri` [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps)中的 - 参数修改电话号码。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-204">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="7d9fc-205">这些步骤对于禁用混合后创建的新用户来说不是必需的，可以直接在云中管理这些用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-205">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="7d9fc-206">如果你习惯混合使用这些方法，并习惯将 msRTCSIP 属性留在本地 Active Directory 中，则只需重新映像本地 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-206">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="7d9fc-207">但是，如果你希望清除所有 msRTCSIP 属性，并执行传统卸载Skype for Business Server，请使用方法 2。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-207">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="7d9fc-208">方法 2 - Skype for Business Active Directory 中所有本地用户的属性</span><span class="sxs-lookup"><span data-stu-id="7d9fc-208">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="7d9fc-209">此选项需要进行额外的工作并进行适当的规划，因为以前从本地Skype for Business Server移动到云的用户需要重新预配。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-209">This option requires additional effort and proper planning because users who were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="7d9fc-210">可以将这些用户分为两个不同的类别：没有电话系统的用户和具有电话系统。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-210">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="7d9fc-211">在将电话系统 Active Directory 中管理到云中时，拥有此号码的用户将遇到电话服务暂时丢失的问题。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-211">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="7d9fc-212">**建议在启动批量用户操作之前执行涉及少量用户电话系统试点。**</span><span class="sxs-lookup"><span data-stu-id="7d9fc-212">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="7d9fc-213">对于大型部署，可以在不同的时间窗口中以较小的组处理用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-213">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="7d9fc-214">对于具有匹配的 sip 地址和 UserPrincipalName 的用户，此过程最简单。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-214">This process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="7d9fc-215">对于用户具有跨这两个属性的不匹配值的组织，必须格外小心，如下所述，以便顺利过渡。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-215">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span>

> [!NOTE]
> <span data-ttu-id="7d9fc-216">如果为自动助理或呼叫队列配置了本地混合应用程序终结点，请确保在停用 Microsoft 365 之前，Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-216">If you have configured on-premises hybrid application endpoints for Auto Attendants or Call Queues, be sure to move these endpoints to Microsoft 365 before decommissioning Skype for Business Server.</span></span>


1. <span data-ttu-id="7d9fc-217">确认以下本地 Skype for Business PowerShell cmdlet 返回空结果。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-217">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="7d9fc-218">空结果意味着没有用户位于本地，并且已移动到Microsoft 365或已禁用：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-218">An empty result means no users are homed on-premises and have either been moved to Microsoft 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="7d9fc-219">通过执行以下本地 Skype for Business Server PowerShell cmdlet 导出用户数据 (LineUri) 、UserPrincipalName 和相关信息，记录用户的当前电话号码：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-219">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="7d9fc-220">在继续打开SfbUserSettings.csv文件并确认已成功导出所有用户数据。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-220">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="7d9fc-221">建议保留此文件的副本。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-221">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="7d9fc-222">请勿在以下步骤中使用此文件处理用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-222">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="7d9fc-223">创建一个包含一组用户的文件，以便执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-223">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="7d9fc-224">成功完成第一组用户后，继续处理下一组用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-224">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="7d9fc-225">在下面的示例中，用户组按字母顺序进行选择，但您可以基于与处理用户匹配的条件筛选用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-225">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="7d9fc-226">在继续打开SfbUsers.csv文件并确认已成功导出用户数据之前。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-226">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="7d9fc-227">在稍后的步骤中，将需要此 (的 LineUri) 、UserPrincipalName、SamAccountName 和 SipAddress。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-227">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="7d9fc-228">从 active Directory 中删除Skype for Business Server准备更新的一组用户的属性信息。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-228">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="7d9fc-229">此过程有 2 个步骤，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-229">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="7d9fc-230">在运行此步骤后的下一个 AAD Sync 周期后，具有 电话系统 的用户（以前从本地 Skype for Business Server 移动到云）将失去拨打和接听呼叫的能力，直到步骤 8 成功完成，且在步骤 9 中确认。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-230">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="7d9fc-231">此外，请确保已按步骤 2 保存用户的电话号码和相关信息，因为此步骤需要该信息。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-231">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="7d9fc-232">接下来，对于同一组用户，使用本地 Active Directory PowerShell 清除 msRTCSIP-DeploymentLocator 的值：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-232">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="7d9fc-233">运行以下内部部署 Active Directory 模块Windows PowerShell cmdlet 将 sip 地址值添加回本地 Active Directory 代理Addresses。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-233">Run the following on-premise Active Directory Module for Windows PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="7d9fc-234">这将防止依赖此属性的互操作性问题。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-234">This will prevent interoperability issues that rely on this attribute.</span></span> 

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
     $userUpn=$user.UserPrincipalName
     $userSip=$user.SipAddress
     $proxies=Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" -properties * | Select-Object @{Name="proxyAddresses";Expression={$_.proxyAddresses}}
     if(($null -eq $proxies) -or ($proxies.proxyAddresses -NotContains $userSip))
     {
             Get-ADUser -Filter "UserPrincipalName -eq '$userUpn'" | Set-ADUser -Add @{"proxyAddresses"=$user.SipAddress}
     }
   }
   ```

6. <span data-ttu-id="7d9fc-235">运行Azure AD Sync</span><span class="sxs-lookup"><span data-stu-id="7d9fc-235">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="7d9fc-236">等待用户预配完成。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-236">Wait for user provisioning to complete.</span></span> <span data-ttu-id="7d9fc-237">可以通过运行以下命令来监视用户预配Skype for Business Online PowerShell 命令。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-237">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="7d9fc-238">以下 Skype for Business Online PowerShell 命令将在进程完成后返回空结果。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-238">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="7d9fc-239">执行以下 Skype for Business Online PowerShell 命令来分配电话号码并允许用户电话系统：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-239">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   if($user.LineUri)
        {
                Set-CsUser -Identity $user.SipAddress -OnPremLineURI $user.LineUri -EnterpriseVoiceEnabled $True
        }
   }
    ```

   > [!Note]
   >  <span data-ttu-id="7d9fc-240">如果仍有Skype for Business终结点 (客户端Skype第三方) ，则还需要将 -HostedVoiceMail 设置为 $true。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-240">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="7d9fc-241">如果您的组织仅对启用Teams使用语音终结点，则此设置不适用于您的用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-241">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="7d9fc-242">确认具有电话系统功能的用户已正确设置。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-242">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="7d9fc-243">以下 Skype for Business Online PowerShell 命令将在进程完成后返回空结果。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-243">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers)
   {
   if($user.LineUri)
        {
                $u=Get-CsOnlineUser -Identity $user.SipAddress
                if ($u.LineURI -ne $user.LineUri -or $u.EnterpriseVoiceEnabled -ne $true)
                {
                Get-CsOnlineUser -Identity $user.SipAddress | fl SipAddress, InterpretedUserType, OnPremLineURI, LineURI, EnterpriseVoiceEnabled, HostedVoicemail
                }
        }
   }
   ``` 

10. <span data-ttu-id="7d9fc-244">重复步骤 3 至 9，直到处理所有用户。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-244">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="7d9fc-245">通过运行以下两个 PowerShell 命令，确认所有用户都已成功处理。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-245">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="7d9fc-246">本地 Skype for Business Server PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-246">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="7d9fc-247">Skype for Business联机 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="7d9fc-247">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 
12. <span data-ttu-id="7d9fc-248">完成方法 2 的所有步骤后，请参阅将混合[](decommission-move-on-prem-endpoints.md)应用程序终结点从本地移动到联机和删除本地[Skype for Business Server，](decommission-remove-on-prem.md)了解删除本地 Skype for Business Server 部署的其他步骤。</span><span class="sxs-lookup"><span data-stu-id="7d9fc-248">After you have completed all steps in Method 2, see [Move hybrid application endpoints from on-premises to online](decommission-move-on-prem-endpoints.md) and [Remove your on-premises Skype for Business Server](decommission-remove-on-prem.md) for additional steps to remove your Skype for Business Server on-premises deployment.</span></span>


## <a name="see-also"></a><span data-ttu-id="7d9fc-249">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7d9fc-249">See also</span></span>

- [<span data-ttu-id="7d9fc-250">云解决方案Teams Skype for Business</span><span class="sxs-lookup"><span data-stu-id="7d9fc-250">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)

- [<span data-ttu-id="7d9fc-251">停用本地 Skype for Business 环境</span><span class="sxs-lookup"><span data-stu-id="7d9fc-251">Decommission your on-premises Skype for Business environment</span></span>](decommission-on-prem-overview.md)

