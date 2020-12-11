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
ms.openlocfilehash: 3204bc58b083f62feca3f878d2189558b69af6bd
ms.sourcegitcommit: 6b24c82837ca2c11f450a162ca4fab3dfa4ac8d4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620723"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="e6c84-103">用于直接路由的 SBA (分支) 设备 - 公共预览版</span><span class="sxs-lookup"><span data-stu-id="e6c84-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="e6c84-104">这是公共预览版。</span><span class="sxs-lookup"><span data-stu-id="e6c84-104">This is a public preview release.</span></span>

<span data-ttu-id="e6c84-105">有时，使用直接路由连接到 Microsoft Phone System 的客户站点可能会遇到 Internet 中断。</span><span class="sxs-lookup"><span data-stu-id="e6c84-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="e6c84-106">假设客户站点（称为分支）暂时无法通过直接路由连接到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="e6c84-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="e6c84-107">但是，分支内的 Intranet 仍然功能正常，用户可以连接到提供 PSTN 连接的 SBC (SBC) 会话边界控制器。</span><span class="sxs-lookup"><span data-stu-id="e6c84-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="e6c84-108">本文介绍如何使用可生存分支设备 (SBA) 在服务中断时让 Microsoft Phone 系统继续拨打和接听公用电话交换网 (PSTN) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="e6c84-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="e6c84-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="e6c84-109">Prerequisites</span></span>

<span data-ttu-id="e6c84-110">SBA 是 Microsoft 提供给 SBC 供应商的可分发代码，SBC 供应商随后将代码嵌入其固件或单独分发，让 SBA 在单独的 VM 或硬件上运行。</span><span class="sxs-lookup"><span data-stu-id="e6c84-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed code into their firmware or distribute it separately to have SBA run on a separate VM or hardware.</span></span> 

<span data-ttu-id="e6c84-111">若要获取具有嵌入式可代理分支设备的最新会话边界控制器固件，请联系 SBC 供应商。</span><span class="sxs-lookup"><span data-stu-id="e6c84-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="e6c84-112">此外，需要以下各项：</span><span class="sxs-lookup"><span data-stu-id="e6c84-112">In addition, the following is required:</span></span>

- <span data-ttu-id="e6c84-113">需要为"媒体绕过"配置 SBC，以确保分支站点中的 Microsoft Teams 客户端媒体可以直接与 SBC 一起流动。</span><span class="sxs-lookup"><span data-stu-id="e6c84-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="e6c84-114">应在 SBA VM OS 上启用 TLS1.2。</span><span class="sxs-lookup"><span data-stu-id="e6c84-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="e6c84-115">支持的 Teams 客户端</span><span class="sxs-lookup"><span data-stu-id="e6c84-115">Supported Teams clients</span></span>

<span data-ttu-id="e6c84-116">以下 Microsoft Teams 客户端支持 SBA 功能：</span><span class="sxs-lookup"><span data-stu-id="e6c84-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="e6c84-117">Microsoft Teams Windows 桌面版</span><span class="sxs-lookup"><span data-stu-id="e6c84-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="e6c84-118">Microsoft Teams macOS 桌面版</span><span class="sxs-lookup"><span data-stu-id="e6c84-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="e6c84-119">运作方式</span><span class="sxs-lookup"><span data-stu-id="e6c84-119">How it works</span></span>

