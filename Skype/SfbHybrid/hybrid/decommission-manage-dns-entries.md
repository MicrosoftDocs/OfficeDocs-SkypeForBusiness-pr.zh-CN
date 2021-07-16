---
title: 在停用本地环境时管理 DNS 条目
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: bjwhalen
audience: ITPro
f1.keywords:
- NOCSH
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
description: 有关如何在停用本地部署环境时管理 DNS Skype for Business说明。
ms.openlocfilehash: bd8f3873ab28ef8e0b7ade86ffc95b4d5bb4e4cb
ms.sourcegitcommit: 405b22cfd94e50d651f4c3f73fb46780cd8a6d06
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458980"
---
# <a name="update-dns-entries-to-enable-your-organization-to-be-all-teams-only"></a><span data-ttu-id="be59c-103">更新 DNS 条目，使组织能够"仅Teams"</span><span class="sxs-lookup"><span data-stu-id="be59c-103">Update DNS entries to enable your organization to be all Teams Only</span></span>

<span data-ttu-id="be59c-104">以前具有本地部署的 Skype for Business Server 或 Lync Server 的组织可能仍具有指向本地部署部署Skype for Business条目。</span><span class="sxs-lookup"><span data-stu-id="be59c-104">Organizations that previously had on-premises deployments of Skype for Business Server or Lync Server may still have DNS entries that point to an on-premises Skype for Business deployment.</span></span> <span data-ttu-id="be59c-105">如果组织包括本地用户，则这些记录Skype for Business要求。</span><span class="sxs-lookup"><span data-stu-id="be59c-105">These records are required if your organization includes on-premises Skype for Business users.</span></span> <span data-ttu-id="be59c-106">但是，一旦组织不再具有任何本地 Skype for Business Lync Server 用户，则不再需要这些记录。</span><span class="sxs-lookup"><span data-stu-id="be59c-106">However, once your organization no longer has any on-premises Skype for Business or Lync Server users, these records are no longer required.</span></span> <span data-ttu-id="be59c-107">事实上，作为完成从本地迁移到 Teams 的一部分，必须更新这些记录以指向Microsoft 365或删除。</span><span class="sxs-lookup"><span data-stu-id="be59c-107">And in fact, as part of completing the migration from on-premises to Teams, these records must be updated to point to Microsoft 365 or removed.</span></span> <span data-ttu-id="be59c-108">Microsoft 无法执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="be59c-108">Microsoft cannot take this step for you.</span></span>

<span data-ttu-id="be59c-109">尝试将 TeamsOnly 授予整个租户时，Teams DNS 以确定组织是否存在这些 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="be59c-109">When attempting to grant TeamsOnly to the entire tenant, Teams will check DNS to determine if any of these DNS records exist for your organization.</span></span> <span data-ttu-id="be59c-110">如果找到任何记录，并且它们指向 Microsoft 365，尝试将租户共存模式更改为 TeamsOnly 将按设计失败。</span><span class="sxs-lookup"><span data-stu-id="be59c-110">If any records are found, and if they point to something other than Microsoft 365, the attempt to change the tenant coexistence mode to TeamsOnly will fail by design.</span></span> <span data-ttu-id="be59c-111">此设计是为了防止具有本地用户的混合组织错误地将 TeamsOnly 模式应用到租户，因为这样做会破坏任何本地 Skype for Business 用户的联盟 (无论使用 Teams 还是 Skype for Business) 。</span><span class="sxs-lookup"><span data-stu-id="be59c-111">This design is to prevent hybrid organizations with on-premises users from mistakenly applying TeamsOnly mode to the tenant--because doing so would break federation for any on-premises Skype for Business users (whether using Teams or Skype for Business).</span></span>

<span data-ttu-id="be59c-112">此外，必须更新这些记录，以便你可以将 TeamsOnly 授予整个租户。</span><span class="sxs-lookup"><span data-stu-id="be59c-112">Furthermore, these records must be updated so that you can grant TeamsOnly to the entire tenant.</span></span>

