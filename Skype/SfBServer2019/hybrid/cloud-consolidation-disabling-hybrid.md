---
title: 禁用混合完成迁移到云中
ms.author: crowe
author: crowe
manager: serdars
ms.reviewer: bjwhalen
ms.topic: article
ms.service:
- skype-for-business-online
- msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
description: 本附录中包括用于云整合个团队和 Skype for Business 的一部分禁用混合的详细的步骤。
ms.openlocfilehash: 03c38a4482d9a0bd6e728138b3d856b552e4754a
ms.sourcegitcommit: 4dac1994b829d7a7aefc3c003eec998e011c1bd3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2018
ms.locfileid: "27247624"
---
# <a name="disable-hybrid-to-complete-migration-to-the-cloud"></a><span data-ttu-id="db7ca-103">禁用混合完成迁移到云中</span><span class="sxs-lookup"><span data-stu-id="db7ca-103">Disable hybrid to complete migration to the cloud</span></span>

<span data-ttu-id="db7ca-104">具有到云从本地移动所有用户后，您可以停用业务部署本地 Skype。</span><span class="sxs-lookup"><span data-stu-id="db7ca-104">After you have moved all users from on-premises to the cloud, you can decommission the on-premises Skype for Business deployment.</span></span> <span data-ttu-id="db7ca-105">删除所有的硬件，除了关键步骤是逻辑分隔禁用混合从 Office 365 的内部部署。</span><span class="sxs-lookup"><span data-stu-id="db7ca-105">Aside from removing any hardware, a critical step is to logically separate that on-premises deployment from Office 365 by disabling hybrid.</span></span> <span data-ttu-id="db7ca-106">禁用混合包含的三个步骤：</span><span class="sxs-lookup"><span data-stu-id="db7ca-106">Disabling hybrid consists of 3 steps:</span></span>

1. <span data-ttu-id="db7ca-107">更新 DNS 记录以指向 Office 365。</span><span class="sxs-lookup"><span data-stu-id="db7ca-107">Update DNS records to point to Office 365.</span></span>
2. <span data-ttu-id="db7ca-108">禁用 Office 365 租户中的拆分域。</span><span class="sxs-lookup"><span data-stu-id="db7ca-108">Disable split domain in the Office 365 tenant.</span></span>
3. <span data-ttu-id="db7ca-109">禁用上 prem 中的功能与 Office 365 进行通信。</span><span class="sxs-lookup"><span data-stu-id="db7ca-109">Disable ability in on-prem to communicate with Office 365.</span></span>


<span data-ttu-id="db7ca-110">应该作为一个整体一起执行这些步骤。</span><span class="sxs-lookup"><span data-stu-id="db7ca-110">These steps should be done together as a unit.</span></span> <span data-ttu-id="db7ca-111">下面提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="db7ca-111">Details are provided below.</span></span>

> [!Note] 
> <span data-ttu-id="db7ca-112">在极少数情况下，从将在本地指向 Office 365 组织更改 DNS 都可能导致联合身份验证与其他组织停止工作，直到其他组织的更新其联合身份验证配置：</span><span class="sxs-lookup"><span data-stu-id="db7ca-112">In rare cases, changing DNS from pointing on premises to Office 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span><ul><li>
<span data-ttu-id="db7ca-113">使用旧直接联盟模式 （也称为允许的伙伴服务器） 的任何联盟的组织需要更新为其组织要删除的代理 FQDN 其允许的域条目。</span><span class="sxs-lookup"><span data-stu-id="db7ca-113">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="db7ca-114">此旧联盟模型不基于 DNS SRV 记录，以便您的组织将移动到云之后，这样的配置将成为过期。</span><span class="sxs-lookup"><span data-stu-id="db7ca-114">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span> </li><li><span data-ttu-id="db7ca-115">没有 sipfed.online.lync 启用宿主提供商任何联盟的组织。<span>com 将需要更新其配置，以启用的。</span><span class="sxs-lookup"><span data-stu-id="db7ca-115">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="db7ca-116">如果联盟的组织仅在本地并且从不具有与任何混合或 online 租户联盟，这种情况下才可能。</span><span class="sxs-lookup"><span data-stu-id="db7ca-116">This situation is only possible if the federated organization is purely on premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="db7ca-117">在这种情况下，它们使其承载服务提供商之前，将无法工作与这些组织建立联盟。</span><span class="sxs-lookup"><span data-stu-id="db7ca-117">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span></li></ul><span data-ttu-id="db7ca-118">如果您怀疑您的联盟任何的伙伴可能正在使用直接联盟或具有 online 与任何联盟或混合的组织，我们建议您将它们发送有关此通信准备完成迁移到云中。</span><span class="sxs-lookup"><span data-stu-id="db7ca-118">If you suspect that any of your federated partners may be using Direct Federation or have federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

