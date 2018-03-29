---
title: 配置多目录林环境中的混合业务的 Skype
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/17/2017
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- Ent_O365_Hybrid
- IT_Skype16
- IT_Skype4B_Hybrid
ms.custom: Strat_SB_Hybrid
ms.assetid: 960ab8a3-352d-4b18-bc01-55b35f30ca0d
description: 以下各节提供有关如何配置为 Skype 提供业务功能的混合方案资源/用户目录林模型中的多个林的环境指导。
ms.openlocfilehash: ea2e650925dee8851419baca2a64d70585b19036
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="configure-a-multi-forest-environment-for-hybrid-skype-for-business"></a><span data-ttu-id="3b50f-103">配置多目录林环境中的混合业务的 Skype</span><span class="sxs-lookup"><span data-stu-id="3b50f-103">Configure a multi-forest environment for hybrid Skype for Business</span></span>
 
<span data-ttu-id="3b50f-104">以下各节提供有关如何配置为 Skype 提供业务功能的混合方案资源/用户目录林模型中的多个林的环境指导。</span><span class="sxs-lookup"><span data-stu-id="3b50f-104">The following sections provide guidance on how to configure an environment that has multiple forests in a Resource/User forest model to provide Skype for Business functionality in a hybrid scenario.</span></span> 
  
![适用于混合部署的多林环境](../../media/5f079435-b252-4a6a-9638-3577d55b2873.png)
  
## <a name="validate-the-forest-topology"></a><span data-ttu-id="3b50f-106">验证林拓扑</span><span class="sxs-lookup"><span data-stu-id="3b50f-106">Validate the Forest Topology</span></span>

<span data-ttu-id="3b50f-p101">支持多个用户林。注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="3b50f-p101">Multiple user forests are supported. Keep the following in mind:</span></span> 
  
- <span data-ttu-id="3b50f-109">对于单个用户目录林或多用户目录林部署中，必须有 Skype 业务服务器的单个部署。</span><span class="sxs-lookup"><span data-stu-id="3b50f-109">For either a single user forest or multiple user forest deployment, there must be a single deployment of Skype for Business Server.</span></span>
    
