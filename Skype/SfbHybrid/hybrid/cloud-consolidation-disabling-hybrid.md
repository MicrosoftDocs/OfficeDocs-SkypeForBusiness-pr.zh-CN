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
ms.openlocfilehash: 053d632b5a07b7ce7cca8ef7a1ddf45a673bcf59
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/22/2020
ms.locfileid: "43780141"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="4ef0d-103">禁用混合以完成云迁移</span><span class="sxs-lookup"><span data-stu-id="4ef0d-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="4ef0d-104">将所有用户从本地移动到云后，可取消本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="4ef0d-105">除了删除任何硬件之外，关键步骤是通过禁用混合，从逻辑上将本地部署与 Office 365 分离开来。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="4ef0d-106">禁用混合的步骤包括三个步骤：</span><span class="sxs-lookup"><span data-stu-id="4ef0d-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="4ef0d-107">将 DNS 记录更新为指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-107">Update DNS records to point to Office 365.</span></span>

2. <span data-ttu-id="4ef0d-108">在 Office 365 组织中禁用拆分域。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-108">Disable split domain in the Office 365 organization.</span></span>

3. <span data-ttu-id="4ef0d-109">禁用本地与 Office 365 通信的功能。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-109">Disable the ability in on-premises to communicate with Office 365.</span></span>

<span data-ttu-id="4ef0d-110">这些步骤应作为一个单元一起完成。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="4ef0d-111">下面提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-111">Details are provided below.</span></span> <span data-ttu-id="4ef0d-112">此外，在本地部署断开连接后，将提供准则来管理迁移用户的电话号码。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-112">In addition, guidelines are provided for managing phone numbers for migrated users once the on-premises deployment is disconnected.</span></span>

> [!Note] 
> <span data-ttu-id="4ef0d-113">在极少数情况下，将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作，直到其他组织更新其联合配置：</span><span class="sxs-lookup"><span data-stu-id="4ef0d-113">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="4ef0d-114">任何使用旧直接联盟模型（也称为 "允许的伙伴服务器"）的联合组织都需要更新其组织的允许的域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="4ef0d-115">此旧版联合模型不基于 DNS SRV 记录，因此一旦您的组织移动到云，这样的配置就会过期。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="4ef0d-116">没有已启用 sipfed.online.lync.com> 的托管提供程序的任何联合组织。<span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="4ef0d-117">只有在联合组织纯粹在本地并且从未与任何混合或联机租户联合的情况下，这种情况才可行。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-117">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="4ef0d-118">在这种情况下，与这些组织的联盟在启用其承载提供程序之前将不起作用。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="4ef0d-119">如果您怀疑任何联盟伙伴可能正在使用直接联盟或与任何在线或混合组织联合，我们建议您在准备完成到云的迁移时向其发送有关此的通信。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-119">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="4ef0d-120">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="4ef0d-120">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="4ef0d-121">组织的内部部署组织的外部 DNS 需要更新，以便 Skype for Business 记录指向 Office 365 而不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-121">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="4ef0d-122">具体来说：</span><span class="sxs-lookup"><span data-stu-id="4ef0d-122">Specifically:</span></span>

    |<span data-ttu-id="4ef0d-123">记录类型</span><span class="sxs-lookup"><span data-stu-id="4ef0d-123">Record type</span></span>|<span data-ttu-id="4ef0d-124">名称</span><span class="sxs-lookup"><span data-stu-id="4ef0d-124">Name</span></span>|<span data-ttu-id="4ef0d-125">TTL</span><span class="sxs-lookup"><span data-stu-id="4ef0d-125">TTL</span></span>|<span data-ttu-id="4ef0d-126">值</span><span class="sxs-lookup"><span data-stu-id="4ef0d-126">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="4ef0d-127">SRV</span><span class="sxs-lookup"><span data-stu-id="4ef0d-127">SRV</span></span>|<span data-ttu-id="4ef0d-128">_sipfederationtls _tcp</span><span class="sxs-lookup"><span data-stu-id="4ef0d-128">_sipfederationtls._tcp</span></span>|<span data-ttu-id="4ef0d-129">3600</span><span class="sxs-lookup"><span data-stu-id="4ef0d-129">3600</span></span>|<span data-ttu-id="4ef0d-130">100 1 5061 sipfed.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="4ef0d-130">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ef0d-131">SRV</span><span class="sxs-lookup"><span data-stu-id="4ef0d-131">SRV</span></span>|<span data-ttu-id="4ef0d-132">_sip _tls</span><span class="sxs-lookup"><span data-stu-id="4ef0d-132">_sip._tls</span></span>|<span data-ttu-id="4ef0d-133">3600</span><span class="sxs-lookup"><span data-stu-id="4ef0d-133">3600</span></span>|<span data-ttu-id="4ef0d-134">100 1 443 sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="4ef0d-134">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ef0d-135">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ef0d-135">CNAME</span></span>| <span data-ttu-id="4ef0d-136">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="4ef0d-136">lyncdiscover</span></span>|   <span data-ttu-id="4ef0d-137">3600</span><span class="sxs-lookup"><span data-stu-id="4ef0d-137">3600</span></span>|   <span data-ttu-id="4ef0d-138">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="4ef0d-138">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ef0d-139">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ef0d-139">CNAME</span></span>| <span data-ttu-id="4ef0d-140">sip</span><span class="sxs-lookup"><span data-stu-id="4ef0d-140">sip</span></span>|    <span data-ttu-id="4ef0d-141">3600</span><span class="sxs-lookup"><span data-stu-id="4ef0d-141">3600</span></span>|   <span data-ttu-id="4ef0d-142">sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="4ef0d-142">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ef0d-143">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ef0d-143">CNAME</span></span>| <span data-ttu-id="4ef0d-144">法规</span><span class="sxs-lookup"><span data-stu-id="4ef0d-144">meet</span></span>|   <span data-ttu-id="4ef0d-145">3600</span><span class="sxs-lookup"><span data-stu-id="4ef0d-145">3600</span></span>|   <span data-ttu-id="4ef0d-146">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="4ef0d-146">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="4ef0d-147">CNAME</span><span class="sxs-lookup"><span data-stu-id="4ef0d-147">CNAME</span></span>| <span data-ttu-id="4ef0d-148">入</span><span class="sxs-lookup"><span data-stu-id="4ef0d-148">dialin</span></span>  |<span data-ttu-id="4ef0d-149">3600</span><span class="sxs-lookup"><span data-stu-id="4ef0d-149">3600</span></span>|  <span data-ttu-id="4ef0d-150">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="4ef0d-150">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="4ef0d-151">*在 Office 365 组织中禁用共享 SIP 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="4ef0d-151">*Disable shared SIP address space in Office 365 organization.*</span></span>
