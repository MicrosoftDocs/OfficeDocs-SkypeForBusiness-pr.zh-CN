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
ms.openlocfilehash: d441d9fcc5e4f2cec495efabdbea423eaaec882c
ms.sourcegitcommit: 7920c47eb73e665dad4bf7214b28541d357bce25
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "37962047"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="ebae4-103">禁用混合以完成到云的迁移</span><span class="sxs-lookup"><span data-stu-id="ebae4-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="ebae4-104">将所有用户从本地迁移到云后，您可以停止本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="ebae4-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="ebae4-105">除删除任何硬件之外，关键步骤是在逻辑上将该本地部署与 Office 365 进行逻辑分离，方法是禁用混合。</span><span class="sxs-lookup"><span data-stu-id="ebae4-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="ebae4-106">禁用混合的步骤包括三个步骤：</span><span class="sxs-lookup"><span data-stu-id="ebae4-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="ebae4-107">更新 DNS 记录以指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="ebae4-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="ebae4-108">在 Office 365 租户中禁用拆分域。</span><span class="sxs-lookup"><span data-stu-id="ebae4-108">Disable split domain in the Office 365 tenant.</span></span>

3. <span data-ttu-id="ebae4-109">禁用本地与 Office 365 通信的功能。</span><span class="sxs-lookup"><span data-stu-id="ebae4-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="ebae4-110">这些步骤应作为一个单元一起完成。</span><span class="sxs-lookup"><span data-stu-id="ebae4-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="ebae4-111">下面提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="ebae4-111">Details are provided below.</span></span> <span data-ttu-id="ebae4-112">此外，在本地部署断开连接后，将提供准则来管理迁移用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="ebae4-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="ebae4-113">在极少数情况下，将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作，直到其他组织更新其联合配置：</span><span class="sxs-lookup"><span data-stu-id="ebae4-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="ebae4-114">任何使用旧直接联盟模型（也称为 "允许的伙伴服务器"）的联合组织都需要更新其组织的允许的域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="ebae4-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="ebae4-115">此旧版联合模型不基于 DNS SRV 记录，因此一旦您的组织移动到云，这样的配置就会过期。</span><span class="sxs-lookup"><span data-stu-id="ebae4-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="ebae4-116">没有已启用 sipfed.online.lync.com> 的托管提供程序的任何联合组织。<span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="ebae4-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="ebae4-117">只有在联合组织纯粹在本地并且从未与任何混合或联机租户联合的情况下，这种情况才可行。</span><span class="sxs-lookup"><span data-stu-id="ebae4-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="ebae4-118">在这种情况下，与这些组织的联盟在启用其承载提供程序之前将不起作用。</span><span class="sxs-lookup"><span data-stu-id="ebae4-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="ebae4-119">如果您怀疑任何联盟伙伴可能正在使用直接联盟或与任何在线或混合组织联合，我们建议您在准备完成到云的迁移时向其发送有关此的通信。</span><span class="sxs-lookup"><span data-stu-id="ebae4-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="ebae4-120">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="ebae4-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="ebae4-121">组织的内部部署组织的外部 DNS 需要更新，以便 Skype for Business 记录指向 Office 365 而不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="ebae4-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="ebae4-122">具体来说：</span><span class="sxs-lookup"><span data-stu-id="ebae4-122">Specifically:</span></span>

    |<span data-ttu-id="ebae4-123">记录类型</span><span class="sxs-lookup"><span data-stu-id="ebae4-123">Record type</span></span>|<span data-ttu-id="ebae4-124">名称</span><span class="sxs-lookup"><span data-stu-id="ebae4-124">Name</span></span>|<span data-ttu-id="ebae4-125">TTL</span><span class="sxs-lookup"><span data-stu-id="ebae4-125">TTL</span></span>|<span data-ttu-id="ebae4-126">值</span><span class="sxs-lookup"><span data-stu-id="ebae4-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="ebae4-127">SRV</span><span class="sxs-lookup"><span data-stu-id="ebae4-127">SRV</span></span>|<span data-ttu-id="ebae4-128">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="ebae4-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="ebae4-129">3600</span><span class="sxs-lookup"><span data-stu-id="ebae4-129">3600</span></span>|<span data-ttu-id="ebae4-130">100 1 5061 sipfed.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="ebae4-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebae4-131">SRV</span><span class="sxs-lookup"><span data-stu-id="ebae4-131">SRV</span></span>|<span data-ttu-id="ebae4-132">_sip。。</span><span class="sxs-lookup"><span data-stu-id="ebae4-132">_sip._tls</span></span>|<span data-ttu-id="ebae4-133">3600</span><span class="sxs-lookup"><span data-stu-id="ebae4-133">3600</span></span>|<span data-ttu-id="ebae4-134">100 1 443 sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="ebae4-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebae4-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebae4-135">CNAME</span></span>| <span data-ttu-id="ebae4-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="ebae4-136">lyncdiscover</span></span>|   <span data-ttu-id="ebae4-137">3600</span><span class="sxs-lookup"><span data-stu-id="ebae4-137">3600</span></span>|   <span data-ttu-id="ebae4-138">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="ebae4-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebae4-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebae4-139">CNAME</span></span>| <span data-ttu-id="ebae4-140">sip</span><span class="sxs-lookup"><span data-stu-id="ebae4-140">sip</span></span>|    <span data-ttu-id="ebae4-141">3600</span><span class="sxs-lookup"><span data-stu-id="ebae4-141">3600</span></span>|   <span data-ttu-id="ebae4-142">sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="ebae4-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebae4-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebae4-143">CNAME</span></span>| <span data-ttu-id="ebae4-144">法规</span><span class="sxs-lookup"><span data-stu-id="ebae4-144">meet</span></span>|   <span data-ttu-id="ebae4-145">3600</span><span class="sxs-lookup"><span data-stu-id="ebae4-145">3600</span></span>|   <span data-ttu-id="ebae4-146">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="ebae4-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="ebae4-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="ebae4-147">CNAME</span></span>| <span data-ttu-id="ebae4-148">入</span><span class="sxs-lookup"><span data-stu-id="ebae4-148">dialin</span></span>  |<span data-ttu-id="ebae4-149">3600</span><span class="sxs-lookup"><span data-stu-id="ebae4-149">3600</span></span>|  <span data-ttu-id="ebae4-150">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="ebae4-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="ebae4-151">*在 Office 365 租户中禁用共享 SIP 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="ebae4-151">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="ebae4-152">下面的命令需要从 Skype for business Online PowerShell 窗口中执行。</span><span class="sxs-lookup"><span data-stu-id="ebae4-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="ebae4-153">*禁用本地中与 Office 365 通信的功能。*</span><span class="sxs-lookup"><span data-stu-id="ebae4-153">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="ebae4-154">需要从内部部署 PowerShell 窗口执行以下命令。</span><span class="sxs-lookup"><span data-stu-id="ebae4-154">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="ebae4-155">如果您之前已导入 Skype for Business Online 会话，请按如下所示启动新的 Skype for Business PowerShell 会话：</span><span class="sxs-lookup"><span data-stu-id="ebae4-155">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session as follows:</span></span>

