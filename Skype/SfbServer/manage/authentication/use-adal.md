---
title: 如何将新式验证 (ADAL) 与 Skype for Business 配合使用
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 2/13/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 本文介绍了如何使用现代的身份验证 （这依赖于活动目录身份验证库 (ADAL) 以及 OAuth 2.0） 3 月 2016年中可以找到有关业务的业务服务器 2015年的 Skype 的 Skype 的累积更新。
ms.openlocfilehash: 9ef430f770b0b5d2ee22f2744e95b6df47fa95b9
ms.sourcegitcommit: ffca287cf70db2cab14cc1a6cb7cea68317bedd1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/05/2018
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="36ab3-103">如何将新式验证 (ADAL) 与 Skype for Business 配合使用</span><span class="sxs-lookup"><span data-stu-id="36ab3-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="36ab3-104">本文介绍了如何使用现代的身份验证 （这依赖于活动目录身份验证库 (ADAL) 以及 OAuth 2.0） 3 月 2016年中可以找到有关业务的业务服务器 2015年的 Skype 的 Skype 的累积更新。</span><span class="sxs-lookup"><span data-stu-id="36ab3-104">This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.</span></span>
  
## <a name="whats-in-this-article"></a><span data-ttu-id="36ab3-105">本文中的内容</span><span class="sxs-lookup"><span data-stu-id="36ab3-105">What's in this article?</span></span>