- <span data-ttu-id="3b50f-110">在混合配置 Lync Server 和 Skype 业务服务器的受支持版本，请参阅在[规划业务服务器和 Skype 的在线业务 Skype 之间的混合连接](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md)[拓扑要求](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-110">For supported versions of Lync Server and Skype for Business Server in a hybrid configuration, see [Topology requirements](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md#BKMK_Topology) in [Plan hybrid connectivity between Skype for Business Server and Skype for Business Online](../../skype-for-business-hybrid-solutions/plan-hybrid-connectivity.md).</span></span>
    
- <span data-ttu-id="3b50f-111">可以在其中可能包含或不包含的林 Skype 业务服务器的一个或多个目录林中部署 Exchange Server。</span><span class="sxs-lookup"><span data-stu-id="3b50f-111">Exchange Server can be deployed in one or more forests, which may or may not include the forest containing Skype for Business Server.</span></span> <span data-ttu-id="3b50f-112">确保您应用了最新的累积更新。</span><span class="sxs-lookup"><span data-stu-id="3b50f-112">Make sure you have applied the latest Cumulative Update.</span></span>
    
- <span data-ttu-id="3b50f-113">有关 Exchange Server 与共存的详细信息，包括支持条件和限制的各种组合的内部部署和联机，请参阅[计划集成 Skype 业务和交换](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md)中的[支持的功能](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-113">For details on co-existence with Exchange Server, including support criteria and limitations in various combinations of on-premises and online, see [Feature support](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md#feature_support) in [Plan to integrate Skype for Business and Exchange](../../plan-your-deployment/integrate-with-exchange/integrate-with-exchange.md).</span></span>
    
<span data-ttu-id="3b50f-114">有关详细信息，请参阅[有关业务服务器 2015年的 Skype 的环境要求](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-114">For more information, please refer to [Environmental requirements for Skype for Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/environmental-requirements.md).</span></span>
  
## <a name="user-homing-considerations"></a><span data-ttu-id="3b50f-115">用户驻留注意事项</span><span class="sxs-lookup"><span data-stu-id="3b50f-115">User homing considerations</span></span>

<span data-ttu-id="3b50f-116">Skype 为业务用户驻留在本地上可以有交换穴内部部署或联机。</span><span class="sxs-lookup"><span data-stu-id="3b50f-116">Skype for Business users homed on premises can have Exchange homed on premises or online.</span></span> <span data-ttu-id="3b50f-117">Skype 的在线业务的用户应使用 Exchange Online 获得最佳的体验;但是，这不是必需的。</span><span class="sxs-lookup"><span data-stu-id="3b50f-117">Skype for Business Online users should use Exchange Online for an optimal experience; however, this is not required.</span></span> <span data-ttu-id="3b50f-118">在部署 Exchange 不需要在任一情况下实现业务的 Skype。</span><span class="sxs-lookup"><span data-stu-id="3b50f-118">Exchange on premises is not required to implement Skype for Business in either case.</span></span>
  
## <a name="configure-forest-trusts"></a><span data-ttu-id="3b50f-119">配置林信任</span><span class="sxs-lookup"><span data-stu-id="3b50f-119">Configure Forest Trusts</span></span>

<span data-ttu-id="3b50f-120">所需的信任是资源林与每个用户林之间的双向可传递信任。</span><span class="sxs-lookup"><span data-stu-id="3b50f-120">The trusts required are two-way transitive trusts between the resource forest and each of the user forests.</span></span> <span data-ttu-id="3b50f-121">如果您有多个用户林，则要启用跨林身份验证，必须为这些林中的每个林启用名称前缀路由。</span><span class="sxs-lookup"><span data-stu-id="3b50f-121">If you have multiple user forests, to enable cross-forest authentication it is important that Name Suffix Routing is enabled for each of these forest trusts.</span></span> <span data-ttu-id="3b50f-122">有关说明，请参阅[管理林信任](https://technet.microsoft.com/en-us/library/cc772440.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-122">For instructions, see [Managing Forest Trusts](https://technet.microsoft.com/en-us/library/cc772440.aspx).</span></span> 
  
## <a name="synchronize-accounts-into-the-forest-hosting-skype-for-business"></a><span data-ttu-id="3b50f-123">同步到承载业务的 Skype 林中的帐户</span><span class="sxs-lookup"><span data-stu-id="3b50f-123">Synchronize Accounts into the forest hosting Skype for Business</span></span>

<span data-ttu-id="3b50f-124">当 Skype 的业务服务器被部署在一个目录林 （资源目录林），但提供的功能到一个或多个其他目录林中的用户 （帐户目录林） 时，必须为目录林中的被禁用的用户对象代表其他目录林中的用户的 Skype 的企业服务器被部署。</span><span class="sxs-lookup"><span data-stu-id="3b50f-124">When Skype for Business Server is deployed in one forest (a resource forest), but provides functionality to users in one or more other forests (account forests), users in the other forests must be represented as disabled user objects in the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="3b50f-125">标识管理产品，如 Microsoft 标识管理器需要部署和配置设置和同步到该目录林中部署 Skype 业务服务器的位置的帐户目录林中的用户。</span><span class="sxs-lookup"><span data-stu-id="3b50f-125">An identity management product, such as Microsoft Identity Manager, needs to be deployed and configured to provision and synchronize the users from the account forests into the forest where Skype for Business Server is deployed.</span></span> <span data-ttu-id="3b50f-126">用户必须到林中为已禁用的用户对象的业务服务器承载 Skype 进行同步。</span><span class="sxs-lookup"><span data-stu-id="3b50f-126">Users must be synchronized into the forest hosting Skype for Business Server as disabled user objects.</span></span> <span data-ttu-id="3b50f-127">用户无法同步为 Active Directory 联系对象，因为 Azure 活动目录连接将不正确地同步联系人到 Azure 用于与 Skype 的广告。</span><span class="sxs-lookup"><span data-stu-id="3b50f-127">Users cannot be synchronized as Active Directory contact objects, because Azure Active Directory Connect will not properly synchronize contacts into Azure AD for use with Skype.</span></span>
  
<span data-ttu-id="3b50f-128">任何多目录林配置，无论业务服务器承载 Skype 林还可以位于同一个目录林中任何已启用用户提供功能。</span><span class="sxs-lookup"><span data-stu-id="3b50f-128">Regardless of any multi-forest configuration, the forest hosting Skype for Business Server can also provide functionality for any enabled users that exist in the same forest.</span></span>
  
<span data-ttu-id="3b50f-129">若要获得正确的身份同步，需要同步下列属性：</span><span class="sxs-lookup"><span data-stu-id="3b50f-129">To get proper identity synchronization, the following attributes need to be synchronized:</span></span> 
  
|<span data-ttu-id="3b50f-130">**用户的目录林**</span><span class="sxs-lookup"><span data-stu-id="3b50f-130">**User Forests**</span></span>|<span data-ttu-id="3b50f-131">**资源目录林**</span><span class="sxs-lookup"><span data-stu-id="3b50f-131">**Resource Forests**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3b50f-132">选择的帐户链接属性</span><span class="sxs-lookup"><span data-stu-id="3b50f-132">chosen account link attribute</span></span>  <br/> |<span data-ttu-id="3b50f-133">选择的帐户链接属性</span><span class="sxs-lookup"><span data-stu-id="3b50f-133">chosen account link attribute</span></span>  <br/> |
|<span data-ttu-id="3b50f-134">邮件 </span><span class="sxs-lookup"><span data-stu-id="3b50f-134">mail</span></span>  <br/> |<span data-ttu-id="3b50f-135">邮件 </span><span class="sxs-lookup"><span data-stu-id="3b50f-135">mail</span></span>  <br/> |
|<span data-ttu-id="3b50f-136">代理地址</span><span class="sxs-lookup"><span data-stu-id="3b50f-136">ProxyAddresses</span></span>  <br/> |<span data-ttu-id="3b50f-137">代理地址</span><span class="sxs-lookup"><span data-stu-id="3b50f-137">ProxyAddresses</span></span>  <br/> |
|<span data-ttu-id="3b50f-138">ObjectSID</span><span class="sxs-lookup"><span data-stu-id="3b50f-138">ObjectSID</span></span>  <br/> |<span data-ttu-id="3b50f-139">msRTCSIP OriginatorSID</span><span class="sxs-lookup"><span data-stu-id="3b50f-139">msRTCSIP-OriginatorSID</span></span>  <br/> |
   
<span data-ttu-id="3b50f-140">[选择帐户链接属性](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)将用作源定位。</span><span class="sxs-lookup"><span data-stu-id="3b50f-140">The [chosen account link attribute](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/) will be used as the Source Anchor.</span></span> <span data-ttu-id="3b50f-141">如果你有偏好使用的不同且不变的属性，则可以这样做，只是务必要编辑 AD FS 声明规则并在 AAD Connect 配置期间选择该属性。</span><span class="sxs-lookup"><span data-stu-id="3b50f-141">If you have a different and immutable attribute that you would prefer to use, you may do so, just be sure you edit the AD FS claims rule and select the attribute during the AAD Connect configuration.</span></span>
  
<span data-ttu-id="3b50f-142">不同步在目录林之间的 UPN。</span><span class="sxs-lookup"><span data-stu-id="3b50f-142">Do not sync the UPN's between the forests.</span></span> <span data-ttu-id="3b50f-143">在测试期间，我们发现我们需要将唯一的 UPN 用于每个用户林，因为不能在多个林中使用相同的 UPN。</span><span class="sxs-lookup"><span data-stu-id="3b50f-143">We found during testing that we needed to use a unique UPN for each user forest, as you cannot use the same UPN across multiple forests.</span></span> <span data-ttu-id="3b50f-144">因此，出现了两种可能性：同步 UPN 或不同步。</span><span class="sxs-lookup"><span data-stu-id="3b50f-144">As a result, we were presented with two possibilities, to synchronize the UPN or to not synchronize.</span></span> 
  
-  <span data-ttu-id="3b50f-p108">如果未将每个用户林中的唯一 UPN 与资源林中相关联的已禁用对象同步，至少会针对初始登录尝试中断单一登录（假设用户选择了保持密码的选项）。在 SfB 客户端中，我们假设 SIP/UPN 值相同。由于在此情况下 SIP 地址是 user@company.com，但用户林中已启用对象的 UPN 实际上是 user@contoso.company.com，初始登录尝试将会失败，并且系统将提示用户输入凭锯。在输入正确/实际 UPN 时，将会针对用户林中的域控制器完成身份验证请求，并且登录将会成功。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p108">If the unique UPN from each user forest was not synchronized to the associated disabled object in the resource forest, Single Sign-on would be broken for at least the initial sign-in attempt (assuming the user selected the option to save password). In the SfB client, we assume that the SIP/UPN values are the same. Since the SIP address in this scenario is user@company.com, but the UPN of the enabled object in the user forest is in fact user@contoso.company.com, the initial login attempt would fail and the user would be prompted to enter credentials. Upon entering their correct/actual UPN, the authentication request would be completed against the domain controllers in the user forest, and sign-in would be successful.</span></span>
    
- <span data-ttu-id="3b50f-p109">如果使每个用户林中的唯一 UPN 与资源林中相关联的已禁用对象同步，则 AD FS 身份验证将会失败。匹配的规则可找到资源林中对象的 UPN，但该 UPN 处于禁用状态，无法用于身份验证。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p109">If the unique UPN from each user forest was synchronized to the associated disabled object in resource forest, AD FS authentication would fail. The matching rule would find the UPN on the object in the resource forest, which was disabled and could not be used for authentication.</span></span> 
    
## <a name="create-an-office-365-tenant"></a><span data-ttu-id="3b50f-151">创建 Office 365 租户</span><span class="sxs-lookup"><span data-stu-id="3b50f-151">Create an Office 365 tenant</span></span>

<span data-ttu-id="3b50f-152">接下来需要设置要用于部署的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="3b50f-152">You will next need to provision an Office 365 tenant to use with your deployment.</span></span> <span data-ttu-id="3b50f-153">有关详细信息，请参阅[Office 365 提供步骤](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-153">For more information, please see [Office 365 Provisioning Steps](https://social.technet.microsoft.com/wiki/contents/articles/22808.office-365-provisioning-steps.aspx).</span></span> 
  
## <a name="configure-ad-fs"></a><span data-ttu-id="3b50f-154">配置 AD FS</span><span class="sxs-lookup"><span data-stu-id="3b50f-154">Configure AD FS</span></span>

<span data-ttu-id="3b50f-p111">具有租户之后，接着需要在每个用户林中配置 Active Directory 联合身份验证服务 (AD FS)。这假设您具有每个林的唯一 SIP 及 SMTP 地址和用户主体名称 (UPN)。AD FS 是可选的，在此处用来获取单一登录。DirSync with Password Sync 也受支持，并且还可以替代 AD FS 使用。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p111">Once you have a tenant, you will next need to configure Active Directory Federation Services (AD FS) ineach of the user forests. This assumes you have a unique SIP and SMTP address and User Principal Name (UPN) for each forest. AD FS is optional and is used here to get single-sign on. DirSync with Password Sync is also supported and can also be used in place of AD FS.</span></span> 
  
<span data-ttu-id="3b50f-p112">只会测试具有匹配的 SIP/SMTP 和 UPN 的部署。不具有匹配的 SIP/SMTP/UPN 可能导致缩减功能，例如 Exchange 集成和单一登入有问题。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p112">Only deployments with matching SIP/SMTP and UPNs were tested. Not having matching SIP/SMTP/UPNs may result in reduced functionality, such as problems with Exchange integration and single-sign on.</span></span> 
  
<span data-ttu-id="3b50f-161">除非您为每个目录林的用户使用唯一的 SIP/SMTP/UPN，您仍然可以运行到单一登录 (SSO) 问题-而不考虑部署 AD FS 的位置：</span><span class="sxs-lookup"><span data-stu-id="3b50f-161">Unless you use a unique SIP/SMTP/UPN for users from each forest, you can still run into Single Sign-on (SSO) problems - regardless of where AD FS is deployed:</span></span> 
  
- <span data-ttu-id="3b50f-162">对于在每个用户林中部署了 AD FS 服务器场的资源/用户林之间的单向或双向信任，所有用户共享共同的 SIP/SMTP 域，但将唯一 UPN 用于每个用户林。</span><span class="sxs-lookup"><span data-stu-id="3b50f-162">One-way or two-way trusts between resource/user forests with AD FS farm deployed in each user forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
- <span data-ttu-id="3b50f-163">对于仅在资源林中部署了 AD FS 服务器场的资源/用户林之间的双向信任，所有用户共享共同的 SIP/SMTP 域，但将唯一 UPN 用于每个用户林。</span><span class="sxs-lookup"><span data-stu-id="3b50f-163">Two-way trusts between resource/user forests with AD FS farm deployed only in resource forest, all users share common SIP/SMTP domain but unique UPN for each user forest.</span></span> 
    
<span data-ttu-id="3b50f-p113">通过在每个用户林中放置 AD FS 服务器场并将唯一的 SIP/SMTP/UPN 用于每个林，我们解决了这两个问题。在身份验证期间，将只搜索并匹配特定用户林中的帐户。这将有助于提供更无缝的身份验证流程。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p113">By placing an AD FS farm in each user forest and using a unique SIP/SMTP/UPN for each forest, we resolve both issues. Only the accounts in that specific user forest would be searched and matched during authentication attempts. This will help provide a more seamless authentication process.</span></span> 
  
<span data-ttu-id="3b50f-167">这将是 Windows Server 2012 R2 AD FS 的标准部署，应处于正常工作状态才能继续。</span><span class="sxs-lookup"><span data-stu-id="3b50f-167">This will be a standard deployment of the Windows Server 2012 R2 AD FS and should be working before continuing.</span></span> <span data-ttu-id="3b50f-168">有关说明，请参阅[如何安装 Office 365 的 AD FS 2012 R2](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-168">For instructions, see [How To Install AD FS 2012 R2 For Office 365](https://blogs.technet.com/b/rmilne/archive/2014/04/28/how-to-install-adfs-2012-r2-for-office-365.aspx).</span></span> 
  
<span data-ttu-id="3b50f-p115">部署之后，您必须编辑声明规则以与先前选择的“来源作者”相匹配。在 AD FS MMC 中，在“依赖方信任”下，右键单击 Microsoft Office 365 身份平台，然后单击“编辑声明规则”。编辑第一个规则并将 ObjectSID 更改为 employeeNumber。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p115">Once deployed, you then have to edit the claims rule to match the Source Anchor selected earlier. In the AD FS MMC, under Relying Party Trusts, right-click Microsoft Office 365 Identity Platform and then click Edit Claim Rules. Edit the first rule and change ObjectSID to employeeNumber.</span></span> 
  
![多林编辑规则屏幕](../../media/f5d485bd-52cc-437f-ba71-217f8902056c.png)
  
## <a name="configure-aad-connect"></a><span data-ttu-id="3b50f-173">配置 AAD Connect</span><span class="sxs-lookup"><span data-stu-id="3b50f-173">Configure AAD Connect</span></span>

<span data-ttu-id="3b50f-p116">AAD Connect 将用于在不同林之间以及不同林与 Office 365 之间合并帐户。您应该在资源林中部署 AAD Connect。必须能够在多个林与 Office 365 之间同步，Dirsync 不支持此操作。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p116">AAD Connect will be used to merge the accounts between the different forests and between the forests and Office 365. You should deploy AAD Connect in the resource forest. It is required to be able to synchronize multiple forests and Office 365, which is not supported by Dirsync.</span></span> 
  
<span data-ttu-id="3b50f-p117">AAD Connect 不会在内部部署林之间同步帐户。它使用 AD 连接来读取已在内部部署林之间同步的对象（通过 FIM 或类似产品）。然后，它利用筛选规则创建其元节中相匹配的已启用和已禁用对象的单一表示，然后将该单一已合并对象复制到 Office 365 中。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p117">AAD Connect does not synchronize the accounts between on-premises forests. It uses AD connectors to read objects that are already synchronized across on-premises forests (by FIM or similar products). It then leverages filtering rules to create a single representation of both the matching enabled and disabled object in its metaverse, and then replicates that single, merged object into Office 365.</span></span> 
  
<span data-ttu-id="3b50f-180">完成之后并且 AAD Connect 正在合并时，如果您查看元节中的对象，应该看到类似如下的内容：</span><span class="sxs-lookup"><span data-stu-id="3b50f-180">When finished and AAD Connect is merging, if you look at an object in the metaverse, you should see something similar to this:</span></span> 
  
![多林元节对象屏幕](../../media/16379880-2de3-4c43-b219-1551f5dec5f6.png)
  
<span data-ttu-id="3b50f-182">已从 Office 365 中合并绿色突出显示的属性，黄色来自用户林，蓝色来自资源林。</span><span class="sxs-lookup"><span data-stu-id="3b50f-182">The green highlighted attributes were merged from Office 365, the yellow are from the user forest and the blue are from the resource forest.</span></span> 
  
<span data-ttu-id="3b50f-p118">这是一个测试用户，您可以看到 AAD Connect 已识别用户和资源林对象及 Office 365 中的 sourceAnchor 和 cloudSourceAnchor，在我们的案例 1101 中，是先前选择的 employeeNumber。然后，系统能够将此对象合并到您在上方看到的内容中。</span><span class="sxs-lookup"><span data-stu-id="3b50f-p118">This is a test user, and you can see that AAD Connect has identified the sourceAnchor and the cloudSourceAnchor from the user and the resource forest objects and from Office 365, in our case 1101 which is the employeeNumber selected earlier. It then was able to merge this object into what you see above.</span></span> 
  
<span data-ttu-id="3b50f-185">有关详细信息，请参阅[集成内部标识使用 Azure 活动目录](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-185">For more information, see [Integrating your on-premises identities with Azure Active Directory](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect/).</span></span> 
  
<span data-ttu-id="3b50f-p119">应使用大部分默认值安装 AAD Connect。以下步骤例外：</span><span class="sxs-lookup"><span data-stu-id="3b50f-p119">AAD Connect should be installed using mostly the defaults. Except for the following steps:</span></span> 
  
1.  <span data-ttu-id="3b50f-188">单一登录-与 AD FS 已部署并正在运行，选择未配置</span><span class="sxs-lookup"><span data-stu-id="3b50f-188">Single sign-in - with AD FS already deployed and working, select Do not configure</span></span>
    
2. <span data-ttu-id="3b50f-189">连接您的目录-添加的所有域</span><span class="sxs-lookup"><span data-stu-id="3b50f-189">Connect your directories - add all of the domains</span></span> 
    
3.  <span data-ttu-id="3b50f-190">识别内部目录中的用户：**用户身份存在跨多个目录**中选择，然后选择**ObjectSID**和**msExchangeMasterAccountSID**属性</span><span class="sxs-lookup"><span data-stu-id="3b50f-190">Identify users in on-premises directories: Select **User identities exist across multiple directories** and select **ObjectSID** and **msExchangeMasterAccountSID** attributes</span></span>
    
4. <span data-ttu-id="3b50f-191">在 Azure AD 中标识用户： 源定位-选择您选择阅读[选择好的 sourceAnchor 特性](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/)后的特性、 用户主体名称的**范围内**</span><span class="sxs-lookup"><span data-stu-id="3b50f-191">Identify users in Azure AD: Source Anchor - Select the attribute you've chosen after reading [Selecting a good sourceAnchor attribute](https://azure.microsoft.com/en-us/documentation/articles/active-directory-aadconnect-design-concepts/), User Principal Name - **userPrincipalName**</span></span>
    
5.  <span data-ttu-id="3b50f-192">可选功能的选择是否有交换混合部署。</span><span class="sxs-lookup"><span data-stu-id="3b50f-192">Optional features - select whether you have Exchange hybrid deployed or not.</span></span>
    
    > [!NOTE]
    >  <span data-ttu-id="3b50f-193">如果您只有 Exchange Online，则在自动发现期间，可能会因为 CNAME 重定向而出现 OAuth 失败问题。</span><span class="sxs-lookup"><span data-stu-id="3b50f-193">If you have only Exchange Online, there could be an issue with OAuth failures during autodiscover because of CNAME redirection.</span></span> <span data-ttu-id="3b50f-194">若要解决此问题，您需要从 Skype 业务服务器管理外壳程序运行以下 cmdlet 来设置 Exchange 自动发现 URL:</span><span class="sxs-lookup"><span data-stu-id="3b50f-194">To correct this, you will need to set the Exchange Autodiscover URL by running the following cmdlet from the Skype for Business Server Management Shell:</span></span>
  
    <span data-ttu-id="3b50f-195">一组 CsOAuthConfiguration ExchangeAutoDiscoverURLhttps://autodiscover-s.outlook.com/autodiscover/autodiscover.svc</span><span class="sxs-lookup"><span data-stu-id="3b50f-195">Set-CsOAuthConfiguration -ExchangeAutoDiscoverURL https://autodiscover-s.outlook.com/autodiscover/autodiscover.svc</span></span> 
    
6.  <span data-ttu-id="3b50f-196">AD FS 服务器场：选择**使用现有 Windows Server 2012 R2 AD FS 服务器场**并输入 AD FS 服务器的名称。</span><span class="sxs-lookup"><span data-stu-id="3b50f-196">AD FS Farm: Select **Use an existing Windows Server 2012 R2 AD FS farm** and enter the name of the AD FS server.</span></span>
    
7.  <span data-ttu-id="3b50f-197">完成向导并执行必要的验证。</span><span class="sxs-lookup"><span data-stu-id="3b50f-197">Finish the wizard and perform the necessary validations.</span></span>
    
## <a name="configure-hybrid-mode-for-skype-for-business-server"></a><span data-ttu-id="3b50f-198">为 Skype for Business Server 配置混合模式</span><span class="sxs-lookup"><span data-stu-id="3b50f-198">Configure Hybrid mode for Skype for Business Server</span></span>

<span data-ttu-id="3b50f-199">按照有关业务混合配置 Skype 的最佳做法。</span><span class="sxs-lookup"><span data-stu-id="3b50f-199">Follow the best practices for configuring Skype for Business hybrid.</span></span> <span data-ttu-id="3b50f-200">计划的详细信息，请参阅[规划业务服务器 2015年的 Skype 的混合部署](https://technet.microsoft.com/en-us/library/jj205403.aspx)，和配置信息，请参阅[配置混合使用 Skype 的在线业务](https://technet.microsoft.com/en-us/library/jj204669.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-200">For more planning information, see [Plan your hybrid deployment for Skype for Business Server 2015](https://technet.microsoft.com/en-us/library/jj205403.aspx), and for configuration information see [Configure hybrid with Skype for Business Online](https://technet.microsoft.com/en-us/library/jj204669.aspx).</span></span> 
  
## <a name="configure-hybrid-mode-for-exchange-server"></a><span data-ttu-id="3b50f-201">为 Exchange Server 配置混合模式</span><span class="sxs-lookup"><span data-stu-id="3b50f-201">Configure hybrid mode for Exchange Server</span></span>

<span data-ttu-id="3b50f-202">如有必要，遵循配置 Exchange 混合部署的最佳做法操作。</span><span class="sxs-lookup"><span data-stu-id="3b50f-202">If necessary, follow the best practices for configuring Exchange hybrid.</span></span> <span data-ttu-id="3b50f-203">有关详细信息，请参阅[Exchange Server 混合部署](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b50f-203">For more information, see [Exchange Server Hybrid Deployments](https://technet.microsoft.com/en-us/library/jj200581%28v=exchg.150%29.aspx).</span></span> 
  

