---
title: 直接路由 SBA
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.date: 01/28/2019
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
description: 了解有关直接路由的详细信息，如配置、必要的核心部署决策和语音路由注意事项。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5b30f8a435f256edc816ebeea075425fddeaf8bb
ms.sourcegitcommit: 4386f4b89331112e0d54943dc3133791d5dca3fb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2020
ms.locfileid: "49611786"
---
# <a name="survivable-branch-appliance-sba-for-direct-routing---public-preview"></a><span data-ttu-id="d3a5c-103">Survivable 分支装置 (SBA) 用于直接路由-公共预览</span><span class="sxs-lookup"><span data-stu-id="d3a5c-103">Survivable Branch Appliance (SBA) for Direct Routing - Public Preview</span></span>


> [!NOTE]
> <span data-ttu-id="d3a5c-104">这是公开预览版本。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-104">This is a public preview release.</span></span>

<span data-ttu-id="d3a5c-105">有时，使用直接路由连接到 Microsoft Phone 系统的客户网站可能会遇到网络中断。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-105">Occasionally, a customer site using Direct Routing to connect to Microsoft Phone System may experience an internet outage.</span></span>

<span data-ttu-id="d3a5c-106">假设客户网站（称为分支）暂时无法通过直接路由连接到 Microsoft 云。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-106">Assume that the customer site--called a branch--temporarily cannot connect to the Microsoft cloud through Direct Routing.</span></span> <span data-ttu-id="d3a5c-107">但是，分支内的 intranet 仍能完全正常工作，并且用户可以连接到提供 PSTN 连接的 SBC) 的会话边界控制器 (。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-107">However, the intranet inside the branch is still fully functional and users can connect to the Session Border Controller (SBC) that is providing PSTN connectivity.</span></span>

<span data-ttu-id="d3a5c-108">本文介绍了如何使用 Survivable 分支装置 (SBA) 启用 Microsoft Phone 系统，以便在发生中断时，继续拨打和接收公共交换电话网络 (PSTN) 呼叫。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-108">This article describes how to use a Survivable Branch Appliance (SBA) to enable Microsoft Phone System to continue to make and receive Public Switched Telephone Network (PSTN) calls in the case of an outage.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="d3a5c-109">先决条件</span><span class="sxs-lookup"><span data-stu-id="d3a5c-109">Prerequisites</span></span>

<span data-ttu-id="d3a5c-110">SBA 是由 Microsoft 向 SBC 供应商提供的可分发代码，这些供应商将代码嵌入到 SBCs 的固件中。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-110">The SBA is distributable code provided by Microsoft to SBC vendors who then embed the code into the firmware of their SBCs.</span></span> 

<span data-ttu-id="d3a5c-111">若要使用嵌入式 Survivable 分支装置获取最新的会话边框控制器固件，请与 SBC 供应商联系。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-111">To get the latest Session Border Controller firmware with the embedded Survivable Branch Appliance,  contact your SBC vendor.</span></span> <span data-ttu-id="d3a5c-112">此外，还需要以下内容：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-112">In addition, the following is required:</span></span>

- <span data-ttu-id="d3a5c-113">需要为媒体旁路配置 SBC，以确保分支网站中的 Microsoft 团队客户可以直接使用 SBC 进行媒体流。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-113">The SBC needs to be configured for Media Bypass to ensure that the Microsoft Teams client in the branch site can have media flowing directly with the SBC.</span></span> 

- <span data-ttu-id="d3a5c-114">应在 SBA VM 操作系统上启用 TLS 1.2。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-114">TLS1.2 should be enabled on the SBA VM OS.</span></span>

## <a name="supported-teams-clients"></a><span data-ttu-id="d3a5c-115">支持的团队客户端</span><span class="sxs-lookup"><span data-stu-id="d3a5c-115">Supported Teams clients</span></span>

<span data-ttu-id="d3a5c-116">以下 Microsoft 团队客户端支持 SBA 功能：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-116">The SBA feature is supported on the following Microsoft Teams clients:</span></span> 

