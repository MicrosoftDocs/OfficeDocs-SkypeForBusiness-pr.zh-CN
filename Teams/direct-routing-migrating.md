---
title: 迁移到直接路由
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: 从 Skype for Business Online 和 Teams 配置角度了解迁移到直接路由所需的内容。
ms.openlocfilehash: fa7a3e09d4f79328545bff29b2f440ba0bfe6990
ms.sourcegitcommit: 1a08ec9069332e19135312d35fc6a6c3247ce2d2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/11/2020
ms.locfileid: "41888581"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="90c5d-103">迁移到直接路由</span><span class="sxs-lookup"><span data-stu-id="90c5d-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="90c5d-104">本文从 Skype for Business Online 和 Microsoft Teams 配置角度描述迁移到直接路由所需的内容。</span><span class="sxs-lookup"><span data-stu-id="90c5d-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="90c5d-105">本文介绍了如何从以下各项进行迁移：</span><span class="sxs-lookup"><span data-stu-id="90c5d-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="90c5d-106">Office 365 电话系统，含通话套餐（适用于 Teams 和 Skype for Business Online）</span><span class="sxs-lookup"><span data-stu-id="90c5d-106">Office 365 Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="90c5d-107">使用 Skype for Business Server 中本地 PSTN 连接的 Office 365 电话系统（适用于 Skype for Business Online）
</span><span class="sxs-lookup"><span data-stu-id="90c5d-107">Office 365 Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="90c5d-108">通过使用云连接器版本使用本地 PSTN 连接的 Office 365 电话系统（适用于 Skype for Business Online）
</span><span class="sxs-lookup"><span data-stu-id="90c5d-108">Office 365 Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>