```
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="ebae4-156">管理从本地迁移的用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="ebae4-156">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="ebae4-157">管理员可以管理以前从本地 Skype for Business 服务器移动到云的用户，即使在本地部署已停止后也是如此。</span><span class="sxs-lookup"><span data-stu-id="ebae4-157">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="ebae4-158">有两种不同的可能性：</span><span class="sxs-lookup"><span data-stu-id="ebae4-158">There are two different possibilities:</span></span>

- <span data-ttu-id="ebae4-159">在移动前，用户没有 lineURI 内部部署的值。</span><span class="sxs-lookup"><span data-stu-id="ebae4-159">The user did not have a value for lineURI on-premises before the move.</span></span> 

  <span data-ttu-id="ebae4-160">在这种情况下，您可以在 Skype for Business Online Powershell 模块中使用[get-csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)中的-onpremLineUri 参数修改 LineURI。</span><span class="sxs-lookup"><span data-stu-id="ebae4-160">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-Csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online Powershell module.</span></span>

- <span data-ttu-id="ebae4-161">用户在移动前有一个 lineURI 内部部署（大概是因为用户已启用企业语音）。</span><span class="sxs-lookup"><span data-stu-id="ebae4-161">The user had a lineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="ebae4-162">如果要更改 lineURI，则必须在本地 Active Directory 中执行此操作，并允许值流传递到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="ebae4-162">If you want to change the lineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="ebae4-163">这不需要本地 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="ebae4-163">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="ebae4-164">相反，可以使用 Active Directory 用户和计算机 MMC 管理单元或使用 PowerShell，直接在内部部署 Active Directory 中编辑此属性（msRTCSIP-Line）。</span><span class="sxs-lookup"><span data-stu-id="ebae4-164">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="ebae4-165">如果使用的是 MMC 管理单元，请打开到用户的 "属性" 页，单击 "属性编辑器" 选项卡，然后找到 "msRTCSIP" 行。</span><span class="sxs-lookup"><span data-stu-id="ebae4-165">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="ebae4-167">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ebae4-167">See also</span></span>

[<span data-ttu-id="ebae4-168">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="ebae4-168">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