1.  <span data-ttu-id="db7ca-119">*更新 DNS 以指向 Office 365。*</span><span class="sxs-lookup"><span data-stu-id="db7ca-119">*Update DNS to point to Office 365.*</span></span>
<span data-ttu-id="db7ca-120">需要进行更新，以便业务记录的 Skype 指向 Office 365 而不是内部部署组织的内部部署组织的外部 DNS。</span><span class="sxs-lookup"><span data-stu-id="db7ca-120">The organization’s external DNS for the on-premises organization needs to be updated so that Skype for Business records point to Office 365 instead of the on-premises deployment.</span></span> <span data-ttu-id="db7ca-121">特别是：</span><span class="sxs-lookup"><span data-stu-id="db7ca-121">Specifically:</span></span>

    |<span data-ttu-id="db7ca-122">记录类型</span><span class="sxs-lookup"><span data-stu-id="db7ca-122">Record type</span></span>|<span data-ttu-id="db7ca-123">名称</span><span class="sxs-lookup"><span data-stu-id="db7ca-123">Name</span></span>|<span data-ttu-id="db7ca-124">TTL</span><span class="sxs-lookup"><span data-stu-id="db7ca-124">TTL</span></span>|<span data-ttu-id="db7ca-125">值</span><span class="sxs-lookup"><span data-stu-id="db7ca-125">Value</span></span>|
    |---|---|---|---|
    |<span data-ttu-id="db7ca-126">SRV</span><span class="sxs-lookup"><span data-stu-id="db7ca-126">SRV</span></span>|<span data-ttu-id="db7ca-127">_sipfederationtls._tcp</span><span class="sxs-lookup"><span data-stu-id="db7ca-127">_sipfederationtls._tcp</span></span>|<span data-ttu-id="db7ca-128">3600</span><span class="sxs-lookup"><span data-stu-id="db7ca-128">3600</span></span>|<span data-ttu-id="db7ca-129">100 1 5061 sipfed.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="db7ca-129">100 1 5061 sipfed.online.lync.<span>com</span></span>|
    |<span data-ttu-id="db7ca-130">SRV</span><span class="sxs-lookup"><span data-stu-id="db7ca-130">SRV</span></span>|<span data-ttu-id="db7ca-131">_sip._tls</span><span class="sxs-lookup"><span data-stu-id="db7ca-131">_sip._tls</span></span>|<span data-ttu-id="db7ca-132">3600</span><span class="sxs-lookup"><span data-stu-id="db7ca-132">3600</span></span>|<span data-ttu-id="db7ca-133">100 1 443 sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="db7ca-133">100 1 443 sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="db7ca-134">CNAME</span><span class="sxs-lookup"><span data-stu-id="db7ca-134">CNAME</span></span>| <span data-ttu-id="db7ca-135">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="db7ca-135">lyncdiscover</span></span>|   <span data-ttu-id="db7ca-136">3600</span><span class="sxs-lookup"><span data-stu-id="db7ca-136">3600</span></span>|   <span data-ttu-id="db7ca-137">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="db7ca-137">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="db7ca-138">CNAME</span><span class="sxs-lookup"><span data-stu-id="db7ca-138">CNAME</span></span>| <span data-ttu-id="db7ca-139">sip</span><span class="sxs-lookup"><span data-stu-id="db7ca-139">sip</span></span>|    <span data-ttu-id="db7ca-140">3600</span><span class="sxs-lookup"><span data-stu-id="db7ca-140">3600</span></span>|   <span data-ttu-id="db7ca-141">sipdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="db7ca-141">sipdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="db7ca-142">CNAME</span><span class="sxs-lookup"><span data-stu-id="db7ca-142">CNAME</span></span>| <span data-ttu-id="db7ca-143">满足</span><span class="sxs-lookup"><span data-stu-id="db7ca-143">meet</span></span>|   <span data-ttu-id="db7ca-144">3600</span><span class="sxs-lookup"><span data-stu-id="db7ca-144">3600</span></span>|   <span data-ttu-id="db7ca-145">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="db7ca-145">webdir.online.lync.<span>com</span></span>|
    |<span data-ttu-id="db7ca-146">CNAME</span><span class="sxs-lookup"><span data-stu-id="db7ca-146">CNAME</span></span>| <span data-ttu-id="db7ca-147">dialin</span><span class="sxs-lookup"><span data-stu-id="db7ca-147">dialin</span></span>  |<span data-ttu-id="db7ca-148">3600</span><span class="sxs-lookup"><span data-stu-id="db7ca-148">3600</span></span>|  <span data-ttu-id="db7ca-149">webdir.online.lync。<span>com</span><span class="sxs-lookup"><span data-stu-id="db7ca-149">webdir.online.lync.<span>com</span></span>|

2.  <span data-ttu-id="db7ca-150">*禁用 Office 365 租户中的共享的 SIP 地址空间。*</span><span class="sxs-lookup"><span data-stu-id="db7ca-150">*Disable shared SIP address space in Office 365 tenant.*</span></span>
<span data-ttu-id="db7ca-151">下面的命令需要从业务 Online PowerShell 窗口 Skype 完成。</span><span class="sxs-lookup"><span data-stu-id="db7ca-151">The command below needs to be done from a Skype for Business Online PowerShell window.</span></span>

    `Set-CsTenantFederationConfiguration -SharedSipAddressSpace $false`
 
3.  <span data-ttu-id="db7ca-152">*禁用上 prem 中的功能与 Office 365 进行通信。*</span><span class="sxs-lookup"><span data-stu-id="db7ca-152">*Disable ability in on-prem to communicate with Office 365.*</span></span>  
<span data-ttu-id="db7ca-153">下面的命令需要完成从本地 PowerShell 窗口。</span><span class="sxs-lookup"><span data-stu-id="db7ca-153">The command below needs to be done from an on-premises PowerShell window.</span></span>  <span data-ttu-id="db7ca-154">如果以前业务 Online 会话导入 Skype，启动新的 Skype 业务 PowerShell 会话。</span><span class="sxs-lookup"><span data-stu-id="db7ca-154">If you have previously imported a Skype for Business Online session, start a new Skype for Business PowerShell session.</span></span>

    `Get-CsHostingProvider|Set-CsHostingProvider -Enabled $false`

## <a name="see-also"></a><span data-ttu-id="db7ca-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="db7ca-155">See also</span></span>

[<span data-ttu-id="db7ca-156">云整合个团队和 Skype for Business</span><span class="sxs-lookup"><span data-stu-id="db7ca-156">Cloud Consolidation for Teams and Skype for Business</span></span>](cloud-consolidation.md)