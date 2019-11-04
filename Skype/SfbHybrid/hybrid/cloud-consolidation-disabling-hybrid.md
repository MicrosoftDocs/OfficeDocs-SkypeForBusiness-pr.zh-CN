---
title: 禁用混合以完成到云的迁移
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
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 此附录包括将混合禁用作为团队和 Skype for Business 的云整合的一部分的详细步骤。
ms.openlocfilehash: f78c5a5cb792ecdb39125292c531097219dc58e3
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/01/2019
ms.locfileid: "37924963"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="8c345-103">禁用混合以完成到云的迁移</span><span class="sxs-lookup"><span data-stu-id="8c345-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="8c345-104">将所有用户从本地迁移到云后，您可以停止本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="8c345-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="8c345-105">除删除任何硬件之外，关键步骤是在逻辑上将该本地部署与 Office 365 进行逻辑分离，方法是禁用混合。</span><span class="sxs-lookup"><span data-stu-id="8c345-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="8c345-106">禁用混合的步骤包括三个步骤：</span><span class="sxs-lookup"><span data-stu-id="8c345-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="8c345-107">更新 DNS 记录以指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8c345-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="8c345-108">在 Office 365 租户中禁用拆分域。</span><span class="sxs-lookup"><span data-stu-id="8c345-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="8c345-109">禁用本地中与 Office 365 通信的功能。</span><span class="sxs-lookup"><span data-stu-id="8c345-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="8c345-110">这些步骤应作为一个单元一起完成。</span><span class="sxs-lookup"><span data-stu-id="8c345-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="8c345-111">下面提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="8c345-111">Details are provided below.</span></span> <span data-ttu-id="8c345-112">此外，在断开本地部署后，用于管理迁移用户的电话号码的准则。</span><span class="sxs-lookup"><span data-stu-id="8c345-112">In addition, guidelines for managing phone numbers for migrated users, once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="8c345-113">在极少数情况下，将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作，直到其他组织更新其联合配置：</span><span class="sxs-lookup"><span data-stu-id="8c345-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="8c345-114">任何使用旧直接联盟模型（也称为 "允许的伙伴服务器"）的联合组织都需要更新其组织的允许的域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="8c345-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="8c345-115">此旧版联合模型不基于 DNS SRV 记录，因此一旦您的组织移动到云，这样的配置就会过期。</span><span class="sxs-lookup"><span data-stu-id="8c345-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="8c345-116">没有已启用 sipfed.online.lync.com> 的托管提供程序的任何联合组织。<span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="8c345-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="8c345-117">只有在联合组织纯粹在本地并且从未与任何混合或联机租户联合的情况下，这种情况才可行。</span><span class="sxs-lookup"><span data-stu-id="8c345-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="8c345-118">在这种情况下，与这些组织的联盟在启用其承载提供程序之前将不起作用。</span><span class="sxs-lookup"><span data-stu-id="8c345-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="8c345-119">如果您怀疑任何联盟伙伴可能正在使用直接联盟或与任何在线或混合组织联合，我们建议您在准备完成到云的迁移时向其发送有关此的通信。</span><span class="sxs-lookup"><span data-stu-id="8c345-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="8c345-120">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="8c345-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="8c345-121">组织的内部部署组织的外部 DNS 需要更新，以便 Skype for Business 记录指向 Office 365 而不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="8c345-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="8c345-122">具体来说：</span><span class="sxs-lookup"><span data-stu-id="8c345-122">Specifically:</span></span>

    |<span data-ttu-id="8c345-123">记录类型</span><span class="sxs-lookup"><span data-stu-id="8c345-123">Record type</span></span>|<span data-ttu-id="8c345-124">名称</span><span class="sxs-lookup"><span data-stu-id="8c345-124">Name</span></span>|<span data-ttu-id="8c345-125">TTL</span><span class="sxs-lookup"><span data-stu-id="8c345-125">TTL</span></span>|<span data-ttu-id="8c345-126">值</span><span class="sxs-lookup"><span data-stu-id="8c345-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="8c345-127">SRV</span><span class="sxs-lookup"><span data-stu-id="8c345-127">SRV</span></span>|<span data-ttu-id="8c345-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="8c345-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="8c345-129">3600</span><span class="sxs-lookup"><span data-stu-id="8c345-129">3600</span></span>|<span data-ttu-id="8c345-130">100 1 5061 sipfed.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="8c345-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8c345-131">SRV</span><span class="sxs-lookup"><span data-stu-id="8c345-131">SRV</span></span>|<span data-ttu-id="8c345-132">_sip。。</span><span class="sxs-lookup"><span data-stu-id="8c345-132">_sip._tls</span></span>|<span data-ttu-id="8c345-133">3600</span><span class="sxs-lookup"><span data-stu-id="8c345-133">3600</span></span>|<span data-ttu-id="8c345-134">100 1 443 sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="8c345-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8c345-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c345-135">CNAME</span></span>| <span data-ttu-id="8c345-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="8c345-136">lyncdiscover</span></span>|   <span data-ttu-id="8c345-137">3600</span><span class="sxs-lookup"><span data-stu-id="8c345-137">3600</span></span>|   <span data-ttu-id="8c345-138">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="8c345-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8c345-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c345-139">CNAME</span></span>| <span data-ttu-id="8c345-140">sip</span><span class="sxs-lookup"><span data-stu-id="8c345-140">sip</span></span>|    <span data-ttu-id="8c345-141">3600</span><span class="sxs-lookup"><span data-stu-id="8c345-141">3600</span></span>|   <span data-ttu-id="8c345-142">sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="8c345-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8c345-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c345-143">CNAME</span></span>| <span data-ttu-id="8c345-144">法规</span><span class="sxs-lookup"><span data-stu-id="8c345-144">meet</span></span>|   <span data-ttu-id="8c345-145">3600</span><span class="sxs-lookup"><span data-stu-id="8c345-145">3600</span></span>|   <span data-ttu-id="8c345-146">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="8c345-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="8c345-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="8c345-147">CNAME</span></span>| <span data-ttu-id="8c345-148">入</span><span class="sxs-lookup"><span data-stu-id="8c345-148">dialin</span></span>  |<span data-ttu-id="8c345-149">3600</span><span class="sxs-lookup"><span data-stu-id="8c345-149">3600</span></span>|  <span data-ttu-id="8c345-150">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="8c345-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="8c345-151">*在 Office 365 租户中禁用共享 SIP 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="8c345-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="8c345-152">下面的命令需要从 Skype for business Online PowerShell 窗口中执行。</span><span class="sxs-lookup"><span data-stu-id="8c345-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="8c345-153">*禁用本地中与 Office 365 通信的功能。*</span><span class="sxs-lookup"><span data-stu-id="8c345-153">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="8c345-154">需要从内部部署 PowerShell 窗口执行以下命令。</span><span class="sxs-lookup"><span data-stu-id="8c345-154">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="8c345-155">如果您之前已导入 Skype for business Online 会话，请启动新的 Skype for Business PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="8c345-155">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