> [!Note] 
> <span data-ttu-id="be59c-113">在极少数情况下，将组织的 DNS 从本地指向Microsoft 365可能会导致与其他一些组织的联盟停止工作，直到其他组织更新其联盟配置：</span><span class="sxs-lookup"><span data-stu-id="be59c-113">In rare cases, changing DNS from pointing on premises to Microsoft 365 for your organization may cause federation with some other organizations to stop working until that other organization updates their federation configuration:</span></span>
>
> - <span data-ttu-id="be59c-114">任何使用旧直接联盟模型 (也称为允许的合作伙伴服务器) 的联合组织都需要更新其组织的允许域条目，以删除代理 FQDN。</span><span class="sxs-lookup"><span data-stu-id="be59c-114">Any federated organizations that are using the older Direct Federation model (also known as Allowed Partner Server) will need to update their allowed domain entries for their organization to remove the proxy FQDN.</span></span> <span data-ttu-id="be59c-115">此旧联盟模型不基于 DNS SRV 记录，因此，一旦组织移动到云，此类配置将过期。</span><span class="sxs-lookup"><span data-stu-id="be59c-115">This legacy federation model is not based on DNS SRV records, so such a configuration will become out of date once your organization moves to the cloud.</span></span>
> 
> - <span data-ttu-id="be59c-116">没有启用 sipfed.online.lync 的宿主提供商的任何联盟组织。 <span>com 将需要更新其配置才能启用。</span><span class="sxs-lookup"><span data-stu-id="be59c-116">Any federated organization that does not have an enabled hosting provider for sipfed.online.lync.<span>com will need to update their configuration to enable that.</span></span> <span data-ttu-id="be59c-117">这种情况只有在联盟组织完全在本地且从未与任何混合或联机租户联盟时才能实现。</span><span class="sxs-lookup"><span data-stu-id="be59c-117">This situation is only possible if the federated organization is purely on-premises and has never federated with any hybrid or online tenant.</span></span> <span data-ttu-id="be59c-118">在这种情况下，在启用其宿主提供商之前，与这些组织的联盟将不起作用。</span><span class="sxs-lookup"><span data-stu-id="be59c-118">In such a case, federation with these organizations will not work until they enable their hosting provider.</span></span>
>
> <span data-ttu-id="be59c-119">如果您怀疑您的任何联盟伙伴可能正在使用直接联盟，或者未与任何联机或混合组织联盟，我们建议您在准备完成迁移到云时发送有关此内容的通信。</span><span class="sxs-lookup"><span data-stu-id="be59c-119">If you suspect that any of your federated partners may be using Direct Federation or have not federated with any online or hybrid organization, we suggest you send them a communication about this as you prepare to complete your migration to the cloud.</span></span>

## <a name="how-to-identify-stale-dns-records"></a><span data-ttu-id="be59c-120">如何识别过时的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="be59c-120">How to identify stale DNS records</span></span>

<span data-ttu-id="be59c-121">若要确定任何阻止组织成为仅Teams DNS 记录，可以使用 Teams 管理中心将共存模式更改为 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="be59c-121">To identify any DNS records that prevent your organization from becoming all Teams Only, you can use the Teams admin center  to change the coexistence mode to TeamsOnly.</span></span> <span data-ttu-id="be59c-122">转到"**组织范围的设置Teams**  ->  **升级"。**</span><span class="sxs-lookup"><span data-stu-id="be59c-122">Go to **Org-wide setting** -> **Teams Upgrade**.</span></span> <span data-ttu-id="be59c-123">任何阻止组织成为Teams仅 DNS 记录都将包含在错误消息中。</span><span class="sxs-lookup"><span data-stu-id="be59c-123">Any DNS records that prevent the organization from becoming Teams Only will be included in the error message.</span></span>  <span data-ttu-id="be59c-124">如果未找到 DNS 记录，组织的共存模式将更改为 TeamsOnly。</span><span class="sxs-lookup"><span data-stu-id="be59c-124">In the event no DNS records are found, the coexistence mode for your organization will be changed to TeamsOnly.</span></span> 

## <a name="how-to-remove-stale-dns-records"></a><span data-ttu-id="be59c-125">如何删除过时的 DNS 记录</span><span class="sxs-lookup"><span data-stu-id="be59c-125">How to remove stale DNS records</span></span>

<span data-ttu-id="be59c-126">如果您的组织不再具有任何本地 Skype for Business Server Lync Server 用户，则必须执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="be59c-126">If your organization no longer has any on-premises Skype for Business Server or Lync Server users, you must do the following:</span></span>

- <span data-ttu-id="be59c-127">将Skype for Business DNS 记录更新为指向Microsoft 365 (，而不是本地部署) 。</span><span class="sxs-lookup"><span data-stu-id="be59c-127">Update Skype for Business DNS records to point to Microsoft 365 (instead of the on-premises deployment).</span></span>

- <span data-ttu-id="be59c-128">如果Skype for Business SIP 域，请删除 DNS 记录。</span><span class="sxs-lookup"><span data-stu-id="be59c-128">Remove Skype for Business DNS records if the SIP domain is no longer used.</span></span> 

<span data-ttu-id="be59c-129">在找到以下任一记录的每个域中，按如下方式更新这些记录：</span><span class="sxs-lookup"><span data-stu-id="be59c-129">In each domain where you find any of the following records, update them as follows:</span></span>

