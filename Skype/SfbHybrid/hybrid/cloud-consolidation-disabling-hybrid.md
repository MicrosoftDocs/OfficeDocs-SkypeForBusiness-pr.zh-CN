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
ms.openlocfilehash: 805010aa16ca8159b5e274847ca7ca2b296f214d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "36160454"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="23e90-103">禁用混合以完成到云的迁移</span><span class="sxs-lookup"><span data-stu-id="23e90-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="23e90-104">将所有用户从本地迁移到云后, 您可以停止本地 Skype for Business 部署。</span><span class="sxs-lookup"><span data-stu-id="23e90-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="23e90-105">除删除任何硬件之外, 关键步骤是在逻辑上将该本地部署与 Office 365 进行逻辑分离, 方法是禁用混合。</span><span class="sxs-lookup"><span data-stu-id="23e90-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="23e90-106">禁用混合的步骤包括三个步骤:</span><span class="sxs-lookup"><span data-stu-id="23e90-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="23e90-107">更新 DNS 记录以指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="23e90-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="23e90-108">在 Office 365 租户中禁用拆分域。</span><span class="sxs-lookup"><span data-stu-id="23e90-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="23e90-109">禁用本地中与 Office 365 通信的功能。</span><span class="sxs-lookup"><span data-stu-id="23e90-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="23e90-110">这些步骤应作为一个单元一起完成。</span><span class="sxs-lookup"><span data-stu-id="23e90-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="23e90-111">下面提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="23e90-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="23e90-112">在极少数情况下, 将 DNS 从指向 Office 365 的本地位置更改为您的组织可能导致其他组织的联盟停止工作, 直到其他组织更新其联合配置:</span><span class="sxs-lookup"><span data-stu-id="23e90-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="23e90-113">任何使用旧直接联盟模型 (也称为 "允许的伙伴服务器") 的联合组织都需要更新其组织的允许的域条目, 以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="23e90-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="23e90-114">此旧版联合模型不基于 DNS SRV 记录, 因此一旦您的组织移动到云, 这样的配置就会过期。</span><span class="sxs-lookup"><span data-stu-id="23e90-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="23e90-115">没有已启用 sipfed.online.lync.com> 的托管提供程序的任何联合组织。<span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="23e90-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="23e90-116">只有在联合组织纯粹在本地并且从未与任何混合或联机租户联合的情况下, 这种情况才可行。</span><span class="sxs-lookup"><span data-stu-id="23e90-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="23e90-117">在这种情况下, 与这些组织的联盟在启用其承载提供程序之前将不起作用。</span><span class="sxs-lookup"><span data-stu-id="23e90-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="23e90-118">如果您怀疑任何联盟伙伴可能正在使用直接联盟或与任何在线或混合组织联合, 我们建议您在准备完成到云的迁移时向其发送有关此的通信。</span><span class="sxs-lookup"><span data-stu-id="23e90-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="23e90-119">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="23e90-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="23e90-120">组织的内部部署组织的外部 DNS 需要更新, 以便 Skype for Business 记录指向 Office 365 而不是本地部署。</span><span class="sxs-lookup"><span data-stu-id="23e90-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="23e90-121">具体来说：</span><span class="sxs-lookup"><span data-stu-id="23e90-121">Specifically:</span></span>

    |<span data-ttu-id="23e90-122">记录类型</span><span class="sxs-lookup"><span data-stu-id="23e90-122">Record type</span></span>|<span data-ttu-id="23e90-123">名称</span><span class="sxs-lookup"><span data-stu-id="23e90-123">Name</span></span>|<span data-ttu-id="23e90-124">TTL</span><span class="sxs-lookup"><span data-stu-id="23e90-124">TTL</span></span>|<span data-ttu-id="23e90-125">值</span><span class="sxs-lookup"><span data-stu-id="23e90-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="23e90-126">SRV</span><span class="sxs-lookup"><span data-stu-id="23e90-126">SRV</span></span>|<span data-ttu-id="23e90-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="23e90-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="23e90-128">3600</span><span class="sxs-lookup"><span data-stu-id="23e90-128">3600</span></span>|<span data-ttu-id="23e90-129">100 1 5061 sipfed.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="23e90-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="23e90-130">SRV</span><span class="sxs-lookup"><span data-stu-id="23e90-130">SRV</span></span>|<span data-ttu-id="23e90-131">_sip。。</span><span class="sxs-lookup"><span data-stu-id="23e90-131">_sip._tls</span></span>|<span data-ttu-id="23e90-132">3600</span><span class="sxs-lookup"><span data-stu-id="23e90-132">3600</span></span>|<span data-ttu-id="23e90-133">100 1 443 sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="23e90-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="23e90-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e90-134">CNAME</span></span>| <span data-ttu-id="23e90-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="23e90-135">lyncdiscover</span></span>|   <span data-ttu-id="23e90-136">3600</span><span class="sxs-lookup"><span data-stu-id="23e90-136">3600</span></span>|   <span data-ttu-id="23e90-137">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="23e90-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="23e90-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e90-138">CNAME</span></span>| <span data-ttu-id="23e90-139">sip</span><span class="sxs-lookup"><span data-stu-id="23e90-139">sip</span></span>|    <span data-ttu-id="23e90-140">3600</span><span class="sxs-lookup"><span data-stu-id="23e90-140">3600</span></span>|   <span data-ttu-id="23e90-141">sipdir.online.lync.com>。<span>com</span><span class="sxs-lookup"><span data-stu-id="23e90-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="23e90-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e90-142">CNAME</span></span>| <span data-ttu-id="23e90-143">法规</span><span class="sxs-lookup"><span data-stu-id="23e90-143">meet</span></span>|   <span data-ttu-id="23e90-144">3600</span><span class="sxs-lookup"><span data-stu-id="23e90-144">3600</span></span>|   <span data-ttu-id="23e90-145">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="23e90-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="23e90-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="23e90-146">CNAME</span></span>| <span data-ttu-id="23e90-147">入</span><span class="sxs-lookup"><span data-stu-id="23e90-147">dialin</span></span>  |<span data-ttu-id="23e90-148">3600</span><span class="sxs-lookup"><span data-stu-id="23e90-148">3600</span></span>|  <span data-ttu-id="23e90-149">webdir。<span>com</span><span class="sxs-lookup"><span data-stu-id="23e90-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="23e90-150">*在 Office 365 租户中禁用共享 SIP 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="23e90-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="23e90-151">下面的命令需要从 Skype for business Online PowerShell 窗口中执行。</span><span class="sxs-lookup"><span data-stu-id="23e90-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="23e90-152">*禁用本地中与 Office 365 通信的功能。*</span><span class="sxs-lookup"><span data-stu-id="23e90-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="23e90-153">需要从内部部署 PowerShell 窗口执行以下命令。</span><span class="sxs-lookup"><span data-stu-id="23e90-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="23e90-154">如果您之前已导入 Skype for business Online 会话, 请启动新的 Skype for Business PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="23e90-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="23e90-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="23e90-155">See also</span></span>

[<span data-ttu-id="23e90-156">针对团队和 Skype for Business 的云整合</span><span class="sxs-lookup"><span data-stu-id="23e90-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)