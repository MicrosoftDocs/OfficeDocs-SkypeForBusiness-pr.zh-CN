---
title: 在 Skype for Business Server 2015 中部署 Web 可下载客户端
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/6/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要： 部署企业 Web 应用程序和 Skype 会议应用程序与 Skype 用于业务 Skype。
ms.openlocfilehash: a81e8744208261934635aee4f8a872a81b179c90
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server-2015"></a><span data-ttu-id="d4359-103">在 Skype for Business Server 2015 中部署 Web 可下载客户端</span><span class="sxs-lookup"><span data-stu-id="d4359-103">Deploy Web downloadable clients in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="d4359-104">**摘要：** 部署企业 Web 应用程序和 Skype 会议应用程序与 Skype 用于业务 Skype。</span><span class="sxs-lookup"><span data-stu-id="d4359-104">**Summary:** Deploy the Skype for Business Web App and Skype Meetings App used with Skype for Business.</span></span>
  
<span data-ttu-id="d4359-105">企业 Web 应用程序的 Skype 是 Skype 业务服务器 2015年和部署的默认按需运行会议用户尚不具有业务客户端 Skype 服务器安装了 Internet 信息服务 (IIS) web 客户端。</span><span class="sxs-lookup"><span data-stu-id="d4359-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server 2015 and default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="d4359-106">这些会议用户通常从你的网络外连接。</span><span class="sxs-lookup"><span data-stu-id="d4359-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="d4359-107">只要用户单击会议 URL，但没有业务客户端安装 Skype，用户将显示使用最新版本的 Skype 企业 Web 应用程序加入会议选项。</span><span class="sxs-lookup"><span data-stu-id="d4359-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App.</span></span>
  
<span data-ttu-id="d4359-108">视频和共享的语音功能 Skype 中的企业 Web 应用程序要求用作用户的浏览器插件一个 Microsoft ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="d4359-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="d4359-109">您可以提前安装 ActiveX 控件或允许用户安装它出现提示时，发生第一次企业 Web 应用程序使用 Skype 或他们访问功能在首次需要的 ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="d4359-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d4359-110">Skype 业务 Server 2015 边缘服务器部署，在外围网络中的 HTTPS 反向代理是需要的 Skype 业务 Web App 客户端访问。</span><span class="sxs-lookup"><span data-stu-id="d4359-110">In Skype for Business Server 2015 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="d4359-111">你还必须发布简单的 URL。</span><span class="sxs-lookup"><span data-stu-id="d4359-111">You must also publish simple URLs.</span></span> <span data-ttu-id="d4359-112">有关详细信息，请参阅[设置 Up Reverse Proxy Servers](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [Planning for Simple URLs](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx)。</span><span class="sxs-lookup"><span data-stu-id="d4359-112">For details, see [Setting Up Reverse Proxy Servers](http://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [Planning for Simple URLs](http://technet.microsoft.com/library/20e4f4b6-b7ff-4297-b00d-d1211ee800ac.aspx).</span></span> 
  
## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="d4359-113">启用 Skype 业务 Web 应用程序的多因素身份的验证</span><span class="sxs-lookup"><span data-stu-id="d4359-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="d4359-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="d4359-114"></span></span>

<span data-ttu-id="d4359-115">Skype 业务 Web 应用程序的业务服务器 2015年版 Skype 支持多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4359-115">The Skype for Business Server 2015 version of Skype for Business Web App supports multi-factor authentication.</span></span> <span data-ttu-id="d4359-116">除了用户名和密码，您可以要求其他身份验证方法，例如智能卡或旋转中心点，当用户登录到 Skype 业务会议加入从外部网络的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4359-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="d4359-117">您可以通过部署 Active Directory 联合身份验证服务 (AD FS) 联合服务器和启用业务服务器 2015年中 Skype 被动身份验证启用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="d4359-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server 2015.</span></span> <span data-ttu-id="d4359-118">配置 AD FS 后，尝试业务会议加入 Skype 的外部用户显示包含用户名的 AD FS 多因素身份验证网页，以及任何其他身份验证方法的密码质询您已配置。</span><span class="sxs-lookup"><span data-stu-id="d4359-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="d4359-119">如果您计划配置 AD FS 以进行多重身份验证，则以下是一些重要注意事项：</span><span class="sxs-lookup"><span data-stu-id="d4359-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
  
- <span data-ttu-id="d4359-p105">如果会议参加者和组织者位于同一组织中或都来自 AD FS 联盟组织，则 ADFS 多重身份验证生效。ADFS 多重身份验证不适用于 Lync 联盟用户，因为 Lync 服务器 Web 基础结构当前不支持该验证方法。</span><span class="sxs-lookup"><span data-stu-id="d4359-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>
    
