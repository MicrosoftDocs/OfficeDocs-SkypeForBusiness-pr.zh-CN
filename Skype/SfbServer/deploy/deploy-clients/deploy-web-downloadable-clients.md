---
title: 在 Skype for Business Server 中部署 Web 可下载客户端
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：部署与 Skype for Business 一起使用的 Skype for Business Web 应用和 Skype 会议应用。
ms.openlocfilehash: 16a2a28bf634524d6f61ba579652a6dddfd06de3
ms.sourcegitcommit: 0ad2fb145496210b728034d291a456b4caabdbf9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "47429418"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="09cf6-103">在 Skype for Business Server 中部署 Web 可下载客户端</span><span class="sxs-lookup"><span data-stu-id="09cf6-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="09cf6-104">**摘要：** 部署与 Skype for Business Server 一起使用的 Skype for Business 2015 Web 应用和 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="09cf6-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="09cf6-105">Skype for Business Web App 是一项 Internet 信息服务 (安装在运行 Skype for Business Server 的服务器上的 IIS) Web 客户端，并且默认情况下，它将按需部署到尚不具有 Skype for Business 客户端的会议用户。</span><span class="sxs-lookup"><span data-stu-id="09cf6-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="09cf6-106">这些会议用户比不从网络外部连接更频繁。</span><span class="sxs-lookup"><span data-stu-id="09cf6-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="09cf6-107">只要用户单击会议 URL，但未安装 Skype for Business 客户端，用户就会看到使用最新版本的 Skype for Business Web App、Skype 会议应用或 Skype for business for Mac 加入会议的选项。</span><span class="sxs-lookup"><span data-stu-id="09cf6-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="09cf6-108">Skype for Business Web 应用程序中的语音、视频和共享功能需要 Microsoft ActiveX 控件，该控件可用作用户浏览器的插件。</span><span class="sxs-lookup"><span data-stu-id="09cf6-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="09cf6-109">您可以提前安装 ActiveX 控件，也可以允许用户在出现提示时安装它，这是在首次使用 Skype for Business Web App 时，或者在首次访问需要 ActiveX 控件的功能时发生。</span><span class="sxs-lookup"><span data-stu-id="09cf6-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="09cf6-110">在 Skype for business Server Edge 服务器部署中，Skype for business Web App 客户端访问需要外围网络中的 HTTPS 反向代理。</span><span class="sxs-lookup"><span data-stu-id="09cf6-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="09cf6-111">您还必须发布简单 Url。</span><span class="sxs-lookup"><span data-stu-id="09cf6-111">You must also publish simple URLs.</span></span> <span data-ttu-id="09cf6-112">有关详细信息，请参阅[为 Skype For Business Server 中的简单 Url](../../plan-your-deployment/network-requirements/simple-urls.md)[设置反向代理服务器](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx)和 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="09cf6-112">For details, see [Setting Up Reverse Proxy Servers](https://technet.microsoft.com/library/00bc138a-243f-4389-bfa5-9c62fcc95132.aspx) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="09cf6-113">为 Skype for Business Web 应用启用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="09cf6-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="09cf6-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="09cf6-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="09cf6-115">Skype for Business Web App、Skype 会议应用和 Skype for business for Mac 支持多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="09cf6-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="09cf6-116">除了用户名和密码之外，您还可以需要其他身份验证方法（如智能卡或 Pin），以便在用户登录 Skype for business 会议时对从外部网络进行联接的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="09cf6-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="09cf6-117">您可以通过在 Skype for business Server 中部署 Active Directory 联合身份验证服务 (AD FS) 联合服务器并启用被动身份验证来启用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="09cf6-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="09cf6-118">配置 AD FS 后，会向尝试加入 Skype for Business 会议的外部用户提供一个 AD FS 多重身份验证网页，其中包含用户名和密码质询以及您已配置的任何其他身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="09cf6-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="09cf6-119">如果您计划为多因素身份验证配置 AD FS，请注意以下事项：</span><span class="sxs-lookup"><span data-stu-id="09cf6-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="09cf6-120">如果会议参与者和组织者在同一组织中或来自 AD FS 联合组织，则多因素 ADFS 身份验证工作正常。</span><span class="sxs-lookup"><span data-stu-id="09cf6-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="09cf6-121">由于 Lync server web 基础结构目前不支持 Lync 联合用户，因此多因素 ADFS 身份验证不起作用。</span><span class="sxs-lookup"><span data-stu-id="09cf6-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="09cf6-122">如果使用硬件负载平衡器，请在负载平衡器上启用 cookie 暂留，以便来自 Skype for Business Web 应用或会议应用程序客户端的所有请求均由同一前端服务器处理。</span><span class="sxs-lookup"><span data-stu-id="09cf6-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="09cf6-123">当您在 Skype for Business Server 和 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌有效期，以跨越 Skype for business 会议的最大长度。</span><span class="sxs-lookup"><span data-stu-id="09cf6-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="09cf6-124">通常情况下，令牌寿命为240分钟就足够了。</span><span class="sxs-lookup"><span data-stu-id="09cf6-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="09cf6-125">这种配置不适用于 Lync 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="09cf6-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="09cf6-126">配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="09cf6-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="09cf6-127">安装 AD FS 联合服务器角色。</span><span class="sxs-lookup"><span data-stu-id="09cf6-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="09cf6-128">有关详细信息，请参阅 [Active Directory 联合身份验证服务2.0 部署指南](https://go.microsoft.com/fwlink/p/?linkid=267511)</span><span class="sxs-lookup"><span data-stu-id="09cf6-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](https://go.microsoft.com/fwlink/p/?linkid=267511)</span></span>

2. <span data-ttu-id="09cf6-129">为 AD FS 创建证书。</span><span class="sxs-lookup"><span data-stu-id="09cf6-129">Create certificates for AD FS.</span></span> <span data-ttu-id="09cf6-130">有关详细信息，请参阅规划和部署 AD FS 的 ["联合服务器证书"](https://go.microsoft.com/fwlink/p/?LinkId=285376) 一节，以便与单一登录主题配合使用。</span><span class="sxs-lookup"><span data-stu-id="09cf6-130">For more information, see ["Federation server certificates"](https://go.microsoft.com/fwlink/p/?LinkId=285376) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="09cf6-131">从 Windows PowerShell 命令行界面中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="09cf6-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="09cf6-132">通过运行以下命令建立合作关系：</span><span class="sxs-lookup"><span data-stu-id="09cf6-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="09cf6-133">设置以下信赖方规则：</span><span class="sxs-lookup"><span data-stu-id="09cf6-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="09cf6-134">禁用 BranchCache</span><span class="sxs-lookup"><span data-stu-id="09cf6-134">Disable BranchCache</span></span>
<span data-ttu-id="09cf6-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="09cf6-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="09cf6-136">Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Skype for Business Web App web 组件。</span><span class="sxs-lookup"><span data-stu-id="09cf6-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="09cf6-137">若要防止 Skype for business Web App 用户的问题，请确保未启用 BranchCache。</span><span class="sxs-lookup"><span data-stu-id="09cf6-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="09cf6-138">有关禁用 BranchCache 的详细信息，请参阅 [BranchCache 部署指南](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="09cf6-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](https://docs.microsoft.com/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="09cf6-139">验证 Skype for Business Web 应用部署</span><span class="sxs-lookup"><span data-stu-id="09cf6-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="09cf6-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="09cf6-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="09cf6-141">您可以使用 Test-csucwaconference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API (UCWA) 参与会议。</span><span class="sxs-lookup"><span data-stu-id="09cf6-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="09cf6-142">有关此 cmdlet 的详细信息，请参阅 Skype for Business Server 命令行管理程序文档中的 [test-csucwaconference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) 。</span><span class="sxs-lookup"><span data-stu-id="09cf6-142">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="09cf6-143">在 Windows Server 2008 R2 上排除插件安装故障</span><span class="sxs-lookup"><span data-stu-id="09cf6-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="09cf6-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="09cf6-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="09cf6-145">如果在运行 Windows Server 2008 R2 的计算机上安装插件失败，您可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。</span><span class="sxs-lookup"><span data-stu-id="09cf6-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="09cf6-146">在 Internet Explorer 中修改安全设置</span><span class="sxs-lookup"><span data-stu-id="09cf6-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="09cf6-147">打开 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="09cf6-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="09cf6-148">依次单击 " **工具**"、" **Internet 选项**" 和 " **高级**"。</span><span class="sxs-lookup"><span data-stu-id="09cf6-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="09cf6-149">向下滚动到 " **安全性** " 部分。</span><span class="sxs-lookup"><span data-stu-id="09cf6-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="09cf6-150">清除 " **不将加密的页面保存到磁盘**"，然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="09cf6-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="09cf6-151">如果选中此选项，则在尝试从 Skype for Business Web 应用下载附件时，此设置也会导致错误。</span><span class="sxs-lookup"><span data-stu-id="09cf6-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="09cf6-152">重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="09cf6-152">Rejoin the meeting.</span></span> <span data-ttu-id="09cf6-153">插件应下载，且不会出现错误。</span><span class="sxs-lookup"><span data-stu-id="09cf6-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="09cf6-154">修改 DisableMSI 注册表设置</span><span class="sxs-lookup"><span data-stu-id="09cf6-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="09cf6-155">单击“开始”\*\*\*\*，然后单击“运行”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="09cf6-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="09cf6-156">若要访问注册表编辑器，请键入 **regedit**。</span><span class="sxs-lookup"><span data-stu-id="09cf6-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="09cf6-157">导航到 HKEY_LOCAL_MACHINE \Software\Policies\Microsoft\Windows\Installer。</span><span class="sxs-lookup"><span data-stu-id="09cf6-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="09cf6-158">编辑或添加 REG_DWORD 类型的 DisableMSI 注册表项，并将其设置为0。</span><span class="sxs-lookup"><span data-stu-id="09cf6-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="09cf6-159">重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="09cf6-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="09cf6-160">启用 Skype 会议应用程序以将 Skype for Business Web App 替换 (可选，Skype for Business Server 2015 仅) </span><span class="sxs-lookup"><span data-stu-id="09cf6-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="09cf6-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="09cf6-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="09cf6-162">此过程是可选的，适用于 Skype for Business Server 2015 CU5 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="09cf6-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="09cf6-163">如果不使用它，外部用户将继续使用 Skype for Business Web 应用加入会议。</span><span class="sxs-lookup"><span data-stu-id="09cf6-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="09cf6-164">启用简化的会议加入和 Skype 会议应用</span><span class="sxs-lookup"><span data-stu-id="09cf6-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="09cf6-165">当您启用对内容传递网络 (CDN) 的访问时，用户将能够连接到 CDN online，并在 Windows) 上获取 Skype for business 应用程序 (，并在 Mac (上获取 skype for business for Mac) ，并将使用简化的会议加入体验。</span><span class="sxs-lookup"><span data-stu-id="09cf6-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="09cf6-166">允许将来自会议加入网页或 Skype 会议应用的客户端日志记录遥测发送到 Microsoft 服务器 (该命令的默认值为 false) 。</span><span class="sxs-lookup"><span data-stu-id="09cf6-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="09cf6-167">发送给 Microsoft 的信息严格遵守 [隐私和 Microsoft 团队](../../../../Teams/teams-privacy.md)。</span><span class="sxs-lookup"><span data-stu-id="09cf6-167">Information sent to Microsoft is in strict compliance with [Privacy and Microsoft Teams](../../../../Teams/teams-privacy.md).</span></span>

3. <span data-ttu-id="09cf6-168">如果 CDN 不可用，则在回退到本地承载的 Skype for Business Web 应用体验之前设置超时。</span><span class="sxs-lookup"><span data-stu-id="09cf6-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="09cf6-169">默认值为6秒。</span><span class="sxs-lookup"><span data-stu-id="09cf6-169">The default value is 6 seconds.</span></span> <span data-ttu-id="09cf6-170">如果此值设置为0，则不会有任何超时。</span><span class="sxs-lookup"><span data-stu-id="09cf6-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="09cf6-171">使用 Skype for Business Server 2015 累积更新5中的 MeetingUxUseCdn 时，默认值设置为 False。</span><span class="sxs-lookup"><span data-stu-id="09cf6-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="09cf6-172">这会导致 Skype for Business for Mac 客户端无法将非联合合作伙伴的会议作为来宾加入，即使 Skype for Business 管理员已将 MeetingUxUseCdn 设置为 True 也是如此。</span><span class="sxs-lookup"><span data-stu-id="09cf6-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="09cf6-173">为使此操作正常运行，Skype for Business Server 2015 必须具有累积更新7、6.0.9319.534 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="09cf6-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="09cf6-174">请参阅 [启用 Skype 会议应用以替换 skype for Business Server 2015 中的 skype For Business Web 应用](https://support.microsoft.com/kb/4132312)。</span><span class="sxs-lookup"><span data-stu-id="09cf6-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="09cf6-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="09cf6-175">See also</span></span>
<span data-ttu-id="09cf6-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="09cf6-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="09cf6-177">规划会议客户端 (Web 应用程序和会议应用程序) </span><span class="sxs-lookup"><span data-stu-id="09cf6-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="09cf6-178">在 Skype for Business Server 中配置会议加入页面</span><span class="sxs-lookup"><span data-stu-id="09cf6-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="09cf6-179">Microsoft Online Services 隐私声明</span><span class="sxs-lookup"><span data-stu-id="09cf6-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="09cf6-180">许可条款和文档</span><span class="sxs-lookup"><span data-stu-id="09cf6-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)
