---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 12/08/2020
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解直接路由，例如配置、必要的核心部署决策和语音路由注意事项。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6d6342f41b3cd4bfad690794c0b6474ca45e78c8
ms.sourcegitcommit: bdd9901db1fc741aaec9c7ddcf5ee1caaca4d777
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "52589236"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing"></a><span data-ttu-id="6f841-103">用于直接路由 (SBA) 的可生存分支设备</span><span class="sxs-lookup"><span data-stu-id="6f841-103">Survivable Branch Appliance (SBA) for Direct Routing</span></span>


<span data-ttu-id="6f841-104">有时，使用直接路由连接到 Microsoft 电话 系统的客户站点可能会遇到 Internet 中断。</span><span class="sxs-lookup"><span data-stu-id="6f841-104">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="6f841-105">假设客户站点（称为分支）暂时无法通过直接路由连接到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="6f841-105">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="6f841-106">但是，该分支内的 Intranet 仍完全正常运行，用户可以连接到提供 PSTN 连接的 SBC (会话) 控制器。</span><span class="sxs-lookup"><span data-stu-id="6f841-106">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="6f841-107">本文介绍如何使用可生存分支设备 (SBA) 使 Microsoft 电话 系统在服务中断时继续拨打和接听公用电话交换网 (PSTN) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="6f841-107">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="6f841-108">先决条件</span><span class="sxs-lookup"><span data-stu-id="6f841-108">Prerequisites</span></span>

<span data-ttu-id="6f841-109">SBA 是 Microsoft 提供给 SBC 供应商的可分发代码，这些供应商随后将代码嵌入其固件或单独分发，让 SBA 在单独的 VM 或硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="6f841-109">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="6f841-110">若要获取具有嵌入式 Survivable 分支设备的最新会话边界控制器固件，请联系 SBC 供应商。</span><span class="sxs-lookup"><span data-stu-id="6f841-110">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="6f841-111">此外，需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="6f841-111">In addition, the following is required:</span></span>

- <span data-ttu-id="6f841-112">需要为"媒体旁路"配置 SBC，以确保分支Microsoft Teams客户端中的媒体可以直接流向 SBC。</span><span class="sxs-lookup"><span data-stu-id="6f841-112">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="6f841-113">应在 SBA VM OS 上启用 TLS1.2。</span><span class="sxs-lookup"><span data-stu-id="6f841-113">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="6f841-114">支持Teams客户端</span><span class="sxs-lookup"><span data-stu-id="6f841-114">Supported Teams clients</span></span>

<span data-ttu-id="6f841-115">以下客户端支持 SBA Microsoft Teams功能：</span><span class="sxs-lookup"><span data-stu-id="6f841-115">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="6f841-116">Microsoft Teams Windows桌面</span><span class="sxs-lookup"><span data-stu-id="6f841-116">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="6f841-117">Microsoft Teams macOS 桌面</span><span class="sxs-lookup"><span data-stu-id="6f841-117">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="6f841-118">运作方式</span><span class="sxs-lookup"><span data-stu-id="6f841-118">How it works</span></span>

<span data-ttu-id="6f841-119">在 Internet 中断期间，Teams客户端应自动切换到 SBA，并且正在进行的调用应继续且不会中断。</span><span class="sxs-lookup"><span data-stu-id="6f841-119">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="6f841-120">用户无需执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="6f841-120">No action is required from the user.</span></span> <span data-ttu-id="6f841-121">当客户端Teams Internet 已启动且所有传出调用完成时，客户端将回退到正常运行模式并连接到其他 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="6f841-121">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="6f841-122">SBA 将收集的呼叫数据记录上传到云，呼叫历史记录将更新，以便租户管理员查看此信息。</span><span class="sxs-lookup"><span data-stu-id="6f841-122">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="6f841-123">当Microsoft Teams客户端处于脱机模式时，可以使用以下与调用相关的功能：</span><span class="sxs-lookup"><span data-stu-id="6f841-123">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="6f841-124">通过本地 SBA/SBC 进行 PSTN 呼叫，媒体流经 SBC。</span><span class="sxs-lookup"><span data-stu-id="6f841-124">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="6f841-125">通过本地 SBA/SBC 接收 PSTN 呼叫，媒体流经 SBC。</span><span class="sxs-lookup"><span data-stu-id="6f841-125">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="6f841-126">PSTN 呼叫的保留和恢复。</span><span class="sxs-lookup"><span data-stu-id="6f841-126">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="6f841-127">配置</span><span class="sxs-lookup"><span data-stu-id="6f841-127">Configuration</span></span>

