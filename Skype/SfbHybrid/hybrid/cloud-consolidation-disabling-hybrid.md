---
title: 禁用混合以完成云迁移
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
description: 本文包括禁用混合作为 Teams 和 Skype for Business 云整合的一部分的详细步骤。
ms.openlocfilehash: 36ec3cba2d821cc8554e0fba95108756c83b7b3d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120351"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud-overview"></a><span data-ttu-id="6828a-103">禁用混合以完成到云的迁移：概述</span><span class="sxs-lookup"><span data-stu-id="6828a-103">Disable hybrid to complete migration to the cloud: Overview</span></span>

<span data-ttu-id="6828a-104">将所有用户从本地移动到云后，可取消本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="6828a-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="6828a-105">除了删除任何硬件之外，关键步骤是通过禁用混合在逻辑上将本地部署与 Microsoft 365 或 Office 365 分离。</span><span class="sxs-lookup"><span data-stu-id="6828a-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="6828a-106">禁用混合由三个步骤组成：</span><span class="sxs-lookup"><span data-stu-id="6828a-106">Disabling hybrid consists of three steps:</span></span>

1. <span data-ttu-id="6828a-107">更新 DNS 记录以指向 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="6828a-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="6828a-108">在 Microsoft 365 或 Office 365 (禁用共享 sip 地址空间) 也称为"拆分域"。</span><span class="sxs-lookup"><span data-stu-id="6828a-108">Disable shared sip address space (also known as "split domain") in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="6828a-109">禁用本地与 Microsoft 365 或 Office 365 进行通信的能力。</span><span class="sxs-lookup"><span data-stu-id="6828a-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="6828a-110">这些步骤在逻辑上将 Skype for Business Server 本地部署与 Office 365 分离，并且应作为一个单元一起执行。</span><span class="sxs-lookup"><span data-stu-id="6828a-110">These steps logically separate your on-premise deployment of Skype for Business Server from Office 365 and should be done together as a unit.</span></span> <span data-ttu-id="6828a-111">下文中提供了每个步骤的详细信息。</span><span class="sxs-lookup"><span data-stu-id="6828a-111">Details for each step are provided in this article below.</span></span> <span data-ttu-id="6828a-112">完成后，可以使用下面引用的两种方法之一停用本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="6828a-112">Once that is complete, you can decommission your on-premises Skype for Business Deployment using one of two methods referenced below.</span></span>

> [!Important] 
><span data-ttu-id="6828a-113">完成此逻辑分离后，本地 Active Directory 中的 msRTCSIP 属性仍具有值，并且将继续通过 Azure AD Connect 同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6828a-113">Once this logical separation is complete, msRTCSIP attributes from your on-premises Active Directory still have values and will continue to sync via Azure AD Connect into Azure AD.</span></span> <span data-ttu-id="6828a-114">如何停用内部部署环境取决于是打算保留这些属性，还是先从本地 Active Directory 中清除它们。</span><span class="sxs-lookup"><span data-stu-id="6828a-114">How you decommission the on-premises environment depends on whether you intend to leave these attributes in place, or first clear them from your on-premises Active Directory.</span></span> <span data-ttu-id="6828a-115">请注意，从本地迁移后清除本地 msRTCSIP 属性可能会导致用户服务丢失！</span><span class="sxs-lookup"><span data-stu-id="6828a-115">Be aware that clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span> <span data-ttu-id="6828a-116">下面将介绍这两种停用方法的详细信息和权衡。</span><span class="sxs-lookup"><span data-stu-id="6828a-116">Details and tradeoffs of the two decommissioning approaches are described later below.</span></span>

## <a name="disable-hybrid-to-complete-migration-to-the-cloud-detailed-steps"></a><span data-ttu-id="6828a-117">禁用混合以完成到云的迁移：详细步骤</span><span class="sxs-lookup"><span data-stu-id="6828a-117">Disable hybrid to complete migration to the cloud: Detailed Steps</span></span>