<span data-ttu-id="90c5d-109">除了这些配置步骤外，还需要在会话边界控制器 (SBC) 上进行配置，才能将通话转接到新的路由。</span><span class="sxs-lookup"><span data-stu-id="90c5d-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="90c5d-110">那超出了本文档的范畴。</span><span class="sxs-lookup"><span data-stu-id="90c5d-110">That is outside the scope of this document.</span></span> <span data-ttu-id="90c5d-111">有关详细信息，请参阅 SBC 供应商文档。</span><span class="sxs-lookup"><span data-stu-id="90c5d-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="90c5d-112">用于各种 PSTN 连接选项的用户预配结束状态</span><span class="sxs-lookup"><span data-stu-id="90c5d-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="90c5d-113">下表显示了为 Office 365 电话系统选定 PSTN 连接选项配置的用户预配结束状态。</span><span class="sxs-lookup"><span data-stu-id="90c5d-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Office 365 Phone System.</span></span> <span data-ttu-id="90c5d-114">仅显示与语音相关的属性。</span><span class="sxs-lookup"><span data-stu-id="90c5d-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="90c5d-115">用户对象属性</span><span class="sxs-lookup"><span data-stu-id="90c5d-115">User object attributes</span></span> |<span data-ttu-id="90c5d-116">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="90c5d-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="90c5d-117">通过 Skype for Business Server 使用本地 PSTN 连接的电话系统
</span><span class="sxs-lookup"><span data-stu-id="90c5d-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="90c5d-118">通过云连接器使用本地 PSTN 连接的电话系统</span><span class="sxs-lookup"><span data-stu-id="90c5d-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="90c5d-119">通过直接路由使用本地 PSTN 连接的电话系统</span><span class="sxs-lookup"><span data-stu-id="90c5d-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="90c5d-120">客户端</span><span class="sxs-lookup"><span data-stu-id="90c5d-120">Client</span></span>|<span data-ttu-id="90c5d-121">Skype For Business 或 Teams</span><span class="sxs-lookup"><span data-stu-id="90c5d-121">Skype for Business or Teams</span></span> |<span data-ttu-id="90c5d-122">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="90c5d-122">Skype for Business</span></span> |<span data-ttu-id="90c5d-123">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="90c5d-123">Skype for Business</span></span> |<span data-ttu-id="90c5d-124">Teams</span><span class="sxs-lookup"><span data-stu-id="90c5d-124">Teams</span></span>|
|<span data-ttu-id="90c5d-125">许可证</span><span class="sxs-lookup"><span data-stu-id="90c5d-125">Licenses</span></span>|<span data-ttu-id="90c5d-126">Skype Business Online</span><span class="sxs-lookup"><span data-stu-id="90c5d-126">Skype Business Online</span></span></br><span data-ttu-id="90c5d-127">套餐 2</span><span class="sxs-lookup"><span data-stu-id="90c5d-127">Plan 2</span></span></br></br><span data-ttu-id="90c5d-128">MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="90c5d-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="90c5d-129">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="90c5d-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="90c5d-130">通话套餐</span><span class="sxs-lookup"><span data-stu-id="90c5d-130">Calling Plans</span></span></br><span data-ttu-id="90c5d-131">Teams</span><span class="sxs-lookup"><span data-stu-id="90c5d-131">Teams</span></span>|<span data-ttu-id="90c5d-132">Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="90c5d-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="90c5d-133">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="90c5d-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="90c5d-134">Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="90c5d-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="90c5d-135">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="90c5d-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="90c5d-136">Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="90c5d-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="90c5d-137">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="90c5d-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="90c5d-138">Teams</span><span class="sxs-lookup"><span data-stu-id="90c5d-138">Teams</span></span>|
<span data-ttu-id="90c5d-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="90c5d-139">OnPremLineURI</span></span> |<span data-ttu-id="90c5d-140">不适用</span><span class="sxs-lookup"><span data-stu-id="90c5d-140">N/A</span></span>|<span data-ttu-id="90c5d-141">电话号码必须与本地 AD 同步。</span><span class="sxs-lookup"><span data-stu-id="90c5d-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="90c5d-142">可在本地 Active Directory 或 Azure Active Directory 中管理电话号码。</span><span class="sxs-lookup"><span data-stu-id="90c5d-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="90c5d-143">可在本地 Active Directory 或 Azure Active Directory 中管理电话号码。</span><span class="sxs-lookup"><span data-stu-id="90c5d-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="90c5d-144">但是，如果组织有本地 Skype for Business，则该号码必须与本地 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="90c5d-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="90c5d-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="90c5d-145">LineURI</span></span>|<span data-ttu-id="90c5d-146">PSTN 通话电话号码</span><span class="sxs-lookup"><span data-stu-id="90c5d-146">PSTN Calling phone number</span></span>|<span data-ttu-id="90c5d-147">从 OnPremLineURI 参数自动设置</span><span class="sxs-lookup"><span data-stu-id="90c5d-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="90c5d-148">从 OnPremLineURI 参数自动设置</span><span class="sxs-lookup"><span data-stu-id="90c5d-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="90c5d-149">从 OnPremLineURI 参数自动设置</span><span class="sxs-lookup"><span data-stu-id="90c5d-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="90c5d-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="90c5d-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="90c5d-151">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-151">True</span></span>|<span data-ttu-id="90c5d-152">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-152">True</span></span>|<span data-ttu-id="90c5d-153">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-153">True</span></span>|<span data-ttu-id="90c5d-154">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-154">True</span></span>|
|<span data-ttu-id="90c5d-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="90c5d-155">HostedVoiceMail</span></span> |<span data-ttu-id="90c5d-156">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-156">True</span></span>|<span data-ttu-id="90c5d-157">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-157">True</span></span>|<span data-ttu-id="90c5d-158">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-158">True</span></span>|<span data-ttu-id="90c5d-159">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-159">True</span></span>|
|<span data-ttu-id="90c5d-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-160">VoicePolicy</span></span>|<span data-ttu-id="90c5d-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-161">BusinessVoice</span></span>|<span data-ttu-id="90c5d-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-162">HybridVoice</span></span>|<span data-ttu-id="90c5d-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-163">HybridVoice</span></span>|<span data-ttu-id="90c5d-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-164">HybridVoice</span></span>|
|<span data-ttu-id="90c5d-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="90c5d-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-166">BusinessVoice</span></span>|<span data-ttu-id="90c5d-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-167">BusinessVoice</span></span>|<span data-ttu-id="90c5d-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-168">BusinessVoice</span></span>|<span data-ttu-id="90c5d-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="90c5d-169">BusinessVoice</span></span>|
|<span data-ttu-id="90c5d-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="90c5d-171">具有值</span><span class="sxs-lookup"><span data-stu-id="90c5d-171">Has a value</span></span>|<span data-ttu-id="90c5d-172">具有值</span><span class="sxs-lookup"><span data-stu-id="90c5d-172">Has a value</span></span>|<span data-ttu-id="90c5d-173">具有值</span><span class="sxs-lookup"><span data-stu-id="90c5d-173">Has a value</span></span>|<span data-ttu-id="90c5d-174">不适用</span><span class="sxs-lookup"><span data-stu-id="90c5d-174">N/A</span></span>|
|<span data-ttu-id="90c5d-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="90c5d-176">$Null</span><span class="sxs-lookup"><span data-stu-id="90c5d-176">$Null</span></span>|<span data-ttu-id="90c5d-177">$Null</span><span class="sxs-lookup"><span data-stu-id="90c5d-177">$Null</span></span>|<span data-ttu-id="90c5d-178">$Null</span><span class="sxs-lookup"><span data-stu-id="90c5d-178">$Null</span></span>|<span data-ttu-id="90c5d-179">具有值</span><span class="sxs-lookup"><span data-stu-id="90c5d-179">Has a value</span></span>|
|<span data-ttu-id="90c5d-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="90c5d-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="90c5d-181">TeamsOnly, SfBOnly</span><span class="sxs-lookup"><span data-stu-id="90c5d-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="90c5d-182">$Null</span><span class="sxs-lookup"><span data-stu-id="90c5d-182">$Null</span></span>|<span data-ttu-id="90c5d-183">$Null</span><span class="sxs-lookup"><span data-stu-id="90c5d-183">$Null</span></span>|<span data-ttu-id="90c5d-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="90c5d-184">TeamsOnly</span></span>|
|<span data-ttu-id="90c5d-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="90c5d-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="90c5d-186">AllowPrivateCalling</span></span>|<span data-ttu-id="90c5d-187">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-187">True</span></span>|<span data-ttu-id="90c5d-188">不适用</span><span class="sxs-lookup"><span data-stu-id="90c5d-188">N/A</span></span>|<span data-ttu-id="90c5d-189">不适用</span><span class="sxs-lookup"><span data-stu-id="90c5d-189">N/A</span></span>|<span data-ttu-id="90c5d-190">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-190">True</span></span>|
|<span data-ttu-id="90c5d-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="90c5d-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="90c5d-192">AllowGroupCalling</span></span>|<span data-ttu-id="90c5d-193">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-193">True</span></span>|<span data-ttu-id="90c5d-194">不适用</span><span class="sxs-lookup"><span data-stu-id="90c5d-194">N/A</span></span>|<span data-ttu-id="90c5d-195">不适用</span><span class="sxs-lookup"><span data-stu-id="90c5d-195">N/A</span></span>|<span data-ttu-id="90c5d-196">True</span><span class="sxs-lookup"><span data-stu-id="90c5d-196">True</span></span>|
||||||