<span data-ttu-id="6f841-128">若要运行 SBA 功能，Teams需要知道每个分支站点中提供哪些 SBA，以及将哪些 SBA 分配给该站点中的用户。</span><span class="sxs-lookup"><span data-stu-id="6f841-128">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="6f841-129">配置步骤如下：</span><span class="sxs-lookup"><span data-stu-id="6f841-129">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="6f841-130">创建 SBA。</span><span class="sxs-lookup"><span data-stu-id="6f841-130">Create the SBAs.</span></span>
2. <span data-ttu-id="6f841-131">创建Teams可生存性策略。</span><span class="sxs-lookup"><span data-stu-id="6f841-131">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="6f841-132">将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="6f841-132">Assign the policy to users.</span></span>
4. <span data-ttu-id="6f841-133">使用应用程序注册 SBA Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="6f841-133">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="6f841-134">所有配置都通过使用 Skype for Business PowerShell cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="6f841-134">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="6f841-135"> (Teams 管理中心尚不支持直接路由 SBA 功能.) </span><span class="sxs-lookup"><span data-stu-id="6f841-135">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="6f841-136"> (有关配置 SBC 的信息，以及指向 SBC 供应商文档的链接，请参阅本文末尾的会话边界控制器配置。) </span><span class="sxs-lookup"><span data-stu-id="6f841-136">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="6f841-137">创建 SBA</span><span class="sxs-lookup"><span data-stu-id="6f841-137">Create the SBAs</span></span>

<span data-ttu-id="6f841-138">若要创建 SBA，请使用 New-CsTeamsSurvivableBranchAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6f841-138">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="6f841-139">此 cmdlet 具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="6f841-139">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="6f841-140">参数</span><span class="sxs-lookup"><span data-stu-id="6f841-140">Parameter</span></span>| <span data-ttu-id="6f841-141">说明</span><span class="sxs-lookup"><span data-stu-id="6f841-141">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="6f841-142">Identity</span><span class="sxs-lookup"><span data-stu-id="6f841-142">Identity</span></span>  | <span data-ttu-id="6f841-143">SBA 的标识</span><span class="sxs-lookup"><span data-stu-id="6f841-143">The identity of the SBA</span></span>  |
| <span data-ttu-id="6f841-144">Fqdn</span><span class="sxs-lookup"><span data-stu-id="6f841-144">Fqdn</span></span> | <span data-ttu-id="6f841-145">SBA 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="6f841-145">The FQDN of the SBA</span></span> |
| <span data-ttu-id="6f841-146">站点</span><span class="sxs-lookup"><span data-stu-id="6f841-146">Site</span></span> | <span data-ttu-id="6f841-147">SBA 所在的 TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="6f841-147">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="6f841-148">说明</span><span class="sxs-lookup"><span data-stu-id="6f841-148">Description</span></span> | <span data-ttu-id="6f841-149">自由格式文本</span><span class="sxs-lookup"><span data-stu-id="6f841-149">Free format text</span></span> |
|||