1. <span data-ttu-id="6828a-118">*更新 DNS 以指向 Microsoft 365 或 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="6828a-118">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span> <span data-ttu-id="6828a-119">需要更新组织内部部署组织的外部 DNS，以便 Skype for Business 记录指向 Microsoft 365 或 Office 365，而不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="6828a-119">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="6828a-120">具体来说：</span><span class="sxs-lookup"><span data-stu-id="6828a-120">Specifically:</span></span>

    |<span data-ttu-id="6828a-121">记录类型</span><span class="sxs-lookup"><span data-stu-id="6828a-121">Record type</span></span>|<span data-ttu-id="6828a-122">名称</span><span class="sxs-lookup"><span data-stu-id="6828a-122">Name</span></span>|<span data-ttu-id="6828a-123">TTL</span><span class="sxs-lookup"><span data-stu-id="6828a-123">TTL</span></span>|<span data-ttu-id="6828a-124">值</span><span class="sxs-lookup"><span data-stu-id="6828a-124">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="6828a-125">SRV</span><span class="sxs-lookup"><span data-stu-id="6828a-125">SRV</span></span>|<span data-ttu-id="6828a-126">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="6828a-126">_sipfederationtls._tcp</span></span>|<span data-ttu-id="6828a-127">3600</span><span class="sxs-lookup"><span data-stu-id="6828a-127">3600</span></span>|<span data-ttu-id="6828a-128">100 1 5061 sipfed.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6828a-128">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6828a-129">SRV</span><span class="sxs-lookup"><span data-stu-id="6828a-129">SRV</span></span>|<span data-ttu-id="6828a-130">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="6828a-130">_sip._tls</span></span>|<span data-ttu-id="6828a-131">3600</span><span class="sxs-lookup"><span data-stu-id="6828a-131">3600</span></span>|<span data-ttu-id="6828a-132">100 1 443 sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6828a-132">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6828a-133">CNAME</span><span class="sxs-lookup"><span data-stu-id="6828a-133">CNAME</span></span>| <span data-ttu-id="6828a-134">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="6828a-134">lyncdiscover</span></span>|   <span data-ttu-id="6828a-135">3600</span><span class="sxs-lookup"><span data-stu-id="6828a-135">3600</span></span>|   <span data-ttu-id="6828a-136">webdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6828a-136">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="6828a-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="6828a-137">CNAME</span></span>| <span data-ttu-id="6828a-138">sip</span><span class="sxs-lookup"><span data-stu-id="6828a-138">sip</span></span>|    <span data-ttu-id="6828a-139">3600</span><span class="sxs-lookup"><span data-stu-id="6828a-139">3600</span></span>|   <span data-ttu-id="6828a-140">sipdir.online.lync。 <span>com</span><span class="sxs-lookup"><span data-stu-id="6828a-140">sipdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="6828a-141">此外，会议或拨入的 CNAME 记录 (如果存在) 可以删除。</span><span class="sxs-lookup"><span data-stu-id="6828a-141">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="6828a-142">最后，应删除内部网络中 Skype for Business 的所有 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="6828a-142">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="6828a-143">在极少数情况下，将 DNS 从本地指向组织的 Microsoft 365 或 Office 365 可能会导致与其他一些组织的联盟停止工作，直到其他组织更新其联盟配置：</span><span class="sxs-lookup"><span data-stu-id="6828a-143">In rare cases, changing DNS from pointing on premises to Microsoft 365 or Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="6828a-144">任何使用旧直接联盟模型 (也称为允许的合作伙伴服务器) 的联合组织都需要更新其组织的允许域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="6828a-144">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="6828a-145">此旧联盟模型不基于 DNS SRV 记录，因此，一旦组织移动到云，此类配置将过期。</span><span class="sxs-lookup"><span data-stu-id="6828a-145">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="6828a-146">没有启用 sipfed.online.lync 的宿主提供商的任何联盟组织。 <span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="6828a-146">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="6828a-147">这种情况只有在联盟组织完全在本地且从未与任何混合或联机租户联盟时才能实现。</span><span class="sxs-lookup"><span data-stu-id="6828a-147">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="6828a-148">在这种情况下，在启用其宿主提供商之前，与这些组织的联盟将不起作用。</span><span class="sxs-lookup"><span data-stu-id="6828a-148">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="6828a-149">如果您怀疑您的任何联盟伙伴可能正在使用直接联盟，或者未与任何联机或混合组织联盟，我们建议您在准备完成迁移到云时发送有关此内容的通信。</span><span class="sxs-lookup"><span data-stu-id="6828a-149">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="6828a-150">*在 Microsoft 365 或 Office 365 组织中禁用共享 sip 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="6828a-150">*Disable shared sip address space in Microsoft 365 or Office 365 organization.*</span></span> <span data-ttu-id="6828a-151">以下命令需要在 Skype for Business Online PowerShell 窗口中完成。</span><span class="sxs-lookup"><span data-stu-id="6828a-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

     ```PowerShell
     Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
     ```
 