- <span data-ttu-id="d3a5c-117">Microsoft 团队 Windows 桌面版</span><span class="sxs-lookup"><span data-stu-id="d3a5c-117">Microsoft Teams Windows desktop</span></span> 

- <span data-ttu-id="d3a5c-118">Microsoft 团队 macOS 桌面版</span><span class="sxs-lookup"><span data-stu-id="d3a5c-118">Microsoft Teams macOS desktop</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="d3a5c-119">运作方式</span><span class="sxs-lookup"><span data-stu-id="d3a5c-119">How it works</span></span>

<span data-ttu-id="d3a5c-120">在 internet 中断期间，团队客户端应自动切换到 SBA，并且持续通话应继续不中断。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-120">During an internet outage, the Teams client should switch to the SBA automatically, and ongoing calls should continue with no interruptions.</span></span> <span data-ttu-id="d3a5c-121">用户不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-121">No action is required from the user.</span></span> <span data-ttu-id="d3a5c-122">一旦团队客户端检测到 internet 已启动且所有传出调用均已完成，客户端将回退到正常操作模式并连接到其他团队服务。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-122">As soon as the Teams client detects that the internet is up and any outgoing calls are finished, the client will fall back to normal operation mode and connect to other Teams services.</span></span> <span data-ttu-id="d3a5c-123">SBA 将向云上载收集的调用数据记录，并且将更新通话记录，以便租户管理员可以查看此信息。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-123">The SBA will upload collected Call Data Records to the cloud and call history will be updated so that this information is available for review by the tenant administrator.</span></span> 

<span data-ttu-id="d3a5c-124">当 Microsoft 团队客户端处于脱机模式时，以下与调用相关的功能可用：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-124">When the Microsoft Teams client is in offline mode, the following calling-related functionality is available:</span></span> 

- <span data-ttu-id="d3a5c-125">通过本地 SBA/SBC 进行 PSTN 呼叫，并将媒体流过 SBC。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-125">Making PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span>

- <span data-ttu-id="d3a5c-126">通过本地 SBA/SBC 接收 PSTN 呼叫，并通过 SBC 进行媒体流。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-126">Receiving PSTN calls via local SBA/SBC with media flowing through the SBC.</span></span> 

- <span data-ttu-id="d3a5c-127">保留和继续 PSTN 呼叫。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-127">Hold and Resume of PSTN calls.</span></span>

## <a name="configuration"></a><span data-ttu-id="d3a5c-128">配置</span><span class="sxs-lookup"><span data-stu-id="d3a5c-128">Configuration</span></span>

<span data-ttu-id="d3a5c-129">为使 SBA 功能正常工作，团队客户需要了解每个分支站点中提供哪些 SBAs，以及将哪些 SBAs 分配给该网站中的用户。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-129">For the SBA feature to work, the Teams client needs to know which SBAs are available in each branch site, and which SBAs are assigned to the users in that site.</span></span> <span data-ttu-id="d3a5c-130">配置步骤如下所示：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-130">The configuration steps are as follows:</span></span>

1. <span data-ttu-id="d3a5c-131">创建 SBAs。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-131">Create the SBAs.</span></span>
2. <span data-ttu-id="d3a5c-132">创建团队分支留存策略。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-132">Create the Teams branch survivability policy.</span></span>
3. <span data-ttu-id="d3a5c-133">为用户分配策略。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-133">Assign the policy to users.</span></span>
4. <span data-ttu-id="d3a5c-134">向 Azure Active Directory 注册 SBA 应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-134">Register an application for the SBA with Azure Active Directory.</span></span>

<span data-ttu-id="d3a5c-135">所有配置均通过使用 Skype for Business Online PowerShell cmdlet 完成。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-135">All configuration is done by using Skype for Business Online PowerShell cmdlets.</span></span> <span data-ttu-id="d3a5c-136"> (团队管理中心尚不支持直接路由 SBA 功能。 ) </span><span class="sxs-lookup"><span data-stu-id="d3a5c-136">(The Teams admin center does not yet support the Direct Routing SBA feature.)</span></span> 

