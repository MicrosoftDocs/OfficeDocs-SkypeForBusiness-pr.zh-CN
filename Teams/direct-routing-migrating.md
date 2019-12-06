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
description: 从 Skype for Business Online 和 Teams 配置角度了解迁移到直接路由所需的内容。
ms.openlocfilehash: dd0b2cd1ac6014ea0f6c79a46314eb4e3d5e0380
ms.sourcegitcommit: 96d98e145ff300833d827a7d43b4e4b0331b7538
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871708"
---
# <a name="migrate-to-direct-routing"></a><span data-ttu-id="0616a-103">迁移到直接路由</span><span class="sxs-lookup"><span data-stu-id="0616a-103">Migrate to Direct Routing</span></span>

<span data-ttu-id="0616a-104">本文从 Skype for Business Online 和 Microsoft Teams 配置角度描述迁移到直接路由所需的内容。</span><span class="sxs-lookup"><span data-stu-id="0616a-104">This article describes what is needed to migrate to Direct Routing from a Skype for Business Online and Microsoft Teams configuration perspective.</span></span> <span data-ttu-id="0616a-105">本文介绍了如何从以下各项进行迁移：</span><span class="sxs-lookup"><span data-stu-id="0616a-105">This article covers migrating from the following:</span></span> 
 
- <span data-ttu-id="0616a-106">Office 365 电话系统，含通话套餐（适用于 Teams 和 Skype for Business Online）</span><span class="sxs-lookup"><span data-stu-id="0616a-106">Office 365 Phone System with Calling Plans (for Teams and Skype for Business Online)</span></span> 
- <span data-ttu-id="0616a-107">使用 Skype for Business Server 中本地 PSTN 连接的 Office 365 电话系统（适用于 Skype for Business Online）
</span><span class="sxs-lookup"><span data-stu-id="0616a-107">Office 365 Phone System with on-premises PSTN Connectivity in Skype for Business Server (for Skype for Business Online)</span></span>  
- <span data-ttu-id="0616a-108">通过使用云连接器版本使用本地 PSTN 连接的 Office 365 电话系统（适用于 Skype for Business Online）
</span><span class="sxs-lookup"><span data-stu-id="0616a-108">Office 365 Phone System with on-premises PSTN Connectivity by using the Cloud Connector Edition (for Skype for Business Online)</span></span>

  
<span data-ttu-id="0616a-109">除了这些配置步骤外，还需要在会话边界控制器 (SBC) 上进行配置，才能将通话转接到新的路由。</span><span class="sxs-lookup"><span data-stu-id="0616a-109">In addition to these configuration steps, configuration is also required on the Session Border Controller (SBC) to route the calls to the new route.</span></span> <span data-ttu-id="0616a-110">那超出了本文档的范畴。</span><span class="sxs-lookup"><span data-stu-id="0616a-110">That is outside the scope of this document.</span></span> <span data-ttu-id="0616a-111">有关详细信息，请参阅 SBC 供应商文档。</span><span class="sxs-lookup"><span data-stu-id="0616a-111">For more information, see your SBC vendor documentation.</span></span>  

## <a name="user-provisioning-end-state-for-various-pstn-connectivity-options"></a><span data-ttu-id="0616a-112">用于各种 PSTN 连接选项的用户预配结束状态</span><span class="sxs-lookup"><span data-stu-id="0616a-112">User provisioning end-state for various PSTN connectivity options</span></span> 

<span data-ttu-id="0616a-113">下表显示了为 Office 365 电话系统选定 PSTN 连接选项配置的用户预配结束状态。</span><span class="sxs-lookup"><span data-stu-id="0616a-113">The following table shows the end-state for a user provisioned for the selected PSTN connectivity options with Office 365 Phone System.</span></span> <span data-ttu-id="0616a-114">仅显示与语音相关的属性。</span><span class="sxs-lookup"><span data-stu-id="0616a-114">Only attributes relevant for voice are shown.</span></span>