3.  <span data-ttu-id="6828a-152">*禁用本地与 Microsoft 365 或 Office 365 进行通信的能力。*</span><span class="sxs-lookup"><span data-stu-id="6828a-152">*Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span> <span data-ttu-id="6828a-153">以下命令需要在内部部署 PowerShell 窗口中完成：</span><span class="sxs-lookup"><span data-stu-id="6828a-153">The command below needs to be done from an on-premises PowerShell window:</span></span>

     ```PowerShell
     Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
     ```

## <a name="managing-attributes-after-moving-users-from-on-premises-to-the-cloud"></a><span data-ttu-id="6828a-154">将用户从本地迁移到云后管理属性</span><span class="sxs-lookup"><span data-stu-id="6828a-154">Managing attributes after moving users from on-premises to the cloud</span></span>

<span data-ttu-id="6828a-155">默认情况下，之前已启用 Skype for Business Server 且随后移动到云的所有用户在本地 Active Directory 中仍配置了 msRTCSIP 属性。</span><span class="sxs-lookup"><span data-stu-id="6828a-155">By default, all users that were previously enabled for Skype for Business Server and subsequently moved to the cloud still have msRTCSIP attributes configured in your on-premises Active Directory.</span></span> <span data-ttu-id="6828a-156">这些属性（尤其是 sip 地址 (msRTCSIP-PrimaryUserAddress) 以及可能的电话号码 (msRTCSIP-Line) ）将继续同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6828a-156">These attributes, in particular sip address (msRTCSIP-PrimaryUserAddress) and potentially phone number (msRTCSIP-Line), continue to sync into Azure AD.</span></span> <span data-ttu-id="6828a-157">如果需要更改任何 msRTCSIP 属性，则必须在本地 Active Directory 中进行更改，然后同步到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6828a-157">If changes are required to any of the msRTCSIP attributes, these changes must be made in the on-premises Active Directory and then sync'd to Azure AD.</span></span> <span data-ttu-id="6828a-158">但是，一旦删除了 Skype for Business Server 部署，Skype for Business Server 工具将不能用于管理这些属性。</span><span class="sxs-lookup"><span data-stu-id="6828a-158">However, once the Skype for Business Server deployment has been removed, the Skype for Business Server tools will not be available to manage these attributes.</span></span>

<span data-ttu-id="6828a-159">有两个选项可用于处理这种情况：</span><span class="sxs-lookup"><span data-stu-id="6828a-159">There are two options available for handling this situation:</span></span>

1. <span data-ttu-id="6828a-160">保留为 Skype for Business 服务器帐户启用的用户，然后使用 Active Directory 工具管理 msRTCSIP 属性。</span><span class="sxs-lookup"><span data-stu-id="6828a-160">Leave users that were enabled for Skype for Business server accounts as is, and manage the  msRTCSIP attributes using Active Directory tools.</span></span> <span data-ttu-id="6828a-161">这可确保迁移用户不会丢失服务，并允许你通过消除 (（例如擦除) ）轻松删除 Skype for Business Server 部署，而无需完全停用。</span><span class="sxs-lookup"><span data-stu-id="6828a-161">This ensures no loss of service for migrated users, and allows you to easily remove the Skype for Business Server deployment by eliminating (e.g. wiping) the servers, without a full decommissioning.</span></span> <span data-ttu-id="6828a-162">但是，新授权的用户不会在本地 Active Directory 中填充这些属性，并且需要联机管理。</span><span class="sxs-lookup"><span data-stu-id="6828a-162">However, newly licensed users will not have these attributes populated in your on-premises Active Directory and will need to be managed online.</span></span>

2.  <span data-ttu-id="6828a-163">清除本地 Active Directory 中迁移用户的所有 msRTCSIP 属性，然后使用联机工具管理这些属性。</span><span class="sxs-lookup"><span data-stu-id="6828a-163">Clear all msRTCSIP attributes from migrated users in your on-premises Active Directory and manage these attributes using online tools.</span></span> <span data-ttu-id="6828a-164">此方法允许现有用户和新用户采用一致的管理方法，但可能会导致本地停用过程中暂时丢失服务。</span><span class="sxs-lookup"><span data-stu-id="6828a-164">This method allows for a consistent management approach for existing and new users, however it may potentially result in a temporary loss of service during the on-premises decommissioning process.</span></span>