- <span data-ttu-id="d4359-122">如果您使用硬件负载平衡器，请启用负载平衡器上的 cookie 持久性，以便使来自业务 Web App 客户端 Skype 的所有请求均由同一前端服务器都处理。</span><span class="sxs-lookup"><span data-stu-id="d4359-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App client are handled by the same Front End Server.</span></span>
    
- <span data-ttu-id="d4359-123">当您信赖方之间建立信任业务服务器和 AD FS 服务器的 Skype 时，分配足够跨业务会议您 Skype 的最大长度令牌生命。</span><span class="sxs-lookup"><span data-stu-id="d4359-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="d4359-124">通常，240 分钟的令牌使用时间就足够了。</span><span class="sxs-lookup"><span data-stu-id="d4359-124">Typically, a token life of 240 minutes is sufficient.</span></span>
    
- <span data-ttu-id="d4359-125">此配置不适用于 Lync 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="d4359-125">This configuration does not apply to Lync mobile clients.</span></span>
    
### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="d4359-126">配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="d4359-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="d4359-127">安装 AD FS 联盟服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d4359-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="d4359-128">有关详细信息，请参阅[Active Directory 联合身份验证服务 2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="d4359-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>
    
2. <span data-ttu-id="d4359-129">为 AD FS 创建证书。</span><span class="sxs-lookup"><span data-stu-id="d4359-129">Create certificates for AD FS.</span></span> <span data-ttu-id="d4359-130">有关详细信息，请参阅["联合身份验证服务器证书"](https://go.microsoft.com/fwlink/p/?LinkId=285376)部分中的规划和部署 AD FS 以用于单一登录主题。</span><span class="sxs-lookup"><span data-stu-id="d4359-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>
    
3. <span data-ttu-id="d4359-131">从 Windows PowerShell 命令行界面，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d4359-131">From the Windows PowerShell command-line interface, run the following command:</span></span>
    
    ```
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="d4359-132">通过运行以下命令来建立合作关系：</span><span class="sxs-lookup"><span data-stu-id="d4359-132">Establish a partnership by running the following command:</span></span>
    
    ```
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="d4359-133">设置以下信赖方规则：</span><span class="sxs-lookup"><span data-stu-id="d4359-133">Set the following relying party rules:</span></span>
    
    ```
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   ```
 
   ```
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   ```

   ```
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="d4359-134">禁用 BranchCache </span><span class="sxs-lookup"><span data-stu-id="d4359-134">Disable BranchCache</span></span>
<span data-ttu-id="d4359-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="d4359-135"></span></span>

<span data-ttu-id="d4359-136">Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能中，可以干扰业务 Web 应用程序 web 组件的 Skype。</span><span class="sxs-lookup"><span data-stu-id="d4359-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="d4359-137">若要为企业 Web 应用程序用户的 Skype 阻止问题，请确保为未启用 BranchCache。</span><span class="sxs-lookup"><span data-stu-id="d4359-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span> 
  
<span data-ttu-id="d4359-138">有关禁用 BranchCache，有关详细信息，请参阅 BranchCache 部署指南中，可在 Microsoft 下载中心 Word 格式[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788)和 Windows Server 2008 R2 技术库中在 HTML 格式[https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789)。</span><span class="sxs-lookup"><span data-stu-id="d4359-138">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?LinkId=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [https://go.microsoft.com/fwlink/p/?LinkId=268789](https://go.microsoft.com/fwlink/p/?LinkId=268789).</span></span>
  
## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="d4359-139">验证 Skype 业务 Web 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="d4359-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="d4359-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="d4359-140"></span></span>

<span data-ttu-id="d4359-141">你可以使用 Test-CsUcwaConference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API (UCWA) 参加会议。</span><span class="sxs-lookup"><span data-stu-id="d4359-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="d4359-142">有关此 cmdlet 的详细信息，请参阅中的业务 Server Management Shell 文档 Skype [Test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="d4359-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>
  
## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="d4359-143">Windows Server 2008 R2 上的插件安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="d4359-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="d4359-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="d4359-144"></span></span>

<span data-ttu-id="d4359-145">如果运行 Windows Server 2008 R2 的计算机上，安装插件失败，您可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。</span><span class="sxs-lookup"><span data-stu-id="d4359-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>
  
### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="d4359-146">修改 Internet Explorer 的安全设置</span><span class="sxs-lookup"><span data-stu-id="d4359-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="d4359-147">打开 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="d4359-147">Open Internet Explorer.</span></span>
    
2. <span data-ttu-id="d4359-148">依次单击 **“工具”**、**“Internet 选项”** 和 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="d4359-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>
    
3. <span data-ttu-id="d4359-149">向下滚动至 **“安全”** 部分。</span><span class="sxs-lookup"><span data-stu-id="d4359-149">Scroll down to the **Security** section.</span></span>
    
4. <span data-ttu-id="d4359-150">清除 **“不将加密的页存盘”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d4359-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="d4359-151">如果选中，此设置还将导致出错，尝试从 Skype 为企业 Web 应用程序下载附件时。</span><span class="sxs-lookup"><span data-stu-id="d4359-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span> 
  
5. <span data-ttu-id="d4359-p111">重新加入会议。插件应该可以无误地下载。</span><span class="sxs-lookup"><span data-stu-id="d4359-p111">Rejoin the meeting. The plug-in should download without errors.</span></span>
    
### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="d4359-154">修改 DisableMSI 注册表设置</span><span class="sxs-lookup"><span data-stu-id="d4359-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="d4359-155">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="d4359-155">Click **Start**, and then click **Run**.</span></span>
    
2. <span data-ttu-id="d4359-156">要访问注册表编辑器，请键入 **regedit**。</span><span class="sxs-lookup"><span data-stu-id="d4359-156">To access the Registry Editor, type **regedit**.</span></span>
    
3. <span data-ttu-id="d4359-157">导航到 HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。</span><span class="sxs-lookup"><span data-stu-id="d4359-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>
    
4. <span data-ttu-id="d4359-158">编辑或添加类型为 REG_DWORD 的 DisableMSI 注册表项，并将其设置为 0。</span><span class="sxs-lookup"><span data-stu-id="d4359-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>
    
5. <span data-ttu-id="d4359-159">重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="d4359-159">Rejoin the meeting.</span></span>
    
## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional"></a><span data-ttu-id="d4359-160">启用 Skype 会议应用以替换 Skype for Business Web 应用（可选）</span><span class="sxs-lookup"><span data-stu-id="d4359-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional)</span></span>
<span data-ttu-id="d4359-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="d4359-161"></span></span>

<span data-ttu-id="d4359-162">此过程可选。</span><span class="sxs-lookup"><span data-stu-id="d4359-162">This procedure is optional.</span></span> <span data-ttu-id="d4359-163">如果不使用它，外部用户将继续使用 Skype 的企业 Web 应用程序加入会议。</span><span class="sxs-lookup"><span data-stu-id="d4359-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span> 
  
### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="d4359-164">启用简化会议加入和 Skype 会议应用</span><span class="sxs-lookup"><span data-stu-id="d4359-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="d4359-165">启用访问到内容交付网络 (CDN) 时，用户将能够连接到 CDN online 和获取 Skype 会议应用程序，并将使用简化会议加入体验。</span><span class="sxs-lookup"><span data-stu-id="d4359-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App, and will use the simplified meeting join experience.</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="d4359-166">允许客户端日志记录遥测从会议加入网页或 Skype 会议应用程序发送给 Microsoft 服务器 （命令默认为 false）。</span><span class="sxs-lookup"><span data-stu-id="d4359-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span> 
    
   ```
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="d4359-167">在严格符合[业务数据集做法的 Skype](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US)信息发送给 Microsoft。</span><span class="sxs-lookup"><span data-stu-id="d4359-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](https://support.office.com/en-us/article/Skype-for-Business-data-collection-practices-c17e8ea6-b83b-4345-9401-47a6c8b13aad?ui=en-US&amp;rs=en-US&amp;ad=US).</span></span>
    
3. <span data-ttu-id="d4359-168">设置超时之前回退到本地承载 Skype 的业务 Web 应用程序体验中，如果 CDN 不可用。</span><span class="sxs-lookup"><span data-stu-id="d4359-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="d4359-169">默认值是 6 秒。</span><span class="sxs-lookup"><span data-stu-id="d4359-169">The default value is 6 seconds.</span></span> <span data-ttu-id="d4359-170">如果将该值设置为 0，则没有超时。</span><span class="sxs-lookup"><span data-stu-id="d4359-170">If this value is set to 0, there will be no timeout.</span></span>
    
   ```
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

## <a name="see-also"></a><span data-ttu-id="d4359-171">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d4359-171">See also</span></span>
<span data-ttu-id="d4359-172"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="d4359-172"></span></span>

#### 

[<span data-ttu-id="d4359-173">规划会议客户端 （Web 应用程序和会议应用程序）</span><span class="sxs-lookup"><span data-stu-id="d4359-173">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)
  
[<span data-ttu-id="d4359-174">规划会议客户端 （Web 应用程序和会议应用程序）</span><span class="sxs-lookup"><span data-stu-id="d4359-174">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="d4359-175">配置与会页面</span><span class="sxs-lookup"><span data-stu-id="d4359-175">Configuring the Meeting Join Page</span></span>](http://technet.microsoft.com/library/45880423-47f4-49af-b825-cbd8e3fc1046.aspx)
  
[<span data-ttu-id="d4359-176">Microsoft Online Services 隐私声明</span><span class="sxs-lookup"><span data-stu-id="d4359-176">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/en-us/privacystatement/OnlineServices/Default.aspx)
  
[<span data-ttu-id="d4359-177">许可条款和文档</span><span class="sxs-lookup"><span data-stu-id="d4359-177">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)