|<span data-ttu-id="0616a-115">用户对象属性</span><span class="sxs-lookup"><span data-stu-id="0616a-115">User object attributes</span></span> |<span data-ttu-id="0616a-116">具有通话套餐的电话系统</span><span class="sxs-lookup"><span data-stu-id="0616a-116">Phone System with Calling Plans</span></span>|<span data-ttu-id="0616a-117">通过 Skype for Business Server 使用本地 PSTN 连接的电话系统
</span><span class="sxs-lookup"><span data-stu-id="0616a-117">Phone System with on-premises PSTN connectivity via Skype for Business Server</span></span>|<span data-ttu-id="0616a-118">通过云连接器使用本地 PSTN 连接的电话系统</span><span class="sxs-lookup"><span data-stu-id="0616a-118">Phone System with on-premises PSTN connectivity via Cloud Connector</span></span>|<span data-ttu-id="0616a-119">通过直接路由使用本地 PSTN 连接的电话系统</span><span class="sxs-lookup"><span data-stu-id="0616a-119">Phone System with on-premises PSTN connectivity via Direct Routing</span></span>|
|---|---|---|---|---|
|<span data-ttu-id="0616a-120">客户端</span><span class="sxs-lookup"><span data-stu-id="0616a-120">Client</span></span>|<span data-ttu-id="0616a-121">Skype For Business 或 Teams</span><span class="sxs-lookup"><span data-stu-id="0616a-121">Skype for Business or Teams</span></span> |<span data-ttu-id="0616a-122">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0616a-122">Skype for Business</span></span> |<span data-ttu-id="0616a-123">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="0616a-123">Skype for Business</span></span> |<span data-ttu-id="0616a-124">Teams</span><span class="sxs-lookup"><span data-stu-id="0616a-124">Teams</span></span>|
|<span data-ttu-id="0616a-125">许可证</span><span class="sxs-lookup"><span data-stu-id="0616a-125">Licenses</span></span>|<span data-ttu-id="0616a-126">Skype Business Online</span><span class="sxs-lookup"><span data-stu-id="0616a-126">Skype Business Online</span></span></br><span data-ttu-id="0616a-127">套餐 2</span><span class="sxs-lookup"><span data-stu-id="0616a-127">Plan 2</span></span></br></br><span data-ttu-id="0616a-128">MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="0616a-128">MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="0616a-129">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="0616a-129">Phone System (MCOEV)</span></span></br></br></br><span data-ttu-id="0616a-130">通话套餐</span><span class="sxs-lookup"><span data-stu-id="0616a-130">Calling Plans</span></span></br><span data-ttu-id="0616a-131">Teams</span><span class="sxs-lookup"><span data-stu-id="0616a-131">Teams</span></span>|<span data-ttu-id="0616a-132">Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="0616a-132">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="0616a-133">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="0616a-133">Phone System (MCOEV)</span></span>|<span data-ttu-id="0616a-134">Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD）</span><span class="sxs-lookup"><span data-stu-id="0616a-134">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD)</span></span></br></br></br><span data-ttu-id="0616a-135">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="0616a-135">Phone System (MCOEV)</span></span>|<span data-ttu-id="0616a-136">Skype Business Online 套餐 2（MCOProfessional 或 MCOSTANDARD</span><span class="sxs-lookup"><span data-stu-id="0616a-136">Skype Business Online Plan 2 (MCOProfessional or MCOSTANDARD</span></span></br></br></br><span data-ttu-id="0616a-137">电话系统 (MCOEV)</span><span class="sxs-lookup"><span data-stu-id="0616a-137">Phone System (MCOEV)</span></span></br></br><span data-ttu-id="0616a-138">Teams</span><span class="sxs-lookup"><span data-stu-id="0616a-138">Teams</span></span>|
<span data-ttu-id="0616a-139">OnPremLineURI</span><span class="sxs-lookup"><span data-stu-id="0616a-139">OnPremLineURI</span></span> |<span data-ttu-id="0616a-140">不适用</span><span class="sxs-lookup"><span data-stu-id="0616a-140">N/A</span></span>|<span data-ttu-id="0616a-141">电话号码必须与本地 AD 同步。</span><span class="sxs-lookup"><span data-stu-id="0616a-141">The phone number  must be synced from the on-premises AD.</span></span> |<span data-ttu-id="0616a-142">可在本地 Active Directory 或 Azure Active Directory 中管理电话号码。</span><span class="sxs-lookup"><span data-stu-id="0616a-142">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span>|<span data-ttu-id="0616a-143">可在本地 Active Directory 或 Azure Active Directory 中管理电话号码。</span><span class="sxs-lookup"><span data-stu-id="0616a-143">The phone number can be managed either in on-premises Active Directory or in Azure Active Directory.</span></span> <span data-ttu-id="0616a-144">但是，如果组织有本地 Skype for Business，则该号码必须与本地 Active Directory 同步。</span><span class="sxs-lookup"><span data-stu-id="0616a-144">However, if the organization has on-premises Skype for Business, the number must be synced from the on-premises Active Directory.</span></span>|
|<span data-ttu-id="0616a-145">LineURI</span><span class="sxs-lookup"><span data-stu-id="0616a-145">LineURI</span></span>|<span data-ttu-id="0616a-146">PSTN 通话电话号码</span><span class="sxs-lookup"><span data-stu-id="0616a-146">PSTN Calling phone number</span></span>|<span data-ttu-id="0616a-147">从 OnPremLineURI 参数自动设置</span><span class="sxs-lookup"><span data-stu-id="0616a-147">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="0616a-148">从 OnPremLineURI 参数自动设置</span><span class="sxs-lookup"><span data-stu-id="0616a-148">Set automatically from the OnPremLineURI parameter</span></span>|<span data-ttu-id="0616a-149">从 OnPremLineURI 参数自动设置</span><span class="sxs-lookup"><span data-stu-id="0616a-149">Set automatically from the OnPremLineURI parameter</span></span>|
|<span data-ttu-id="0616a-150">EnterpriseVoiceEnabled</span><span class="sxs-lookup"><span data-stu-id="0616a-150">EnterpriseVoiceEnabled</span></span>|<span data-ttu-id="0616a-151">True</span><span class="sxs-lookup"><span data-stu-id="0616a-151">True</span></span>|<span data-ttu-id="0616a-152">True</span><span class="sxs-lookup"><span data-stu-id="0616a-152">True</span></span>|<span data-ttu-id="0616a-153">True</span><span class="sxs-lookup"><span data-stu-id="0616a-153">True</span></span>|<span data-ttu-id="0616a-154">True</span><span class="sxs-lookup"><span data-stu-id="0616a-154">True</span></span>|
|<span data-ttu-id="0616a-155">HostedVoiceMail</span><span class="sxs-lookup"><span data-stu-id="0616a-155">HostedVoiceMail</span></span> |<span data-ttu-id="0616a-156">True</span><span class="sxs-lookup"><span data-stu-id="0616a-156">True</span></span>|<span data-ttu-id="0616a-157">True</span><span class="sxs-lookup"><span data-stu-id="0616a-157">True</span></span>|<span data-ttu-id="0616a-158">True</span><span class="sxs-lookup"><span data-stu-id="0616a-158">True</span></span>|<span data-ttu-id="0616a-159">True</span><span class="sxs-lookup"><span data-stu-id="0616a-159">True</span></span>|
|<span data-ttu-id="0616a-160">VoicePolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-160">VoicePolicy</span></span>|<span data-ttu-id="0616a-161">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-161">BusinessVoice</span></span>|<span data-ttu-id="0616a-162">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-162">HybridVoice</span></span>|<span data-ttu-id="0616a-163">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-163">HybridVoice</span></span>|<span data-ttu-id="0616a-164">HybridVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-164">HybridVoice</span></span>|
|<span data-ttu-id="0616a-165">HostedVoiceMailPolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-165">HostedVoiceMailPolicy</span></span> |<span data-ttu-id="0616a-166">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-166">BusinessVoice</span></span>|<span data-ttu-id="0616a-167">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-167">BusinessVoice</span></span>|<span data-ttu-id="0616a-168">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-168">BusinessVoice</span></span>|<span data-ttu-id="0616a-169">BusinessVoice</span><span class="sxs-lookup"><span data-stu-id="0616a-169">BusinessVoice</span></span>|
|<span data-ttu-id="0616a-170">VoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-170">VoiceRoutingPolicy</span></span>|<span data-ttu-id="0616a-171">具有值</span><span class="sxs-lookup"><span data-stu-id="0616a-171">Has a value</span></span>|<span data-ttu-id="0616a-172">具有值</span><span class="sxs-lookup"><span data-stu-id="0616a-172">Has a value</span></span>|<span data-ttu-id="0616a-173">具有值</span><span class="sxs-lookup"><span data-stu-id="0616a-173">Has a value</span></span>|<span data-ttu-id="0616a-174">不适用</span><span class="sxs-lookup"><span data-stu-id="0616a-174">N/A</span></span>|
|<span data-ttu-id="0616a-175">OnlineVoiceRoutingPolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-175">OnlineVoiceRoutingPolicy</span></span>|<span data-ttu-id="0616a-176">$Null</span><span class="sxs-lookup"><span data-stu-id="0616a-176">$Null</span></span>|<span data-ttu-id="0616a-177">$Null</span><span class="sxs-lookup"><span data-stu-id="0616a-177">$Null</span></span>|<span data-ttu-id="0616a-178">$Null</span><span class="sxs-lookup"><span data-stu-id="0616a-178">$Null</span></span>|<span data-ttu-id="0616a-179">具有值</span><span class="sxs-lookup"><span data-stu-id="0616a-179">Has a value</span></span>|
|<span data-ttu-id="0616a-180">TeamsUpgradePolicy<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="0616a-180">TeamsUpgradePolicy<sup>1</sup></span></span>|<span data-ttu-id="0616a-181">TeamsOnly, SfBOnly</span><span class="sxs-lookup"><span data-stu-id="0616a-181">TeamsOnly, SfBOnly</span></span>|<span data-ttu-id="0616a-182">$Null</span><span class="sxs-lookup"><span data-stu-id="0616a-182">$Null</span></span>|<span data-ttu-id="0616a-183">$Null</span><span class="sxs-lookup"><span data-stu-id="0616a-183">$Null</span></span>|<span data-ttu-id="0616a-184">TeamsOnly</span><span class="sxs-lookup"><span data-stu-id="0616a-184">TeamsOnly</span></span>|
|<span data-ttu-id="0616a-185">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-185">TeamsCallingPolicy</span></span></br><span data-ttu-id="0616a-186">AllowPrivateCalling</span><span class="sxs-lookup"><span data-stu-id="0616a-186">AllowPrivateCalling</span></span>|<span data-ttu-id="0616a-187">True</span><span class="sxs-lookup"><span data-stu-id="0616a-187">True</span></span>|<span data-ttu-id="0616a-188">不适用</span><span class="sxs-lookup"><span data-stu-id="0616a-188">N/A</span></span>|<span data-ttu-id="0616a-189">不适用</span><span class="sxs-lookup"><span data-stu-id="0616a-189">N/A</span></span>|<span data-ttu-id="0616a-190">True</span><span class="sxs-lookup"><span data-stu-id="0616a-190">True</span></span>|
|<span data-ttu-id="0616a-191">TeamsCallingPolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-191">TeamsCallingPolicy</span></span></br><span data-ttu-id="0616a-192">AllowGroupCalling</span><span class="sxs-lookup"><span data-stu-id="0616a-192">AllowGroupCalling</span></span>|<span data-ttu-id="0616a-193">True</span><span class="sxs-lookup"><span data-stu-id="0616a-193">True</span></span>|<span data-ttu-id="0616a-194">不适用</span><span class="sxs-lookup"><span data-stu-id="0616a-194">N/A</span></span>|<span data-ttu-id="0616a-195">不适用</span><span class="sxs-lookup"><span data-stu-id="0616a-195">N/A</span></span>|<span data-ttu-id="0616a-196">True</span><span class="sxs-lookup"><span data-stu-id="0616a-196">True</span></span>|
||||||

<span data-ttu-id="0616a-197"><sup>1</sup>选择合适的 TeamsUpgradePolicy 模式取决于场景。</span><span class="sxs-lookup"><span data-stu-id="0616a-197"><sup>1</sup>Choosing the right mode of the TeamsUpgradePolicy depends on the scenario.</span></span> <span data-ttu-id="0616a-198">请阅读了解[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)中各种模式的语音体验。</span><span class="sxs-lookup"><span data-stu-id="0616a-198">Please read about the voice experience in different modes in [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

<span data-ttu-id="0616a-199">作为此工作的一部分，Microsoft 最近更新了“Microsoft Teams 管理中心”（也称为“新式门户”），以反映基于共存模式的新管理模型。</span><span class="sxs-lookup"><span data-stu-id="0616a-199">As part of this effort, Microsoft recently updated the “Microsoft Teams admin center” (also known as Modern Portal) to reflect the new management model based on coexistence modes.</span></span> <span data-ttu-id="0616a-200">在新式门户中，配置 TeamsUpgradePolicy 也会立即将 TeamsInteropPolicy 自动设置为一致的值，因此不会再在用户界面中公开 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="0616a-200">In Modern Portal, configuring TeamsUpgradePolicy will now automatically also set TeamsInteropPolicy to consistent value, so TeamsInteropPolicy is no longer exposed in the user interface.</span></span> <span data-ttu-id="0616a-201">但是，使用 PowerShell 的管理员仍然必须同时设置 TeamsUpgradePolicy 和 TeamsInteropPolicy，以确保正确转接。</span><span class="sxs-lookup"><span data-stu-id="0616a-201">However, admins using PowerShell must still set both TeamsUpgradePolicy and TeamsInteropPolicy together to ensure proper routing.</span></span> <span data-ttu-id="0616a-202">完成到 TeamsUpgradePolicy 的转换后，将不再需要设置 TeamsInteropPolicy。</span><span class="sxs-lookup"><span data-stu-id="0616a-202">After the transition to TeamsUpgradePolicy is complete, it will no longer be necessary to also set TeamsInteropPolicy.</span></span>

<span data-ttu-id="0616a-203">有关详细信息，请参阅[面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导](migration-interop-guidance-for-teams-with-skype.md)。</span><span class="sxs-lookup"><span data-stu-id="0616a-203">For more information, please refer to [Migration and interoperability Guidance for organizations using Teams together with Skype for Business](migration-interop-guidance-for-teams-with-skype.md).</span></span>

## <a name="migrating-from-calling-plans"></a><span data-ttu-id="0616a-204">从通话套餐迁移</span><span class="sxs-lookup"><span data-stu-id="0616a-204">Migrating from Calling Plans</span></span>

<span data-ttu-id="0616a-205">有关从通话套餐迁移的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="0616a-205">For more information about migrating from Calling Plans, see:</span></span>

- [<span data-ttu-id="0616a-206">设置通话套餐</span><span class="sxs-lookup"><span data-stu-id="0616a-206">Set up Calling Plans</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)
- [<span data-ttu-id="0616a-207">Set-CsOnlineVoice 用户</span><span class="sxs-lookup"><span data-stu-id="0616a-207">Set-CsOnlineVoice User</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsOnlineVoiceUser?view=skype-ps)
- [<span data-ttu-id="0616a-208">Get-CsOnlineLisLocation</span><span class="sxs-lookup"><span data-stu-id="0616a-208">Get-CsOnlineLisLocation</span></span>](https://docs.microsoft.com/powershell/module/skype/get-csonlinelislocation?view=skype-ps)  
 
 
<span data-ttu-id="0616a-209">建议删除以前配置的许可证计划信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0616a-209">It is recommended that you remove previously configured licensing plan information as follows:</span></span>
 
```
$companyname = “contoso” 
$lic1 = $companyname + “:MCOPSTN1” 
$lic2 = $companyname + “:MCOPSTN2” 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic1 
Set-MsolUserLicense -UserPrincipalName <UPN> -RemoveLicenses $lic2 
```
## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-in-skype-for-business-server"></a><span data-ttu-id="0616a-210">在 Skype for Business Server 中使用本地 PSTN 连接从 Office 365 电话系统迁移
</span><span class="sxs-lookup"><span data-stu-id="0616a-210">Migrating from Office 365 Phone System with on-premises PSTN connectivity in Skype for Business Server</span></span>

<span data-ttu-id="0616a-211">有关在 Skype for Business Server 中使用本地 PSTN 连接从电话系统迁移的详细信息，请参阅以下内容：
</span><span class="sxs-lookup"><span data-stu-id="0616a-211">For more information about migrating from Phone System with on-premises PSTN connectivity in Skype for Business Server, see the following:</span></span>

- [<span data-ttu-id="0616a-212">规划</span><span class="sxs-lookup"><span data-stu-id="0616a-212">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-phone-system-with-on-premises-pstn-connectivity)
- [<span data-ttu-id="0616a-213">部署</span><span class="sxs-lookup"><span data-stu-id="0616a-213">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system) 

<span data-ttu-id="0616a-214">建议删除以前配置的语音转接信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0616a-214">It is recommended that you remove previously configured voice routing information as follows:</span></span>

```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
```
> <span data-ttu-id="0616a-215">如果配置了全局 CsVoiceRoutingPolicy，建议你删除与此全局策略关联的任何 PSTN 用法。</span><span class="sxs-lookup"><span data-stu-id="0616a-215">If a global CsVoiceRoutingPolicy is configured, it is recommended that you remove any PSTN usages associated with this global policy.</span></span> 

## <a name="migrating-from-office-365-phone-system-with-on-premises-pstn-connectivity-via-cloud-connector-edition"></a><span data-ttu-id="0616a-216">通过云连接器版本使用本地 PSTN 连接从 Office 365 电话系统迁移
</span><span class="sxs-lookup"><span data-stu-id="0616a-216">Migrating from Office 365 Phone System with on-premises PSTN connectivity via Cloud Connector Edition</span></span> 

<span data-ttu-id="0616a-217">有关通过云连接器版本使用本地 PSTN 连接从电话系统迁移的详细信息，请参阅以下内容：
</span><span class="sxs-lookup"><span data-stu-id="0616a-217">For more information about migrating from Phone System with on-premises PSTN connectivity via Cloud Connector, see the following:</span></span>

- [<span data-ttu-id="0616a-218">规划</span><span class="sxs-lookup"><span data-stu-id="0616a-218">Planning</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition)  
- [<span data-ttu-id="0616a-219">部署</span><span class="sxs-lookup"><span data-stu-id="0616a-219">Deploying</span></span>](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-phone-system)
- [<span data-ttu-id="0616a-220">用户配置</span><span class="sxs-lookup"><span data-stu-id="0616a-220">User configuration</span></span>](https://docs.microsoft.com/powershell/module/skype/set-csuserpstnsettings?view=skype-ps) 

<span data-ttu-id="0616a-221">建议删除以前配置的语音转接信息，如下所示：</span><span class="sxs-lookup"><span data-stu-id="0616a-221">It is recommended that you remove previously configured voice routing information as follows:</span></span>
 
```
Grant-CsVoiceRoutingPolicy -PolicyName $NULL -Identity <UPN> 
Set-CsUserPstnSettings -Identity <UPN> -AllowInternationalCalls $false -HybridPSTNSite $null 
```


## <a name="related-links"></a><span data-ttu-id="0616a-222">相关链接</span><span class="sxs-lookup"><span data-stu-id="0616a-222">RELATED LINKS</span></span>

[<span data-ttu-id="0616a-223">面向同时使用 Teams 和 Skype for Business 的组织的迁移和互操作性指导</span><span class="sxs-lookup"><span data-stu-id="0616a-223">Migration and interoperability guidance for organizations using Teams together with Skype for Business</span></span>](migration-interop-guidance-for-teams-with-skype.md)

[<span data-ttu-id="0616a-224">Grant-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-224">Grant-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamsupgradepolicy)

[<span data-ttu-id="0616a-225">Get-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-225">Get-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradePolicy)

[<span data-ttu-id="0616a-226">New-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-226">New-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsTeamsUpgradePolicy)

[<span data-ttu-id="0616a-227">Remove-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-227">Remove-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Remove-CsTeamsUpgradePolicy)

[<span data-ttu-id="0616a-228">Set-CsTeamsUpgradePolicy</span><span class="sxs-lookup"><span data-stu-id="0616a-228">Set-CsTeamsUpgradePolicy</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradePolicy)

[<span data-ttu-id="0616a-229">Get-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0616a-229">Get-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsTeamsUpgradeConfiguration)

[<span data-ttu-id="0616a-230">Set-CsTeamsUpgradeConfiguration</span><span class="sxs-lookup"><span data-stu-id="0616a-230">Set-CsTeamsUpgradeConfiguration</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsTeamsUpgradeConfiguration)

