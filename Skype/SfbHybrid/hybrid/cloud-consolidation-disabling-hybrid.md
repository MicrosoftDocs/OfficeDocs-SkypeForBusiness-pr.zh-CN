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
description: 此附录包括将混合禁用作为团队和 Skype for Business 的云整合的一部分的详细步骤。
ms.openlocfilehash: 93aad1ea230d9edbb81673a3ddabc7088b06d422
ms.sourcegitcommit: a28232f16bfefe6414d1f5a54d5f8c8665eb0e23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277259"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="9923a-103">禁用混合以完成云迁移</span><span class="sxs-lookup"><span data-stu-id="9923a-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="9923a-104">将所有用户从本地移动到云后，可取消本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="9923a-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="9923a-105">除删除任何硬件之外，关键步骤是在逻辑上将该本地部署与 Microsoft 365 或 Office 365 分开，方法是禁用混合。</span><span class="sxs-lookup"><span data-stu-id="9923a-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Microsoft 365 or Office 365 by disabling hybrid.</span></span> <span data-ttu-id="9923a-106">禁用混合的步骤包括三个步骤：</span><span class="sxs-lookup"><span data-stu-id="9923a-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="9923a-107">更新 DNS 记录以指向 Microsoft 365 或 Office 365。</span><span class="sxs-lookup"><span data-stu-id="9923a-107">Update DNS records to point to Microsoft 365 or Office 365.</span></span>

2. <span data-ttu-id="9923a-108">在 Microsoft 365 或 Office 365 组织中禁用拆分域。</span><span class="sxs-lookup"><span data-stu-id="9923a-108">Disable split domain in the Microsoft 365 or Office 365 organization.</span></span>

3. <span data-ttu-id="9923a-109">禁用内部部署中与 Microsoft 365 或 Office 365 通信的功能。</span><span class="sxs-lookup"><span data-stu-id="9923a-109">Disable the ability in on-premises to communicate with Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="9923a-110">这些步骤应作为一个单元一起完成。</span><span class="sxs-lookup"><span data-stu-id="9923a-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="9923a-111">下面提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="9923a-111">Details are provided below.</span></span> <span data-ttu-id="9923a-112">此外，在本地部署断开连接后，将提供准则来管理迁移用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="9923a-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

<span data-ttu-id="9923a-113">完成这些步骤后，将不再使用本地 Skype for Business 服务器，并且可以重新映像这些服务器。</span><span class="sxs-lookup"><span data-stu-id="9923a-113">Once these steps are complete, the on-premises Skype for Business servers are no longer used, and these servers can be re-imaged.</span></span>

> [!Important] 
><span data-ttu-id="9923a-114">应继续让 Active Directory 同步中的 msRTCSIP 属性通过 Azure AD 连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9923a-114">You should continue to let the msRTCSIP attributes in Active Directory sync via Azure AD Connect into Azure AD.</span></span>  <span data-ttu-id="9923a-115">请勿清除这些属性中的任何一个，除非由支持定向。</span><span class="sxs-lookup"><span data-stu-id="9923a-115">Do not clear any of these attributes unless directed to by Support.</span></span>  <span data-ttu-id="9923a-116">请勿在本地环境中运行 Disable-Get-csuser。</span><span class="sxs-lookup"><span data-stu-id="9923a-116">Do not run Disable-CsUser in the on-premises environment.</span></span> <span data-ttu-id="9923a-117">如果需要修改用户的 SIP 地址，请在本地 Active Directory 中执行此操作，并通过 Azure AD Connect 将此更改同步到 Azure AD，如下所述。</span><span class="sxs-lookup"><span data-stu-id="9923a-117">If you need to modify a user’s SIP address, do this in your on-premises Active Directory and let this change sync into Azure AD via Azure AD Connect as described below.</span></span> <span data-ttu-id="9923a-118">同样，如果需要更改电话号码，并且用户已在本地定义了用户的 LineURI，则应在本地 Active Directory 中进行修改。</span><span class="sxs-lookup"><span data-stu-id="9923a-118">Similarly, if you need to change a telephone number and the user’s LineURI is already defined on-premises, you should modify this in the on-premises Active Directory.</span></span>
><span data-ttu-id="9923a-119">从本地迁移后清除本地 msRTCSIP 属性可能会导致用户的服务丢失！</span><span class="sxs-lookup"><span data-stu-id="9923a-119">Clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span>