### <a name="method-1---manage-sip-addresses-and-phone-numbers-for-users-in-active-directory"></a><span data-ttu-id="6828a-165">方法 1 - 在 Active Directory 中管理用户的 sip 地址和电话号码</span><span class="sxs-lookup"><span data-stu-id="6828a-165">Method 1 - Manage sip addresses and phone numbers for users in Active Directory</span></span>

<span data-ttu-id="6828a-166">即使已取消本地部署，管理员也可以管理之前从本地 Skype for Business Server 移动到云的用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-166">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="6828a-167">如果要更改用户的 sip 地址或用户的电话号码 (并且 sip 地址或电话号码在本地 Active Directory) 中已有值，则必须在本地 Active Directory 中这样做，让值 (s) 流向 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="6828a-167">If you want to make changes to a user’s sip address or to a user’s phone number (and the sip address or phone number already has a value in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="6828a-168">这不需要本地 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="6828a-168">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="6828a-169">相反，您可以直接在本地 Active Directory 中修改这些属性，使用 Active Directory 用户和计算机 MMC 管理单元 (如下) 所示，或者使用 PowerShell 修改这些属性。</span><span class="sxs-lookup"><span data-stu-id="6828a-169">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in (as shown below), or by using PowerShell.</span></span> <span data-ttu-id="6828a-170">如果使用的是 MMC 管理单元，请打开用户的属性页，单击"属性编辑器"选项卡，并查找要修改的适当属性：</span><span class="sxs-lookup"><span data-stu-id="6828a-170">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="6828a-171">若要修改用户的 sip 地址，请修改 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="6828a-171">To modify a user’s sip address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="6828a-172">请注意，如果 `ProxyAddresses` 属性包含 sip 地址，作为最佳做法，还应更新该值。</span><span class="sxs-lookup"><span data-stu-id="6828a-172">Note, if the `ProxyAddresses` attribute contains a sip address, also update that value as a best practice.</span></span> <span data-ttu-id="6828a-173">尽管已填充的 O365 将忽略 中的 sip 地址，但其他本地组件 `ProxyAddresses` `msRTCSIP-PrimaryUserAddress` 可能会使用。</span><span class="sxs-lookup"><span data-stu-id="6828a-173">Although the sip address in `ProxyAddresses` is ignored by O365 if `msRTCSIP-PrimaryUserAddress` is populated, it may be used by other on-premises components.</span></span>

- <span data-ttu-id="6828a-174">若要修改用户的电话号码，请 `msRTCSIP-Line` *修改（如果已具有值*）。</span><span class="sxs-lookup"><span data-stu-id="6828a-174">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
-  <span data-ttu-id="6828a-176">如果用户在移动之前最初没有本地值，可以使用 `msRTCSIP-Line` Skype for Business Online PowerShell 模块中 `onpremLineUri` [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) 中的 - 参数修改电话号码。</span><span class="sxs-lookup"><span data-stu-id="6828a-176">If the user did not originally have a value for `msRTCSIP-Line` on-premises before the move, you can modify the phone number using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

<span data-ttu-id="6828a-177">这些步骤对于禁用混合后创建的新用户来说不是必需的，可以直接在云中管理这些用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-177">These steps are not necessary for new users created after you disable hybrid, and those users can be managed directly in the cloud.</span></span> <span data-ttu-id="6828a-178">如果你习惯混合使用这些方法以及将 msRTCSIP 属性留在本地 Active Directory 中，则只需重新映像本地 Skype for Business 服务器。</span><span class="sxs-lookup"><span data-stu-id="6828a-178">If you are comfortable using the mix of these method as well as with leaving the msRTCSIP attributes in place in your on-premises Active Directory, you can simply re-image the on-premises Skype for Business servers.</span></span> <span data-ttu-id="6828a-179">但是，如果你希望清除所有 msRTCSIP 属性，并传统卸载 Skype for Business Server，请使用方法 2。</span><span class="sxs-lookup"><span data-stu-id="6828a-179">However, if you prefer to clear all msRTCSIP attributes and do a traditional uninstall of Skype for Business Server, then use Method 2.</span></span>