<span data-ttu-id="d3a5c-137"> (有关配置 SBC 以及指向 SBC 供应商文档的链接的信息，请参阅本文末尾的会话边框控制器配置。 ) </span><span class="sxs-lookup"><span data-stu-id="d3a5c-137">(For information on configuring the SBC, with links to SBC vendor documentation, see Session Border Controller configuration at the end of this article.)</span></span>

### <a name="create-the-sbas"></a><span data-ttu-id="d3a5c-138">创建 SBAs</span><span class="sxs-lookup"><span data-stu-id="d3a5c-138">Create the SBAs</span></span>

<span data-ttu-id="d3a5c-139">若要创建 SBAs，你将使用 New-CsTeamsSurvivableBranchAppliance cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-139">To create the SBAs, you will use the New-CsTeamsSurvivableBranchAppliance cmdlet.</span></span> <span data-ttu-id="d3a5c-140">此 cmdlet 具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-140">This cmdlet has has the following parameters:</span></span>

| <span data-ttu-id="d3a5c-141">参数</span><span class="sxs-lookup"><span data-stu-id="d3a5c-141">Parameter</span></span>| <span data-ttu-id="d3a5c-142">说明</span><span class="sxs-lookup"><span data-stu-id="d3a5c-142">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="d3a5c-143">Identity</span><span class="sxs-lookup"><span data-stu-id="d3a5c-143">Identity</span></span>  | <span data-ttu-id="d3a5c-144">SBA 的标识</span><span class="sxs-lookup"><span data-stu-id="d3a5c-144">The identity of the SBA</span></span>  |
| <span data-ttu-id="d3a5c-145">Fqdn</span><span class="sxs-lookup"><span data-stu-id="d3a5c-145">Fqdn</span></span> | <span data-ttu-id="d3a5c-146">SBA 的 FQDN</span><span class="sxs-lookup"><span data-stu-id="d3a5c-146">The FQDN of the SBA</span></span> |
| <span data-ttu-id="d3a5c-147">站点</span><span class="sxs-lookup"><span data-stu-id="d3a5c-147">Site</span></span> | <span data-ttu-id="d3a5c-148">SBA 所在的 TenantNetworkSite</span><span class="sxs-lookup"><span data-stu-id="d3a5c-148">The TenantNetworkSite where the SBA is located</span></span> |
| <span data-ttu-id="d3a5c-149">说明</span><span class="sxs-lookup"><span data-stu-id="d3a5c-149">Description</span></span> | <span data-ttu-id="d3a5c-150">自由格式文本</span><span class="sxs-lookup"><span data-stu-id="d3a5c-150">Free format text</span></span> |
|||

<span data-ttu-id="d3a5c-151">例如：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-151">For example:</span></span>

``` powershell
C:\> New-CsTeamsSurvivableBranchAppliance  -Fqdn sba1.contoso.com -Description "SBA 1" 
Identity    : sba1.contoso.com 
Fqdn        : sba1.contoso.com 
Site        : 
Description : SBA 1 
```

### <a name="create-the-teams-branch-survivability-policy"></a><span data-ttu-id="d3a5c-152">创建团队分支留存策略</span><span class="sxs-lookup"><span data-stu-id="d3a5c-152">Create the Teams Branch Survivability Policy</span></span> 

<span data-ttu-id="d3a5c-153">若要创建策略，请使用 New-CsTeamsSurvivableBranchAppliancePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-153">To create a policy, you use the New-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="d3a5c-154">此 cmdlet 具有下列参数。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-154">This cmdlet has the following parameters.</span></span> <span data-ttu-id="d3a5c-155">请注意，该策略可以包含一个或多个 SBAs。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-155">Note that the policy can contain one or more SBAs.</span></span>

