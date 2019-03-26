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
ms.openlocfilehash: 0121e1a99aab70b10a00dbcf72d3a8be8a50553a
ms.sourcegitcommit: 8e5fc1d8c19a7f26f53e40b23dd6476a8c6d805f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/26/2019
ms.locfileid: "30800137"
---
# <a name="how-to-use-modern-authentication-adal-with-skype-for-business"></a><span data-ttu-id="889e2-103">如何将新式验证 (ADAL) 与 Skype for Business 配合使用</span><span class="sxs-lookup"><span data-stu-id="889e2-103">How to use Modern Authentication (ADAL) with Skype for Business</span></span>
 
<span data-ttu-id="889e2-104">本文介绍如何使用现代身份验证 （这基于 Active Directory 身份验证库 (ADAL) 和 OAuth 2.0） 可以位于年 3 月 2016 for Business 的 Skype 业务服务器 2015，或从初始 Skype 的累积更新业务服务器 2019 Skype 的的发行版。</span><span class="sxs-lookup"><span data-stu-id="889e2-104">This article explains how to use Modern Authentication (which is based on the Active Directory Authentication Library (ADAL) and OAuth 2.0) that can be found in the March 2016 Cumulative Update for Skype for Business for Skype for Business Server 2015, or from initial release for Skype for Business Server 2019.</span></span>
  
## <a name="whats-in-this-article"></a><span data-ttu-id="889e2-105">本文中的内容</span><span class="sxs-lookup"><span data-stu-id="889e2-105">What's in this article?</span></span>