<span data-ttu-id="e6c84-120">在 Internet 中断期间，Teams 客户端应自动切换到 SBA，并且正在进行的调用应继续进行且不会中断。</span><span class="sxs-lookup"><span data-stu-id="e6c84-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="e6c84-121">用户无需任何操作。</span><span class="sxs-lookup"><span data-stu-id="e6c84-121">No action is required from the user.</span></span> <span data-ttu-id="e6c84-122">一旦 Teams 客户端检测到 Internet 已启动且任何传出调用完成，客户端将回退到正常操作模式并连接到其他 Teams 服务。</span><span class="sxs-lookup"><span data-stu-id="e6c84-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="e6c84-123">SBA 将收集的呼叫数据记录上传到云，并更新呼叫历史记录，以便租户管理员能够查看此信息。</span><span class="sxs-lookup"><span data-stu-id="e6c84-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="e6c84-124">当 Microsoft Teams 客户端处于脱机模式时，可以使用以下与通话相关的功能：</span><span class="sxs-lookup"><span data-stu-id="e6c84-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="e6c84-125">通过本地 SBA/SBC 进行 PSTN 呼叫，媒体流经 SBC。</span><span class="sxs-lookup"><span data-stu-id="e6c84-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="e6c84-126">通过本地 SBA/SBC 接收 PSTN 呼叫，媒体流经 SBC。</span><span class="sxs-lookup"><span data-stu-id="e6c84-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="e6c84-127">PSTN 呼叫的保留和恢复。</span><span class="sxs-lookup"><span data-stu-id="e6c84-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="e6c84-128">配置</span><span class="sxs-lookup"><span data-stu-id="e6c84-128">Configuration</span></span>

<span data-ttu-id="e6c84-129">若要运行 SBA 功能，Teams 客户端需要知道每个分支站点中可用的 SBA，以及将哪些 SBA 分配给该站点中的用户。</span><span class="sxs-lookup"><span data-stu-id="e6c84-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="e6c84-130">配置步骤如下：</span><span class="sxs-lookup"><span data-stu-id="e6c84-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="e6c84-131">创建 SBA。</span><span class="sxs-lookup"><span data-stu-id="e6c84-131">Create the SBAs.</span></span>
2. <span data-ttu-id="e6c84-132">创建 Teams 分支生存能力策略。</span><span class="sxs-lookup"><span data-stu-id="e6c84-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="e6c84-133">将策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="e6c84-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="e6c84-134">向 Azure Active Directory 注册 SBA 的应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6c84-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="e6c84-135">所有配置都是使用 Skype for Business Online PowerShell cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="e6c84-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="e6c84-136"> (Teams 管理中心尚不支持直接路由 SBA 功能。) </span><span class="sxs-lookup"><span data-stu-id="e6c84-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="e6c84-137"> (有关配置 SBC 的信息以及 SBC 供应商文档的链接，请参阅本文末尾的会话边界控制器配置。) </span><span class="sxs-lookup"><span data-stu-id="e6c84-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="e6c84-138">创建 SBA</span><span class="sxs-lookup"><span data-stu-id="e6c84-138">Create the SBAs</span></span>

<span data-ttu-id="e6c84-139">若要创建 SBA，请使用 New-CsTeamsSurvivableBranchAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c84-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="e6c84-140">此 cmdlet 具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="e6c84-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="e6c84-141">参数</span><span class="sxs-lookup"><span data-stu-id="e6c84-141">Parameter</span></span>| <span data-ttu-id="e6c84-142">说明</span><span class="sxs-lookup"><span data-stu-id="e6c84-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e6c84-143">Identity</span><span class="sxs-lookup"><span data-stu-id="e6c84-143">Identity</span></span>  | <span data-ttu-id="e6c84-144">SBA 的标识</span><span class="sxs-lookup"><span data-stu-id="e6c84-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="e6c84-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="e6c84-145">Fqdn</span></span> | <span data-ttu-id="e6c84-146">SBA 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="e6c84-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="e6c84-147">站点</span><span class="sxs-lookup"><span data-stu-id="e6c84-147">Site</span></span> | <span data-ttu-id="e6c84-148">SBA 所在的 TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="e6c84-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="e6c84-149">说明</span><span class="sxs-lookup"><span data-stu-id="e6c84-149">Description</span></span> | <span data-ttu-id="e6c84-150">自由格式文本</span><span class="sxs-lookup"><span data-stu-id="e6c84-150">Free format text</span></span> |
|||