### <a name="method-2---clear-skype-for-business-attributes-for-all-on-premises-users-in-active-directory"></a><span data-ttu-id="6828a-180">方法 2 - 清除 Active Directory 中所有本地用户的 Skype for Business 属性</span><span class="sxs-lookup"><span data-stu-id="6828a-180">Method 2 - Clear Skype for Business Attributes for all on-premises users in Active Directory</span></span>

<span data-ttu-id="6828a-181">此选项需要进行额外的工作和正确的规划，因为需要重新预配之前从本地 Skype for Business Server 移动到云的用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-181">This option requires additional effort and proper planning because users that were previously moved from an on-premises Skype for Business Server to the cloud are required to be re-provisioned.</span></span> <span data-ttu-id="6828a-182">可以将这些用户分为两个不同的类别：没有电话系统的用户和具有电话系统的用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-182">These users can be categorized into two different categories: users without Phone System and users with Phone System.</span></span> <span data-ttu-id="6828a-183">在将电话号码从本地 Active Directory 中管理到云过程中，使用电话系统的用户将遇到电话服务暂时丢失的问题。</span><span class="sxs-lookup"><span data-stu-id="6828a-183">Users with Phone System will experience a temporary loss of phone service as part of transitioning the phone number from being managed in on-premises Active Directory to the cloud.</span></span> <span data-ttu-id="6828a-184">**建议先执行涉及少数电话系统的用户的试点，然后开始批量用户操作。**</span><span class="sxs-lookup"><span data-stu-id="6828a-184">**It's recommended to perform a pilot involving a small number of users with Phone System prior to start bulk user operations.**</span></span> <span data-ttu-id="6828a-185">对于大型部署，可以在不同的时间窗口中以较小的组处理用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-185">For large deployments users can be processed in smaller groups in different time windows.</span></span> 

> [!NOTE]
> <span data-ttu-id="6828a-186">此过程对于具有匹配的 sip 地址和 UserPrincipalName 的用户来说最简单。</span><span class="sxs-lookup"><span data-stu-id="6828a-186">The process is simplest for users who have a matching sip address and UserPrincipalName.</span></span> <span data-ttu-id="6828a-187">对于用户具有跨这两个属性的不匹配值的组织，必须格外小心，如下所述，以便顺利过渡。</span><span class="sxs-lookup"><span data-stu-id="6828a-187">For organizations that have users with non-matching values across these two attributes, extra care must be taken as noted below for a smooth transition.</span></span> 


1. <span data-ttu-id="6828a-188">确认以下本地 Skype for Business PowerShell cmdlet 返回空结果。</span><span class="sxs-lookup"><span data-stu-id="6828a-188">Confirm the following on-premises Skype for Business PowerShell cmdlet returns an empty result.</span></span> <span data-ttu-id="6828a-189">空结果意味着没有用户位于本地，并且已移动到 Office 365 或已禁用：</span><span class="sxs-lookup"><span data-stu-id="6828a-189">An empty result means no users are homed on-premises and have either been moved to Office 365 or have been disabled:</span></span>

   ```PowerShell
   Get-CsUser -Filter { HostingProvider -eq "SRV:"} | Select-Object Identity, SipAddress, UserPrincipalName, RegistrarPool
   ```

