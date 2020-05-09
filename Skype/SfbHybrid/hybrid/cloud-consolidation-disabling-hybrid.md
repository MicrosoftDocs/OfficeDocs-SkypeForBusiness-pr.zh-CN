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
ms.openlocfilehash: c6d042095298f6cab8d9474a521b9362ece13e0d
ms.sourcegitcommit: 0dda90122769385529f78f70b0467848da97e5ec
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2020
ms.locfileid: "44173968"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="09e6c-103">禁用混合以完成云迁移</span><span class="sxs-lookup"><span data-stu-id="09e6c-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="09e6c-104">将所有用户从本地移动到云后，可取消本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="09e6c-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="09e6c-105">除了删除任何硬件之外，关键步骤是通过禁用混合，从逻辑上将本地部署与 Office 365 分离开来。</span><span class="sxs-lookup"><span data-stu-id="09e6c-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="09e6c-106">禁用混合的步骤包括三个步骤：</span><span class="sxs-lookup"><span data-stu-id="09e6c-106">Disabling hybrid consists of 3 steps:</span></span>

- <span data-ttu-id="09e6c-107">将 DNS 记录更新为指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="09e6c-107">Update DNS records to point to Office 365.</span></span>
- <span data-ttu-id="09e6c-108">在 Office 365 组织中禁用拆分域。</span><span class="sxs-lookup"><span data-stu-id="09e6c-108">Disable split domain in the Office 365 organization.</span></span>
- <span data-ttu-id="09e6c-109">禁用本地与 Office 365 通信的功能。</span><span class="sxs-lookup"><span data-stu-id="09e6c-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="09e6c-110">这些步骤应作为一个单元一起完成。</span><span class="sxs-lookup"><span data-stu-id="09e6c-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="09e6c-111">下面提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="09e6c-111">Details are provided below.</span></span> <span data-ttu-id="09e6c-112">此外，在本地部署断开连接后，将提供准则来管理迁移用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="09e6c-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Important] 
><span data-ttu-id="09e6c-113">应继续让 Active Directory 同步中的 msRTCSIP 属性通过 Azure AD 连接到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="09e6c-113">You should continue to let the msRTCSIP attributes in Active Directory sync via Azure AD Connect into Azure AD.</span></span>  <span data-ttu-id="09e6c-114">请勿清除这些属性中的任何一个，除非由支持定向。</span><span class="sxs-lookup"><span data-stu-id="09e6c-114">Do not clear any of these attributes unless directed to by Support.</span></span>  <span data-ttu-id="09e6c-115">请勿在本地环境中运行 Disable-Get-csuser。</span><span class="sxs-lookup"><span data-stu-id="09e6c-115">Do not run Disable-CsUser in the on-premises environment.</span></span> <span data-ttu-id="09e6c-116">如果需要修改用户的 SIP 地址，请在本地 Active Directory 中执行此操作，并通过 Azure AD Connect 将此更改同步到 Azure AD，如下所述。</span><span class="sxs-lookup"><span data-stu-id="09e6c-116">If you need to modify a user’s SIP address, do this in your on-premises Active Directory and let this change sync into Azure AD via Azure AD Connect as described below.</span></span> <span data-ttu-id="09e6c-117">同样，如果需要更改电话号码，并且用户已在本地定义了用户的 LineURI，则应在本地 Active Directory 中进行修改。</span><span class="sxs-lookup"><span data-stu-id="09e6c-117">Similarly, if you need to change a telephone number and the user’s LineURI is already defined on-premises, you should modify this in the on-premises Active Directory.</span></span>
><span data-ttu-id="09e6c-118">从本地迁移后清除本地 msRTCSIP 属性可能会导致用户的服务丢失！</span><span class="sxs-lookup"><span data-stu-id="09e6c-118">Clearing the on-premises msRTCSIP attributes after you have migrated from on-premises could result in loss of service for users!</span></span>