<span data-ttu-id="e6c84-151">例如：</span><span class="sxs-lookup"><span data-stu-id="e6c84-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="e6c84-152">创建 Teams 分支生存能力策略</span><span class="sxs-lookup"><span data-stu-id="e6c84-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="e6c84-153">若要创建策略，请使用 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c84-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e6c84-154">此 cmdlet 具有以下参数。</span><span class="sxs-lookup"><span data-stu-id="e6c84-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="e6c84-155">请注意，该策略可以包含一个或多个 SBA。</span><span class="sxs-lookup"><span data-stu-id="e6c84-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="e6c84-156">参数</span><span class="sxs-lookup"><span data-stu-id="e6c84-156">Parameter</span></span>| <span data-ttu-id="e6c84-157">说明</span><span class="sxs-lookup"><span data-stu-id="e6c84-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e6c84-158">Identity</span><span class="sxs-lookup"><span data-stu-id="e6c84-158">Identity</span></span> | <span data-ttu-id="e6c84-159">策略的标识</span><span class="sxs-lookup"><span data-stu-id="e6c84-159">The identity of the policy</span></span> |
| <span data-ttu-id="e6c84-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="e6c84-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="e6c84-161">在站点中 (SBA) FQDN</span><span class="sxs-lookup"><span data-stu-id="e6c84-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="e6c84-162">例如：</span><span class="sxs-lookup"><span data-stu-id="e6c84-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="e6c84-163">可以使用 Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet 在策略中添加或删除 SBA。</span><span class="sxs-lookup"><span data-stu-id="e6c84-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e6c84-164">例如：</span><span class="sxs-lookup"><span data-stu-id="e6c84-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="e6c84-165">向用户分配策略</span><span class="sxs-lookup"><span data-stu-id="e6c84-165">Assign a policy to a user</span></span>

<span data-ttu-id="e6c84-166">若要将策略分配给单个用户，请使用 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e6c84-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="e6c84-167">此 cmdlet 具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="e6c84-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="e6c84-168">参数</span><span class="sxs-lookup"><span data-stu-id="e6c84-168">Parameter</span></span>| <span data-ttu-id="e6c84-169">说明</span><span class="sxs-lookup"><span data-stu-id="e6c84-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="e6c84-170">Identity</span><span class="sxs-lookup"><span data-stu-id="e6c84-170">Identity</span></span> | <span data-ttu-id="e6c84-171">用户的标识</span><span class="sxs-lookup"><span data-stu-id="e6c84-171">The identity of the user</span></span> |
| <span data-ttu-id="e6c84-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="e6c84-172">PolicyName</span></span> | <span data-ttu-id="e6c84-173">策略的标识</span><span class="sxs-lookup"><span data-stu-id="e6c84-173">The identity of the policy</span></span> |
||

<span data-ttu-id="e6c84-174">例如：</span><span class="sxs-lookup"><span data-stu-id="e6c84-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="e6c84-175">可以通过向用户授予策略$Null删除策略，如下一示例所示：</span><span class="sxs-lookup"><span data-stu-id="e6c84-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="e6c84-176">向 Azure Active Directory 注册 SBA 的应用程序</span><span class="sxs-lookup"><span data-stu-id="e6c84-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="e6c84-177">若要允许租户中使用的不同 SBA 从 Microsoft 365 读取所需数据，需要向 Azure Active Directory 注册 SBA 应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6c84-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="e6c84-178">有关应用程序注册详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="e6c84-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="e6c84-179">为 Azure Active Directory 开发业务线应用</span><span class="sxs-lookup"><span data-stu-id="e6c84-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="e6c84-180">[将应用程序注册到 Microsoft 标识平台](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="e6c84-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="e6c84-181">只需注册一个应用程序，供租户中所有 SBA 使用。</span><span class="sxs-lookup"><span data-stu-id="e6c84-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="e6c84-182">对于 SBA 注册，需要注册创建的以下值：</span><span class="sxs-lookup"><span data-stu-id="e6c84-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="e6c84-183">应用程序 (客户端) ID</span><span class="sxs-lookup"><span data-stu-id="e6c84-183">Application (client) ID</span></span> 
- <span data-ttu-id="e6c84-184">客户端机密</span><span class="sxs-lookup"><span data-stu-id="e6c84-184">Client secret</span></span> 