<span data-ttu-id="6f841-150">例如：</span><span class="sxs-lookup"><span data-stu-id="6f841-150">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="6f841-151">创建 Teams 分支可生存性策略</span><span class="sxs-lookup"><span data-stu-id="6f841-151">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="6f841-152">若要创建策略，请使用 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6f841-152">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="6f841-153">此 cmdlet 具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="6f841-153">This cmdlet has the following parameters.</span></span> <span data-ttu-id="6f841-154">请注意，策略可以包含一个或多个 SBA。</span><span class="sxs-lookup"><span data-stu-id="6f841-154">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="6f841-155">参数</span><span class="sxs-lookup"><span data-stu-id="6f841-155">Parameter</span></span>| <span data-ttu-id="6f841-156">说明</span><span class="sxs-lookup"><span data-stu-id="6f841-156">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="6f841-157">Identity</span><span class="sxs-lookup"><span data-stu-id="6f841-157">Identity</span></span> | <span data-ttu-id="6f841-158">策略的标识</span><span class="sxs-lookup"><span data-stu-id="6f841-158">The identity of the policy</span></span> |
| <span data-ttu-id="6f841-159">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="6f841-159">BranchApplianceFqdns</span></span>  | <span data-ttu-id="6f841-160">站点中 SBA () FQDN</span><span class="sxs-lookup"><span data-stu-id="6f841-160">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="6f841-161">例如：</span><span class="sxs-lookup"><span data-stu-id="6f841-161">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="6f841-162">可以使用 Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet 在策略中添加或删除 SBA。</span><span class="sxs-lookup"><span data-stu-id="6f841-162">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="6f841-163">例如：</span><span class="sxs-lookup"><span data-stu-id="6f841-163">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="6f841-164">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="6f841-164">Assign a policy to a user</span></span>

<span data-ttu-id="6f841-165">若要将策略分配给单个用户，请使用 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="6f841-165">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="6f841-166">此 cmdlet 具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="6f841-166">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="6f841-167">参数</span><span class="sxs-lookup"><span data-stu-id="6f841-167">Parameter</span></span>| <span data-ttu-id="6f841-168">说明</span><span class="sxs-lookup"><span data-stu-id="6f841-168">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="6f841-169">Identity</span><span class="sxs-lookup"><span data-stu-id="6f841-169">Identity</span></span> | <span data-ttu-id="6f841-170">用户的标识</span><span class="sxs-lookup"><span data-stu-id="6f841-170">The identity of the user</span></span> |
| <span data-ttu-id="6f841-171">PolicyName</span><span class="sxs-lookup"><span data-stu-id="6f841-171">PolicyName</span></span> | <span data-ttu-id="6f841-172">策略的标识</span><span class="sxs-lookup"><span data-stu-id="6f841-172">The identity of the policy</span></span> |
||