1.  <span data-ttu-id="09e6c-119">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="09e6c-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="09e6c-120">组织现有的内部部署组织的外部 DNS 记录需要更新，以便 Skype for Business 记录指向 Office 365 而不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="09e6c-120">The organization’s existing external DNS records for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="09e6c-121">具体来说：</span><span class="sxs-lookup"><span data-stu-id="09e6c-121">Specifically:</span></span>

    |<span data-ttu-id="09e6c-122">记录类型</span><span class="sxs-lookup"><span data-stu-id="09e6c-122">Record type</span></span>|<span data-ttu-id="09e6c-123">名称</span><span class="sxs-lookup"><span data-stu-id="09e6c-123">Name</span></span>|<span data-ttu-id="09e6c-124">TTL</span><span class="sxs-lookup"><span data-stu-id="09e6c-124">TTL</span></span>|<span data-ttu-id="09e6c-125">值</span><span class="sxs-lookup"><span data-stu-id="09e6c-125">Value</span></span>|<span data-ttu-id="09e6c-126">用途</span><span class="sxs-lookup"><span data-stu-id="09e6c-126">Purpose</span></span>|
    |---|---|---|---|---|
    |<span data-ttu-id="09e6c-127">SRV</span><span class="sxs-lookup"><span data-stu-id="09e6c-127">SRV</span></span>|<span data-ttu-id="09e6c-128">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="09e6c-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="09e6c-129">3600</span><span class="sxs-lookup"><span data-stu-id="09e6c-129">3600</span></span>|<span data-ttu-id="09e6c-130">100 1 5061 sipfed.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="09e6c-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|<span data-ttu-id="09e6c-131">启用联合</span><span class="sxs-lookup"><span data-stu-id="09e6c-131">Enables federation</span></span>|
    |<span data-ttu-id="09e6c-132">SRV</span><span class="sxs-lookup"><span data-stu-id="09e6c-132">SRV</span></span>|<span data-ttu-id="09e6c-133">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="09e6c-133">_sip._tls</span></span>|<span data-ttu-id="09e6c-134">3600</span><span class="sxs-lookup"><span data-stu-id="09e6c-134">3600</span></span>|<span data-ttu-id="09e6c-135">100 1 443 sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="09e6c-135">100 1 443 sipdir.online.lync.<span>com</span></span>|<span data-ttu-id="09e6c-136">对于 Skype for Business 用户是必需的</span><span class="sxs-lookup"><span data-stu-id="09e6c-136">Required for Skype for Business users</span></span>|
    |<span data-ttu-id="09e6c-137">CNAME</span><span class="sxs-lookup"><span data-stu-id="09e6c-137">CNAME</span></span>| <span data-ttu-id="09e6c-138">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="09e6c-138">lyncdiscover</span></span>|   <span data-ttu-id="09e6c-139">3600</span><span class="sxs-lookup"><span data-stu-id="09e6c-139">3600</span></span>|   <span data-ttu-id="09e6c-140">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="09e6c-140">webdir.online.lync.<span>com</span></span>|<span data-ttu-id="09e6c-141">对于 Skype for Business 用户是必需的</span><span class="sxs-lookup"><span data-stu-id="09e6c-141">Required for Skype for Business users</span></span>|
    |<span data-ttu-id="09e6c-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="09e6c-142">CNAME</span></span>| <span data-ttu-id="09e6c-143">sip</span><span class="sxs-lookup"><span data-stu-id="09e6c-143">sip</span></span>|    <span data-ttu-id="09e6c-144">3600</span><span class="sxs-lookup"><span data-stu-id="09e6c-144">3600</span></span>|   <span data-ttu-id="09e6c-145">sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="09e6c-145">sipdir.online.lync.<span>com</span></span>|<span data-ttu-id="09e6c-146">仅对较旧的旧 SIP 电话是必需的</span><span class="sxs-lookup"><span data-stu-id="09e6c-146">Required only for older legacy SIP phones</span></span>|

    <span data-ttu-id="09e6c-147">此外，可以删除符合或拨入的 CNAME 记录（如果存在）。</span><span class="sxs-lookup"><span data-stu-id="09e6c-147">In addition, CNAME records for meet or dialin (if present) can be deleted.</span></span>

    > [!Note] 
    > <span data-ttu-id="09e6c-148">在极少数情况下，将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作，直到其他组织更新其联合配置：</span><span class="sxs-lookup"><span data-stu-id="09e6c-148">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
    >
    > - <span data-ttu-id="09e6c-149">任何使用旧直接联盟模型（也称为 "允许的伙伴服务器"）的联合组织都需要更新其组织的允许的域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="09e6c-149">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="09e6c-150">此旧版联合模型不基于 DNS SRV 记录，因此一旦您的组织移动到云，这样的配置就会过期。</span><span class="sxs-lookup"><span data-stu-id="09e6c-150">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
    > 
    > - <span data-ttu-id="09e6c-151">没有已启用 sipfed.online.lync.com> 的托管提供程序的任何联合组织。<span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="09e6c-151">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="09e6c-152">仅当联合组织完全在本地，且从未与任何混合或联机租户联合时，这种情况才可行。</span><span class="sxs-lookup"><span data-stu-id="09e6c-152">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="09e6c-153">在这种情况下，与这些组织的联盟在启用其承载提供程序之前将不起作用。</span><span class="sxs-lookup"><span data-stu-id="09e6c-153">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
    >
    > <span data-ttu-id="09e6c-154">如果您怀疑任何联盟伙伴可能正在使用直接联盟，或者未与任何 online 或混合组织联合，我们建议您在准备完成到云的迁移时向其发送有关这方面的通信。</span><span class="sxs-lookup"><span data-stu-id="09e6c-154">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