| <span data-ttu-id="d3a5c-156">参数</span><span class="sxs-lookup"><span data-stu-id="d3a5c-156">Parameter</span></span>| <span data-ttu-id="d3a5c-157">说明</span><span class="sxs-lookup"><span data-stu-id="d3a5c-157">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="d3a5c-158">Identity</span><span class="sxs-lookup"><span data-stu-id="d3a5c-158">Identity</span></span> | <span data-ttu-id="d3a5c-159">策略的标识</span><span class="sxs-lookup"><span data-stu-id="d3a5c-159">The identity of the policy</span></span> |
| <span data-ttu-id="d3a5c-160">BranchApplianceFqdns</span><span class="sxs-lookup"><span data-stu-id="d3a5c-160">BranchApplianceFqdns</span></span>  | <span data-ttu-id="d3a5c-161">网站中的 SBA (s 的 FQDN) </span><span class="sxs-lookup"><span data-stu-id="d3a5c-161">The FQDN of the SBA(s) in the site</span></span> |
||

<span data-ttu-id="d3a5c-162">例如：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-162">For example:</span></span>

``` powershell
C:\> new-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns "sba1.contoso.com","sba2.contoso.com" 
Identity             : Tag:CPH 
BranchApplianceFqdns : {sba1.contoso.com, sba2.contoso.com} 
```

<span data-ttu-id="d3a5c-163">你可以使用 Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet 在策略中添加或删除 SBAs。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-163">You can add or remove SBAs from a policy by using the Set-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="d3a5c-164">例如：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-164">For example:</span></span> 

``` powershell
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{remove="sba1.contoso.com"} 
Set-CsTeamsSurvivableBranchAppliancePolicy -Identity CPH -BranchApplianceFqdns @{add="sba1.contoso.com"} 
```

### <a name="assign-a-policy-to-a-user"></a><span data-ttu-id="d3a5c-165">为用户分配策略</span><span class="sxs-lookup"><span data-stu-id="d3a5c-165">Assign a policy to a user</span></span>

<span data-ttu-id="d3a5c-166">若要将策略分配给单个用户，您将使用 Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-166">To assign the policy to individual users, you will use the Grant-CsTeamsSurvivableBranchAppliancePolicy cmdlet.</span></span> <span data-ttu-id="d3a5c-167">此 cmdlet 具有以下参数：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-167">This cmdlet has the following parameters:</span></span>

| <span data-ttu-id="d3a5c-168">参数</span><span class="sxs-lookup"><span data-stu-id="d3a5c-168">Parameter</span></span>| <span data-ttu-id="d3a5c-169">说明</span><span class="sxs-lookup"><span data-stu-id="d3a5c-169">Description</span></span> |
| :------------|:-------|
| <span data-ttu-id="d3a5c-170">Identity</span><span class="sxs-lookup"><span data-stu-id="d3a5c-170">Identity</span></span> | <span data-ttu-id="d3a5c-171">用户的标识</span><span class="sxs-lookup"><span data-stu-id="d3a5c-171">The identity of the user</span></span> |
| <span data-ttu-id="d3a5c-172">PolicyName</span><span class="sxs-lookup"><span data-stu-id="d3a5c-172">PolicyName</span></span> | <span data-ttu-id="d3a5c-173">策略的标识</span><span class="sxs-lookup"><span data-stu-id="d3a5c-173">The identity of the policy</span></span> |
||