| <span data-ttu-id="be59c-130">记录类型</span><span class="sxs-lookup"><span data-stu-id="be59c-130">Record type</span></span> | <span data-ttu-id="be59c-131">名称</span><span class="sxs-lookup"><span data-stu-id="be59c-131">Name</span></span> | <span data-ttu-id="be59c-132">TTL</span><span class="sxs-lookup"><span data-stu-id="be59c-132">TTL</span></span> | <span data-ttu-id="be59c-133">优先级</span><span class="sxs-lookup"><span data-stu-id="be59c-133">Priority</span></span> | <span data-ttu-id="be59c-134">粗细</span><span class="sxs-lookup"><span data-stu-id="be59c-134">Weight</span></span> | <span data-ttu-id="be59c-135">端口</span><span class="sxs-lookup"><span data-stu-id="be59c-135">Port</span></span> | <span data-ttu-id="be59c-136">值</span><span class="sxs-lookup"><span data-stu-id="be59c-136">Value</span></span> |
| :-----| :-----| :---- | :-----| :-----| :-----| :-----|
| <span data-ttu-id="be59c-137">SRV</span><span class="sxs-lookup"><span data-stu-id="be59c-137">SRV</span></span> | <span data-ttu-id="be59c-138">_sipfederationtls.tcp</span><span class="sxs-lookup"><span data-stu-id="be59c-138">_sipfederationtls.tcp</span></span> | <span data-ttu-id="be59c-139">3600</span><span class="sxs-lookup"><span data-stu-id="be59c-139">3600</span></span> |  <span data-ttu-id="be59c-140">100</span><span class="sxs-lookup"><span data-stu-id="be59c-140">100</span></span> | <span data-ttu-id="be59c-141">1</span><span class="sxs-lookup"><span data-stu-id="be59c-141">1</span></span> | <span data-ttu-id="be59c-142">5061</span><span class="sxs-lookup"><span data-stu-id="be59c-142">5061</span></span>  | <span data-ttu-id="be59c-143">sipfed.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="be59c-143">sipfed.online.lync.com</span></span> |
| <span data-ttu-id="be59c-144">SRV</span><span class="sxs-lookup"><span data-stu-id="be59c-144">SRV</span></span> | <span data-ttu-id="be59c-145">_sip.tls</span><span class="sxs-lookup"><span data-stu-id="be59c-145">_sip.tls</span></span> | <span data-ttu-id="be59c-146">3600</span><span class="sxs-lookup"><span data-stu-id="be59c-146">3600</span></span>  | <span data-ttu-id="be59c-147">100</span><span class="sxs-lookup"><span data-stu-id="be59c-147">100</span></span> |    <span data-ttu-id="be59c-148">1</span><span class="sxs-lookup"><span data-stu-id="be59c-148">1</span></span>   | <span data-ttu-id="be59c-149">443</span><span class="sxs-lookup"><span data-stu-id="be59c-149">443</span></span>   | <span data-ttu-id="be59c-150">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="be59c-150">sipdir.online.lync.com</span></span> |
| <span data-ttu-id="be59c-151">CNAME</span><span class="sxs-lookup"><span data-stu-id="be59c-151">CNAME</span></span> | <span data-ttu-id="be59c-152">lyncdiscover</span><span class="sxs-lookup"><span data-stu-id="be59c-152">lyncdiscover</span></span> |    <span data-ttu-id="be59c-153">3600</span><span class="sxs-lookup"><span data-stu-id="be59c-153">3600</span></span> |  <span data-ttu-id="be59c-154">不适用</span><span class="sxs-lookup"><span data-stu-id="be59c-154">N/A</span></span> |   <span data-ttu-id="be59c-155">不适用</span><span class="sxs-lookup"><span data-stu-id="be59c-155">N/A</span></span> |   <span data-ttu-id="be59c-156">不适用</span><span class="sxs-lookup"><span data-stu-id="be59c-156">N/A</span></span> |   <span data-ttu-id="be59c-157">webdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="be59c-157">webdir.online.lync.com</span></span> |
| <span data-ttu-id="be59c-158">CNAME</span><span class="sxs-lookup"><span data-stu-id="be59c-158">CNAME</span></span> |   <span data-ttu-id="be59c-159">sip</span><span class="sxs-lookup"><span data-stu-id="be59c-159">sip</span></span> | <span data-ttu-id="be59c-160">3600</span><span class="sxs-lookup"><span data-stu-id="be59c-160">3600</span></span> |    <span data-ttu-id="be59c-161">不适用</span><span class="sxs-lookup"><span data-stu-id="be59c-161">N/A</span></span> |   <span data-ttu-id="be59c-162">不适用</span><span class="sxs-lookup"><span data-stu-id="be59c-162">N/A</span></span>  | <span data-ttu-id="be59c-163">不适用</span><span class="sxs-lookup"><span data-stu-id="be59c-163">N/A</span></span> |    <span data-ttu-id="be59c-164">sipdir.online.lync.com</span><span class="sxs-lookup"><span data-stu-id="be59c-164">sipdir.online.lync.com</span></span> |
|||||||




