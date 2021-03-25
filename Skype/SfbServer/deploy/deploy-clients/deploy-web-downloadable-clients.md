---
title: 在 Skype for Business Server 中部署 Web 可下载客户端
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: PhillipGarding
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
description: 摘要：部署与 Skype for Business 一同使用的 Skype for Business Web App 和 Skype 会议应用。
ms.openlocfilehash: 20489dddb244b179908f8c8a565bb1f4d539a5a7
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51122126"
---
# <a name="deploy-web-downloadable-clients-in-skype-for-business-server"></a><span data-ttu-id="cf7a3-103">在 Skype for Business Server 中部署 Web 可下载客户端</span><span class="sxs-lookup"><span data-stu-id="cf7a3-103">Deploy Web downloadable clients in Skype for Business Server</span></span>

<span data-ttu-id="cf7a3-104">**摘要：** 部署与 Skype for Business Server 一同使用的 Skype for Business 2015 Web 应用和 Skype 会议应用。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-104">**Summary:** Deploy the Skype for Business 2015 Web App and Skype Meetings App used with Skype for Business Server.</span></span>

<span data-ttu-id="cf7a3-105">Skype for Business Web App 是一个 Internet Information Services (IIS) Web 客户端，安装在运行 Skype for Business Server 的服务器上，默认情况下，它将按需部署到尚未拥有 Skype for Business 客户端的会议用户。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-105">Skype for Business Web App is an Internet Information Services (IIS) web client that is installed on the server running Skype for Business Server and by default it is deployed on demand to meeting users who do not already have the Skype for Business client.</span></span> <span data-ttu-id="cf7a3-106">这些会议用户通常不是从网络外部连接。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-106">These meeting users are more often than not connecting from outside your network.</span></span> <span data-ttu-id="cf7a3-107">每当用户单击会议 URL 但没有安装 Skype for Business 客户端时，都会向用户显示使用最新版本的 Skype for Business Web App、Skype 会议应用或 Skype for Business for Mac 加入会议的选项。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-107">Whenever a user clicks a meeting URL but does not have the Skype for Business client installed, the user is presented with the option to join the meeting by using the latest version of Skype for Business Web App, Skype Meetings App, or Skype for Business for Mac.</span></span>

<span data-ttu-id="cf7a3-108">Skype for Business Web App 中的语音、视频和共享功能需要 Microsoft ActiveX 控件，该控件用作用户的浏览器的插件。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-108">The voice, video, and sharing features in Skype for Business Web App require a Microsoft ActiveX control that is used as a plugin by the user's browser.</span></span> <span data-ttu-id="cf7a3-109">你可以提前安装 ActiveX 控件，或允许用户在出现提示时安装它，这发生在他们第一次使用 Skype for Business Web App 或首次访问需要 ActiveX 控件的功能时。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-109">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Skype for Business Web App or the first time they access a feature that requires the ActiveX control.</span></span>

> [!NOTE]
> <span data-ttu-id="cf7a3-110">在 Skype for Business Server 边缘服务器部署中，外围网络中需要 HTTPS 反向代理才能访问 Skype for Business Web App 客户端。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-110">In Skype for Business Server Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Skype for Business Web App client access.</span></span> <span data-ttu-id="cf7a3-111">您还必须发布简单 URL。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-111">You must also publish simple URLs.</span></span> <span data-ttu-id="cf7a3-112">有关详细信息，请参阅在[Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md)中设置反向[代理服务器](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers)和简单 URL 的 DNS 要求。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-112">For details, see [Setting Up Reverse Proxy Servers](/previous-versions/office/lync-server-2013/lync-server-2013-setting-up-reverse-proxy-servers) and [DNS requirements for simple URLs in Skype for Business Server](../../plan-your-deployment/network-requirements/simple-urls.md).</span></span>