<span data-ttu-id="4ef0d-152">下面的命令需要从 Skype for business Online PowerShell 窗口中执行。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-152">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    ```PowerShell
    Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false
    ```
 
3.  <span data-ttu-id="4ef0d-153">*禁用本地与 Office 365 通信的功能。*</span><span class="sxs-lookup"><span data-stu-id="4ef0d-153">*Disable ability in on-premises to communicate with Office 365.*</span></span>  
<span data-ttu-id="4ef0d-154">需要从内部部署 PowerShell 窗口中执行以下命令：</span><span class="sxs-lookup"><span data-stu-id="4ef0d-154">The command below needs to be done from an on-premises PowerShell window:</span></span>
```PowerShell
    Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false
```

### <a name="manage-phone-numbers-for-users-who-were-migrated-from-on-premises"></a><span data-ttu-id="4ef0d-155">管理从本地迁移的用户的电话号码</span><span class="sxs-lookup"><span data-stu-id="4ef0d-155">Manage phone numbers for users who were migrated from on-premises</span></span>

<span data-ttu-id="4ef0d-156">管理员可以管理以前从本地 Skype for Business 服务器移动到云的用户，即使在本地部署已停止后也是如此。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-156">Administrators can manage users who were previously moved from an on-premises Skype for Business Server to the cloud, even after the on-premises deployment is decommissioned.</span></span> <span data-ttu-id="4ef0d-157">有两种不同的可能性：</span><span class="sxs-lookup"><span data-stu-id="4ef0d-157">There are two different possibilities:</span></span>

- <span data-ttu-id="4ef0d-158">在移动前，用户没有 LineURI 内部部署的值。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-158">The user did not have a value for LineURI on-premises before the move.</span></span> 

  <span data-ttu-id="4ef0d-159">在这种情况下，您可以在 Skype for Business Online PowerShell 模块中使用[get-csuser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps)中的-onpremLineUri 参数修改 LineURI。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-159">In this case, you can modify the LineURI using the -onpremLineUri parameters in the [Set-CsUser cmdlet](https://docs.microsoft.com/powershell/module/skype/set-csuser?view=skype-ps) in the Skype for Business Online PowerShell module.</span></span>

- <span data-ttu-id="4ef0d-160">用户在移动前有一个 LineURI 内部部署（大概是因为用户已启用企业语音）。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-160">The user had a LineURI on-premises before the move (presumably because the user was enabled for Enterprise Voice).</span></span> 

  <span data-ttu-id="4ef0d-161">如果要更改 LineURI，则必须在本地 Active Directory 中执行此操作，并允许值流传递到 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-161">If you want to change the LineURI, you must do this in the on-premises Active Directory and let the value flow up to Azure AD.</span></span> <span data-ttu-id="4ef0d-162">这不需要本地 Skype for Business Server。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-162">This does NOT require on-premises Skype for Business Server.</span></span> <span data-ttu-id="4ef0d-163">相反，可以使用 Active Directory 用户和计算机 MMC 管理单元或使用 PowerShell，直接在内部部署 Active Directory 中编辑此属性（msRTCSIP-Line）。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-163">Rather, this attribute, msRTCSIP-Line, can be edited directly in the on-premises Active Directory, using either the Active Directory Users and Computers MMC snap-in, or by using PowerShell.</span></span> <span data-ttu-id="4ef0d-164">如果使用的是 MMC 管理单元，请打开到用户的 "属性" 页，单击 "属性编辑器" 选项卡，然后找到 "msRTCSIP" 行。</span><span class="sxs-lookup"><span data-stu-id="4ef0d-164">If you are using the MMC snap-in, open to the properties page of the user, click Attribute Editor tab, and find msRTCSIP-Line.</span></span>

  ![Active Directory 用户和计算机工具](../media/disable-hybrid-1.png)

## <a name="see-also"></a><span data-ttu-id="4ef0d-166">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ef0d-166">See also</span></span>

[<span data-ttu-id="4ef0d-167">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="4ef0d-167">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)