<span data-ttu-id="e6c84-185">对于 SBA 应用程序，请记住以下事项：</span><span class="sxs-lookup"><span data-stu-id="e6c84-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="e6c84-186">该名称可以是你决定的任何名称。</span><span class="sxs-lookup"><span data-stu-id="e6c84-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="e6c84-187">支持的帐户类型 = 仅此组织目录中的帐户。</span><span class="sxs-lookup"><span data-stu-id="e6c84-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="e6c84-188">Web 重定向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。</span><span class="sxs-lookup"><span data-stu-id="e6c84-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="e6c84-189">隐式授予令牌 = 访问令牌和 ID 令牌。</span><span class="sxs-lookup"><span data-stu-id="e6c84-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="e6c84-190">API 权限 = Skype 和 Teams 租户管理员访问权限 ->应用程序权限 -> application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="e6c84-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="e6c84-191">客户端机密：可以使用任何说明和过期时间。</span><span class="sxs-lookup"><span data-stu-id="e6c84-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="e6c84-192">请记住在创建客户端机密后立即复制它。</span><span class="sxs-lookup"><span data-stu-id="e6c84-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="e6c84-193">应用程序 (客户端) ID 显示在"概述"选项卡上。</span><span class="sxs-lookup"><span data-stu-id="e6c84-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="e6c84-194">然后执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="e6c84-194">Then follow these steps:</span></span>

1. <span data-ttu-id="e6c84-195">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="e6c84-195">Register the application.</span></span>
2. <span data-ttu-id="e6c84-196">设置隐式授权令牌。</span><span class="sxs-lookup"><span data-stu-id="e6c84-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="e6c84-197">设置 API 权限。</span><span class="sxs-lookup"><span data-stu-id="e6c84-197">Set the API permissions.</span></span>
4. <span data-ttu-id="e6c84-198">创建客户端机密。</span><span class="sxs-lookup"><span data-stu-id="e6c84-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="e6c84-199">会话边界控制器配置</span><span class="sxs-lookup"><span data-stu-id="e6c84-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="e6c84-200">有关如何使用嵌入式 Survivable 分支设备配置会话边界控制器的分步指南，请参阅 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="e6c84-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="e6c84-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="e6c84-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="e6c84-202">功能区</span><span class="sxs-lookup"><span data-stu-id="e6c84-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="e6c84-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="e6c84-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="e6c84-204">TE-Systems</span><span class="sxs-lookup"><span data-stu-id="e6c84-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="e6c84-205">报告问题</span><span class="sxs-lookup"><span data-stu-id="e6c84-205">Reporting issues</span></span>

<span data-ttu-id="e6c84-206">向 SBC 供应商的支持组织报告任何问题。</span><span class="sxs-lookup"><span data-stu-id="e6c84-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="e6c84-207">报告问题时，指示已配置了可生存分支设备。</span><span class="sxs-lookup"><span data-stu-id="e6c84-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="e6c84-208">已知问题</span><span class="sxs-lookup"><span data-stu-id="e6c84-208">Known issues</span></span>

- <span data-ttu-id="e6c84-209">添加新的可生存分支设备时，可能需要一些时间才能在"可生存分支设备"策略中使用它们。</span><span class="sxs-lookup"><span data-stu-id="e6c84-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="e6c84-210">将可生存分支设备策略分配给用户时，可能需要一些时间，SBA 才能显示在 Get-CsOnlineUser 的输出中。</span><span class="sxs-lookup"><span data-stu-id="e6c84-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="e6c84-211">不针对 Azure AD 联系人执行反向数字查找。</span><span class="sxs-lookup"><span data-stu-id="e6c84-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="e6c84-212">SBA 不支持呼叫转发设置。</span><span class="sxs-lookup"><span data-stu-id="e6c84-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="e6c84-213">不支持对为 E911 (动态紧急呼叫配置的紧急) 紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="e6c84-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="e6c84-214">该策略的输出Get-CsOnlineUser TeamsBranchSurvivabilityPolicy。</span><span class="sxs-lookup"><span data-stu-id="e6c84-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