2. <span data-ttu-id="6828a-190">通过执行以下本地 Skype for Business Server PowerShell cmdlet 导出用户数据， (LineUri) 、UserPrincipalName 和相关信息来记录用户的当前电话号码：</span><span class="sxs-lookup"><span data-stu-id="6828a-190">Record users' current phones number (LineUri), UserPrincipalName and related info, by executing the following on-premises Skype for Business Server PowerShell cmdlet to export user data:</span></span>

   ```PowerShell
   Get-CsUser | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path  "c:\backup\SfbUserSettings.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="6828a-191">在继续打开SfbUserSettings.csv文件并确认已成功导出所有用户数据。</span><span class="sxs-lookup"><span data-stu-id="6828a-191">Before proceeding open SfbUserSettings.csv file and confirm all user data has been successfully exported.</span></span> <span data-ttu-id="6828a-192">建议保留此文件的副本。</span><span class="sxs-lookup"><span data-stu-id="6828a-192">It's recommended to keep a copy of this file.</span></span>  <span data-ttu-id="6828a-193">请勿在以下步骤中使用此文件处理用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-193">Do not use this file in the following steps for processing users.</span></span> 

3. <span data-ttu-id="6828a-194">创建一个包含一组用户的文件，以便执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="6828a-194">Create a file with a group of users to be used in the following steps.</span></span> <span data-ttu-id="6828a-195">成功完成第一组用户后，继续处理下一组用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-195">After the first group of users has completed successfully, proceed with the next group of users.</span></span> <span data-ttu-id="6828a-196">在下面的示例中，用户组按字母顺序进行选择，但您可以基于与处理用户匹配的条件筛选用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-196">In the example below, the groups of users are selected alphabetically, but you may filter on users based on criteria that matches how you would like to process the users.</span></span>

   ```PowerShell
   Get-CsUser | where userprincipalname -like "abc*" | Select-Object SipAddress, UserPrincipalName, SamAccountName, RegistrarPool, HostingProvider, EnabledForFederation, EnabledForInternetAccess, LineUri, EnterpriseVoiceEnabled, HostedVoiceMail | Sort SipAddress | Export-Csv -Path "c:\data\SfbUsers.csv"
   ```

   > [!Important] 
   > <span data-ttu-id="6828a-197">在继续打开SfbUsers.csv文件并确认已成功导出用户数据之前。</span><span class="sxs-lookup"><span data-stu-id="6828a-197">Before proceeding open SfbUsers.csv file and confirm user data has been successfully exported.</span></span> <span data-ttu-id="6828a-198">在稍后的步骤中，将需要此 (的 LineUri) 、UserPrincipalName、SamAccountName 和 SipAddress。</span><span class="sxs-lookup"><span data-stu-id="6828a-198">You will need the LineUri (phone number), UserPrincipalName, SamAccountName, and SipAddress from this file in a later step.</span></span>

4. <span data-ttu-id="6828a-199">从 active Directory 中删除与 Skype for Business Server 相关的属性信息，以用于准备更新的一组用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-199">Delete the attribute information related to Skype for Business Server from active Directory for the set of users you are ready to update.</span></span>  <span data-ttu-id="6828a-200">此过程有 2 个步骤，如下所示。</span><span class="sxs-lookup"><span data-stu-id="6828a-200">There are 2 steps to this process, as shown below.</span></span>

   > [!Important] 
   > <span data-ttu-id="6828a-201">运行此步骤后的下一个 AAD 同步周期后，具有电话系统且之前从本地 Skype for Business Server 移动到云的用户将失去拨打和接听呼叫的能力，直到步骤 8 成功完成，且在步骤 9 中确认。</span><span class="sxs-lookup"><span data-stu-id="6828a-201">After the next AAD Sync cycle after running this step, users with Phone System who were previously moved from an on-premises Skype for Business Server to the cloud will lose the ability to make and receive calls until step 8 is successfully completed and confirmed in step 9.</span></span> <span data-ttu-id="6828a-202">此外，请确保已按步骤 2 保存用户的电话号码和相关信息，因为此步骤需要该信息。</span><span class="sxs-lookup"><span data-stu-id="6828a-202">In addition, make sure you have saved user's phone numbers and related information as per step 2, since that information is required for that step.</span></span>

 
   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Disable-CsUser -Identity $user.SipAddress}
   ```

   <span data-ttu-id="6828a-203">接下来，对于同一组用户，使用本地 Active Directory PowerShell 清除 msRTCSIP-DeploymentLocator 的值：</span><span class="sxs-lookup"><span data-stu-id="6828a-203">Next, for the same set of users, clear the value of msRTCSIP-DeploymentLocator using on-premises Active Directory PowerShell:</span></span>

   ```PowerShell
   $sfbusers=import-csv "c:\data\SfbUsers.csv"
   foreach($user in $sfbusers){
   Set-ADUser -Identity $user.SamAccountName -Clear msRTCSIP-DeploymentLocator}
   ```

5. <span data-ttu-id="6828a-204">运行以下本地 Skype for Business PowerShell cmdlet，将 sip 地址值添加回本地 Active Directory 代理Addresses。</span><span class="sxs-lookup"><span data-stu-id="6828a-204">Run the following on-premise Skype for Business PowerShell cmdlet to add sip address value back to the on-premises Active Directory proxyAddresses.</span></span> <span data-ttu-id="6828a-205">这将防止依赖此属性的互操作性问题。</span><span class="sxs-lookup"><span data-stu-id="6828a-205">This will prevent interoperability issues that rely on this attribute.</span></span> 

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