2.  <span data-ttu-id="09e6c-155">*在 Office 365 组织中禁用共享 SIP 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="09e6c-155">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="09e6c-156">下面的命令需要从 Skype for business Online PowerShell 窗口中执行。</span><span class="sxs-lookup"><span data-stu-id="09e6c-156">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="09e6c-157">*禁用本地与 Office 365 通信的功能。*</span><span class="sxs-lookup"><span data-stu-id="09e6c-157">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="09e6c-158">需要从内部部署 PowerShell 窗口中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="09e6c-158">The command below needs to be done from an on-premises PowerShell window:</span></span>

    ```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
    ```

### <a name="manage-sip-addresses-and-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="09e6c-159">管理从本地迁移的用户的 sip 地址和电话号码</span><span class="sxs-lookup"><span data-stu-id="09e6c-159">Manage sip addresses and phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="09e6c-160">管理员可以管理以前从本地 Skype for Business 服务器移动到云的用户，即使在本地部署已停止后也是如此。</span><span class="sxs-lookup"><span data-stu-id="09e6c-160">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="09e6c-161">如果要更改用户的 SIP 地址或用户的线路 URI （且 SIP 地址或线路 URI 已在内部部署 Active Directory 中定义），则必须在本地 Active Directory 中执行此操作，并让值（s）流入 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="09e6c-161">If you want to make changes to a user’s SIP address or to a user’s Line URI (and the SIP address or Line URI is already defined in the on-premises Active Directory), you must do this in the on-premises Active Directory and let the value(s) flow up to Azure AD.</span></span> <span data-ttu-id="09e6c-162">这不需要本地 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="09e6c-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="09e6c-163">相反，您可以使用 Active Directory 用户和计算机 MMC 管理单元或使用 PowerShell，直接在内部部署 Active Directory 中修改这些属性。</span><span class="sxs-lookup"><span data-stu-id="09e6c-163">Rather, you can modify these attributes directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="09e6c-164">如果使用的是 MMC 管理单元，请打开用户的 "属性" 页，单击 "属性编辑器" 选项卡，然后找到要修改的相应属性：</span><span class="sxs-lookup"><span data-stu-id="09e6c-164">If you are using the MMC snap-in, open the properties page of the user, click Attribute Editor tab, and find the appropriate attributes to modify:</span></span>

- <span data-ttu-id="09e6c-165">若要修改用户的 SIP 地址，请修改`msRTCSIP-PrimaryUserAddress`。</span><span class="sxs-lookup"><span data-stu-id="09e6c-165">To modify a user’s SIP address, modify the `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="09e6c-166">此外，如果该`ProxyAddresses`属性包含 sip 值，请更新该 sip 值以匹配的新值。 `msRTCSIP-PrimaryUserAddress`</span><span class="sxs-lookup"><span data-stu-id="09e6c-166">In addition, if the `ProxyAddresses` attribute contains a SIP value, update that SIP value to match the new value of `msRTCSIP-PrimaryUserAddress`.</span></span> <span data-ttu-id="09e6c-167">如果不包含 SIP 值，则可以将其保留为空。</span><span class="sxs-lookup"><span data-stu-id="09e6c-167">If it does not contain a SIP value, you can leave it blank.</span></span>

- <span data-ttu-id="09e6c-168">若要修改用户的电话号码，请`msRTCSIP-Line`修改（*如果它已有值*）。</span><span class="sxs-lookup"><span data-stu-id="09e6c-168">To modify a user’s phone number, modify `msRTCSIP-Line` *if it already has a value*.</span></span>

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)
  
<span data-ttu-id="09e6c-170">如果用户最初没有`LineURI`在移动前的本地值，则可以使用 Skype For Business Online PowerShell 模块中的[get-csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)中`onpremLineUri`的-参数修改 LineURI。</span><span class="sxs-lookup"><span data-stu-id="09e6c-170">If the user did not originally have a value for `LineURI` on-premises before the move, you can modify the LineURI using the -`onpremLineUri` parameter in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>


## <a name="see-also"></a><span data-ttu-id="09e6c-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09e6c-171">See also</span></span>

[<span data-ttu-id="09e6c-172">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="09e6c-172">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