[<span data-ttu-id="36ab3-106">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="36ab3-106">What is ADAL?</span></span>](use-adal.md#BKMK_ADAL)
  
[<span data-ttu-id="36ab3-107">在你的池中配置 ADAL 并将 ADFS 设置为安全令牌服务器</span><span class="sxs-lookup"><span data-stu-id="36ab3-107">Configure ADAL in your pool and set ADFS as security token server</span></span>](use-adal.md#BKMK_Config)
  
[<span data-ttu-id="36ab3-108">用于启用 ADAL 登录的其他选项（如 Office 客户端应用）</span><span class="sxs-lookup"><span data-stu-id="36ab3-108">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>](use-adal.md#BKMK_Options)
  
[<span data-ttu-id="36ab3-109">新式验证/ADAL 不受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="36ab3-109">Clients where Modern Authentication / ADAL isn't Supported</span></span>](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a><span data-ttu-id="36ab3-110">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="36ab3-110">What is ADAL?</span></span>
<span data-ttu-id="36ab3-111"><a name="BKMK_ADAL"> </a></span><span class="sxs-lookup"><span data-stu-id="36ab3-111"></span></span>

<span data-ttu-id="36ab3-112">ADAL 是“Active Directory Authentication Library”的缩写，它和 OAuth 2.0 是新式验证的基础。</span><span class="sxs-lookup"><span data-stu-id="36ab3-112">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="36ab3-113">此代码库旨在使目录中的受保护的资源 （如 Skype 业务) 通过安全令牌的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="36ab3-113">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="36ab3-114">ADAL 与 OAuth 2.0 配合工作来支持更多身份验证和授权方案，例如多重身份验证 (MFA) 和更多的 SAML 身份验证形式。</span><span class="sxs-lookup"><span data-stu-id="36ab3-114">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="36ab3-115">充当客户端的各种应用可以利用新式验证来帮助访问受安全保护的资源。</span><span class="sxs-lookup"><span data-stu-id="36ab3-115">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="36ab3-116">在业务服务器 2015年的 Skype，这项技术为使用户对资源的授权的适当级别使用内部部署客户端和内部服务器之间。</span><span class="sxs-lookup"><span data-stu-id="36ab3-116">In Skype for Business Server 2015, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="36ab3-117">新式验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。</span><span class="sxs-lookup"><span data-stu-id="36ab3-117">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="36ab3-118">客户端发出请求的资源，在这种情况下，客户端是 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="36ab3-118">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="36ab3-119">没有的资源的客户端需要特定级别的访问，该资源由目录服务安全，在这种情况下的资源是业务服务器 2015年的 Skype。</span><span class="sxs-lookup"><span data-stu-id="36ab3-119">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server 2015.</span></span>
    
- <span data-ttu-id="36ab3-120">OAuth 连接，换句话说，是专门用来*授权*用户访问资源。</span><span class="sxs-lookup"><span data-stu-id="36ab3-120">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="36ab3-121">（OAuth 闻名的更具描述性的名称，服务器授权和通常缩写为 S2S）</span><span class="sxs-lookup"><span data-stu-id="36ab3-121">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="36ab3-122">在 Skype 的服务器 2015年现代商业身份验证 (ADAL) 对话，Skype 的业务服务器 2015年通过 ADFS (Windows Server 2012 R2 在 ADFS 3.0) 进行通信。</span><span class="sxs-lookup"><span data-stu-id="36ab3-122">In Skype for Business Server 2015 Modern Authentication (ADAL) conversations, Skype for Business Server 2015 communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="36ab3-123">可能会使用其他一些身份提供程序 (IdP) 执行身份验证，但是需要将 Skype for Business 服务器配置为直接与 ADFS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="36ab3-123">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="36ab3-124">如果您还没有配置 ADFS 使用 Skype 的业务服务器 2015年请填写[ADFS 安装](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="36ab3-124">If you haven't configured ADFS to work with Skype for Business Server 2015 please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="36ab3-125">ADAL 包括在 3 月 2016年累积更新的业务服务器 2015，Skype 和 3 月 2016年安装累积更新为 Skype 的业务**必须**成功配置的需要。</span><span class="sxs-lookup"><span data-stu-id="36ab3-125">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span>
  
> [!NOTE]
> <span data-ttu-id="36ab3-126">在初始版本中，只有当不涉及混合 Skype 拓扑时才支持本地环境中的新式验证。</span><span class="sxs-lookup"><span data-stu-id="36ab3-126">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="36ab3-127">例如，如果环境是纯粹的业务服务器 2015 Skype。</span><span class="sxs-lookup"><span data-stu-id="36ab3-127">For example, if the environment is purely Skype for Business Server 2015.</span></span> <span data-ttu-id="36ab3-128">此陈述可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="36ab3-128">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="36ab3-129">必须下载包含 ps1 文件与 ADAL 使用的命令的 PowerShell 程序包才能成功配置。</span><span class="sxs-lookup"><span data-stu-id="36ab3-129">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a><span data-ttu-id="36ab3-130">在你的池中配置 ADAL 并将 ADFS 设置为安全令牌服务器</span><span class="sxs-lookup"><span data-stu-id="36ab3-130">Configure ADAL in your pool and set ADFS as security token server</span></span>
<span data-ttu-id="36ab3-131"><a name="BKMK_Config"> </a></span><span class="sxs-lookup"><span data-stu-id="36ab3-131"></span></span>

<span data-ttu-id="36ab3-132">在此过程中，则连接到配置为 ADAL 的业务服务器 2015年池 Skype ADFS 的安装。</span><span class="sxs-lookup"><span data-stu-id="36ab3-132">In this process, you connect your installation of ADFS to a Skype for Business Server 2015 pool that is configured for ADAL.</span></span>
  
1. <span data-ttu-id="36ab3-133">安装 3 月 2016年到您的业务服务器 2015年池 Skype 业务服务器 2015年或标准版服务器的 Skype 的累积更新。</span><span class="sxs-lookup"><span data-stu-id="36ab3-133">Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server 2015 pool or Standard Edition server.</span></span> <span data-ttu-id="36ab3-134">（安排维护窗口，根据需要运行 Windows 更新的自动安装）。</span><span class="sxs-lookup"><span data-stu-id="36ab3-134">(Schedule maintenance windows, as needed, to run Windows Update for the automatic installation.)</span></span>
    
2. <span data-ttu-id="36ab3-135">在您的内部部署 ADFS 的服务器，请[下载](https://aka.ms/sfbadalscripts)安装 AdfsOAuthTrustForSfB 脚本。</span><span class="sxs-lookup"><span data-stu-id="36ab3-135">On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script.</span></span> <span data-ttu-id="36ab3-136">（这需要每个 ADF 场或独立 ADFS 服务器完成。</span><span class="sxs-lookup"><span data-stu-id="36ab3-136">(This needs to be done per ADFS farm or independent ADFS server(s).</span></span> <span data-ttu-id="36ab3-137">它不需要在 ADFS 代理服务器或代理服务器上完成）。</span><span class="sxs-lookup"><span data-stu-id="36ab3-137">It does not need to be done on ADFS Proxy or proxies).</span></span>
    
3. <span data-ttu-id="36ab3-138">记下的内部和外部 Web 服务您 Skype 业务服务器 2015年池或标准版服务器的完全合格的域名 (Fqdn)。</span><span class="sxs-lookup"><span data-stu-id="36ab3-138">Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server 2015 pool or Standard Edition server.</span></span> <span data-ttu-id="36ab3-139">需要对所有 Skype for Business 池执行此操作。</span><span class="sxs-lookup"><span data-stu-id="36ab3-139">This needs to be done for all the Skype for Business Pools.</span></span>
    
4. <span data-ttu-id="36ab3-p109">从 ADFS 服务器上的 PowerShell，运行 Setup-AdfsOAuthTrustForSfB。你需要输入内部和外部 Web 服务 FQDN 的正确 URL。下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="36ab3-p109">From PowerShell on the ADFS Server(s), run the Setup-AdfsOAuthTrustForSfB. You will need to enter the proper URLs for the internal and external Web Service FQDNs. Here's an example:</span></span>
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    <span data-ttu-id="36ab3-143">对于任何其他池，需要池的 Web 服务 Url 手动添加到 Skype 业务服务器 2015年信赖方信任在 ADF 中。</span><span class="sxs-lookup"><span data-stu-id="36ab3-143">For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server 2015 Relying Party Trust in ADFS.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="36ab3-144">不能对池同时使用被动身份验证和 ADAL。</span><span class="sxs-lookup"><span data-stu-id="36ab3-144">It isn't possible to use Passive Authentication for a Pool and also use ADAL.</span></span> <span data-ttu-id="36ab3-145">必须禁用被动身份验证才能使用 ADAL。</span><span class="sxs-lookup"><span data-stu-id="36ab3-145">You must disable Passive Authentication in order to use ADAL.</span></span> <span data-ttu-id="36ab3-146">如何设置身份验证池 PowerShell cmdlet 请参见[这](https://technet.microsoft.com/en-us/library/gg398396.aspx)篇文章。</span><span class="sxs-lookup"><span data-stu-id="36ab3-146">For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.</span></span>
  
    > [!TIP]
    > <span data-ttu-id="36ab3-147">如果您有其他池需要将它们用作[标识符](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)添加到配置成信赖方信任在 ADFS。 > 转到 ADF 服务器并打开 ADFS 管理。</span><span class="sxs-lookup"><span data-stu-id="36ab3-147">If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management.</span></span> <span data-ttu-id="36ab3-148">信任关系展开\>信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="36ab3-148">Expand Trust Relationships \> Relying Party Trusts.</span></span> <span data-ttu-id="36ab3-149">右击配置成信赖方信任列出并右击属性\>标识符\>键入其他池 URL(s)\>单击添加。</span><span class="sxs-lookup"><span data-stu-id="36ab3-149">Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add.</span></span> 
  
5. <span data-ttu-id="36ab3-150">返回到您 Skype 业务服务器 2015年前端或标准版服务器的服务器。</span><span class="sxs-lookup"><span data-stu-id="36ab3-150">Return to your Skype for Business Server 2015 Front End or Standard Edition server server.</span></span> <span data-ttu-id="36ab3-151">从这里，您必须运行 cmdlet 的 OAuth 服务器创建和修改该 OAuth 配置使用 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="36ab3-151">From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business.</span></span> <span data-ttu-id="36ab3-152">您只需执行 Skype 业务服务器 2015年部署的每一次此步骤。</span><span class="sxs-lookup"><span data-stu-id="36ab3-152">You only need to do this step once per Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="36ab3-153">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="36ab3-153">Here is an example:</span></span>
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > <span data-ttu-id="36ab3-154">在此命令中看到的身份 URL 实际上是 ADFS 联合身份验证服务名称右键单击服务时，可以看到在 ADFS 管理\>属性。</span><span class="sxs-lookup"><span data-stu-id="36ab3-154">The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties.</span></span> <span data-ttu-id="36ab3-155">Type 始终是 ADF，并且始终是 'MetadataURL'\<您 ADFS 服务名称\>+"/ FederationMetadata/2007-06/FederationMetadata.xml"。</span><span class="sxs-lookup"><span data-stu-id="36ab3-155">The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml".</span></span> 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. <span data-ttu-id="36ab3-156">仍在您 Skype 业务服务器 2015年前端或标准版服务器中，通过输入用户名和池的 FQDN 的 SIP 地址中测试新的配置。</span><span class="sxs-lookup"><span data-stu-id="36ab3-156">Still on your Skype for Business Server 2015 Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN.</span></span> <span data-ttu-id="36ab3-157">您只需执行 Skype 业务服务器 2015年部署的每一次此步骤。</span><span class="sxs-lookup"><span data-stu-id="36ab3-157">You only need to do this step once per Skype for Business Server 2015 deployment.</span></span> <span data-ttu-id="36ab3-158">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="36ab3-158">This is an example:</span></span>
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. <span data-ttu-id="36ab3-p115">出现提示时，请务必输入测试用户的凭据。验证测试是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="36ab3-p115">When prompted, be sure to enter the credentials of the test user. Verify that the test completes successfully.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="36ab3-161">STS URL 解析为 ADFS*内部*，您会看到的提示将**Windows 安全**提示。</span><span class="sxs-lookup"><span data-stu-id="36ab3-161">When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt.</span></span> <span data-ttu-id="36ab3-162">如果 URL 在外部解析，你将看到一个名为“**登录**”的提示。</span><span class="sxs-lookup"><span data-stu-id="36ab3-162">If the URL resolves externally, you'll see a prompt named **Sign in**.</span></span> <span data-ttu-id="36ab3-163">通常，我们在这里需要“**Windows 安全**”提示。</span><span class="sxs-lookup"><span data-stu-id="36ab3-163">Typically, we would want a **Windows Security** prompt here.</span></span> <span data-ttu-id="36ab3-164">请注意，此行为各不相同，特别是当你实施了基于表单的身份验证 (FBA) 时。</span><span class="sxs-lookup"><span data-stu-id="36ab3-164">Note that this behaviour varies, particularly if you implemented Forms-Based Authentication (or FBA).</span></span>
  
<span data-ttu-id="36ab3-p117">此外，请注意，当 STS URL 解析为内部 ADFS 服务器并且在浏览器中启用了 Windows 集成身份验证时，许多不同用户在其上登录到客户端应用程序的计算机可能无法进行身份验证，除非浏览器显式配置为在给定的浏览器安全区域中提示用户提供其凭据。以 kiosk 为例。登录到操作系统的帐户可能不同于登录到 Skype for Business 客户端的用户帐户。如果的确如此，你可能会看到此处所述的故障。</span><span class="sxs-lookup"><span data-stu-id="36ab3-p117">Also be aware, when the STS URL resolves to an internal ADFS server and Windows Integrated authentication is enabled in browsers, computers where many different users sign in to client applications may have failures to authenticate unless the browser is explicitly configured to prompt users for their credentials in a given browser Security Zone. Think of a kiosk as an example. The account that is logged in to the Operating System may be different than the user account logging into the Skype for Business client. If this is the case, you may see the failures described here.</span></span>
    
<span data-ttu-id="36ab3-169">您可以查看和更改此浏览器设置在 Internet Explorer 中的单击\>工具 （或齿轮） \> Internet 选项\>安全选项卡\>和安全区域 （例如本地 Intranet)。</span><span class="sxs-lookup"><span data-stu-id="36ab3-169">You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet).</span></span> <span data-ttu-id="36ab3-170">从此对话框，单击“自定义级别”按钮并滚动到“设置”对话框中的列表末尾。</span><span class="sxs-lookup"><span data-stu-id="36ab3-170">From this dialog, click the Custom level button and scroll to the end of the list in the Settings dialog.</span></span> <span data-ttu-id="36ab3-171">在用户身份验证下\>登录\>您将看到提示用户名和密码选项。</span><span class="sxs-lookup"><span data-stu-id="36ab3-171">Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'.</span></span> <span data-ttu-id="36ab3-172">如果在你的 kiosk 中，启动 Skype for Business 客户端的用户不同于（具有不同的帐户）登录计算机的用户，你可能需要在组策略中测试将这些计算机的这个选项设置为“打开”。</span><span class="sxs-lookup"><span data-stu-id="36ab3-172">If you have kiosks where the user who starts the Skype for Business client is different (has a different account) from the user logged into the computer, you may want to test setting this option to 'ON' for these machines in a Group Policy.</span></span>
    
<span data-ttu-id="36ab3-173">最后，重要的是，你可能会遇到多个提示，因为安全系统会收集对你的帐户进行身份验证或授权所需的信息。</span><span class="sxs-lookup"><span data-stu-id="36ab3-173">Finally, and importantly, you may experience more than one prompt as the security system collects the information it needs to authenticate or authorize your account.</span></span>
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a><span data-ttu-id="36ab3-174">用于启用 ADAL 登录的其他选项（如 Office 客户端应用）</span><span class="sxs-lookup"><span data-stu-id="36ab3-174">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>
<span data-ttu-id="36ab3-175"><a name="BKMK_Options"> </a></span><span class="sxs-lookup"><span data-stu-id="36ab3-175"></span></span>

<span data-ttu-id="36ab3-176">现在，ADAL 配置为您的业务 Skype 和 （自动） 办公室 2016年跨平台的客户端应用程序，您可能需要 Exchange Online （其中不 On，默认情况下），或者在 Office 2013 客户端中利用它。</span><span class="sxs-lookup"><span data-stu-id="36ab3-176">Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="36ab3-177">需要了解现代身份验证登录从客户端应用程序期望是什么？</span><span class="sxs-lookup"><span data-stu-id="36ab3-177">Need to know what to expect from Modern Authentication sign-ins from your client apps?</span></span> <span data-ttu-id="36ab3-178">看一看[如何现代验证用于办公室 2013年和 Office 2016 的客户端应用程序的工作原理](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="36ab3-178">Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
<span data-ttu-id="36ab3-179">若要启用 Exchange Online 的现代身份验证，您需要运行一些 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="36ab3-179">To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets.</span></span> <span data-ttu-id="36ab3-180">对于 Office 2013 客户端应用程序，需要更改客户端计算机上的某些注册表项。</span><span class="sxs-lookup"><span data-stu-id="36ab3-180">In the case of Office 2013 client apps, you will need to change some registry keys on client machines.</span></span>
  
- <span data-ttu-id="36ab3-181">连接到 Exchange 联机并运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="36ab3-181">Connect to Exchange Online and run the following cmdlets:</span></span>
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- <span data-ttu-id="36ab3-182">为要启用新式验证的每个设备或计算机设置这些注册表项。</span><span class="sxs-lookup"><span data-stu-id="36ab3-182">Set these registry keys for every device or computer on which you want to enable Modern Authentication.</span></span> <span data-ttu-id="36ab3-183">在大型组织中需要一个 GPO。</span><span class="sxs-lookup"><span data-stu-id="36ab3-183">You will need a GPO in larger organizations.</span></span> <span data-ttu-id="36ab3-184">如何使一个 GPO 的信息，请参阅创建组策略对象来修改域联接计算机上的注册表[这](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)篇文章。</span><span class="sxs-lookup"><span data-stu-id="36ab3-184">For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.</span></span>
    
|<span data-ttu-id="36ab3-185">注册表项</span><span class="sxs-lookup"><span data-stu-id="36ab3-185">Registry Key</span></span>  <br/> |<span data-ttu-id="36ab3-186">类型</span><span class="sxs-lookup"><span data-stu-id="36ab3-186">Type</span></span>  <br/> |<span data-ttu-id="36ab3-187">值</span><span class="sxs-lookup"><span data-stu-id="36ab3-187">Value</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="36ab3-188">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="36ab3-188">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  <br/> |<span data-ttu-id="36ab3-189">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="36ab3-189">REG_DWORD</span></span>  <br/> |<span data-ttu-id="36ab3-190">1</span><span class="sxs-lookup"><span data-stu-id="36ab3-190">1</span></span>  <br/> |
|<span data-ttu-id="36ab3-191">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="36ab3-191">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span>  <br/> |<span data-ttu-id="36ab3-192">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="36ab3-192">REG_DWORD</span></span>  <br/> |<span data-ttu-id="36ab3-193">1</span><span class="sxs-lookup"><span data-stu-id="36ab3-193">1</span></span>  <br/> |
   
<span data-ttu-id="36ab3-194">一旦设置了这些参数，设置为[使用 Multifactor 身份验证 (MFA) 与 Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)Office 2013 应用程序。</span><span class="sxs-lookup"><span data-stu-id="36ab3-194">Once these keys are set, set your Office 2013 apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!TIP]
> <span data-ttu-id="36ab3-195">要禁用 Office 2013 的设备上的现代身份验证，请为零值设置 HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL 注册表项。</span><span class="sxs-lookup"><span data-stu-id="36ab3-195">To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero.</span></span> <span data-ttu-id="36ab3-196">请注意，类似的注册表项 (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) 也可用来禁用 Office 2016 年的设备上的现代身份验证。</span><span class="sxs-lookup"><span data-stu-id="36ab3-196">Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.</span></span>
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a><span data-ttu-id="36ab3-197">新式验证/ADAL 不受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="36ab3-197">Clients where Modern Authentication / ADAL isn't Supported</span></span>
<span data-ttu-id="36ab3-198"><a name="BKMK_Support"> </a></span><span class="sxs-lookup"><span data-stu-id="36ab3-198"></span></span>

<span data-ttu-id="36ab3-p123">某些客户端版本不支持 OAuth。你可以在用于添加和删除程序的控制面板中检查你的 Office 客户端版本，以便将你的版本号与此处所列的版本（或版本范围）进行比较：</span><span class="sxs-lookup"><span data-stu-id="36ab3-p123">Some client versions don't support OAuth. You can check your version of Office client in Control Panel where you Add and Remove programs in order to compare your version number to the versions (or ranges of versions) listed here:</span></span>
  
- <span data-ttu-id="36ab3-201">Office 客户端于 15.0。[0000-4766]。\*</span><span class="sxs-lookup"><span data-stu-id="36ab3-201">Office Client 15.0.[0000-4766].\*</span></span>
    
- <span data-ttu-id="36ab3-202">Office 客户端 16.0。[0000-4293]。\*</span><span class="sxs-lookup"><span data-stu-id="36ab3-202">Office Client 16.0.[0000-4293].\*</span></span>
    
- <span data-ttu-id="36ab3-203">Office 客户端 16.0.6001.[0000-1032]</span><span class="sxs-lookup"><span data-stu-id="36ab3-203">Office Client 16.0.6001.[0000-1032]</span></span>
    
- <span data-ttu-id="36ab3-204">Office 客户端 16.0。[6000-6224]。\*</span><span class="sxs-lookup"><span data-stu-id="36ab3-204">Office Client 16.0.[6000-6224].\*</span></span>
    