6. <span data-ttu-id="6828a-206">运行 Azure AD 同步</span><span class="sxs-lookup"><span data-stu-id="6828a-206">Run Azure AD Sync</span></span>

   ```PowerShell
   Start-ADSyncSyncCycle -PolicyType Delta
   ```

7. <span data-ttu-id="6828a-207">等待用户预配完成。</span><span class="sxs-lookup"><span data-stu-id="6828a-207">Wait for user provisioning to complete.</span></span> <span data-ttu-id="6828a-208">可以通过运行以下 Skype for Business Online PowerShell 命令来监视用户预配进度。</span><span class="sxs-lookup"><span data-stu-id="6828a-208">You can monitor user provisioning progress by running the following Skype for Business Online PowerShell command.</span></span> <span data-ttu-id="6828a-209">以下 Skype for Business Online PowerShell 命令在进程完成后将返回空结果。</span><span class="sxs-lookup"><span data-stu-id="6828a-209">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

   ```PowerShell
   Get-CsOnlineUser -Filter {Enabled -eq $True -and (MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
   ```

8. <span data-ttu-id="6828a-210">执行以下 Skype for Business Online PowerShell 命令，为用户分配电话号码并启用电话系统：</span><span class="sxs-lookup"><span data-stu-id="6828a-210">Execute the following Skype for Business Online PowerShell command to assign phone numbers and enable users for Phone System:</span></span>
     
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
   >  <span data-ttu-id="6828a-211">如果 Skype 客户端或第三 (电话上仍有 Skype for Business) ，则还需要将 -HostedVoiceMail 设置为 $true。</span><span class="sxs-lookup"><span data-stu-id="6828a-211">If you still have Skype for Business endpoints (either Skype clients or 3rd party phones), you will also want to set -HostedVoiceMail to $true.</span></span> <span data-ttu-id="6828a-212">如果你的组织仅对启用语音的用户使用 Teams 终结点，则此设置不适用于你的用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-212">If your organization is only using Teams endpoints for voice enabled users, this setting is not applicable to your users.</span></span> 

9. <span data-ttu-id="6828a-213">确认具有电话系统功能的用户已正确设置。</span><span class="sxs-lookup"><span data-stu-id="6828a-213">Confirm users with Phone System functionality have been provisioned correctly.</span></span> <span data-ttu-id="6828a-214">以下 Skype for Business Online PowerShell 命令在进程完成后将返回空结果。</span><span class="sxs-lookup"><span data-stu-id="6828a-214">The following Skype for Business Online PowerShell command returns an empty result as soon process is completed.</span></span>

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

10. <span data-ttu-id="6828a-215">重复步骤 3 至 9，直到处理所有用户。</span><span class="sxs-lookup"><span data-stu-id="6828a-215">Repeat steps 3 through 9 until all users are processed.</span></span>

11. <span data-ttu-id="6828a-216">通过运行以下两个 PowerShell 命令，确认所有用户都已成功处理。</span><span class="sxs-lookup"><span data-stu-id="6828a-216">Confirm that all users have been processed successfully by running the following two PowerShell commands.</span></span>

    <span data-ttu-id="6828a-217">本地 Skype for Business Server 本地 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="6828a-217">On-premises Skype for Business Server on-premises PowerShell command:</span></span>

    ```PowerShell
    Get-CsUser | Select-Object SipAddress, UserPrincipalName
    ``` 
    <span data-ttu-id="6828a-218">Skype for Business Online PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="6828a-218">Skype for Business Online PowerShell command:</span></span>

    ```PowerShell
    Get-CsOnlineUser -Filter {Enabled -eq $True -and (OnPremHostingProvider -ne $null -or MCOValidationError -ne $null -or ProvisioningStamp -ne $null -or SubProvisioningStamp -ne $null)} | fl SipAddress, InterpretedUserType, OnPremHostingProvider, MCOValidationError, *ProvisioningStamp
    ``` 


## <a name="see-also"></a><span data-ttu-id="6828a-219">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6828a-219">See also</span></span>

[<span data-ttu-id="6828a-220">Teams 和 Skype for Business 云合并</span><span class="sxs-lookup"><span data-stu-id="6828a-220">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)