## <a name="enable-multi-factor-authentication-for-skype-for-business-web-app"></a><span data-ttu-id="cf7a3-113">为 Skype for Business Web App 启用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="cf7a3-113">Enable Multi-Factor Authentication for Skype for Business Web App</span></span>
<span data-ttu-id="cf7a3-114"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7a3-114"><a name="MFA"> </a></span></span>

<span data-ttu-id="cf7a3-115">Skype for Business Web App、Skype 会议应用和 Skype for Business for Mac 支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-115">Skype for Business Web App,  Skype Meetings App, and Skype for Business for Mac support multi-factor authentication.</span></span> <span data-ttu-id="cf7a3-116">除了用户名和密码之外，还可以要求其他身份验证方法（如智能卡或 PIN）来验证在登录到 Skype for Business 会议时从外部网络加入的用户。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-116">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Skype for Business meetings.</span></span> <span data-ttu-id="cf7a3-117">可以通过部署 Active Directory 联合身份验证服务 (AD FS) 联合服务器，在 Skype for Business Server 中启用被动身份验证来启用多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-117">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Skype for Business Server.</span></span> <span data-ttu-id="cf7a3-118">配置 AD FS 后，将向尝试加入 Skype for Business 会议的外部用户显示 AD FS 多重身份验证网页，其中包含用户名和密码质询以及已配置的其他身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-118">After AD FS is configured, external users who attempt to join Skype for Business meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cf7a3-119">如果您计划为多重身份验证配置 AD FS，则以下为重要注意事项：</span><span class="sxs-lookup"><span data-stu-id="cf7a3-119">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span>

- <span data-ttu-id="cf7a3-120">如果会议参与者和组织者位于同一组织中或都来自 AD FS 联盟组织，则多重 ADFS 身份验证有效。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-120">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization.</span></span> <span data-ttu-id="cf7a3-121">多重 ADFS 身份验证对 Lync 联盟用户不起作用，因为 Lync Server Web 基础结构当前不支持它。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-121">Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span>

- <span data-ttu-id="cf7a3-122">如果使用硬件负载平衡器，请对负载平衡器启用 Cookie 持久性，以便来自 Skype for Business Web App 或会议应用客户端的所有请求都由同一前端服务器处理。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-122">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Skype for Business Web App or Meetings App clients are handled by the same Front End Server.</span></span>

- <span data-ttu-id="cf7a3-123">在 Skype for Business Server 和 AD FS 服务器之间建立信赖方信任时，分配一个足够长的令牌生命周期，以跨越 Skype for Business 会议的最大长度。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-123">When you establish a relying party trust between Skype for Business Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Skype for Business meetings.</span></span> <span data-ttu-id="cf7a3-124">通常，240 分钟的令牌使用时间就足够了。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-124">Typically, a token life of 240 minutes is sufficient.</span></span>

- <span data-ttu-id="cf7a3-125">此配置不适用于 Lync 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-125">This configuration does not apply to Lync mobile clients.</span></span>

### <a name="configure-multi-factor-authentication"></a><span data-ttu-id="cf7a3-126">配置多重身份验证</span><span class="sxs-lookup"><span data-stu-id="cf7a3-126">Configure Multi-Factor Authentication</span></span>

1. <span data-ttu-id="cf7a3-127">安装 AD FS 联合服务器角色。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-127">Install an AD FS federation server role.</span></span> <span data-ttu-id="cf7a3-128">有关详细信息，请参阅 [Active Directory 联合身份验证服务 2.0 部署指南](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span><span class="sxs-lookup"><span data-stu-id="cf7a3-128">For details, see the [Active Directory Federation Services 2.0 Deployment Guide](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/dd807092(v=ws.10))</span></span>

2. <span data-ttu-id="cf7a3-129">为 AD FS 创建证书。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-129">Create certificates for AD FS.</span></span> <span data-ttu-id="cf7a3-130">有关详细信息，请参阅计划和 [部署](/previous-versions/azure/azure-services/jj205462(v=azure.100)) AD FS 以用于单一登录主题的"联合服务器证书"部分。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-130">For more information, see ["Federation server certificates"](/previous-versions/azure/azure-services/jj205462(v=azure.100)) section of the Plan for and deploy AD FS for use with single sign-on topic.</span></span>

