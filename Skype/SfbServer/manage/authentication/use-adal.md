---
title: 如何将新式验证 (ADAL) 与 Skype for Business 配合使用
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 5ca71746-ead6-4e8c-90b1-461e846d1f4a
description: 本文介绍如何使用现代身份验证 （这基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0） 可以位于年 3 月 2016 for Business 的业务服务器 2015年的 Skype Skype 的累积更新。
ms.openlocfilehash: 4bf802d2710c9c271c54cf2e127cf51b24875db1
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20966571"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="cd37d-103">如何将新式验证 (ADAL) 与 Skype for Business 配合使用</span><span class="sxs-lookup"><span data-stu-id="cd37d-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="cd37d-104">本文介绍如何使用现代身份验证 （这基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0） 可以位于年 3 月 2016 for Business 的业务服务器 2015年的 Skype Skype 的累积更新。</span><span class="sxs-lookup"><span data-stu-id="cd37d-104">This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015.</span></span>
  
## <a name="whats-in-this-article"></a><span data-ttu-id="cd37d-105">本文中的内容</span><span class="sxs-lookup"><span data-stu-id="cd37d-105">What's in this article?</span></span>

[<span data-ttu-id="cd37d-106">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="cd37d-106">What is ADAL?</span></span>](use-adal.md#BKMK_ADAL)
  
[<span data-ttu-id="cd37d-107">在你的池中配置 ADAL 并将 ADFS 设置为安全令牌服务器</span><span class="sxs-lookup"><span data-stu-id="cd37d-107">Configure ADAL in your pool and set ADFS as security token server</span></span>](use-adal.md#BKMK_Config)
  
[<span data-ttu-id="cd37d-108">用于启用 ADAL 登录的其他选项（如 Office 客户端应用）</span><span class="sxs-lookup"><span data-stu-id="cd37d-108">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>](use-adal.md#BKMK_Options)
  
[<span data-ttu-id="cd37d-109">新式验证/ADAL 不受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="cd37d-109">Clients where Modern Authentication / ADAL isn't Supported</span></span>](use-adal.md#BKMK_Support)
  
## <a name="what-is-adal"></a><span data-ttu-id="cd37d-110">什么是 ADAL？</span><span class="sxs-lookup"><span data-stu-id="cd37d-110">What is ADAL?</span></span>
<span data-ttu-id="cd37d-111"><a name="BKMK_ADAL"> </a></span><span class="sxs-lookup"><span data-stu-id="cd37d-111"></span></span>

<span data-ttu-id="cd37d-112">ADAL 是“Active Directory Authentication Library”的缩写，它和 OAuth 2.0 是新式验证的基础。</span><span class="sxs-lookup"><span data-stu-id="cd37d-112">ADAL is the acronym for the 'Active Directory Authentication Library', and, along with OAuth 2.0, it is an underpinning of Modern Authentication.</span></span> <span data-ttu-id="cd37d-113">此代码库旨在使您目录中的安全的资源 （如 for Business 的 Skype) 通过安全令牌的客户端应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd37d-113">This code library is designed to make secured resources in your directory available to client applications (like Skype for Business) via security tokens.</span></span> <span data-ttu-id="cd37d-114">ADAL 与 OAuth 2.0 配合工作来支持更多身份验证和授权方案，例如多重身份验证 (MFA) 和更多的 SAML 身份验证形式。</span><span class="sxs-lookup"><span data-stu-id="cd37d-114">ADAL works with OAuth 2.0 to enable more authentication and authorization scenarios, like Multi-factor Authentication (MFA), and more forms of SAML Auth.</span></span>
  
<span data-ttu-id="cd37d-115">充当客户端的各种应用可以利用新式验证来帮助访问受安全保护的资源。</span><span class="sxs-lookup"><span data-stu-id="cd37d-115">A variety of apps that act as clients can leverage Modern Authentication for help in getting to secured resources.</span></span> <span data-ttu-id="cd37d-116">Skype 业务服务器，在这种技术以便为用户提供适当级别的资源授权使用内部部署客户端和内部部署服务器之间。</span><span class="sxs-lookup"><span data-stu-id="cd37d-116">In Skype for Business Server, this technology is used between on-premises clients and on-premises servers in order to give users a proper level of authorization to resources.</span></span>
  
<span data-ttu-id="cd37d-117">新式验证对话（基于 ADAL 和 OAuth 2.0）具有一些常见元素。</span><span class="sxs-lookup"><span data-stu-id="cd37d-117">Modern Authentication conversations (which are based on ADAL and OAuth 2.0) have some elements in common.</span></span>
  
- <span data-ttu-id="cd37d-118">客户端进行资源的请求，在这种情况下，客户端是 for Business 的 Skype。</span><span class="sxs-lookup"><span data-stu-id="cd37d-118">There is a client making a request for a resource, in this case, the client is Skype for Business.</span></span>
    
- <span data-ttu-id="cd37d-119">没有向其客户端需要特定的访问级别的资源和此资源安全的目录服务，在这种情况下该资源是 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="cd37d-119">There is a resource to which the client needs a specific level of access, and this resource is secured by a directory service, in this case the resource is Skype for Business Server.</span></span>
    
- <span data-ttu-id="cd37d-120">OAuth 连接，换句话说，连接的专用于*授权*用户访问资源。</span><span class="sxs-lookup"><span data-stu-id="cd37d-120">There is an OAuth connection, in other words, a connection that is dedicated to  *authorizing*  a user to access a resource.</span></span> <span data-ttu-id="cd37d-121">（OAuth 通过更具描述性的名称、 服务器到服务器身份验证，也称为和通常缩写为 S2S）</span><span class="sxs-lookup"><span data-stu-id="cd37d-121">(OAuth is also known by the more descriptive name, 'Server-to-Server' auth, and is often abbreviated as S2S.)</span></span>
    
<span data-ttu-id="cd37d-122">在业务服务器现代身份验证 (ADAL) 对话的 Skype，Skype 业务服务器通过 ADFS (在 Windows Server 2012 R2 ADFS 3.0) 进行通信。</span><span class="sxs-lookup"><span data-stu-id="cd37d-122">In Skype for Business Server Modern Authentication (ADAL) conversations, Skype for Business Server communicates through ADFS (ADFS 3.0 in Windows Server 2012 R2).</span></span> <span data-ttu-id="cd37d-123">可能会使用其他一些身份提供程序 (IdP) 执行身份验证，但是需要将 Skype for Business 服务器配置为直接与 ADFS 进行通信。</span><span class="sxs-lookup"><span data-stu-id="cd37d-123">The authentication may happen using some other Identity Provider (IdP), but Skype for Business server needs to be configured to communicate with ADFS, directly.</span></span> <span data-ttu-id="cd37d-124">如果尚未配置 ADFS 业务服务器处理 Skype 请完成[ADFS 安装](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx)。</span><span class="sxs-lookup"><span data-stu-id="cd37d-124">If you haven't configured ADFS to work with Skype for Business Server please complete the [ADFS installation](https://technet.microsoft.com/en-us/library/adfs2-step-by-step-guides%28v=ws.10%29.aspx).</span></span>
  
<span data-ttu-id="cd37d-125">ADAL 中包含年 3 月 2016年业务服务器 2015年的 Skype 的累积更新和年 3 月 2016年安装累积更新的业务**必须**Skype 和所需的成功配置。</span><span class="sxs-lookup"><span data-stu-id="cd37d-125">ADAL is included in the March 2016 Cumulative Update for Skype for Business Server 2015, and the March 2016 Cumulative Update for Skype for Business **must** be installed and is needed for successful configuration.</span></span>
  
> [!NOTE]
> <span data-ttu-id="cd37d-126">在初始版本中，只有当不涉及混合 Skype 拓扑时才支持本地环境中的新式验证。</span><span class="sxs-lookup"><span data-stu-id="cd37d-126">During the initial release, Modern Authentication in an on-premises environment is supported only if there is no mixed Skype topology involved.</span></span> <span data-ttu-id="cd37d-127">例如，如果环境纯粹 Skype 业务服务器。</span><span class="sxs-lookup"><span data-stu-id="cd37d-127">For example, if the environment is purely Skype for Business Server.</span></span> <span data-ttu-id="cd37d-128">此陈述可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="cd37d-128">This statement may be subject to change.</span></span> 
  
<span data-ttu-id="cd37d-129">必须下载包含 ps1 文件与 ADAL 使用的命令的 PowerShell 程序包才能成功配置。</span><span class="sxs-lookup"><span data-stu-id="cd37d-129">A PowerShell package including .ps1 files with the commands used by ADAL must be downloaded for successful configuration.</span></span>
  
### <a name="configure-adal-in-your-pool-and-set-adfs-as-security-token-server"></a><span data-ttu-id="cd37d-130">在你的池中配置 ADAL 并将 ADFS 设置为安全令牌服务器</span><span class="sxs-lookup"><span data-stu-id="cd37d-130">Configure ADAL in your pool and set ADFS as security token server</span></span>
<span data-ttu-id="cd37d-131"><a name="BKMK_Config"> </a></span><span class="sxs-lookup"><span data-stu-id="cd37d-131"></span></span>

<span data-ttu-id="cd37d-132">在此过程中，将连接到业务服务器池的配置为使用 ADAL Skype 所安装的 ADFS。</span><span class="sxs-lookup"><span data-stu-id="cd37d-132">In this process, you connect your installation of ADFS to a Skype for Business Server pool that is configured for ADAL.</span></span>
  
1. <span data-ttu-id="cd37d-133">安装年 3 月 2016 Skype 业务服务器 2015 到您 Skype 业务服务器池或 Standard Edition 服务器的累积更新。</span><span class="sxs-lookup"><span data-stu-id="cd37d-133">Install the March 2016 Cumulative Update for Skype for Business Server 2015 to your Skype for Business Server pool or Standard Edition server.</span></span> <span data-ttu-id="cd37d-134">（计划维护时段，根据需要运行自动安装的 Windows Update）。</span><span class="sxs-lookup"><span data-stu-id="cd37d-134">(Schedule maintenance windows, as needed, to run Windows Update for the automatic installation.)</span></span>
    
2. <span data-ttu-id="cd37d-135">您的本地 ADFS 服务器上，[下载](https://aka.ms/sfbadalscripts)安装 AdfsOAuthTrustForSfB 脚本。</span><span class="sxs-lookup"><span data-stu-id="cd37d-135">On your on-premises ADFS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script.</span></span> <span data-ttu-id="cd37d-136">（这需要完成每个 ADFS 服务器场或独立的 ADFS 服务器。</span><span class="sxs-lookup"><span data-stu-id="cd37d-136">(This needs to be done per ADFS farm or independent ADFS server(s).</span></span> <span data-ttu-id="cd37d-137">它不需要 ADFS 代理服务器上完成）。</span><span class="sxs-lookup"><span data-stu-id="cd37d-137">It does not need to be done on ADFS Proxy or proxies).</span></span>
    
3. <span data-ttu-id="cd37d-138">记下的内部和外部 Web 服务的完全限定域名 (Fqdn) 为您 Skype 业务服务器池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="cd37d-138">Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server pool or Standard Edition server.</span></span> <span data-ttu-id="cd37d-139">需要对所有 Skype for Business 池执行此操作。</span><span class="sxs-lookup"><span data-stu-id="cd37d-139">This needs to be done for all the Skype for Business Pools.</span></span>
    
4. <span data-ttu-id="cd37d-p109">从 ADFS 服务器上的 PowerShell，运行 Setup-AdfsOAuthTrustForSfB。你需要输入内部和外部 Web 服务 FQDN 的正确 URL。下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="cd37d-p109">From PowerShell on the ADFS Server(s), run the Setup-AdfsOAuthTrustForSfB. You will need to enter the proper URLs for the internal and external Web Service FQDNs. Here's an example:</span></span>
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    <span data-ttu-id="cd37d-143">对于任何其他池，您将需要池 Web 服务 Url 手动添加到 Skype 的业务服务器信赖方信任 ADFS 中。</span><span class="sxs-lookup"><span data-stu-id="cd37d-143">For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server Relying Party Trust in ADFS.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="cd37d-144">不能对池同时使用被动身份验证和 ADAL。</span><span class="sxs-lookup"><span data-stu-id="cd37d-144">It isn't possible to use Passive Authentication for a Pool and also use ADAL.</span></span> <span data-ttu-id="cd37d-145">必须禁用被动身份验证才能使用 ADAL。</span><span class="sxs-lookup"><span data-stu-id="cd37d-145">You must disable Passive Authentication in order to use ADAL.</span></span> <span data-ttu-id="cd37d-146">有关如何为池设置身份验证的 PowerShell cmdlet，请参阅[这](https://technet.microsoft.com/en-us/library/gg398396.aspx)篇文章。</span><span class="sxs-lookup"><span data-stu-id="cd37d-146">For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.</span></span>
  
    > [!TIP]
    > <span data-ttu-id="cd37d-147">如果您有其他池需要将其作为[标识符](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)添加到信赖方信任 ADFS。 > 转到您的 ADFS 服务器并打开 ADFS 管理。</span><span class="sxs-lookup"><span data-stu-id="cd37d-147">If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in ADFS.> Go to your ADFS server and open ADFS Management.</span></span> <span data-ttu-id="cd37d-148">展开信任关系\>信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="cd37d-148">Expand Trust Relationships \> Relying Party Trusts.</span></span> <span data-ttu-id="cd37d-149">右键单击信赖方信任列出和属性的右键单击\>标识符\>键入其他池 URL(s)\>单击添加。</span><span class="sxs-lookup"><span data-stu-id="cd37d-149">Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add.</span></span> 
  
5. <span data-ttu-id="cd37d-150">返回到您 Skype 业务 Server 前端服务器或 Standard Edition server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="cd37d-150">Return to your Skype for Business Server Front End or Standard Edition server server.</span></span> <span data-ttu-id="cd37d-151">从此处，您必须运行 cmdlet 创建的 OAuth 服务器和修改的 OAuth 配置才能与 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="cd37d-151">From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business.</span></span> <span data-ttu-id="cd37d-152">您只需执行的业务服务器部署的 Skype 每次此步骤。</span><span class="sxs-lookup"><span data-stu-id="cd37d-152">You only need to do this step once per Skype for Business Server deployment.</span></span> <span data-ttu-id="cd37d-153">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="cd37d-153">Here is an example:</span></span>
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > <span data-ttu-id="cd37d-154">您在此命令中看到的标识 URL 是实际的 ADFS 联合身份验证服务名称时，您可以看到 ADFS 管理中右键单击服务\>属性。</span><span class="sxs-lookup"><span data-stu-id="cd37d-154">The 'Identity' URL you see in this command is actually the ADFS Federation Service Name you can see in ADFS Management when you right-click Service \> Properties.</span></span> <span data-ttu-id="cd37d-155">类型始终是 ADFS，并且始终是 MetadataURL\<您的 ADFS 服务名称\>+"/ FederationMetadata/2007-06/FederationMetadata.xml"。</span><span class="sxs-lookup"><span data-stu-id="cd37d-155">The 'Type' is always ADFS, and the 'MetadataURL' is always \<Your ADFS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml".</span></span> 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. <span data-ttu-id="cd37d-156">仍在您 Skype 业务 Server 前端服务器或 Standard Edition server，通过输入用户名和池 FQDN 的 SIP 地址来测试新的配置。</span><span class="sxs-lookup"><span data-stu-id="cd37d-156">Still on your Skype for Business Server Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN.</span></span> <span data-ttu-id="cd37d-157">您只需执行的业务服务器部署的 Skype 每次此步骤。</span><span class="sxs-lookup"><span data-stu-id="cd37d-157">You only need to do this step once per Skype for Business Server deployment.</span></span> <span data-ttu-id="cd37d-158">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="cd37d-158">This is an example:</span></span>
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. <span data-ttu-id="cd37d-p115">出现提示时，请务必输入测试用户的凭据。验证测试是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="cd37d-p115">When prompted, be sure to enter the credentials of the test user. Verify that the test completes successfully.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="cd37d-161">当您 STS 的 URL 将解析为 ADFS*内部*时，您将看到的提示将**Windows 安全**提示。</span><span class="sxs-lookup"><span data-stu-id="cd37d-161">When your STS URL resolves to ADFS  *internally*  , the prompt you will see will be a **Windows Security** prompt.</span></span> <span data-ttu-id="cd37d-162">如果 URL 在外部解析，你将看到一个名为“**登录**”的提示。</span><span class="sxs-lookup"><span data-stu-id="cd37d-162">If the URL resolves externally, you'll see a prompt named **Sign in**.</span></span> <span data-ttu-id="cd37d-163">通常，我们在这里需要“**Windows 安全**”提示。</span><span class="sxs-lookup"><span data-stu-id="cd37d-163">Typically, we would want a **Windows Security** prompt here.</span></span> <span data-ttu-id="cd37d-164">请注意，此行为各不相同，特别是当你实施了基于表单的身份验证 (FBA) 时。</span><span class="sxs-lookup"><span data-stu-id="cd37d-164">Note that this behaviour varies, particularly if you implemented Forms-Based Authentication (or FBA).</span></span>
  
<span data-ttu-id="cd37d-p117">此外，请注意，当 STS URL 解析为内部 ADFS 服务器并且在浏览器中启用了 Windows 集成身份验证时，许多不同用户在其上登录到客户端应用程序的计算机可能无法进行身份验证，除非浏览器显式配置为在给定的浏览器安全区域中提示用户提供其凭据。以 kiosk 为例。登录到操作系统的帐户可能不同于登录到 Skype for Business 客户端的用户帐户。如果的确如此，你可能会看到此处所述的故障。</span><span class="sxs-lookup"><span data-stu-id="cd37d-p117">Also be aware, when the STS URL resolves to an internal ADFS server and Windows Integrated authentication is enabled in browsers, computers where many different users sign in to client applications may have failures to authenticate unless the browser is explicitly configured to prompt users for their credentials in a given browser Security Zone. Think of a kiosk as an example. The account that is logged in to the Operating System may be different than the user account logging into the Skype for Business client. If this is the case, you may see the failures described here.</span></span>
    
<span data-ttu-id="cd37d-169">可以查看和更改此浏览器设置在 Internet Explorer 中的单击\>工具 （或齿轮） \> Internet 选项\>安全选项卡\>（如本地 Intranet) 的安全区域。</span><span class="sxs-lookup"><span data-stu-id="cd37d-169">You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet).</span></span> <span data-ttu-id="cd37d-170">从此对话框，单击“自定义级别”按钮并滚动到“设置”对话框中的列表末尾。</span><span class="sxs-lookup"><span data-stu-id="cd37d-170">From this dialog, click the Custom level button and scroll to the end of the list in the Settings dialog.</span></span> <span data-ttu-id="cd37d-171">在用户身份验证下\>登录\>您将看到用户名和密码提示选项。</span><span class="sxs-lookup"><span data-stu-id="cd37d-171">Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'.</span></span> <span data-ttu-id="cd37d-172">如果在你的 kiosk 中，启动 Skype for Business 客户端的用户不同于（具有不同的帐户）登录计算机的用户，你可能需要在组策略中测试将这些计算机的这个选项设置为“打开”。</span><span class="sxs-lookup"><span data-stu-id="cd37d-172">If you have kiosks where the user who starts the Skype for Business client is different (has a different account) from the user logged into the computer, you may want to test setting this option to 'ON' for these machines in a Group Policy.</span></span>
    
<span data-ttu-id="cd37d-173">最后，重要的是，你可能会遇到多个提示，因为安全系统会收集对你的帐户进行身份验证或授权所需的信息。</span><span class="sxs-lookup"><span data-stu-id="cd37d-173">Finally, and importantly, you may experience more than one prompt as the security system collects the information it needs to authenticate or authorize your account.</span></span>
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a><span data-ttu-id="cd37d-174">用于启用 ADAL 登录的其他选项（如 Office 客户端应用）</span><span class="sxs-lookup"><span data-stu-id="cd37d-174">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>
<span data-ttu-id="cd37d-175"><a name="BKMK_Options"> </a></span><span class="sxs-lookup"><span data-stu-id="cd37d-175"></span></span>

<span data-ttu-id="cd37d-176">既然 ADAL 配置为您的业务 Skype 和 （自动） 对于 Office 2016 跨平台客户端应用程序，您可能想要利用它，Exchange Online 中 （其中不是 On 默认情况下），或在 Office 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="cd37d-176">Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cd37d-177">需要了解期望现代身份验证登录从您的客户端应用程序是什么？</span><span class="sxs-lookup"><span data-stu-id="cd37d-177">Need to know what to expect from Modern Authentication sign-ins from your client apps?</span></span> <span data-ttu-id="cd37d-178">了解一下[如何现代身份验证适用于 Office 2013 和 Office 2016 客户端应用程序](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="cd37d-178">Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
<span data-ttu-id="cd37d-179">要打开 Exchange Online 的现代身份验证，您将需要运行某些 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="cd37d-179">To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets.</span></span> <span data-ttu-id="cd37d-180">对于 Office 2013 客户端应用程序，您将需要更改某些客户端计算机上的注册表项。</span><span class="sxs-lookup"><span data-stu-id="cd37d-180">In the case of Office 2013 client apps, you will need to change some registry keys on client machines.</span></span>
  
- <span data-ttu-id="cd37d-181">连接到 Exchange Online 并运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="cd37d-181">Connect to Exchange Online and run the following cmdlets:</span></span>
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- <span data-ttu-id="cd37d-182">为要启用新式验证的每个设备或计算机设置这些注册表项。</span><span class="sxs-lookup"><span data-stu-id="cd37d-182">Set these registry keys for every device or computer on which you want to enable Modern Authentication.</span></span> <span data-ttu-id="cd37d-183">在大型组织中需要一个 GPO。</span><span class="sxs-lookup"><span data-stu-id="cd37d-183">You will need a GPO in larger organizations.</span></span> <span data-ttu-id="cd37d-184">有关如何使 GPO 的信息，请参阅创建组策略对象修改域联接计算机上的注册表的[这](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)篇文章。</span><span class="sxs-lookup"><span data-stu-id="cd37d-184">For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.</span></span>
    
|<span data-ttu-id="cd37d-185">注册表项</span><span class="sxs-lookup"><span data-stu-id="cd37d-185">Registry Key</span></span>  <br/> |<span data-ttu-id="cd37d-186">类型</span><span class="sxs-lookup"><span data-stu-id="cd37d-186">Type</span></span>  <br/> |<span data-ttu-id="cd37d-187">值</span><span class="sxs-lookup"><span data-stu-id="cd37d-187">Value</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="cd37d-188">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="cd37d-188">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  <br/> |<span data-ttu-id="cd37d-189">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="cd37d-189">REG_DWORD</span></span>  <br/> |<span data-ttu-id="cd37d-190">1</span><span class="sxs-lookup"><span data-stu-id="cd37d-190">1</span></span>  <br/> |
|<span data-ttu-id="cd37d-191">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="cd37d-191">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span>  <br/> |<span data-ttu-id="cd37d-192">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="cd37d-192">REG_DWORD</span></span>  <br/> |<span data-ttu-id="cd37d-193">1</span><span class="sxs-lookup"><span data-stu-id="cd37d-193">1</span></span>  <br/> |
   
<span data-ttu-id="cd37d-194">这些注册表项设置后, 设置为[使用 Multifactor 身份验证 (MFA) 与 Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="cd37d-194">Once these keys are set, set your Office apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!TIP]
> <span data-ttu-id="cd37d-195">要在 Office 2013 的设备上禁用现代的身份验证，将设置为零值的 HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL 注册表项。</span><span class="sxs-lookup"><span data-stu-id="cd37d-195">To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero.</span></span> <span data-ttu-id="cd37d-196">请注意，类似的注册表项 (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) 也用于 Office 2016 的设备上禁用现代身份验证。</span><span class="sxs-lookup"><span data-stu-id="cd37d-196">Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.</span></span>
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a><span data-ttu-id="cd37d-197">新式验证/ADAL 不受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="cd37d-197">Clients where Modern Authentication / ADAL isn't Supported</span></span>
<span data-ttu-id="cd37d-198"><a name="BKMK_Support"> </a></span><span class="sxs-lookup"><span data-stu-id="cd37d-198"></span></span>

<span data-ttu-id="cd37d-p123">某些客户端版本不支持 OAuth。你可以在用于添加和删除程序的控制面板中检查你的 Office 客户端版本，以便将你的版本号与此处所列的版本（或版本范围）进行比较：</span><span class="sxs-lookup"><span data-stu-id="cd37d-p123">Some client versions don't support OAuth. You can check your version of Office client in Control Panel where you Add and Remove programs in order to compare your version number to the versions (or ranges of versions) listed here:</span></span>
  
- <span data-ttu-id="cd37d-201">Office 客户端 15.0。[0000-4766]。\*</span><span class="sxs-lookup"><span data-stu-id="cd37d-201">Office Client 15.0.[0000-4766].\*</span></span>
    
- <span data-ttu-id="cd37d-202">Office 客户端 16.0。[0000-4293]。\*</span><span class="sxs-lookup"><span data-stu-id="cd37d-202">Office Client 16.0.[0000-4293].\*</span></span>
    
- <span data-ttu-id="cd37d-203">Office 客户端 16.0.6001.[0000-1032]</span><span class="sxs-lookup"><span data-stu-id="cd37d-203">Office Client 16.0.6001.[0000-1032]</span></span>
    
- <span data-ttu-id="cd37d-204">Office 客户端 16.0。[6000-6224]。\*</span><span class="sxs-lookup"><span data-stu-id="cd37d-204">Office Client 16.0.[6000-6224].\*</span></span>
    