[<span data-ttu-id="889e2-106">在池中配置 ADAL 并将 AD FS 设置为安全令牌服务器</span><span class="sxs-lookup"><span data-stu-id="889e2-106">Configure ADAL in your pool and set AD FS as security token server</span></span>](use-adal.md#BKMK_Config)
  
[<span data-ttu-id="889e2-107">用于启用 ADAL 登录的其他选项（如 Office 客户端应用）</span><span class="sxs-lookup"><span data-stu-id="889e2-107">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>](use-adal.md#BKMK_Options)
  
[<span data-ttu-id="889e2-108">新式验证/ADAL 不受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="889e2-108">Clients where Modern Authentication / ADAL isn't Supported</span></span>](use-adal.md#BKMK_Support)
  
### <a name="configure-adal-in-your-pool-and-set-ad-fs-as-security-token-server"></a><span data-ttu-id="889e2-109">在池中配置 ADAL 并将 AD FS 设置为安全令牌服务器</span><span class="sxs-lookup"><span data-stu-id="889e2-109">Configure ADAL in your pool and set AD FS as security token server</span></span>
<span data-ttu-id="889e2-110"><a name="BKMK_Config"> </a></span><span class="sxs-lookup"><span data-stu-id="889e2-110"></span></span>

<span data-ttu-id="889e2-111">在此过程中，将连接到业务服务器池的配置为使用 ADAL Skype 所安装的 AD FS。</span><span class="sxs-lookup"><span data-stu-id="889e2-111">In this process, you connect your installation of AD FS to a Skype for Business Server pool that is configured for ADAL.</span></span>
  
1. <span data-ttu-id="889e2-112">安装年 3 月 2016年累积更新 （或更高版本） 的 Skype 业务服务器 2015 到您 Skype 业务服务器池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="889e2-112">Install the March 2016 Cumulative Update (or newer) for Skype for Business Server 2015 to your Skype for Business Server pool or Standard Edition server.</span></span> <span data-ttu-id="889e2-113">（计划维护时段，根据需要运行自动安装的 Windows Update）。</span><span class="sxs-lookup"><span data-stu-id="889e2-113">(Schedule maintenance windows, as needed, to run Windows Update for the automatic installation.)</span></span>
    
2. <span data-ttu-id="889e2-114">在您的内部部署 AD FS 服务器、[下载](https://aka.ms/sfbadalscripts)安装 AdfsOAuthTrustForSfB 脚本。</span><span class="sxs-lookup"><span data-stu-id="889e2-114">On your on-premises AD FS server(s), [download](https://aka.ms/sfbadalscripts) the Setup-AdfsOAuthTrustForSfB script.</span></span> <span data-ttu-id="889e2-115">（这需要完成每个 AD FS 服务器场或独立 AD FS 服务器。</span><span class="sxs-lookup"><span data-stu-id="889e2-115">(This needs to be done per AD FS farm or independent AD FS server(s).</span></span> <span data-ttu-id="889e2-116">它不会不需要 AD FS 代理服务器或 Web 应用程序代理上完成。）</span><span class="sxs-lookup"><span data-stu-id="889e2-116">It does not need to be done on AD FS Proxies or Web Application Proxies.)</span></span>
    
3. <span data-ttu-id="889e2-117">记下的内部和外部 Web 服务的完全限定域名 (Fqdn) 为您 Skype 业务服务器池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="889e2-117">Make a note of the internal and external Web Service fully qualified domain names (FQDNs) for your Skype for Business Server pool or Standard Edition server.</span></span> <span data-ttu-id="889e2-118">需要对所有 Skype for Business 池执行此操作。</span><span class="sxs-lookup"><span data-stu-id="889e2-118">This needs to be done for all the Skype for Business Pools.</span></span>
    
4. <span data-ttu-id="889e2-119">从 PowerShell 在 AD FS 服务器上，运行`Setup-AdfsOAuthTrustForSfB.ps1`（对于 Windows Server 2012 R2) 或`Setup-Adfs2016OAuthTrustForSfB.ps1`（对于 Windows Server 2016 或更高版本。）您需要输入正确的 Url 的内部和外部 Web 服务完全限定域名 (Fqdn)。</span><span class="sxs-lookup"><span data-stu-id="889e2-119">From PowerShell on the AD FS Server(s), run `Setup-AdfsOAuthTrustForSfB.ps1` (for Windows Server 2012 R2) or `Setup-Adfs2016OAuthTrustForSfB.ps1` (for Windows Server 2016 or later.) You will need to enter the proper URLs for the internal and external Web Service fully-qualified domain names (FQDNs).</span></span> <span data-ttu-id="889e2-120">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="889e2-120">Here's an example:</span></span>
    
     `Setup-AdfsOAuthTrustForSfB.ps1 -poolIDs https://contosoSkype.contoso.com,https://contoso01Skype.contosoIn.com`
    
    <span data-ttu-id="889e2-121">对于任何其他池，您将需要池 Web 服务 Url 手动添加到 Skype 的业务服务器信赖方信任在 AD FS。</span><span class="sxs-lookup"><span data-stu-id="889e2-121">For any additional pools, you will need to add the Pool Web Services URLs manually to the Skype for Business Server Relying Party Trust in AD FS.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="889e2-122">不能对池同时使用被动身份验证和 ADAL。</span><span class="sxs-lookup"><span data-stu-id="889e2-122">It isn't possible to use Passive Authentication for a Pool and also use ADAL.</span></span> <span data-ttu-id="889e2-123">必须禁用被动身份验证才能使用 ADAL。</span><span class="sxs-lookup"><span data-stu-id="889e2-123">You must disable Passive Authentication in order to use ADAL.</span></span> <span data-ttu-id="889e2-124">有关如何为池设置身份验证的 PowerShell cmdlet，请参阅[这](https://technet.microsoft.com/en-us/library/gg398396.aspx)篇文章。</span><span class="sxs-lookup"><span data-stu-id="889e2-124">For PowerShell cmdlets on how to set authentication for a Pool see [this](https://technet.microsoft.com/en-us/library/gg398396.aspx) article.</span></span>
  
    > [!TIP]
    > <span data-ttu-id="889e2-125">如果您有其他池，需要将其作为[标识符](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx)添加到信赖方信任在 AD FS.> 转到您的 AD FS 服务器并打开 AD FS 管理。</span><span class="sxs-lookup"><span data-stu-id="889e2-125">If you have additional pools you need to add them as [Identifiers](https://technet.microsoft.com/en-us/library/gg557759%28v=ws.10%29.aspx) to the Relying Party Trust in AD FS.> Go to your AD FS server and open AD FS Management.</span></span> <span data-ttu-id="889e2-126">展开信任关系\>信赖方信任。</span><span class="sxs-lookup"><span data-stu-id="889e2-126">Expand Trust Relationships \> Relying Party Trusts.</span></span> <span data-ttu-id="889e2-127">右键单击信赖方信任列出和属性的右键单击\>标识符\>键入其他池 URL(s)\>单击添加。</span><span class="sxs-lookup"><span data-stu-id="889e2-127">Right-click the Relying Party Trust that's listed and right-click for Properties \> Identifiers \> type the additional Pool URL(s) \> click Add.</span></span> 
  
5. <span data-ttu-id="889e2-128">返回到您 Skype 业务 Server 前端服务器或 Standard Edition server 的服务器。</span><span class="sxs-lookup"><span data-stu-id="889e2-128">Return to your Skype for Business Server Front End or Standard Edition server server.</span></span> <span data-ttu-id="889e2-129">从此处，您必须运行 cmdlet 创建的 OAuth 服务器和修改的 OAuth 配置才能与 Skype 的业务。</span><span class="sxs-lookup"><span data-stu-id="889e2-129">From here you must run cmdlets that create an OAuth server and modify that OAuth configuration to work with Skype for Business.</span></span> <span data-ttu-id="889e2-130">您只需执行的业务服务器部署的 Skype 每次此步骤。</span><span class="sxs-lookup"><span data-stu-id="889e2-130">You only need to do this step once per Skype for Business Server deployment.</span></span> <span data-ttu-id="889e2-131">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="889e2-131">Here is an example:</span></span>
    
     `New-CsOAuthServer -Identity sts.contosoIn.com -Type ADFS -MetadataURL https://sts.contosoIn.com/FederationMetadata/2007-06/FederationMetadata.xml`
    
    > [!TIP]
    > <span data-ttu-id="889e2-132">您在此命令中看到的标识 URL 实际上是 AD FS 联合身份验证服务名称时，您可以看到 AD FS 管理中右键单击服务\>属性。</span><span class="sxs-lookup"><span data-stu-id="889e2-132">The 'Identity' URL you see in this command is actually the AD FS Federation Service Name you can see in AD FS Management when you right-click Service \> Properties.</span></span> <span data-ttu-id="889e2-133">类型始终是 ADFS，并且始终是 MetadataURL\<您的 AD FS 服务名称\>+"/ FederationMetadata/2007-06/FederationMetadata.xml"。</span><span class="sxs-lookup"><span data-stu-id="889e2-133">The 'Type' is always 'ADFS', and the 'MetadataURL' is always \<Your AD FS service name\> + "/FederationMetadata/2007-06/FederationMetadata.xml".</span></span> 
  
     `Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity sts.contosoIn.com`
    
6. <span data-ttu-id="889e2-134">仍在您 Skype 业务 Server 前端服务器或 Standard Edition server，通过输入用户名和池 FQDN 的 SIP 地址来测试新的配置。</span><span class="sxs-lookup"><span data-stu-id="889e2-134">Still on your Skype for Business Server Front End or Standard Edition server, test the new configuration by entering the SIP address of a user and the pool FQDN.</span></span> <span data-ttu-id="889e2-135">您只需执行的业务服务器部署的 Skype 每次此步骤。</span><span class="sxs-lookup"><span data-stu-id="889e2-135">You only need to do this step once per Skype for Business Server deployment.</span></span> <span data-ttu-id="889e2-136">下面是一个示例：</span><span class="sxs-lookup"><span data-stu-id="889e2-136">This is an example:</span></span>
    
     `Test-CsRegistration -UserSipAddress AyakaY@contosoIns.com -TargetFqdn Pool1.contoso.com -Authentication OAuthInteractive`
    
7. <span data-ttu-id="889e2-137">出现提示时，请务必输入测试用户的凭据。</span><span class="sxs-lookup"><span data-stu-id="889e2-137">When prompted, be sure to enter the credentials of the test user.</span></span> <span data-ttu-id="889e2-138">验证测试是否成功完成。</span><span class="sxs-lookup"><span data-stu-id="889e2-138">Verify that the test completes successfully.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="889e2-139">当您 STS 的 URL 将解析为 AD FS*内部*时，您将看到的提示将**Windows 安全**提示。</span><span class="sxs-lookup"><span data-stu-id="889e2-139">When your STS URL resolves to AD FS  *internally*  , the prompt you will see will be a **Windows Security** prompt.</span></span> <span data-ttu-id="889e2-140">如果 URL 在外部解析，你将看到一个名为“**登录**”的提示。</span><span class="sxs-lookup"><span data-stu-id="889e2-140">If the URL resolves externally, you'll see a prompt named **Sign in**.</span></span> <span data-ttu-id="889e2-141">通常，我们在这里需要“**Windows 安全**”提示。</span><span class="sxs-lookup"><span data-stu-id="889e2-141">Typically, we would want a **Windows Security** prompt here.</span></span> <span data-ttu-id="889e2-142">请注意，此行为各不相同，特别是当你实施了基于表单的身份验证 (FBA) 时。</span><span class="sxs-lookup"><span data-stu-id="889e2-142">Note that this behaviour varies, particularly if you implemented Forms-Based Authentication (or FBA).</span></span>
  
<span data-ttu-id="889e2-143">另外请注意，当 STS URL 解析为内部 AD FS 服务器时，在浏览器中启用 Windows 集成身份验证，其中许多不同的用户登录到客户端应用程序的计算机可能失败进行身份验证，除非明确是在浏览器配置为提示用户输入凭据在给定浏览器中安全区域。</span><span class="sxs-lookup"><span data-stu-id="889e2-143">Also be aware, when the STS URL resolves to an internal AD FS server and Windows Integrated authentication is enabled in browsers, computers where many different users sign in to client applications may have failures to authenticate unless the browser is explicitly configured to prompt users for their credentials in a given browser Security Zone.</span></span> <span data-ttu-id="889e2-144">以 kiosk 为例。</span><span class="sxs-lookup"><span data-stu-id="889e2-144">Think of a kiosk as an example.</span></span> <span data-ttu-id="889e2-145">登录到操作系统的帐户可能不同于登录到 Skype for Business 客户端的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="889e2-145">The account that is logged in to the Operating System may be different than the user account logging into the Skype for Business client.</span></span> <span data-ttu-id="889e2-146">如果的确如此，你可能会看到此处所述的故障。</span><span class="sxs-lookup"><span data-stu-id="889e2-146">If this is the case, you may see the failures described here.</span></span>
    
<span data-ttu-id="889e2-147">可以查看和更改此浏览器设置在 Internet Explorer 中的单击\>工具 （或齿轮） \> Internet 选项\>安全选项卡\>（如本地 Intranet) 的安全区域。</span><span class="sxs-lookup"><span data-stu-id="889e2-147">You can see and change this browser setting in Internet Explorer by clicking \> Tools (or the Gear) \> Internet Options \> Security tab \> and the Security Zone (such as Local Intranet).</span></span> <span data-ttu-id="889e2-148">从此对话框，单击“自定义级别”按钮并滚动到“设置”对话框中的列表末尾。</span><span class="sxs-lookup"><span data-stu-id="889e2-148">From this dialog, click the Custom level button and scroll to the end of the list in the Settings dialog.</span></span> <span data-ttu-id="889e2-149">在用户身份验证下\>登录\>您将看到用户名和密码提示选项。</span><span class="sxs-lookup"><span data-stu-id="889e2-149">Under User Authentication \> Login \> you'll see an option to 'Prompt for user name and password'.</span></span> <span data-ttu-id="889e2-150">如果在你的 kiosk 中，启动 Skype for Business 客户端的用户不同于（具有不同的帐户）登录计算机的用户，你可能需要在组策略中测试将这些计算机的这个选项设置为“打开”。</span><span class="sxs-lookup"><span data-stu-id="889e2-150">If you have kiosks where the user who starts the Skype for Business client is different (has a different account) from the user logged into the computer, you may want to test setting this option to 'ON' for these machines in a Group Policy.</span></span>
    
<span data-ttu-id="889e2-151">最后，重要的是，你可能会遇到多个提示，因为安全系统会收集对你的帐户进行身份验证或授权所需的信息。</span><span class="sxs-lookup"><span data-stu-id="889e2-151">Finally, and importantly, you may experience more than one prompt as the security system collects the information it needs to authenticate or authorize your account.</span></span>
    
### <a name="other-options-for-enabling-adal-sign-in-like-office-client-apps"></a><span data-ttu-id="889e2-152">用于启用 ADAL 登录的其他选项（如 Office 客户端应用）</span><span class="sxs-lookup"><span data-stu-id="889e2-152">Other Options for Enabling ADAL sign-in (like Office client apps)</span></span>
<span data-ttu-id="889e2-153"><a name="BKMK_Options"> </a></span><span class="sxs-lookup"><span data-stu-id="889e2-153"></span></span>

<span data-ttu-id="889e2-154">既然 ADAL 配置为您的业务 Skype 和 （自动） 对于 Office 2016 跨平台客户端应用程序，您可能想要利用它，Exchange Online 中 （其中不是 On 默认情况下），或在 Office 2013 客户端。</span><span class="sxs-lookup"><span data-stu-id="889e2-154">Now that ADAL is configured for your Skype for Business and (automatically) for Office 2016 client apps across platforms, you may want to leverage it for Exchange Online (where it is not 'On' by default), or in Office 2013 clients.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="889e2-155">需要了解期望现代身份验证登录从您的客户端应用程序是什么？</span><span class="sxs-lookup"><span data-stu-id="889e2-155">Need to know what to expect from Modern Authentication sign-ins from your client apps?</span></span> <span data-ttu-id="889e2-156">了解一下[如何现代身份验证适用于 Office 2013 和 Office 2016 客户端应用程序](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US)。</span><span class="sxs-lookup"><span data-stu-id="889e2-156">Take a look at [How modern authentication works for Office 2013 and Office 2016 client apps](https://support.office.com/en-us/article/How-modern-authentication-works-for-Office-2013-and-Office-2016-client-apps-e4c45989-4b1a-462e-a81b-2a13191cf517?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span> 
  
<span data-ttu-id="889e2-157">要打开 Exchange Online 的现代身份验证，您将需要运行某些 PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="889e2-157">To turn Modern Authentication on for Exchange Online, you'll need to run some PowerShell cmdlets.</span></span> <span data-ttu-id="889e2-158">对于 Office 2013 客户端应用程序，您将需要更改某些客户端计算机上的注册表项。</span><span class="sxs-lookup"><span data-stu-id="889e2-158">In the case of Office 2013 client apps, you will need to change some registry keys on client machines.</span></span>
  
- <span data-ttu-id="889e2-159">连接到 Exchange Online 并运行以下 cmdlet:</span><span class="sxs-lookup"><span data-stu-id="889e2-159">Connect to Exchange Online and run the following cmdlets:</span></span>
    
     `Set-OrganizationConfig -OAuth2ClientProfileEnabled:$true`
    
     `Get-OrganizationConfig | ft name, *OAuth*`
    
- <span data-ttu-id="889e2-160">为要启用新式验证的每个设备或计算机设置这些注册表项。</span><span class="sxs-lookup"><span data-stu-id="889e2-160">Set these registry keys for every device or computer on which you want to enable Modern Authentication.</span></span> <span data-ttu-id="889e2-161">在大型组织中需要一个 GPO。</span><span class="sxs-lookup"><span data-stu-id="889e2-161">You will need a GPO in larger organizations.</span></span> <span data-ttu-id="889e2-162">有关如何使 GPO 的信息，请参阅创建组策略对象修改域联接计算机上的注册表的[这](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)篇文章。</span><span class="sxs-lookup"><span data-stu-id="889e2-162">For information on how to make a GPO, see the 'Create a Group Policy Object to modify the registry on a domain joined computer' of [this ](https://support.office.com/en-us/article/Switching-between-the-Skype-for-Business-and-the-Lync-client-user-interfaces-a2394a4c-7522-484c-a047-7b3289742be0)article.</span></span>
    
|<span data-ttu-id="889e2-163">注册表项</span><span class="sxs-lookup"><span data-stu-id="889e2-163">Registry Key</span></span>  <br/> |<span data-ttu-id="889e2-164">类型</span><span class="sxs-lookup"><span data-stu-id="889e2-164">Type</span></span>  <br/> |<span data-ttu-id="889e2-165">值</span><span class="sxs-lookup"><span data-stu-id="889e2-165">Value</span></span>  <br/> |
|:-----|:-----|:-----|
|<span data-ttu-id="889e2-166">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span><span class="sxs-lookup"><span data-stu-id="889e2-166">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL</span></span>  <br/> |<span data-ttu-id="889e2-167">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="889e2-167">REG_DWORD</span></span>  <br/> |<span data-ttu-id="889e2-168">1</span><span class="sxs-lookup"><span data-stu-id="889e2-168">1</span></span>  <br/> |
|<span data-ttu-id="889e2-169">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span><span class="sxs-lookup"><span data-stu-id="889e2-169">HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version</span></span>  <br/> |<span data-ttu-id="889e2-170">REG_DWORD</span><span class="sxs-lookup"><span data-stu-id="889e2-170">REG_DWORD</span></span>  <br/> |<span data-ttu-id="889e2-171">1</span><span class="sxs-lookup"><span data-stu-id="889e2-171">1</span></span>  <br/> |
   
<span data-ttu-id="889e2-172">这些注册表项设置后, 设置为[使用 Multifactor 身份验证 (MFA) 与 Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US)的 Office 应用程序。</span><span class="sxs-lookup"><span data-stu-id="889e2-172">Once these keys are set, set your Office apps to [use Multifactor Authentication (MFA) with Office 365](https://support.office.com/en-us/article/Set-up-multi-factor-authentication-for-Office-365-8f0454b2-f51a-4d9c-bcde-2c48e41621c6?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
  
> [!TIP]
> <span data-ttu-id="889e2-173">要在 Office 2013 的设备上禁用现代的身份验证，将设置为零值的 HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL 注册表项。</span><span class="sxs-lookup"><span data-stu-id="889e2-173">To disable Modern Authentication on devices for Office 2013, set the HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL registry key to a value of zero.</span></span> <span data-ttu-id="889e2-174">请注意，类似的注册表项 (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) 也用于 Office 2016 的设备上禁用现代身份验证。</span><span class="sxs-lookup"><span data-stu-id="889e2-174">Be aware that a similar Registry key (HKCU\SOFTWARE\Microsoft\Office\ **16.0** \Common\Identity\EnableADAL) can also be used to disable Modern Authentication on devices for Office 2016.</span></span>
  
### <a name="clients-where-modern-authentication--adal-isnt-supported"></a><span data-ttu-id="889e2-175">新式验证/ADAL 不受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="889e2-175">Clients where Modern Authentication / ADAL isn't Supported</span></span>
<span data-ttu-id="889e2-176"><a name="BKMK_Support"> </a></span><span class="sxs-lookup"><span data-stu-id="889e2-176"></span></span>

<span data-ttu-id="889e2-p118">某些客户端版本不支持 OAuth。你可以在用于添加和删除程序的控制面板中检查你的 Office 客户端版本，以便将你的版本号与此处所列的版本（或版本范围）进行比较：</span><span class="sxs-lookup"><span data-stu-id="889e2-p118">Some client versions don't support OAuth. You can check your version of Office client in Control Panel where you Add and Remove programs in order to compare your version number to the versions (or ranges of versions) listed here:</span></span>
  
- <span data-ttu-id="889e2-179">Office 客户端 15.0。[0000-4766]。\*</span><span class="sxs-lookup"><span data-stu-id="889e2-179">Office Client 15.0.[0000-4766].\*</span></span>
    
- <span data-ttu-id="889e2-180">Office 客户端 16.0。[0000-4293]。\*</span><span class="sxs-lookup"><span data-stu-id="889e2-180">Office Client 16.0.[0000-4293].\*</span></span>
    
- <span data-ttu-id="889e2-181">Office 客户端 16.0.6001.[0000-1032]</span><span class="sxs-lookup"><span data-stu-id="889e2-181">Office Client 16.0.6001.[0000-1032]</span></span>
    
- <span data-ttu-id="889e2-182">Office 客户端 16.0。[6000-6224]。\*</span><span class="sxs-lookup"><span data-stu-id="889e2-182">Office Client 16.0.[6000-6224].\*</span></span>
    
> [!NOTE]
> <span data-ttu-id="889e2-183">混合现代身份验证中也有与 Skype 的业务内部部署，如果您想要了解，请访问[如何配置 for Business 的 Skype 本地用于混合现代身份验证](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)</span><span class="sxs-lookup"><span data-stu-id="889e2-183">Hybrid Modern Authentication is also available with Skype For Business on-premises, if you want to know more, please visit [How to configure Skype for Business on-premises to use Hybrid Modern Authentication](https://docs.microsoft.com/en-us/office365/enterprise/configure-skype-for-business-for-hybrid-modern-authentication)</span></span>