3. <span data-ttu-id="cf7a3-131">从Windows PowerShell命令行接口运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="cf7a3-131">From the Windows PowerShell command-line interface, run the following command:</span></span>

    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```

4. <span data-ttu-id="cf7a3-132">通过运行以下命令建立合作关系：</span><span class="sxs-lookup"><span data-stu-id="cf7a3-132">Establish a partnership by running the following command:</span></span>

    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```

5. <span data-ttu-id="cf7a3-133">设置以下信赖方规则：</span><span class="sxs-lookup"><span data-stu-id="cf7a3-133">Set the following relying party rules:</span></span>

    ```powershell
   $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
   Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
   Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
   ```

## <a name="disable-branchcache"></a><span data-ttu-id="cf7a3-134">禁用 BranchCache</span><span class="sxs-lookup"><span data-stu-id="cf7a3-134">Disable BranchCache</span></span>
<span data-ttu-id="cf7a3-135"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7a3-135"><a name="MFA"> </a></span></span>

<span data-ttu-id="cf7a3-136">Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Skype for Business Web App Web 组件。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-136">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Skype for Business Web App web components.</span></span> <span data-ttu-id="cf7a3-137">若要防止 Skype for Business Web App 用户的问题，请确保未启用 BranchCache。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-137">To prevent issues for Skype for Business Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="cf7a3-138">有关禁用 BranchCache 的详细信息，请参阅 [BranchCache 部署指南](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide)。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-138">For details about disabling BranchCache, see the [BranchCache Deployment Guide](/windows-server/networking/branchcache/deploy/branchcache-deployment-guide).</span></span>

## <a name="verifying-skype-for-business-web-app-deployment"></a><span data-ttu-id="cf7a3-139">验证 Skype for Business Web App 部署</span><span class="sxs-lookup"><span data-stu-id="cf7a3-139">Verifying Skype for Business Web App Deployment</span></span>
<span data-ttu-id="cf7a3-140"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7a3-140"><a name="MFA"> </a></span></span>

<span data-ttu-id="cf7a3-141">可以使用 Test-CsUcwaConference cmdlet 验证一对测试用户能否使用 UCWA (统一通信 Web API 参与) 。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-141">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="cf7a3-142">有关此 cmdlet 的详细信息，请参阅 Skype for Business Server 命令行管理程序文档中的[Test-CsUcwaConference。](/powershell/module/skype/test-csucwaconference?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="cf7a3-142">For details about this cmdlet, see [Test-CsUcwaConference](/powershell/module/skype/test-csucwaconference?view=skype-ps) in the Skype for Business Server Management Shell documentation.</span></span>

## <a name="troubleshooting-plug-in-installation-on-windows-server-2008-r2"></a><span data-ttu-id="cf7a3-143">Windows Server 2008 R2 上的插件安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="cf7a3-143">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>
<span data-ttu-id="cf7a3-144"><a name="MFA"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7a3-144"><a name="MFA"> </a></span></span>

<span data-ttu-id="cf7a3-145">如果在运行 Windows Server 2008 R2 的计算机上安装插件失败，您可能需要修改 Internet Explorer 安全性设置或 DisableMSI 注册表项设置。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-145">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

### <a name="modify-the-security-setting-in-internet-explorer"></a><span data-ttu-id="cf7a3-146">修改 Internet Explorer</span><span class="sxs-lookup"><span data-stu-id="cf7a3-146">Modify the security setting in Internet Explorer</span></span>

1. <span data-ttu-id="cf7a3-147">打开 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-147">Open Internet Explorer.</span></span>

2. <span data-ttu-id="cf7a3-148">单击 **"工具**"，单击 **"Internet 选项**"，然后单击"**高级"。**</span><span class="sxs-lookup"><span data-stu-id="cf7a3-148">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3. <span data-ttu-id="cf7a3-149">向下滚动到"安全性 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-149">Scroll down to the **Security** section.</span></span>