1.  <span data-ttu-id="9923a-120">*更新 DNS 以指向 Microsoft 365 或 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="9923a-120">*Update DNS to point to Microsoft 365 or  Office 365.*</span></span>
<span data-ttu-id="9923a-121">组织的内部部署组织的外部 DNS 需要更新，以便 Skype for Business 记录指向 Microsoft 365 或 Office 365 而不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="9923a-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Microsoft 365 or Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="9923a-122">具体来说：</span><span class="sxs-lookup"><span data-stu-id="9923a-122">Specifically:</span></span>

    |<span data-ttu-id="9923a-123">记录类型</span><span class="sxs-lookup"><span data-stu-id="9923a-123">Record type</span></span>|<span data-ttu-id="9923a-124">名称</span><span class="sxs-lookup"><span data-stu-id="9923a-124">Name</span></span>|<span data-ttu-id="9923a-125">TTL</span><span class="sxs-lookup"><span data-stu-id="9923a-125">TTL</span></span>|<span data-ttu-id="9923a-126">值</span><span class="sxs-lookup"><span data-stu-id="9923a-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="9923a-127">SRV</span><span class="sxs-lookup"><span data-stu-id="9923a-127">SRV</span></span>|<span data-ttu-id="9923a-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="9923a-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="9923a-129">3600</span><span class="sxs-lookup"><span data-stu-id="9923a-129">3600</span></span>|<span data-ttu-id="9923a-130">100 1 5061 sipfed.online.lync.com>。 <span>com</span><span class="sxs-lookup"><span data-stu-id="9923a-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="9923a-131">SRV</span><span class="sxs-lookup"><span data-stu-id="9923a-131">SRV</span></span>|<span data-ttu-id="9923a-132">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="9923a-132">_sip._tls</span></span>|<span data-ttu-id="9923a-133">3600</span><span class="sxs-lookup"><span data-stu-id="9923a-133">3600</span></span>|<span data-ttu-id="9923a-134">100 1 443 sipdir.online.lync.com>。 <span>com</span><span class="sxs-lookup"><span data-stu-id="9923a-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="9923a-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="9923a-135">CNAME</span></span>| <span data-ttu-id="9923a-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="9923a-136">lyncdiscover</span></span>|   <span data-ttu-id="9923a-137">3600</span><span class="sxs-lookup"><span data-stu-id="9923a-137">3600</span></span>|   <span data-ttu-id="9923a-138">webdir。 <span>com</span><span class="sxs-lookup"><span data-stu-id="9923a-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="9923a-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="9923a-139">CNAME</span></span>| <span data-ttu-id="9923a-140">sip</span><span class="sxs-lookup"><span data-stu-id="9923a-140">sip</span></span>|    <span data-ttu-id="9923a-141">3600</span><span class="sxs-lookup"><span data-stu-id="9923a-141">3600</span></span>|   <span data-ttu-id="9923a-142">sipdir.online.lync.com>。 <span>com</span><span class="sxs-lookup"><span data-stu-id="9923a-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="9923a-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="9923a-143">CNAME</span></span>| <span data-ttu-id="9923a-144">法规</span><span class="sxs-lookup"><span data-stu-id="9923a-144">meet</span></span>|   <span data-ttu-id="9923a-145">3600</span><span class="sxs-lookup"><span data-stu-id="9923a-145">3600</span></span>|   <span data-ttu-id="9923a-146">webdir。 <span>com</span><span class="sxs-lookup"><span data-stu-id="9923a-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="9923a-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="9923a-147">CNAME</span></span>| <span data-ttu-id="9923a-148">入</span><span class="sxs-lookup"><span data-stu-id="9923a-148">dialin</span></span>  |<span data-ttu-id="9923a-149">3600</span><span class="sxs-lookup"><span data-stu-id="9923a-149">3600</span></span>|  <span data-ttu-id="9923a-150">webdir。 <span>com</span><span class="sxs-lookup"><span data-stu-id="9923a-150">webdir.online.lync.<span>com</span></span>|

    <span data-ttu-id="9923a-151">此外，如果存在) 可以删除 (，则用于满足或拨入的 CNAME 记录。</span><span class="sxs-lookup"><span data-stu-id="9923a-151">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span> <span data-ttu-id="9923a-152">最后，应删除内部网络中 Skype for Business 的任何 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="9923a-152">Finally, any DNS records for Skype for Business in your internal network should be removed.</span></span>

    > [!Note] 
    > <span data-ttu-id="9923a-153">在极少数情况下，将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作，直到其他组织更新其联合配置：</span><span class="sxs-lookup"><span data-stu-id="9923a-153">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="9923a-154">任何使用旧直接联盟模型的联合组织 (也称为 "允许的伙伴服务器) " 将需要更新其组织的允许的域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="9923a-154">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="9923a-155">此旧版联合模型不基于 DNS SRV 记录，因此一旦您的组织移动到云，这样的配置就会过期。</span><span class="sxs-lookup"><span data-stu-id="9923a-155">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="9923a-156">没有已启用 sipfed.online.lync.com> <span> 的托管提供程序的任何联合组织。com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="9923a-156">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="9923a-157">仅当联合组织完全在本地，且从未与任何混合或联机租户联合时，这种情况才可行。</span><span class="sxs-lookup"><span data-stu-id="9923a-157">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="9923a-158">在这种情况下，与这些组织的联盟在启用其承载提供程序之前将不起作用。</span><span class="sxs-lookup"><span data-stu-id="9923a-158">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="9923a-159">如果您怀疑任何联盟伙伴可能正在使用直接联盟，或者未与任何 online 或混合组织联合，我们建议您在准备完成到云的迁移时向其发送有关这方面的通信。</span><span class="sxs-lookup"><span data-stu-id="9923a-159">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>


2.  <span data-ttu-id="9923a-160">*在 Microsoft 365 或 Office 365 组织中禁用共享 SIP 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="9923a-160">*Disable shared SIP address space in Microsoft 365 or Office 365 organization.*</span></span>
<span data-ttu-id="9923a-161">下面的命令需要从 Skype for business Online PowerShell 窗口中执行。</span><span class="sxs-lookup"><span data-stu-id="9923a-161">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="9923a-162">*在本地中禁用与 Microsoft 365 或 Office 365 通信的功能。*</span><span class="sxs-lookup"><span data-stu-id="9923a-162">*Disable ability in on-premises to communicate with Microsoft 365 or Office 365.*</span></span>  
<span data-ttu-id="9923a-163">需要从内部部署 PowerShell 窗口中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="9923a-163">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="9923a-164">管理从本地迁移的用户的 sip 地址和电话号码</span><span class="sxs-lookup"><span data-stu-id="9923a-164">Manage sip addresses and phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="9923a-165">管理员可以管理以前从本地 Skype for Business 服务器移动到云的用户，即使在本地部署已停止后也是如此。</span><span class="sxs-lookup"><span data-stu-id="9923a-165">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="9923a-166">如果要对用户的 SIP 地址或用户的线路 URI 进行更改 (并且 SIP 地址或线路 URI 已在内部部署 Active Directory) 中定义，则必须在本地 Active Directory 中执行此操作，并允许值 (s) 流到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="9923a-166">If you want to make changes to a user’s SIP address or to a user’s Line URI (and the SIP address or Line URI is already defined in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="9923a-167">这不需要本地 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="9923a-167">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="9923a-168">相反，您可以使用 Active Directory 用户和计算机 MMC 管理单元或使用 PowerShell，直接在内部部署 Active Directory 中修改这些属性。</span><span class="sxs-lookup"><span data-stu-id="9923a-168">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="9923a-169">如果使用的是 MMC 管理单元，请打开用户的 "属性" 页，单击 "属性编辑器" 选项卡，然后找到要修改的相应属性：</span><span class="sxs-lookup"><span data-stu-id="9923a-169">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="9923a-170">若要修改用户的 SIP 地址，请修改 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="9923a-170">To modify a user’s SIP address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="9923a-171">此外，如果该 `ProxyAddresses` 属性包含 sip 值，请更新该 sip 值以匹配的新值 `msRTCSIP-PrimaryUserAddress` 。</span><span class="sxs-lookup"><span data-stu-id="9923a-171">In addition, if the `ProxyAddresses` attribute contains a SIP value, update that SIP value to match the new value of `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="9923a-172">如果不包含 SIP 值，则可以将其保留为空。</span><span class="sxs-lookup"><span data-stu-id="9923a-172">If it does not contain a SIP value, you can leave it blank.</span></span>

- <span data-ttu-id="9923a-173">若要修改用户的电话号码，请修改（ `msRTCSIP-Line` *如果它已有值*）。</span><span class="sxs-lookup"><span data-stu-id="9923a-173">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
<span data-ttu-id="9923a-175">如果用户最初没有 `LineURI` 在移动前的本地值，则可以使用 `onpremLineUri` Skype For Business Online PowerShell 模块中的 [get-csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) 中的-参数修改 LineURI。</span><span class="sxs-lookup"><span data-stu-id="9923a-175">If the user did not originally have a value for `LineURI` on-premises before the move, you can modify the LineURI using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>


## <a name="see-also"></a><span data-ttu-id="9923a-176">另请参阅</span><span class="sxs-lookup"><span data-stu-id="9923a-176">See also</span></span>

[<span data-ttu-id="9923a-177">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="9923a-177">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