<span data-ttu-id="90c5d-197"><sup>1</sup>选择 TeamsUpgradePolicy 的正确模式取决于方案。</span><span class="sxs-lookup"><span data-stu-id="90c5d-197"><sup>1</sup> Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="90c5d-198">请阅读了解[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)中各种模式的语音体验。</span><span class="sxs-lookup"><span data-stu-id="90c5d-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="90c5d-199">作为此工作的一部分，Microsoft 最近更新了“Microsoft Teams 管理中心”（也称为“新式门户”），以反映基于共存模式的新管理模型。</span><span class="sxs-lookup"><span data-stu-id="90c5d-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="90c5d-200">在新式门户中，配置 TeamsUpgradePolicy 也会立即将 TeamsInteropPolicy 自动设置为一致的值，因此不会再在用户界面中公开 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="90c5d-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="90c5d-201">但是，使用 PowerShell 的管理员仍然必须同时设置 TeamsUpgradePolicy 和 TeamsInteropPolicy，以确保正确转接。</span><span class="sxs-lookup"><span data-stu-id="90c5d-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="90c5d-202">完成到 TeamsUpgradePolicy 的转换后，将不再需要设置 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="90c5d-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="90c5d-203">有关详细信息，请参阅[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="90c5d-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="90c5d-204">从通话套餐迁移</span><span class="sxs-lookup"><span data-stu-id="90c5d-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="90c5d-205">有关从通话套餐迁移的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="90c5d-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="90c5d-206">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="90c5d-206">Set up Calling Plans</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="90c5d-207">Set-CsOnlineVoice 用户</span><span class="sxs-lookup"><span data-stu-id="90c5d-207">Set-CsOnlineVoice User</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="90c5d-208">Get-CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="90c5d-208">Get-CsOnlineLisLocation</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="90c5d-209">建议删除以前配置的许可证计划信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="90c5d-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```powershell
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="90c5d-210">在 Skype for Business Server 中使用本地 PSTN 连接从 Office 365 电话系统迁移
</span><span class="sxs-lookup"><span data-stu-id="90c5d-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="90c5d-211">有关在 Skype for Business Server 中使用本地 PSTN 连接从电话系统迁移的详细信息，请参阅以下内容：
</span><span class="sxs-lookup"><span data-stu-id="90c5d-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="90c5d-212">规划</span><span class="sxs-lookup"><span data-stu-id="90c5d-212">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="90c5d-213">部署</span><span class="sxs-lookup"><span data-stu-id="90c5d-213">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="90c5d-214">建议删除以前配置的语音转接信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="90c5d-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> [!NOTE]
> <span data-ttu-id="90c5d-215">如果配置了全局 CsVoiceRoutingPolicy，建议你删除与此全局策略关联的任何 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="90c5d-215">If a global CsVoiceRoutingPolicy is configured, it is recommended that you remove any PSTN usages associated with this global policy.</span></span> 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="90c5d-216">通过云连接器版本使用本地 PSTN 连接从 Office 365 电话系统迁移
</span><span class="sxs-lookup"><span data-stu-id="90c5d-216">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

<span data-ttu-id="90c5d-217">有关通过云连接器版本使用本地 PSTN 连接从电话系统迁移的详细信息，请参阅以下内容：
</span><span class="sxs-lookup"><span data-stu-id="90c5d-217">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="90c5d-218">规划</span><span class="sxs-lookup"><span data-stu-id="90c5d-218">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="90c5d-219">部署</span><span class="sxs-lookup"><span data-stu-id="90c5d-219">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="90c5d-220">用户配置</span><span class="sxs-lookup"><span data-stu-id="90c5d-220">User configuration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="90c5d-221">建议删除以前配置的语音转接信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="90c5d-221">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```PowerShell
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="90c5d-222">相关链接</span><span class="sxs-lookup"><span data-stu-id="90c5d-222">Related links</span></span>

[<span data-ttu-id="90c5d-223">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="90c5d-223">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="90c5d-224">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-224">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="90c5d-225">Get-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-225">Get-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="90c5d-226">New-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-226">New-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="90c5d-227">Remove-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-227">Remove-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="90c5d-228">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="90c5d-228">Set-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="90c5d-229">Get-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="90c5d-229">Get-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="90c5d-230">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="90c5d-230">Set-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