<span data-ttu-id="d3a5c-174">例如：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-174">For example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName CPH -Identity user@contoso.com 
```

<span data-ttu-id="d3a5c-175">你可以通过授予 $Null 策略来删除用户的策略，如下例中所示：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-175">You can remove a policy from a user by granting the $Null policy as shown in the next example:</span></span>

``` powershell
C:\> Grant-CsTeamsSurvivableBranchAppliancePolicy -PolicyName $Null -Identity user@contoso.com 
```

### <a name="register-an-application-for-the-sba-with-azure-active-directory"></a><span data-ttu-id="d3a5c-176">向 Azure Active Directory 注册 SBA 应用程序</span><span class="sxs-lookup"><span data-stu-id="d3a5c-176">Register an application for the SBA with Azure Active Directory</span></span>

<span data-ttu-id="d3a5c-177">若要允许租户内使用的不同 SBAs 从 Microsoft 365 中读取所需的数据，你需要使用 Azure Active Directory 为 SBA 注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-177">To allow different SBAs used within your tenant to read required data from Microsoft 365, you need to register an application for the SBA with Azure Active Directory.</span></span> 

<span data-ttu-id="d3a5c-178">有关应用程序注册的详细信息，请参阅以下内容：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-178">For more information about application registration, see the following:</span></span>

- [<span data-ttu-id="d3a5c-179">开发适用于 Azure Active Directory 的业务线应用</span><span class="sxs-lookup"><span data-stu-id="d3a5c-179">Develop line-of-business apps for Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/manage-apps/developer-guidance-for-integrating-applications)

- <span data-ttu-id="d3a5c-180">[使用 Microsoft 标识平台注册应用程序](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app)。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-180">[Register an application with the Microsoft identity platform](https://docs.microsoft.com/azure/active-directory/develop/quickstart-register-app).</span></span>  

<span data-ttu-id="d3a5c-181">您只需注册一个应用程序，即可供租户中的所有 SBAs 使用。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-181">You only need to register one application for use by all the SBAs in your tenant.</span></span> 

<span data-ttu-id="d3a5c-182">对于 SBA 注册，你需要由注册创建的以下值：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-182">For the SBA registration, you need the following values created by the registration:</span></span> 

- <span data-ttu-id="d3a5c-183">应用程序 (客户端) ID</span><span class="sxs-lookup"><span data-stu-id="d3a5c-183">Application (client) ID</span></span> 
- <span data-ttu-id="d3a5c-184">客户端密码</span><span class="sxs-lookup"><span data-stu-id="d3a5c-184">Client secret</span></span> 

<span data-ttu-id="d3a5c-185">对于 SBA 应用程序，请记住以下几点：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-185">For the SBA application, keep the following in mind:</span></span> 

- <span data-ttu-id="d3a5c-186">名称可以是您决定的任何内容。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-186">The name can be whatever you decide.</span></span>  
- <span data-ttu-id="d3a5c-187">受支持的帐户类型 = 仅限此组织目录中的帐户。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-187">Supported account types = Account in this organizational directory only.</span></span> 
- <span data-ttu-id="d3a5c-188">Web 重定向 Uri = https://login.microsoftonline.com/common/oauth2/nativeclient 。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-188">The Web Redirect Uri = https://login.microsoftonline.com/common/oauth2/nativeclient.</span></span>
- <span data-ttu-id="d3a5c-189">隐式授予令牌 = 访问令牌和 ID 令牌。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-189">Implicit grant tokens = Access tokens and ID tokens.</span></span> 
- <span data-ttu-id="d3a5c-190">API 权限 = Skype 和团队租户管理员访问-> 应用程序权限-> application_access_custom_sba_appliance。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-190">API permissions = Skype and Teams Tenant Admin Access -> Application permissions -> application_access_custom_sba_appliance.</span></span>
- <span data-ttu-id="d3a5c-191">客户端密码：你可以使用任何描述和到期。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-191">Client secret: you can use any description and expiration.</span></span> 
- <span data-ttu-id="d3a5c-192">请记住在创建客户端密码后立即将其复制。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-192">Remember to copy the client secret immediately after creating it.</span></span> 
- <span data-ttu-id="d3a5c-193"> (客户端) ID 的应用程序显示在 "概述" 选项卡上。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-193">The Application (client) ID is shown on the Overview tab.</span></span>

<span data-ttu-id="d3a5c-194">然后按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-194">Then follow these steps:</span></span>

1. <span data-ttu-id="d3a5c-195">注册应用程序。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-195">Register the application.</span></span>
2. <span data-ttu-id="d3a5c-196">设置隐式授予令牌。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-196">Set the implicit grant tokens.</span></span>
3. <span data-ttu-id="d3a5c-197">设置 API 权限。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-197">Set the API permissions.</span></span>
4. <span data-ttu-id="d3a5c-198">创建客户端密码。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-198">Create the client secret.</span></span>


## <a name="session-border-controller-configuration"></a><span data-ttu-id="d3a5c-199">会话边框控制器配置</span><span class="sxs-lookup"><span data-stu-id="d3a5c-199">Session Border Controller configuration</span></span> 

<span data-ttu-id="d3a5c-200">有关如何使用嵌入式 Survivable 分支设备配置会话边框控制器的分步指导，请参阅 SBC 供应商提供的文档：</span><span class="sxs-lookup"><span data-stu-id="d3a5c-200">For step-by-step guidance on how to configure your Session Border Controller with the embedded Survivable Branch Appliance, see the documentation provided by your SBC vendor:</span></span> 

- [<span data-ttu-id="d3a5c-201">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="d3a5c-201">AudioCodes</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-survivable-branch-appliances)

- [<span data-ttu-id="d3a5c-202">带</span><span class="sxs-lookup"><span data-stu-id="d3a5c-202">Ribbon</span></span>](https://support.sonus.net/pages/viewpage.action?pageId=248644034)

- [<span data-ttu-id="d3a5c-203">Oracle</span><span class="sxs-lookup"><span data-stu-id="d3a5c-203">Oracle</span></span>](https://www.oracle.com/technical-resources/documentation/acme-packet.html#Link-MicrosoftTeams) 

- [<span data-ttu-id="d3a5c-204">TE-系统</span><span class="sxs-lookup"><span data-stu-id="d3a5c-204">TE-Systems</span></span>](https://www.anynode.de/microsoft-teams-sba/)

## <a name="reporting-issues"></a><span data-ttu-id="d3a5c-205">报告问题</span><span class="sxs-lookup"><span data-stu-id="d3a5c-205">Reporting issues</span></span>

<span data-ttu-id="d3a5c-206">向 SBC 供应商的支持组织报告任何问题。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-206">Report any issues to your SBC vendor's support organization.</span></span> <span data-ttu-id="d3a5c-207">报告问题时，请指明你拥有已配置的 Survivable 分支装置。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-207">When reporting the issue, indicate that you have a configured Survivable Branch Appliance.</span></span>

## <a name="known-issues"></a><span data-ttu-id="d3a5c-208">已知问题</span><span class="sxs-lookup"><span data-stu-id="d3a5c-208">Known issues</span></span>

- <span data-ttu-id="d3a5c-209">添加新的 Survivable 分支设备时，可能需要一些时间才能在 Survivable 分支装置策略中使用它们。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-209">When you add new Survivable Branch Appliances, it might take some time before you can use them in Survivable Branch Appliance policies.</span></span>

- <span data-ttu-id="d3a5c-210">向用户分配 Survivable 分支装置策略时，可能需要一段时间才能在 CsOnlineUser 的输出中显示 SBA。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-210">When you assign a Survivable Branch Appliance policy to a user, it might take some time before the SBA is shown in the output of Get-CsOnlineUser.</span></span> 

- <span data-ttu-id="d3a5c-211">不执行对 Azure AD 联系人的反向号码查找。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-211">Reverse number lookup against Azure AD Contacts is not performed.</span></span> 

- <span data-ttu-id="d3a5c-212">SBA 不支持呼叫转接设置。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-212">The SBA does not support call forwarding settings.</span></span> 

- <span data-ttu-id="d3a5c-213">不支持 (E911) 为动态紧急呼叫配置的紧急电话号码进行紧急通话。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-213">Making an emergency call to an emergency number configured for dynamic emergency calling (E911) is not supported.</span></span>

- <span data-ttu-id="d3a5c-214">Get-CsOnlineUser 的输出显示 TeamsBranchSurvivabilityPolicy。</span><span class="sxs-lookup"><span data-stu-id="d3a5c-214">The output of Get-CsOnlineUser shows TeamsBranchSurvivabilityPolicy.</span></span>