4. <span data-ttu-id="cf7a3-150">清除 **"不将加密页面保存到磁盘"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="cf7a3-150">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="cf7a3-151">如果选中此设置，则尝试从 Skype for Business Web App 下载附件时也会导致错误。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-151">If selected, this setting will also cause an error when trying to download an attachment from Skype for Business Web App.</span></span>

5. <span data-ttu-id="cf7a3-152">重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-152">Rejoin the meeting.</span></span> <span data-ttu-id="cf7a3-153">插件应下载且不会出现错误。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-153">The plug-in should download without errors.</span></span>

### <a name="modify-the-disablemsi-registry-setting"></a><span data-ttu-id="cf7a3-154">修改 DisableMSI 注册表设置</span><span class="sxs-lookup"><span data-stu-id="cf7a3-154">Modify the DisableMSI Registry setting</span></span>

1. <span data-ttu-id="cf7a3-155">单击“开始”，然后单击“运行”。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-155">Click **Start**, and then click **Run**.</span></span>

2. <span data-ttu-id="cf7a3-156">若要访问注册表编辑器，请键入 **regedit**。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-156">To access the Registry Editor, type **regedit**.</span></span>

3. <span data-ttu-id="cf7a3-157">导航到HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-157">Navigate to HKEY_LOCAL_MACHINE\Software\Policies\Microsoft\Windows\Installer.</span></span>

4. <span data-ttu-id="cf7a3-158">编辑或添加类型为 REG_DWORD的 DisableMSI 注册表项，将其设置为 0。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-158">Edit or add the DisableMSI registry key of type REG_DWORD and set it to 0.</span></span>

5. <span data-ttu-id="cf7a3-159">重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-159">Rejoin the meeting.</span></span>

## <a name="enable-skype-meetings-app-to-replace-skype-for-business-web-app-optional-skype-for-business-server-2015-only"></a><span data-ttu-id="cf7a3-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional， Skype for Business Server 2015 only) </span><span class="sxs-lookup"><span data-stu-id="cf7a3-160">Enable Skype Meetings App to replace Skype for Business Web App (Optional, Skype for Business Server 2015 only)</span></span>
<span data-ttu-id="cf7a3-161"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7a3-161"><a name="SMA_Enable"> </a></span></span>

<span data-ttu-id="cf7a3-162">此过程是可选的，适用于 Skype for Business Server 2015 CU5 及更高版本。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-162">This procedure is optional, and applies to Skype for Business Server 2015 CU5 and later.</span></span> <span data-ttu-id="cf7a3-163">如果不使用它，外部用户将继续使用 Skype for Business Web App 加入会议。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-163">If you do not use it, external users will continue to join meetings using Skype for Business Web App.</span></span>

### <a name="enable-simplified-meeting-join-and-skype-meetings-app"></a><span data-ttu-id="cf7a3-164">启用简化的会议加入和 Skype 会议应用</span><span class="sxs-lookup"><span data-stu-id="cf7a3-164">Enable simplified meeting join and Skype Meetings App</span></span>