<span data-ttu-id="6f841-173">例如：</span><span class="sxs-lookup"><span data-stu-id="6f841-173">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="6f841-174">可以通过向用户授予策略$Null策略，如下例所示：</span><span class="sxs-lookup"><span data-stu-id="6f841-174">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="6f841-175">使用应用程序注册 SBA Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f841-175">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="6f841-176">若要允许租户中使用的不同 SBA 从 Microsoft 365 读取所需数据，需要向 Azure Active Directory 注册 SBA 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f841-176">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="6f841-177">有关应用程序注册详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="6f841-177">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="6f841-178">开发适用于企业的业务线Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="6f841-178">Develop line-of-business apps for Azure Active Directory</span></span>](/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="6f841-179">[将应用程序注册到 Microsoft 标识平台。](/azure/active-directory/develop/quickstart-register-app)</span><span class="sxs-lookup"><span data-stu-id="6f841-179">[Register an application with the Microsoft identity platform](/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="6f841-180">只需注册一个应用程序，供租户中所有 SBA 使用。</span><span class="sxs-lookup"><span data-stu-id="6f841-180">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="6f841-181">对于 SBA 注册，需要注册创建的以下值：</span><span class="sxs-lookup"><span data-stu-id="6f841-181">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="6f841-182">应用程序 (客户端) ID</span><span class="sxs-lookup"><span data-stu-id="6f841-182">Application (client) ID</span></span> 
- <span data-ttu-id="6f841-183">客户端机密</span><span class="sxs-lookup"><span data-stu-id="6f841-183">Client secret</span></span> 

<span data-ttu-id="6f841-184">对于 SBA 应用程序，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="6f841-184">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="6f841-185">名称可以是你决定的任何名称。</span><span class="sxs-lookup"><span data-stu-id="6f841-185">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="6f841-186">支持的帐户类型 = 仅此组织目录中的帐户。</span><span class="sxs-lookup"><span data-stu-id="6f841-186">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="6f841-187">Web 重定向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。</span><span class="sxs-lookup"><span data-stu-id="6f841-187">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="6f841-188">隐式授予令牌 = 访问令牌和 ID 令牌。</span><span class="sxs-lookup"><span data-stu-id="6f841-188">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="6f841-189">API 权限 = Skype Teams 管理员访问权限 -> 应用程序权限 -> application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="6f841-189">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="6f841-190">客户端机密：可以使用任何说明和过期时间。</span><span class="sxs-lookup"><span data-stu-id="6f841-190">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="6f841-191">请记住在创建客户端机密后立即复制它。</span><span class="sxs-lookup"><span data-stu-id="6f841-191">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="6f841-192">应用程序 (客户端) ID 显示在"概述"选项卡上。</span><span class="sxs-lookup"><span data-stu-id="6f841-192">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="6f841-193">然后执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="6f841-193">Then follow these steps:</span></span>

1. <span data-ttu-id="6f841-194">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="6f841-194">Register the application.</span></span>
2. <span data-ttu-id="6f841-195">设置隐式授权令牌。</span><span class="sxs-lookup"><span data-stu-id="6f841-195">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="6f841-196">设置 API 权限。</span><span class="sxs-lookup"><span data-stu-id="6f841-196">Set the API permissions.</span></span>
4. <span data-ttu-id="6f841-197">创建客户端机密。</span><span class="sxs-lookup"><span data-stu-id="6f841-197">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="6f841-198">会话边界控制器配置</span><span class="sxs-lookup"><span data-stu-id="6f841-198">Session Border Controller configuration</span></span> 

<span data-ttu-id="6f841-199">有关如何使用嵌入式 Survivable 分支设备配置会话边界控制器的分步指南，请参阅 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="6f841-199">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="6f841-200">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="6f841-200">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="6f841-201">功能区</span><span class="sxs-lookup"><span data-stu-id="6f841-201">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="6f841-202">Oracle</span><span class="sxs-lookup"><span data-stu-id="6f841-202">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="6f841-203">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="6f841-203">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="6f841-204">报告问题</span><span class="sxs-lookup"><span data-stu-id="6f841-204">Reporting issues</span></span>

<span data-ttu-id="6f841-205">向 SBC 供应商的支持组织报告任何问题。</span><span class="sxs-lookup"><span data-stu-id="6f841-205">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="6f841-206">报告问题时，指示已配置了"可生存分支设备"。</span><span class="sxs-lookup"><span data-stu-id="6f841-206">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="6f841-207">已知问题</span><span class="sxs-lookup"><span data-stu-id="6f841-207">Known issues</span></span>

- <span data-ttu-id="6f841-208">添加新的可生存分支设备时，可能需要一些时间才能在"可生存分支设备"策略中使用它们。</span><span class="sxs-lookup"><span data-stu-id="6f841-208">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="6f841-209">将可生存分支设备策略分配给用户时，可能需要一些时间，SBA 才能显示在 Get-CsOnlineUser 的输出中。</span><span class="sxs-lookup"><span data-stu-id="6f841-209">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="6f841-210">不会针对 Azure AD 联系人执行反向数字查找。</span><span class="sxs-lookup"><span data-stu-id="6f841-210">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="6f841-211">SBA 不支持呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="6f841-211">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="6f841-212">不支持对为 E911 (动态紧急呼叫配置的紧急) 紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="6f841-212">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>