### <a name="managing-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="8c345-156">管理从本地迁移的用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="8c345-156">Managing phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="8c345-157">管理员可以管理以前从本地 Skype for Business 服务器移动到云的用户，即使在本地部署已停止后也是如此。</span><span class="sxs-lookup"><span data-stu-id="8c345-157">Admins can manage users that were previously moved from on-premise Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="8c345-158">有两种不同的可能性：</span><span class="sxs-lookup"><span data-stu-id="8c345-158">There are 2 different possibilities:</span></span>
1.  <span data-ttu-id="8c345-159">如果用户在移动前有 lineURI 内部部署（大概是因为用户已启用企业语音），如果要更改 lineURI，则必须在本地 AD 中执行此操作，并允许值流向上到 AAD。</span><span class="sxs-lookup"><span data-stu-id="8c345-159">If the user had a lineURI on-premise before the move (presumably because the user was enabled for Enterprise Voice), if you want to change the lineURI, you must do this in on-premise AD and let the value flow up to AAD.</span></span> <span data-ttu-id="8c345-160">这不需要本地 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="8c345-160">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="8c345-161">相反，可以使用 Active Directory 用户和计算机 MMC 管理单元或通过 PowerShell 在内部部署 Active Directory 中直接编辑 msRTCSIP 行。</span><span class="sxs-lookup"><span data-stu-id="8c345-161">Rather, this attribute, msRTCSIP-Line can be edited directly in the on-premises Active Directory, using either Active Directory Users and Computers MMC snap-in, or via PowerShell.</span></span> <span data-ttu-id="8c345-162">如果使用 MMC 管理单元，请打开用户的 "属性" 页，然后单击 "属性编辑器" 选项卡并找到 "msRTCSIP" 行。</span><span class="sxs-lookup"><span data-stu-id="8c345-162">If using the MMC snap-in, open to properties page of the user, and click Attribute Editor tab and find msRTCSIP-Line.</span></span>

2.  <span data-ttu-id="8c345-163">如果用户在移动之前没有 lineURI on 本地的值，则可以使用 Skype for Business Online Powershell 模块中的 get-csuser cmdlet 中的-onpremLineUri 参数修改 LineURI。</span><span class="sxs-lookup"><span data-stu-id="8c345-163">If the user did not have a value for lineURI on-prem before the move, you can modify the LineURI using the -onpremLineUri parameters in the set-csuser cmdlet in the Skype for Business Online Powershell module.</span></span>

## <a name="see-also"></a><span data-ttu-id="8c345-164">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8c345-164">See also</span></span>

[<span data-ttu-id="8c345-165">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="8c345-165">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