1. <span data-ttu-id="cf7a3-165">当你启用对内容交付网络 (CDN) 的访问权限时，用户将能够在 Windows) 和 Mac) 上的 Skype for Business (上联机连接到 CDN 和获取 Skype 会议应用 (，并且将使用简化的会议加入体验。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-165">When you enable access to the Content Delivery Network (CDN), users will have the ability to connect to CDN online and get Skype Meetings App (on Windows) and Skype for Business for Mac (on Mac), and will use the simplified meeting join experience.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxUseCdn $True
   ```

2. <span data-ttu-id="cf7a3-166">允许将来自与会网页或 Skype 会议应用的客户端日志记录遥测发送到 Microsoft 服务器， (命令默认为 false) 。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-166">Allow client side logging telemetry from the meeting join web page or the Skype Meetings App to be sent to Microsoft servers (the command defaults to false).</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -MeetingUxEnableTelemetry $True
   ```

    <span data-ttu-id="cf7a3-167">发送给 Microsoft 的信息严格遵循 [Skype for Business 数据收集实践](/skypeforbusiness/legal-and-regulatory/data-collection-practices)。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-167">Information sent to Microsoft is in strict compliance with [Skype for Business data collection practices](/skypeforbusiness/legal-and-regulatory/data-collection-practices).</span></span>

3. <span data-ttu-id="cf7a3-168">设置回退到本地托管的 Skype for Business Web App 体验（如果 CDN 不可用）前的超时。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-168">Set the timeout before fall back to the locally hosted Skype for Business Web App experience if CDN isn't available.</span></span> <span data-ttu-id="cf7a3-169">默认值为 6 秒。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-169">The default value is 6 seconds.</span></span> <span data-ttu-id="cf7a3-170">如果此值设置为 0，则没有超时。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-170">If this value is set to 0, there will be no timeout.</span></span>

   ```powershell
   Set-CsWebServiceConfiguration -JoinLauncherCdnTimeout (New-TimeSpan -Seconds 10)
   ```

> [!NOTE]
> <span data-ttu-id="cf7a3-171">对于 Skype for Business Server 2015 累积更新 5 中的 MeetingUxUseCdn，默认值设置为 False。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-171">With MeetingUxUseCdn in Skype for Business Server 2015 Cumulative Update 5, the default value is set to False.</span></span> <span data-ttu-id="cf7a3-172">这会导致 Skype for Business for Mac 客户端无法以来宾身份加入非联盟伙伴的会议的问题，即使 Skype for Business 管理员将 MeetingUxUseCdn 设置为 True 也是如此。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-172">This causes an issue where Skype for Business for Mac client is unable to join non-federated partners' meetings as a guest, even if Skype for Business Admin has set MeetingUxUseCdn to True.</span></span> <span data-ttu-id="cf7a3-173">为此，Skype for Business Server 2015 必须具有累积更新 7、6.0.9319.534 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-173">For this to work, Skype for Business Server 2015 must have the Cumulative Update 7, 6.0.9319.534, or later.</span></span> <span data-ttu-id="cf7a3-174">请参阅 [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312)。</span><span class="sxs-lookup"><span data-stu-id="cf7a3-174">See [Enable Skype Meetings App to replace Skype for Business Web App in Skype for Business Server 2015](https://support.microsoft.com/kb/4132312).</span></span>


## <a name="see-also"></a><span data-ttu-id="cf7a3-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="cf7a3-175">See also</span></span>
<span data-ttu-id="cf7a3-176"><a name="SMA_Enable"> </a></span><span class="sxs-lookup"><span data-stu-id="cf7a3-176"><a name="SMA_Enable"> </a></span></span>

[<span data-ttu-id="cf7a3-177">Plan for Meetings clients (Web App and Meetings App) </span><span class="sxs-lookup"><span data-stu-id="cf7a3-177">Plan for Meetings clients (Web App and Meetings App)</span></span>](../../plan-your-deployment/clients-and-devices/meetings-clients.md)

[<span data-ttu-id="cf7a3-178">在 Skype for Business Server 中配置与会页面</span><span class="sxs-lookup"><span data-stu-id="cf7a3-178">Configure the meeting join page in Skype for Business Server</span></span>](../../manage/conferencing/meeting-join-page.md)

[<span data-ttu-id="cf7a3-179">Microsoft Online Services 隐私声明</span><span class="sxs-lookup"><span data-stu-id="cf7a3-179">Microsoft Online Services Privacy Statement</span></span>](https://www.microsoft.com/privacystatement/OnlineServices/Default.aspx)

[<span data-ttu-id="cf7a3-180">许可条款和文档</span><span class="sxs-lookup"><span data-stu-id="cf7a3-180">Licensing Terms and Documentation</span></span>](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;amp;DocumentTypeId=31)