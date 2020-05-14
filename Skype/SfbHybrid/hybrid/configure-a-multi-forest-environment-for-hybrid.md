---
title: 部署资源林拓扑
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Hybrid
- M365-voice
- M365-collaboration
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
ms.custom: ''
description: 以下各节提供了有关如何配置在资源/用户林模型中具有多个林的环境以在混合方案中提供 Skype for Business 功能的指南。
ms.openlocfilehash: cf3a162001756661afd0f204e9968713d9db0f5b
ms.sourcegitcommit: d69bad69ba9a9bca4614d72d8f34fb2a0a9e4dc4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44221476"
---
# <a name="deploy-a-resource-forest-topology"></a><span data-ttu-id="28fe5-103">部署资源林拓扑</span><span class="sxs-lookup"><span data-stu-id="28fe5-103">Deploy a resource forest topology</span></span>
 
<span data-ttu-id="28fe5-104">以下各节提供了有关如何配置在资源/用户林模型中具有多个林的环境以在混合方案中提供 Skype for Business 功能的指南。</span><span class="sxs-lookup"><span data-stu-id="28fe5-104">The following sections provide guidance on how to configure an environment that has multiple forests in a resource/user forest model to provide Skype for Business functionality in a hybrid scenario.</span></span> 
  
![混合的多林环境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="topology-requirements"></a><span data-ttu-id="28fe5-106">拓扑要求</span><span class="sxs-lookup"><span data-stu-id="28fe5-106">Topology requirements</span></span>

<span data-ttu-id="28fe5-107">支持多个用户林。</span><span class="sxs-lookup"><span data-stu-id="28fe5-107">Multiple user forests are supported.</span></span> <span data-ttu-id="28fe5-108">请注意以下几点：</span><span class="sxs-lookup"><span data-stu-id="28fe5-108">Keep the following in mind:</span></span> 
    
- <span data-ttu-id="28fe5-109">有关混合配置中的 Lync Server 和 Skype for business Server 支持的版本，请参阅在[Skype For Business Server 与 Microsoft 365 或 Office 365 之间规划混合连接](plan-hybrid-connectivity.md)中的[服务器版本要求](plan-hybrid-connectivity.md#server-version-requirements)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-109">For supported versions of Lync Server and Skype for Business Server in a hybrid configuration, see [Server version requirements](plan-hybrid-connectivity.md#server-version-requirements) in [Plan hybrid connectivity between Skype for Business Server and Microsoft 365 or Office 365](plan-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="28fe5-110">可以在一个或多个林中部署 Exchange 服务器，其中可能包含（也可能不包含）包含 Skype for Business Server 的林。</span><span class="sxs-lookup"><span data-stu-id="28fe5-110">Exchange Server can be deployed in one or more forests, which may or may not include the forest containing Skype for Business Server.</span></span> <span data-ttu-id="28fe5-111">请确保您已应用最新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="28fe5-111">Make sure you have applied the latest Cumulative Update.</span></span>
    
- <span data-ttu-id="28fe5-112">有关与 Exchange Server 共存的详细信息（包括在各种本地和联机组合中支持的条件和限制），请参阅[Plan for 集成 Skype For business 和 Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[功能支持](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-112">For details on co-existence with Exchange Server, including support criteria and limitations in various combinations of on-premises and online, see [Feature support](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).</span></span>
    
  
## <a name="user-homing-considerations"></a><span data-ttu-id="28fe5-113">用户托管注意事项</span><span class="sxs-lookup"><span data-stu-id="28fe5-113">User homing considerations</span></span>

<span data-ttu-id="28fe5-114">驻留在本地的 Skype for Business 用户可以让 Exchange 驻留在本地或联机。</span><span class="sxs-lookup"><span data-stu-id="28fe5-114">Skype for Business users homed on premises can have Exchange homed on premises or online.</span></span> <span data-ttu-id="28fe5-115">Skype for Business Online 用户应使用 Exchange Online 获得最佳体验;但是，这并不是必需的。</span><span class="sxs-lookup"><span data-stu-id="28fe5-115">Skype for Business Online users should use Exchange Online for an optimal experience; however, this is not required.</span></span> <span data-ttu-id="28fe5-116">在这两种情况下，无需在本地 Exchange 中实施 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="28fe5-116">Exchange on premises is not required to implement Skype for Business in either case.</span></span>
  
## <a name="configure-forest-trusts"></a><span data-ttu-id="28fe5-117">配置林信任</span><span class="sxs-lookup"><span data-stu-id="28fe5-117">Configure forest trusts</span></span>

<span data-ttu-id="28fe5-118">在资源林拓扑中，托管 Skype for Business Server 的资源林必须信任包含将访问它的用户帐户的每个帐户林。</span><span class="sxs-lookup"><span data-stu-id="28fe5-118">In a resource forest topology, the resource forests hosting Skype for Business Server must trust each account forest that contains users' accounts that will access it.</span></span> <span data-ttu-id="28fe5-119">如果有多个用户林，若要启用跨林身份验证，请务必为每个林信任启用名称后缀路由。</span><span class="sxs-lookup"><span data-stu-id="28fe5-119">If you have multiple user forests, to enable cross-forest authentication it is important that Name Suffix Routing is enabled for each of these forest trusts.</span></span> <span data-ttu-id="28fe5-120">有关说明，请参阅[管理林信任](https://technet.microsoft.com/library/cc772440.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-120">For instructions, see [Managing Forest Trusts](https://technet.microsoft.com/library/cc772440.aspx).</span></span> <span data-ttu-id="28fe5-121">如果您在另一个林中部署了 Exchange 服务器，并且它为 Skype for Business 用户提供了功能，则承载 Exchange 的林必须信任托管 Skype for Business Server 的林。</span><span class="sxs-lookup"><span data-stu-id="28fe5-121">If you have Exchange Server deployed in an another forest and it provides functionality for Skype for Business users, the forest hosting Exchange must trust the forest hosting Skype for Business Server.</span></span> <span data-ttu-id="28fe5-122">例如，如果 Exchange 已部署在帐户林中，这将有效地表示在该配置中需要帐户和 Skype for business 林之间的双向信任。</span><span class="sxs-lookup"><span data-stu-id="28fe5-122">For example, if Exchange were deployed in the account forest, this would effectively mean a two-way trust between account and Skype for Business forests is required in that configuration.</span></span>
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a><span data-ttu-id="28fe5-123">将帐户同步到托管 Skype for Business 的林中</span><span class="sxs-lookup"><span data-stu-id="28fe5-123">Synchronize accounts into the forest hosting Skype for Business</span></span>

<span data-ttu-id="28fe5-124">当 Skype for Business Server 部署在一个林中（资源林），但向一个或多个其他林（帐户林）中的用户提供功能时，其他林中的用户必须在部署了 Skype for Business Server 的林中表示为禁用的用户对象。</span><span class="sxs-lookup"><span data-stu-id="28fe5-124">When Skype for Business Server is deployed in one forest (a resource forest), but provides functionality to users in one or more other forests (account forests), users in the other forests must be represented as disabled user objects in the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="28fe5-125">需要部署和配置身份管理产品（如 Microsoft Identity Manager），以设置帐户林的用户并将其同步到部署 Skype for Business Server 的林中。</span><span class="sxs-lookup"><span data-stu-id="28fe5-125">An identity management product, such as Microsoft Identity Manager, needs to be deployed and configured to provision and synchronize the users from the account forests into the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="28fe5-126">用户必须以被禁用的用户对象的形式托管 Skype for Business Server 的林中进行同步。</span><span class="sxs-lookup"><span data-stu-id="28fe5-126">Users must be synchronized into the forest hosting Skype for Business Server as disabled user objects.</span></span> <span data-ttu-id="28fe5-127">无法将用户同步为 Active Directory contact 对象，因为 Azure Active Directory Connect 不会将联系人正确同步到 Azure AD，以便与 Skype 一起使用。</span><span class="sxs-lookup"><span data-stu-id="28fe5-127">Users cannot be synchronized as Active Directory contact objects, because Azure Active Directory Connect will not properly synchronize contacts into Azure AD for use with Skype.</span></span>
  
<span data-ttu-id="28fe5-128">无论任何多林配置如何，托管 Skype for Business Server 的林也可以为同一林中存在的任何已启用用户提供功能。</span><span class="sxs-lookup"><span data-stu-id="28fe5-128">Regardless of any multi-forest configuration, the forest hosting Skype for Business Server can also provide functionality for any enabled users that exist in the same forest.</span></span>
  
<span data-ttu-id="28fe5-129">若要获取正确的标识同步，需要同步以下属性：</span><span class="sxs-lookup"><span data-stu-id="28fe5-129">To get proper identity synchronization, the following attributes need to be synchronized:</span></span> 
  
|<span data-ttu-id="28fe5-130">**用户林**</span><span class="sxs-lookup"><span data-stu-id="28fe5-130">**User forests**</span></span>|<span data-ttu-id="28fe5-131">**资源林**</span><span class="sxs-lookup"><span data-stu-id="28fe5-131">**Resource forests**</span></span>|
|:-----|:-----|
|<span data-ttu-id="28fe5-132">选择的帐户链接属性</span><span class="sxs-lookup"><span data-stu-id="28fe5-132">chosen account link attribute</span></span>  <br/> |<span data-ttu-id="28fe5-133">选择的帐户链接属性</span><span class="sxs-lookup"><span data-stu-id="28fe5-133">chosen account link attribute</span></span>  <br/> |
|<span data-ttu-id="28fe5-134">mail</span><span class="sxs-lookup"><span data-stu-id="28fe5-134">mail</span></span>  <br/> |<span data-ttu-id="28fe5-135">mail</span><span class="sxs-lookup"><span data-stu-id="28fe5-135">mail</span></span>  <br/> |
|<span data-ttu-id="28fe5-136">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="28fe5-136">ProxyAddresses</span></span>  <br/> |<span data-ttu-id="28fe5-137">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="28fe5-137">ProxyAddresses</span></span>  <br/> |
|<span data-ttu-id="28fe5-138">ObjectSID</span><span class="sxs-lookup"><span data-stu-id="28fe5-138">ObjectSID</span></span>  <br/> |<span data-ttu-id="28fe5-139">msRTCSIP-OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="28fe5-139">msRTCSIP-OriginatorSID</span></span>  <br/> |
   
<span data-ttu-id="28fe5-140">[选择的帐户链接属性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)将用作源定位点。</span><span class="sxs-lookup"><span data-stu-id="28fe5-140">The [chosen account link attribute](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts) will be used as the Source Anchor.</span></span> <span data-ttu-id="28fe5-141">如果您希望使用不同且不可变的属性，则可以执行此操作;只需确保编辑 AD FS 声明规则并在 AAD 连接配置过程中选择属性。</span><span class="sxs-lookup"><span data-stu-id="28fe5-141">If you have a different and immutable attribute that you would prefer to use, you may do so; just be sure to edit the AD FS claims rule and select the attribute during the AAD Connect configuration.</span></span>
  
<span data-ttu-id="28fe5-142">请勿在林之间同步 Upn。</span><span class="sxs-lookup"><span data-stu-id="28fe5-142">Do not sync the UPNs between the forests.</span></span> <span data-ttu-id="28fe5-143">我们在测试过程中发现，我们需要对每个用户林使用唯一的 UPN，因为不能在多个林之间使用同一 UPN。</span><span class="sxs-lookup"><span data-stu-id="28fe5-143">We found during testing that we needed to use a unique UPN for each user forest, as you cannot use the same UPN across multiple forests.</span></span> <span data-ttu-id="28fe5-144">因此，我们提供了两种可能性，即同步 UPN 或不同步。</span><span class="sxs-lookup"><span data-stu-id="28fe5-144">As a result, we were presented with two possibilities, to synchronize the UPN or to not synchronize.</span></span> 
  
- <span data-ttu-id="28fe5-145">如果每个用户林中的唯一 UPN 未同步到资源林中的关联禁用对象，则首次登录（SSO）至少将被中断（假定用户选择了 "保存密码" 选项）。</span><span class="sxs-lookup"><span data-stu-id="28fe5-145">If the unique UPN from each user forest was not synchronized to the associated disabled object in the resource forest, single sign-on (SSO) would be broken for at least the initial sign-in attempt (assuming the user selected the option to save password).</span></span> <span data-ttu-id="28fe5-146">在 Skype for Business 客户端中，我们假定 SIP/UPN 值相同。</span><span class="sxs-lookup"><span data-stu-id="28fe5-146">In the Skype for Business client, we assume that the SIP/UPN values are the same.</span></span> <span data-ttu-id="28fe5-147">由于此方案中的 SIP 地址为 user@company.com，但用户林中启用的对象的 UPN 实际上是 user@contoso.company.com，因此初始登录尝试将失败，并且系统会提示用户输入凭据。</span><span class="sxs-lookup"><span data-stu-id="28fe5-147">Since the SIP address in this scenario is user@company.com, but the UPN of the enabled object in the user forest is in fact user@contoso.company.com, the initial login attempt would fail and the user would be prompted to enter credentials.</span></span> <span data-ttu-id="28fe5-148">在输入其正确/实际 UPN 时，身份验证请求将针对用户林中的域控制器完成，登录将成功。</span><span class="sxs-lookup"><span data-stu-id="28fe5-148">Upon entering their correct/actual UPN, the authentication request would be completed against the domain controllers in the user forest, and sign-in would be successful.</span></span>
    
- <span data-ttu-id="28fe5-149">如果每个用户林中的唯一 UPN 已同步到资源林中关联的禁用对象，则 AD FS 身份验证将失败。</span><span class="sxs-lookup"><span data-stu-id="28fe5-149">If the unique UPN from each user forest was synchronized to the associated disabled object in the resource forest, AD FS authentication would fail.</span></span> <span data-ttu-id="28fe5-150">匹配规则将在资源林中的对象上查找 UPN，该 UPN 已被禁用，无法用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="28fe5-150">The matching rule would find the UPN on the object in the resource forest, which was disabled and could not be used for authentication.</span></span> 
    
## <a name="create-a-microsoft-365-or-office-365-organization"></a><span data-ttu-id="28fe5-151">创建 Microsoft 365 或 Office 365 组织</span><span class="sxs-lookup"><span data-stu-id="28fe5-151">Create a Microsoft 365 or Office 365 organization</span></span>

<span data-ttu-id="28fe5-152">接下来，你将需要设置 Microsoft 365 或 Office 365 组织以用于你的部署。</span><span class="sxs-lookup"><span data-stu-id="28fe5-152">You will next need to provision a Microsoft 365 or Office 365 organization to use with your deployment.</span></span> <span data-ttu-id="28fe5-153">有关详细信息，请参阅[Microsoft 云产品服务的订阅、许可证、帐户和租户](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-153">For more information, please see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](https://docs.microsoft.com/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings).</span></span> 
  
## <a name="configure-active-directory-federation-services"></a><span data-ttu-id="28fe5-154">配置 Active Directory 联合身份验证服务</span><span class="sxs-lookup"><span data-stu-id="28fe5-154">Configure Active Directory Federation Services</span></span>

<span data-ttu-id="28fe5-155">拥有租户后，你将需要在每个用户林中配置 Active Directory 联合身份验证服务（AD FS）。</span><span class="sxs-lookup"><span data-stu-id="28fe5-155">Once you have a tenant, you will need to configure Active Directory Federation Services (AD FS) in each of the user forests.</span></span> <span data-ttu-id="28fe5-156">这假设您有每个林的唯一 SIP 和 SMTP 地址和用户主体名称（UPN）。</span><span class="sxs-lookup"><span data-stu-id="28fe5-156">This assumes you have a unique SIP and SMTP address and User Principal Name (UPN) for each forest.</span></span> <span data-ttu-id="28fe5-157">AD FS 是可选的，在此处用于获取单一登录（SSO）。</span><span class="sxs-lookup"><span data-stu-id="28fe5-157">AD FS is optional and is used here to get single sign-on (SSO).</span></span> <span data-ttu-id="28fe5-158">也支持使用密码同步的 DirSync，也可替代 AD FS 使用。</span><span class="sxs-lookup"><span data-stu-id="28fe5-158">DirSync with Password Sync is also supported and can also be used in place of AD FS.</span></span> 
  
<span data-ttu-id="28fe5-159">仅测试具有匹配的 SIP/SMTP 和 Upn 的部署。</span><span class="sxs-lookup"><span data-stu-id="28fe5-159">Only deployments with matching SIP/SMTP and UPNs were tested.</span></span> <span data-ttu-id="28fe5-160">不具有匹配的 SIP/SMTP/Upn 可能会导致功能下降，例如 Exchange 集成和 SSO 问题。</span><span class="sxs-lookup"><span data-stu-id="28fe5-160">Not having matching SIP/SMTP/UPNs may result in reduced functionality, such as problems with Exchange integration and SSO.</span></span> 
  
<span data-ttu-id="28fe5-161">除非您对每个林中的用户使用唯一的 SIP/SMTP/UPN，否则您仍可以遇到 SSO 问题，而不考虑部署 AD FS 的位置：</span><span class="sxs-lookup"><span data-stu-id="28fe5-161">Unless you use a unique SIP/SMTP/UPN for users from each forest, you can still run into SSO problems, regardless of where AD FS is deployed:</span></span> 
  
- <span data-ttu-id="28fe5-162">在每个用户林中部署了 AD FS 服务器场的资源/用户林之间的单向或双向信任，所有用户共享公用 SIP/SMTP 域，但对于每个用户林都具有唯一的 UPN。</span><span class="sxs-lookup"><span data-stu-id="28fe5-162">One-way or two-way trusts between resource/user forests with AD FS farm deployed in each user forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
- <span data-ttu-id="28fe5-163">仅在资源林中部署了 AD FS 场的资源/用户林之间的双向信任，所有用户都共享公用 SIP/SMTP 域，但对于每个用户林为唯一的 UPN。</span><span class="sxs-lookup"><span data-stu-id="28fe5-163">Two-way trusts between resource/user forests with AD FS farm deployed only in resource forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
<span data-ttu-id="28fe5-164">通过在每个用户林中放置 AD FS 服务器场，并对每个林使用唯一的 SIP/SMTP/UPN，我们会解决这两个问题。</span><span class="sxs-lookup"><span data-stu-id="28fe5-164">By placing an AD FS farm in each user forest and using a unique SIP/SMTP/UPN for each forest, we resolve both issues.</span></span> <span data-ttu-id="28fe5-165">在身份验证尝试过程中，仅搜索特定用户林中的帐户并匹配这些帐户。</span><span class="sxs-lookup"><span data-stu-id="28fe5-165">Only the accounts in that specific user forest would be searched and matched during authentication attempts.</span></span> <span data-ttu-id="28fe5-166">这将有助于提供更无缝的身份验证过程。</span><span class="sxs-lookup"><span data-stu-id="28fe5-166">This will help provide a more seamless authentication process.</span></span> 
  
<span data-ttu-id="28fe5-167">这将是 Windows Server 2012 R2 AD FS 的标准部署，在继续之前，它应正常工作。</span><span class="sxs-lookup"><span data-stu-id="28fe5-167">This will be a standard deployment of the Windows Server 2012 R2 AD FS and should be working before continuing.</span></span> <span data-ttu-id="28fe5-168">有关说明，请参阅 how [To INSTALL AD FS 2012 R2 For Microsoft 365 或 Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-168">For instructions, see [How To Install AD FS 2012 R2 For Microsoft 365 or Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx).</span></span> 
  
<span data-ttu-id="28fe5-169">部署后，您必须编辑声明规则以匹配之前选择的源定位点。</span><span class="sxs-lookup"><span data-stu-id="28fe5-169">Once deployed, you then have to edit the claims rule to match the Source Anchor selected earlier.</span></span> <span data-ttu-id="28fe5-170">在 AD FS MMC 中，在 "信赖方信任" 下，右键单击 " **microsoft 365 Identity platform** " 或 " **Microsoft Office 365 标识平台**"，然后选择 "**编辑声明规则**"。</span><span class="sxs-lookup"><span data-stu-id="28fe5-170">In the AD FS MMC, under Relying Party Trusts, right-click **Microsoft 365 Identity Platform** or **Microsoft Office 365 Identity Platform**, and then select **Edit Claim Rules**.</span></span> <span data-ttu-id="28fe5-171">编辑第一个规则，然后将 ObjectSID 更改为**employeeNumber**。</span><span class="sxs-lookup"><span data-stu-id="28fe5-171">Edit the first rule, and change ObjectSID to **employeeNumber**.</span></span> 
  
![多林编辑规则屏幕](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a><span data-ttu-id="28fe5-173">配置 AAD Connect</span><span class="sxs-lookup"><span data-stu-id="28fe5-173">Configure AAD Connect</span></span>

<span data-ttu-id="28fe5-174">在资源林拓扑中，需要将资源林和任何帐户林中的用户属性同步到 Azure AD 中。</span><span class="sxs-lookup"><span data-stu-id="28fe5-174">In resource forest topologies, it’s required that user attributes from both the resource forest and any account forests(s) are synchronized into Azure AD.</span></span> <span data-ttu-id="28fe5-175">执行此操作的最简单和建议的方法是让 Azure AD Connect 同步并合并已启用用户帐户和包含 Skype for Business 的林的*所有*林的用户标识。</span><span class="sxs-lookup"><span data-stu-id="28fe5-175">The simplest and recommended way to do this is to have Azure AD Connect synchronize and merge user identities from *all* forests that have enabled user accounts and the forest that contains Skype for Business.</span></span> <span data-ttu-id="28fe5-176">有关详细信息，请参阅[为 Skype For business 和团队配置 AZURE AD Connect](configure-azure-ad-connect.md)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-176">For details see, [Configure Azure AD Connect for Skype for Business and Teams](configure-azure-ad-connect.md).</span></span>

<span data-ttu-id="28fe5-177">请注意，AAD 连接不提供帐户和资源林之间的本地同步。</span><span class="sxs-lookup"><span data-stu-id="28fe5-177">Note that AAD Connect does not provide synchronization on premises between the account and resource forests.</span></span> <span data-ttu-id="28fe5-178">必须使用 Microsoft Identity Manager 或类似产品单独进行配置，如前文所述。</span><span class="sxs-lookup"><span data-stu-id="28fe5-178">That must be separately configured using Microsoft Identity Manager or similar product, as described earlier.</span></span>
  
<span data-ttu-id="28fe5-179">完成和 AAD 连接合并后，如果您查看元节中的对象，您应该会看到类似于以下的内容：</span><span class="sxs-lookup"><span data-stu-id="28fe5-179">When finished and AAD Connect is merging, if you look at an object in the metaverse, you should see something similar to this:</span></span> 
  
![多林元节对象屏幕](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
<span data-ttu-id="28fe5-181">绿色突出显示的属性已从 Microsoft 365 或 Office 365 合并，黄色来自用户林，蓝色来自资源林。</span><span class="sxs-lookup"><span data-stu-id="28fe5-181">The green highlighted attributes were merged from Microsoft 365 or Office 365, the yellow are from the user forest, and the blue are from the resource forest.</span></span> 
  
<span data-ttu-id="28fe5-182">这是一种测试用户，可以看到 AAD 连接已识别来自用户的 sourceAnchor 和 cloudSourceAnchor，以及 Microsoft 365 或 Office 365 中的资源林对象，在我们的1101示例中，这是之前选择的 employeeNumber。</span><span class="sxs-lookup"><span data-stu-id="28fe5-182">This is a test user, and you can see that AAD Connect has identified the sourceAnchor and the cloudSourceAnchor from the user and the resource forest objects from Microsoft 365 or Office 365, in our case 1101, which is the employeeNumber selected earlier.</span></span> <span data-ttu-id="28fe5-183">然后，它能够将此对象合并到上面看到的内容中。</span><span class="sxs-lookup"><span data-stu-id="28fe5-183">It then was able to merge this object into what you see above.</span></span> 
  
<span data-ttu-id="28fe5-184">有关详细信息，请参阅[将本地目录与 Azure Active Directory 集成](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-184">For more information, see [Integrate your on-premises directories with Azure Active Directory](https://azure.microsoft.com/documentation/articles/active-directory-aadconnect/).</span></span> 
  
<span data-ttu-id="28fe5-185">应使用默认值安装 AAD Connect，但以下情况除外：</span><span class="sxs-lookup"><span data-stu-id="28fe5-185">AAD Connect should be installed using the defaults, except for the following:</span></span> 
  
1. <span data-ttu-id="28fe5-186">已部署和工作的单一登录（AD FS）：选择 "不**配置**"。</span><span class="sxs-lookup"><span data-stu-id="28fe5-186">Single sign-in - with AD FS already deployed and working: Select **Do not configure**.</span></span>
    
2. <span data-ttu-id="28fe5-187">连接目录：添加所有域。</span><span class="sxs-lookup"><span data-stu-id="28fe5-187">Connect your directories: Add all of the domains.</span></span>
    
3. <span data-ttu-id="28fe5-188">标识本地目录中的用户：选择**多个目录中存在的用户标识**，然后选择**ObjectSID**和**msExchangeMasterAccountSID**属性。</span><span class="sxs-lookup"><span data-stu-id="28fe5-188">Identify users in on-premises directories: Select **User identities exist across multiple directories**, and select the **ObjectSID** and **msExchangeMasterAccountSID** attributes.</span></span>
    
4. <span data-ttu-id="28fe5-189">在 Azure AD 中标识用户：源锚点：选择您在阅读[选择一个好的 sourceAnchor 属性](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute)（用户主体名称- **userPrincipalName**）后选择的属性。</span><span class="sxs-lookup"><span data-stu-id="28fe5-189">Identify users in Azure AD: Source Anchor: Select the attribute you've chosen after reading [Selecting a good sourceAnchor attribute](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts#selecting-a-good-sourceanchor-attribute), User Principal Name - **userPrincipalName**.</span></span>
    
5.  <span data-ttu-id="28fe5-190">可选功能：选择是否已部署 Exchange 混合。</span><span class="sxs-lookup"><span data-stu-id="28fe5-190">Optional features: Select whether you have Exchange hybrid deployed.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="28fe5-191">如果您仅拥有 Exchange Online，则在自动发现过程中可能存在由于 CNAME 重定向导致 OAuth 故障的问题。</span><span class="sxs-lookup"><span data-stu-id="28fe5-191">If you have only Exchange Online, there could be an issue with OAuth failures during autodiscover because of CNAME redirection.</span></span> <span data-ttu-id="28fe5-192">若要更正此错误，您需要通过从 Skype for Business Server 命令行管理程序运行以下 cmdlet 来设置 Exchange 自动发现 URL：</span><span class="sxs-lookup"><span data-stu-id="28fe5-192">To correct this, you will need to set the Exchange Autodiscover URL by running the following cmdlet from the Skype for Business Server Management Shell:</span></span>
    >
    > ```powershell
    > Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc 
    > ```
    
6.  <span data-ttu-id="28fe5-193">AD FS 服务器场：选择 "**使用现有 Windows Server 2012 R2 AD fs 场**"，并输入 AD FS 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="28fe5-193">AD FS Farm: Select **Use an existing Windows Server 2012 R2 AD FS farm** and enter the name of the AD FS server.</span></span>
    
7.  <span data-ttu-id="28fe5-194">完成向导并执行必要的验证。</span><span class="sxs-lookup"><span data-stu-id="28fe5-194">Finish the wizard and perform the necessary validations.</span></span>
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a><span data-ttu-id="28fe5-195">为 Skype for Business Server 配置混合连接</span><span class="sxs-lookup"><span data-stu-id="28fe5-195">Configure hybrid connectivity for Skype for Business Server</span></span>

<span data-ttu-id="28fe5-196">遵循配置 Skype for Business 混合的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="28fe5-196">Follow the best practices for configuring Skype for Business hybrid.</span></span> <span data-ttu-id="28fe5-197">有关详细信息，请参阅[规划混合连接](plan-hybrid-connectivity.md)和[配置混合连接](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-197">For more information information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a><span data-ttu-id="28fe5-198">为 Exchange Server 配置混合连接</span><span class="sxs-lookup"><span data-stu-id="28fe5-198">Configure hybrid connectivity for Exchange Server</span></span>

<span data-ttu-id="28fe5-199">如有必要，请遵循配置 Exchange 混合的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="28fe5-199">If necessary, follow the best practices for configuring Exchange hybrid.</span></span> <span data-ttu-id="28fe5-200">有关详细信息，请参阅[Exchange Server 混合部署](https://docs.microsoft.com/exchange/exchange-hybrid)。</span><span class="sxs-lookup"><span data-stu-id="28fe5-200">For more information, see [Exchange Server Hybrid Deployments](https://docs.microsoft.com/exchange/exchange-hybrid).</span></span> 
  
