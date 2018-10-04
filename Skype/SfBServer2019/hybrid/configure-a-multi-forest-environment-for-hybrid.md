---
title: 配置混合 for Business 的 Skype 的多林环境
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
ms.custom: ''
description: 以下各节提供有关如何配置具有资源/用户林模型，以提供业务功能在混合方案的 Skype 中的多林环境的指南。
ms.openlocfilehash: 72c0a91c3a5a90b4ec83eb5f71a5601ccfb48bb1
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375104"
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a><span data-ttu-id="45b1b-103">配置混合 for Business 的 Skype 的多林环境</span><span class="sxs-lookup"><span data-stu-id="45b1b-103">Configure a multi-forest environment for hybrid Skype for Business</span></span>
 
<span data-ttu-id="45b1b-104">以下各节提供有关如何配置具有资源/用户林模型，以提供业务功能在混合方案的 Skype 中的多林环境的指南。</span><span class="sxs-lookup"><span data-stu-id="45b1b-104">The following sections provide guidance on how to configure an environment that has multiple forests in a Resource/User forest model to provide Skype for Business functionality in a hybrid scenario.</span></span> 
  
![适用于混合部署的多林环境](../../sfbserver/media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a><span data-ttu-id="45b1b-106">验证林拓扑</span><span class="sxs-lookup"><span data-stu-id="45b1b-106">Validate the forest topology</span></span>

<span data-ttu-id="45b1b-p101">支持多个用户林。注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="45b1b-p101">Multiple user forests are supported. Keep the following in mind:</span></span> 
  
- <span data-ttu-id="45b1b-109">对于单用户林或多个用户林部署，必须有 Skype 业务 server 的单个部署。</span><span class="sxs-lookup"><span data-stu-id="45b1b-109">For either a single-user forest or multiple-user forest deployment, there must be a single deployment of Skype for Business Server.</span></span>
    
- <span data-ttu-id="45b1b-110">有关受支持版本的 Lync Server 和企业服务器的 Skype 混合配置，请参阅[规划之间 Skype Business Server 和 Office 365 的混合连接性](plan-hybrid-connectivity.md)中的[拓扑要求](plan-hybrid-connectivity.md#BKMK_Topology)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-110">For supported versions of Lync Server and Skype for Business Server in a hybrid configuration, see [Topology requirements](plan-hybrid-connectivity.md#BKMK_Topology) in [Plan hybrid connectivity between Skype for Business Server and Office 365](plan-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="45b1b-111">可以在一个或多个林中，其中可能包含或不包含业务服务器包含 Skype 的林部署 Exchange 服务器。</span><span class="sxs-lookup"><span data-stu-id="45b1b-111">Exchange Server can be deployed in one or more forests, which may or may not include the forest containing Skype for Business Server.</span></span> <span data-ttu-id="45b1b-112">请确保您应用了最新累积更新。</span><span class="sxs-lookup"><span data-stu-id="45b1b-112">Make sure you have applied the latest Cumulative Update.</span></span>
    
- <span data-ttu-id="45b1b-113">有关与 Exchange Server 的共存的详细信息，包括支持条件和限制各种组合中的内部部署和联机状态，请参阅[计划集成 Skype 商业和 Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[支持的功能](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-113">For details on co-existence with Exchange Server, including support criteria and limitations in various combinations of on-premises and online, see [Feature support](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../sfbserver/plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).</span></span>
    
<span data-ttu-id="45b1b-114">有关详细信息，请参阅[系统要求](../plan/system-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-114">For more information, please refer to [System requirements](../plan/system-requirements.md).</span></span>
  
## <a name="user-homing-considerations"></a><span data-ttu-id="45b1b-115">用户驻留注意事项</span><span class="sxs-lookup"><span data-stu-id="45b1b-115">User homing considerations</span></span>

<span data-ttu-id="45b1b-116">Skype 的企业用户驻留在本地可以具有 Exchange 驻留在本地或联机。</span><span class="sxs-lookup"><span data-stu-id="45b1b-116">Skype for Business users homed on premises can have Exchange homed on premises or online.</span></span> <span data-ttu-id="45b1b-117">为了获得最佳体验; 应使用 Skype Online 业务用户的 Exchange Online但是，这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="45b1b-117">Skype for Business Online users should use Exchange Online for an optimal experience; however, this is not required.</span></span> <span data-ttu-id="45b1b-118">本地 Exchange 不需要在任一情况下实现 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="45b1b-118">Exchange on premises is not required to implement Skype for Business in either case.</span></span>
  
## <a name="configure-forest-trusts"></a><span data-ttu-id="45b1b-119">配置林信任</span><span class="sxs-lookup"><span data-stu-id="45b1b-119">Configure forest trusts</span></span>

<span data-ttu-id="45b1b-120">所需的信任是资源林与每个用户林之间的双向可传递信任。</span><span class="sxs-lookup"><span data-stu-id="45b1b-120">The trusts required are two-way transitive trusts between the resource forest and each of the user forests.</span></span> <span data-ttu-id="45b1b-121">如果您有多个用户林，则要启用跨林身份验证，必须为这些林中的每个林启用名称前缀路由。</span><span class="sxs-lookup"><span data-stu-id="45b1b-121">If you have multiple user forests, to enable cross-forest authentication it is important that Name Suffix Routing is enabled for each of these forest trusts.</span></span> <span data-ttu-id="45b1b-122">有关说明，请参阅[管理林信任](https://technet.microsoft.com/en-us/library/cc772440.aspx)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-122">For instructions, see [Managing Forest Trusts](https://technet.microsoft.com/en-us/library/cc772440.aspx).</span></span> 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a><span data-ttu-id="45b1b-123">到林中承载 Skype for Business 同步帐户</span><span class="sxs-lookup"><span data-stu-id="45b1b-123">Synchronize accounts into the forest hosting Skype for Business</span></span>

<span data-ttu-id="45b1b-124">当 Skype 的业务服务器部署在一个林中 （资源林），但功能向用户提供在一个或多个其他林中 （帐户林） 时，必须作为林中已禁用的用户对象表示其他林中的用户其中的 Skype业务服务器部署。</span><span class="sxs-lookup"><span data-stu-id="45b1b-124">When Skype for Business Server is deployed in one forest (a resource forest), but provides functionality to users in one or more other forests (account forests), users in the other forests must be represented as disabled user objects in the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="45b1b-125">标识管理产品，例如 Microsoft Identity Manager 中，需要部署和配置设置并将从帐户林的用户同步到林中部署 Skype 业务服务器的位置。</span><span class="sxs-lookup"><span data-stu-id="45b1b-125">An identity management product, such as Microsoft Identity Manager, needs to be deployed and configured to provision and synchronize the users from the account forests into the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="45b1b-126">用户必须同步到林中承载 Skype 业务服务器作为已禁用的用户对象。</span><span class="sxs-lookup"><span data-stu-id="45b1b-126">Users must be synchronized into the forest hosting Skype for Business Server as disabled user objects.</span></span> <span data-ttu-id="45b1b-127">用户无法同步为 Active Directory 联系人对象，因为 Azure Active Directory 连接将不正确同步联系人到用于与 Skype 的 Azure AD。</span><span class="sxs-lookup"><span data-stu-id="45b1b-127">Users cannot be synchronized as Active Directory contact objects, because Azure Active Directory Connect will not properly synchronize contacts into Azure AD for use with Skype.</span></span>
  
<span data-ttu-id="45b1b-128">任何多林配置，无论业务服务器承载 Skype 林还可以位于同一林中的任何已启用用户提供功能。</span><span class="sxs-lookup"><span data-stu-id="45b1b-128">Regardless of any multi-forest configuration, the forest hosting Skype for Business Server can also provide functionality for any enabled users that exist in the same forest.</span></span>
  
<span data-ttu-id="45b1b-129">若要获得正确的身份同步，需要同步下列属性：</span><span class="sxs-lookup"><span data-stu-id="45b1b-129">To get proper identity synchronization, the following attributes need to be synchronized:</span></span> 
  
|<span data-ttu-id="45b1b-130">**用户林**</span><span class="sxs-lookup"><span data-stu-id="45b1b-130">**User forests**</span></span>|<span data-ttu-id="45b1b-131">**资源林**</span><span class="sxs-lookup"><span data-stu-id="45b1b-131">**Resource forests**</span></span>|
|:-----|:-----|
|<span data-ttu-id="45b1b-132">选择的帐户链接属性</span><span class="sxs-lookup"><span data-stu-id="45b1b-132">chosen account link attribute</span></span>  <br/> |<span data-ttu-id="45b1b-133">选择的帐户链接属性</span><span class="sxs-lookup"><span data-stu-id="45b1b-133">chosen account link attribute</span></span>  <br/> |
|<span data-ttu-id="45b1b-134">邮件 </span><span class="sxs-lookup"><span data-stu-id="45b1b-134">mail</span></span>  <br/> |<span data-ttu-id="45b1b-135">邮件 </span><span class="sxs-lookup"><span data-stu-id="45b1b-135">mail</span></span>  <br/> |
|<span data-ttu-id="45b1b-136">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45b1b-136">ProxyAddresses</span></span>  <br/> |<span data-ttu-id="45b1b-137">ProxyAddresses</span><span class="sxs-lookup"><span data-stu-id="45b1b-137">ProxyAddresses</span></span>  <br/> |
|<span data-ttu-id="45b1b-138">ObjectSID</span><span class="sxs-lookup"><span data-stu-id="45b1b-138">ObjectSID</span></span>  <br/> |<span data-ttu-id="45b1b-139">msRTCSIP OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="45b1b-139">msRTCSIP-OriginatorSID</span></span>  <br/> |
   
<span data-ttu-id="45b1b-140">[选择帐户链接属性](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)将用作源定位标记。</span><span class="sxs-lookup"><span data-stu-id="45b1b-140">The [chosen account link attribute](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/) will be used as the Source Anchor.</span></span> <span data-ttu-id="45b1b-141">如果您想要使用的不同且不会改变属性，您可能会这样;只需一定要编辑的 AD FS 声明规则和 AAD 连接配置过程中选择的属性。</span><span class="sxs-lookup"><span data-stu-id="45b1b-141">If you have a different and immutable attribute that you would prefer to use, you may do so; just be sure to edit the AD FS claims rule and select the attribute during the AAD Connect configuration.</span></span>
  
<span data-ttu-id="45b1b-142">不同步林之间 Upn。</span><span class="sxs-lookup"><span data-stu-id="45b1b-142">Do not sync the UPNs between the forests.</span></span> <span data-ttu-id="45b1b-143">在测试期间，我们发现我们需要将唯一的 UPN 用于每个用户林，因为不能在多个林中使用相同的 UPN。</span><span class="sxs-lookup"><span data-stu-id="45b1b-143">We found during testing that we needed to use a unique UPN for each user forest, as you cannot use the same UPN across multiple forests.</span></span> <span data-ttu-id="45b1b-144">因此，出现了两种可能性：同步 UPN 或不同步。</span><span class="sxs-lookup"><span data-stu-id="45b1b-144">As a result, we were presented with two possibilities, to synchronize the UPN or to not synchronize.</span></span> 
  
- <span data-ttu-id="45b1b-145">如果不会从每个用户林的唯一 UPN 已同步到关联的已禁用对象在资源林中，单一登录 (SSO) 将分解为至少初始登录尝试 （假定该用户选择保存密码选项）。</span><span class="sxs-lookup"><span data-stu-id="45b1b-145">If the unique UPN from each user forest was not synchronized to the associated disabled object in the resource forest, single sign-on (SSO) would be broken for at least the initial sign-in attempt (assuming the user selected the option to save password).</span></span> <span data-ttu-id="45b1b-146">在业务客户端 Skype，我们假定的 SIP/UPN 值都相同。</span><span class="sxs-lookup"><span data-stu-id="45b1b-146">In the Skype for Business client, we assume that the SIP/UPN values are the same.</span></span> <span data-ttu-id="45b1b-147">由于在此情况下 SIP 地址是 user@company.com，但用户林中已启用对象的 UPN 实际上是 user@contoso.company.com，初始登录尝试将会失败，并且系统将提示用户输入凭锯。</span><span class="sxs-lookup"><span data-stu-id="45b1b-147">Since the SIP address in this scenario is user@company.com, but the UPN of the enabled object in the user forest is in fact user@contoso.company.com, the initial login attempt would fail and the user would be prompted to enter credentials.</span></span> <span data-ttu-id="45b1b-148">在输入正确/实际 UPN 时，将会针对用户林中的域控制器完成身份验证请求，并且登录将会成功。</span><span class="sxs-lookup"><span data-stu-id="45b1b-148">Upon entering their correct/actual UPN, the authentication request would be completed against the domain controllers in the user forest, and sign-in would be successful.</span></span>
    
- <span data-ttu-id="45b1b-149">如果从每个用户林的唯一 UPN 已同步到关联的已禁用对象在资源林中，AD FS 身份验证将失败。</span><span class="sxs-lookup"><span data-stu-id="45b1b-149">If the unique UPN from each user forest was synchronized to the associated disabled object in the resource forest, AD FS authentication would fail.</span></span> <span data-ttu-id="45b1b-150">匹配的规则可找到资源林中对象的 UPN，但该 UPN 处于禁用状态，无法用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="45b1b-150">The matching rule would find the UPN on the object in the resource forest, which was disabled and could not be used for authentication.</span></span> 
    
## <a name="create-an-office-365-tenant"></a><span data-ttu-id="45b1b-151">创建 Office 365 租户</span><span class="sxs-lookup"><span data-stu-id="45b1b-151">Create an Office 365 tenant</span></span>

<span data-ttu-id="45b1b-152">接下来需要设置要用于部署的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="45b1b-152">You will next need to provision an Office 365 tenant to use with your deployment.</span></span> <span data-ttu-id="45b1b-153">有关详细信息，请参阅[订阅、 许可证、 帐户和 Microsoft 云服务的租户](https://docs.microsoft.com/en-us/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-153">For more information, please see [Subscriptions, licenses, accounts, and tenants for Microsoft's cloud offerings](https://docs.microsoft.com/en-us/office365/enterprise/subscriptions-licenses-accounts-and-tenants-for-microsoft-cloud-offerings).</span></span> 
  
## <a name="configure-active-directory-federation-services"></a><span data-ttu-id="45b1b-154">配置 Active Directory 联合身份验证服务</span><span class="sxs-lookup"><span data-stu-id="45b1b-154">Configure Active Directory Federation Services</span></span>

<span data-ttu-id="45b1b-155">租户后，您将需要配置 Active Directory 联合身份验证服务 (AD FS) 在每个用户林。</span><span class="sxs-lookup"><span data-stu-id="45b1b-155">Once you have a tenant, you will need to configure Active Directory Federation Services (AD FS) in each of the user forests.</span></span> <span data-ttu-id="45b1b-156">这假设您具有每个林的唯一 SIP 及 SMTP 地址和用户主体名称 (UPN)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-156">This assumes you have a unique SIP and SMTP address and User Principal Name (UPN) for each forest.</span></span> <span data-ttu-id="45b1b-157">AD FS 是可选的此处用于获取单一登录 (SSO)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-157">AD FS is optional and is used here to get single sign-on (SSO).</span></span> <span data-ttu-id="45b1b-158">DirSync with Password Sync 也受支持，并且还可以替代 AD FS 使用。</span><span class="sxs-lookup"><span data-stu-id="45b1b-158">DirSync with Password Sync is also supported and can also be used in place of AD FS.</span></span> 
  
<span data-ttu-id="45b1b-159">只会测试具有匹配的 SIP/SMTP 和 UPN 的部署。</span><span class="sxs-lookup"><span data-stu-id="45b1b-159">Only deployments with matching SIP/SMTP and UPNs were tested.</span></span> <span data-ttu-id="45b1b-160">不具有匹配的 SIP/SMTP/Upn 可能会导致缩减功能，如 Exchange 集成和 SSO 问题。</span><span class="sxs-lookup"><span data-stu-id="45b1b-160">Not having matching SIP/SMTP/UPNs may result in reduced functionality, such as problems with Exchange integration and SSO.</span></span> 
  
<span data-ttu-id="45b1b-161">除非您使用唯一的 SIP/SMTP/UPN 中每个林的用户时，您仍然可以运行 SSO 问题，无论部署 AD FS 的位置：</span><span class="sxs-lookup"><span data-stu-id="45b1b-161">Unless you use a unique SIP/SMTP/UPN for users from each forest, you can still run into SSO problems, regardless of where AD FS is deployed:</span></span> 
  
- <span data-ttu-id="45b1b-162">对于在每个用户林中部署了 AD FS 服务器场的资源/用户林之间的单向或双向信任，所有用户共享共同的 SIP/SMTP 域，但将唯一 UPN 用于每个用户林。</span><span class="sxs-lookup"><span data-stu-id="45b1b-162">One-way or two-way trusts between resource/user forests with AD FS farm deployed in each user forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
- <span data-ttu-id="45b1b-163">对于仅在资源林中部署了 AD FS 服务器场的资源/用户林之间的双向信任，所有用户共享共同的 SIP/SMTP 域，但将唯一 UPN 用于每个用户林。</span><span class="sxs-lookup"><span data-stu-id="45b1b-163">Two-way trusts between resource/user forests with AD FS farm deployed only in resource forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
<span data-ttu-id="45b1b-p113">通过在每个用户林中放置 AD FS 服务器场并将唯一的 SIP/SMTP/UPN 用于每个林，我们解决了这两个问题。在身份验证期间，将只搜索并匹配特定用户林中的帐户。这将有助于提供更无缝的身份验证流程。</span><span class="sxs-lookup"><span data-stu-id="45b1b-p113">By placing an AD FS farm in each user forest and using a unique SIP/SMTP/UPN for each forest, we resolve both issues. Only the accounts in that specific user forest would be searched and matched during authentication attempts. This will help provide a more seamless authentication process.</span></span> 
  
<span data-ttu-id="45b1b-167">这将是 Windows Server 2012 R2 AD FS 的标准部署，应处于正常工作状态才能继续。</span><span class="sxs-lookup"><span data-stu-id="45b1b-167">This will be a standard deployment of the Windows Server 2012 R2 AD FS and should be working before continuing.</span></span> <span data-ttu-id="45b1b-168">有关说明，请参阅[How To Office 365 的安装 AD FS 2012 R2](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-168">For instructions, see [How To Install AD FS 2012 R2 For Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx).</span></span> 
  
<span data-ttu-id="45b1b-169">部署之后，您必须编辑声明规则以与先前选择的“来源作者”相匹配。</span><span class="sxs-lookup"><span data-stu-id="45b1b-169">Once deployed, you then have to edit the claims rule to match the Source Anchor selected earlier.</span></span> <span data-ttu-id="45b1b-170">在 AD FS MMC 中，在信赖方信任下右键单击**Microsoft Office 365 标识平台**，，然后单击**编辑声明规则**。</span><span class="sxs-lookup"><span data-stu-id="45b1b-170">In the AD FS MMC, under Relying Party Trusts, right-click **Microsoft Office 365 Identity Platform**, and then click **Edit Claim Rules**.</span></span> <span data-ttu-id="45b1b-171">编辑的第一个规则，并将 ObjectSID 更改为**employeeNumber**。</span><span class="sxs-lookup"><span data-stu-id="45b1b-171">Edit the first rule, and change ObjectSID to **employeeNumber**.</span></span> 
  
![多林编辑规则屏幕](../../sfbserver/media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a><span data-ttu-id="45b1b-173">配置 AAD Connect</span><span class="sxs-lookup"><span data-stu-id="45b1b-173">Configure AAD Connect</span></span>

<span data-ttu-id="45b1b-p116">AAD Connect 将用于在不同林之间以及不同林与 Office 365 之间合并帐户。您应该在资源林中部署 AAD Connect。必须能够在多个林与 Office 365 之间同步，Dirsync 不支持此操作。</span><span class="sxs-lookup"><span data-stu-id="45b1b-p116">AAD Connect will be used to merge the accounts between the different forests and between the forests and Office 365. You should deploy AAD Connect in the resource forest. It is required to be able to synchronize multiple forests and Office 365, which is not supported by Dirsync.</span></span> 
  
<span data-ttu-id="45b1b-p117">AAD Connect 不会在内部部署林之间同步帐户。它使用 AD 连接来读取已在内部部署林之间同步的对象（通过 FIM 或类似产品）。然后，它利用筛选规则创建其元节中相匹配的已启用和已禁用对象的单一表示，然后将该单一已合并对象复制到 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="45b1b-p117">AAD Connect does not synchronize the accounts between on-premises forests. It uses AD connectors to read objects that are already synchronized across on-premises forests (by FIM or similar products). It then leverages filtering rules to create a single representation of both the matching enabled and disabled object in its metaverse, and then replicates that single, merged object into Office 365.</span></span> 
  
<span data-ttu-id="45b1b-180">完成之后并且 AAD Connect 正在合并时，如果您查看元节中的对象，应该看到类似如下的内容：</span><span class="sxs-lookup"><span data-stu-id="45b1b-180">When finished and AAD Connect is merging, if you look at an object in the metaverse, you should see something similar to this:</span></span> 
  
![多林元节对象屏幕](../../sfbserver/media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
<span data-ttu-id="45b1b-182">突出显示的属性已从 Office 365 合并的绿色，黄色是从用户林，并且蓝色来自资源林。</span><span class="sxs-lookup"><span data-stu-id="45b1b-182">The green highlighted attributes were merged from Office 365, the yellow are from the user forest, and the blue are from the resource forest.</span></span> 
  
<span data-ttu-id="45b1b-183">这是一个测试用户，，您可以看到 sourceAnchor 和用户 cloudSourceAnchor AAD 连接已识别和本例中为 1101，即 employeeNumber 资源林对象从 Office 365 中，选择之前。</span><span class="sxs-lookup"><span data-stu-id="45b1b-183">This is a test user, and you can see that AAD Connect has identified the sourceAnchor and the cloudSourceAnchor from the user and the resource forest objects from Office 365, in our case 1101, which is the employeeNumber selected earlier.</span></span> <span data-ttu-id="45b1b-184">然后，系统能够将此对象合并到您在上方看到的内容中。</span><span class="sxs-lookup"><span data-stu-id="45b1b-184">It then was able to merge this object into what you see above.</span></span> 
  
<span data-ttu-id="45b1b-185">有关详细信息，请参阅[Azure Active Directory 集成本地目录](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-185">For more information, see [Integrate your on-premises directories with Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/).</span></span> 
  
<span data-ttu-id="45b1b-186">应使用默认设置，除以下安装 AAD 连接：</span><span class="sxs-lookup"><span data-stu-id="45b1b-186">AAD Connect should be installed using the defaults, except for the following:</span></span> 
  
1. <span data-ttu-id="45b1b-187">单一登录-与已部署的 AD FS 和工作： 选择**不要配置**。</span><span class="sxs-lookup"><span data-stu-id="45b1b-187">Single sign-in - with AD FS already deployed and working: Select **Do not configure**.</span></span>
    
2. <span data-ttu-id="45b1b-188">连接您的目录： 添加的所有域。</span><span class="sxs-lookup"><span data-stu-id="45b1b-188">Connect your directories: Add all of the domains.</span></span>
    
3. <span data-ttu-id="45b1b-189">确定本地目录中的用户： 选择**跨多个目录存在用户标识**，然后选择**ObjectSID**和**msExchangeMasterAccountSID**属性。</span><span class="sxs-lookup"><span data-stu-id="45b1b-189">Identify users in on-premises directories: Select **User identities exist across multiple directories**, and select the **ObjectSID** and **msExchangeMasterAccountSID** attributes.</span></span>
    
4. <span data-ttu-id="45b1b-190">Azure AD 中标识用户： 源定位： 选择您已阅读[选择良好 sourceAnchor 属性](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)，用户主体名称- **userPrincipalName**后选择的属性。</span><span class="sxs-lookup"><span data-stu-id="45b1b-190">Identify users in Azure AD: Source Anchor: Select the attribute you've chosen after reading [Selecting a good sourceAnchor attribute](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/), User Principal Name - **userPrincipalName**.</span></span>
    
5.  <span data-ttu-id="45b1b-191">可选功能： 选择是否已部署的 Exchange 混合部署。</span><span class="sxs-lookup"><span data-stu-id="45b1b-191">Optional features: Select whether you have Exchange hybrid deployed.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="45b1b-192">如果您只有 Exchange Online，则在自动发现期间，可能会因为 CNAME 重定向而出现 OAuth 失败问题。</span><span class="sxs-lookup"><span data-stu-id="45b1b-192">If you have only Exchange Online, there could be an issue with OAuth failures during autodiscover because of CNAME redirection.</span></span> <span data-ttu-id="45b1b-193">若要纠正此问题，您将需要从 Skype 的业务 Server Management Shell 中运行以下 cmdlet 设置 Exchange 自动发现 URL:</span><span class="sxs-lookup"><span data-stu-id="45b1b-193">To correct this, you will need to set the Exchange Autodiscover URL by running the following cmdlet from the Skype for Business Server Management Shell:</span></span>
  
    <span data-ttu-id="45b1b-194">Set-csoauthconfiguration-ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc</span><span class="sxs-lookup"><span data-stu-id="45b1b-194">Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://<span>autodiscover-s.outlook.com/autodiscover/autodiscover.svc</span></span> 
    
6.  <span data-ttu-id="45b1b-195">AD FS 服务器场：选择**使用现有 Windows Server 2012 R2 AD FS 服务器场**并输入 AD FS 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="45b1b-195">AD FS Farm: Select **Use an existing Windows Server 2012 R2 AD FS farm** and enter the name of the AD FS server.</span></span>
    
7.  <span data-ttu-id="45b1b-196">完成向导并执行必要的验证。</span><span class="sxs-lookup"><span data-stu-id="45b1b-196">Finish the wizard and perform the necessary validations.</span></span>
    
## <a name="configure-hybrid-connectivity-for-skype-for-business-server"></a><span data-ttu-id="45b1b-197">为业务 Server 的 Skype 配置混合连接性</span><span class="sxs-lookup"><span data-stu-id="45b1b-197">Configure hybrid connectivity for Skype for Business Server</span></span>

<span data-ttu-id="45b1b-198">按照业务混合配置 Skype 的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="45b1b-198">Follow the best practices for configuring Skype for Business hybrid.</span></span> <span data-ttu-id="45b1b-199">信息的详细信息，请参阅[规划混合连接性](plan-hybrid-connectivity.md)和[配置混合连接性](configure-hybrid-connectivity.md)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-199">For more information information, see [Plan hybrid connectivity](plan-hybrid-connectivity.md) and [Configure hybrid connectivity](configure-hybrid-connectivity.md).</span></span> 
  
## <a name="configure-hybrid-connectivity-for-exchange-server"></a><span data-ttu-id="45b1b-200">配置 Exchange Server 混合连接性</span><span class="sxs-lookup"><span data-stu-id="45b1b-200">Configure hybrid connectivity for Exchange Server</span></span>

<span data-ttu-id="45b1b-201">如有必要，遵循配置 Exchange 混合部署的最佳做法操作。</span><span class="sxs-lookup"><span data-stu-id="45b1b-201">If necessary, follow the best practices for configuring Exchange hybrid.</span></span> <span data-ttu-id="45b1b-202">有关详细信息，请参阅[Exchange Server 混合部署](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="45b1b-202">For more information, see [Exchange Server Hybrid Deployments](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx).</span></span> 
  

