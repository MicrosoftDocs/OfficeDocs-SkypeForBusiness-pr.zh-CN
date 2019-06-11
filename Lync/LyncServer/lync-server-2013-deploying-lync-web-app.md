---
title: 'Lync Server 2013: 部署 Lync Web App'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deploying Lync Web App
ms:assetid: b6301e98-051c-4e4b-8e10-ec922a8f508a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205190(v=OCS.15)
ms:contentKeyID: 48185189
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ca2a0d2da0b10b8e60df8489b8cc0a584cd70e3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830543"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-web-app-in-lync-server-2013"></a><span data-ttu-id="6cad3-102">在 Lync Server 2013 中部署 Lync Web App</span><span class="sxs-lookup"><span data-stu-id="6cad3-102">Deploying Lync Web App in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6cad3-103">_**主题上次修改时间:** 2013-07-18_</span><span class="sxs-lookup"><span data-stu-id="6cad3-103">_**Topic Last Modified:** 2013-07-18_</span></span>

<span data-ttu-id="6cad3-104">Lync Web App 是使用 Lync Server 2013 安装的 Internet Information Services (IIS) Web 客户端, 默认情况下处于启用状态。</span><span class="sxs-lookup"><span data-stu-id="6cad3-104">Lync Web App is an Internet Information Services (IIS) web client that installs with Lync Server 2013 and is enabled by default.</span></span> <span data-ttu-id="6cad3-105">无需额外步骤即可在服务器上启用 Lync Web App 或将 Web 客户端部署到用户。</span><span class="sxs-lookup"><span data-stu-id="6cad3-105">No additional steps are necessary to either enable Lync Web App on the server or deploy the web client to users.</span></span> <span data-ttu-id="6cad3-106">当用户单击会议 URL 但未安装 Lync 2013 客户端时, 将向用户显示通过使用最新版本的 Lync Web App 加入会议的选项。</span><span class="sxs-lookup"><span data-stu-id="6cad3-106">Whenever a user clicks a meeting URL but does not have the Lync 2013 client installed, the user is presented with the option to join the meeting by using the latest version of Lync Web App.</span></span>

<span data-ttu-id="6cad3-107">Lync Web App 中的语音、视频和共享功能需要 Microsoft ActiveX 控件。</span><span class="sxs-lookup"><span data-stu-id="6cad3-107">The voice, video, and sharing features in Lync Web App require a Microsoft ActiveX control.</span></span> <span data-ttu-id="6cad3-108">你可以提前安装 ActiveX 控件, 或允许用户在出现提示时安装该控件, 这会在首次使用 Lync Web App 时或首次访问需要 ActiveX 控件的功能时进行安装。</span><span class="sxs-lookup"><span data-stu-id="6cad3-108">You can either install the ActiveX control in advance or allow users to install it when prompted, which happens the first time they use Lync Web App or the first time they access a feature that requires the ActiveX control.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="6cad3-109">在 Lync Server 2013 Edge 服务器部署中, Lync Web App 客户端访问需要在外围网络中使用 HTTPS 反向代理。</span><span class="sxs-lookup"><span data-stu-id="6cad3-109">In Lync Server 2013 Edge Server deployments, an HTTPS reverse proxy in the perimeter network is required for Lync Web App client access.</span></span> <span data-ttu-id="6cad3-110">你还必须发布简单的 URL。</span><span class="sxs-lookup"><span data-stu-id="6cad3-110">You must also publish simple URLs.</span></span> <span data-ttu-id="6cad3-111">有关详细信息, 请参阅为<A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Lync server 2013 设置反向代理服务器</A>和<A href="lync-server-2013-planning-for-simple-urls.md">在 Lync Server 2013 中规划简单 url</A>。</span><span class="sxs-lookup"><span data-stu-id="6cad3-111">For details, see <A href="lync-server-2013-setting-up-reverse-proxy-servers.md">Setting up reverse proxy servers for Lync Server 2013</A> and <A href="lync-server-2013-planning-for-simple-urls.md">Planning for simple URLs in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-web-app"></a><span data-ttu-id="6cad3-112">为 Lync Web App 启用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="6cad3-112">Enabling Multi-Factor Authentication for Lync Web App</span></span>

<span data-ttu-id="6cad3-113">Lync Server 2013 版本的 Lync Web App 支持多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="6cad3-113">The Lync Server 2013 version of Lync Web App supports multi-factor authentication.</span></span> <span data-ttu-id="6cad3-114">除了用户名和密码之外, 你还可以要求其他身份验证方法 (如智能卡或 Pin) 对从外部网络登录到 Lync 会议的用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="6cad3-114">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate users who are joining from external networks when they sign in to Lync meetings.</span></span> <span data-ttu-id="6cad3-115">你可以通过在 Lync Server 2013 中部署 Active Directory 联合身份验证服务 (AD FS) 联合服务器并启用被动身份验证来启用多因素身份验证。</span><span class="sxs-lookup"><span data-stu-id="6cad3-115">You can enable multi-factor authentication by deploying Active Directory Federation Service (AD FS) federation server and enabling passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="6cad3-116">配置广告 FS 后, 尝试加入 Lync 会议的外部用户将显示一个广告 FS 多重身份验证网页, 其中包含用户名和密码质询以及已配置的任何其他身份验证方法。.</span><span class="sxs-lookup"><span data-stu-id="6cad3-116">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="6cad3-117">如果您计划配置 AD FS 以进行多重身份验证，则以下是一些重要注意事项：</span><span class="sxs-lookup"><span data-stu-id="6cad3-117">The following are important considerations if you plan to configure AD FS for multi-factor authentication:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="6cad3-p105">如果会议参加者和组织者位于同一组织中或都来自 AD FS 联盟组织，则 ADFS 多重身份验证生效。ADFS 多重身份验证不适用于 Lync 联盟用户，因为 Lync 服务器 Web 基础结构当前不支持该验证方法。</span><span class="sxs-lookup"><span data-stu-id="6cad3-p105">Multi-factor ADFS authentication works if the meeting participant and organizer are both in the same organization or are both from an AD FS federated organization. Multi-factor ADFS authentication does not work for Lync federated users because the Lync server web infrastructure does not currently support it.</span></span></P>
> <LI>
> <P><span data-ttu-id="6cad3-120">如果使用硬件负载平衡器, 请在负载平衡器上启用 cookie 持久性, 以便来自 Lync Web App 客户端的所有请求都由同一前端服务器处理。</span><span class="sxs-lookup"><span data-stu-id="6cad3-120">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Web App client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="6cad3-121">当您在 Lync Server 和 AD FS 服务器之间建立信赖方信任时, 请分配足够长的令牌有效期以使您的 Lync 会议的最大长度更长。</span><span class="sxs-lookup"><span data-stu-id="6cad3-121">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="6cad3-122">通常，240 分钟的令牌使用时间就足够了。</span><span class="sxs-lookup"><span data-stu-id="6cad3-122">Typically, a token life of 240 minutes is sufficient.</span></span></P>
> <LI>
> <P><span data-ttu-id="6cad3-123">此配置不适用于 Lync 移动客户端。</span><span class="sxs-lookup"><span data-stu-id="6cad3-123">This configuration does not apply to Lync mobile clients.</span></span></P></LI></UL>



</div>

<span data-ttu-id="6cad3-124">**配置多因素身份验证**</span><span class="sxs-lookup"><span data-stu-id="6cad3-124">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="6cad3-125">安装 AD FS 联盟服务器角色。</span><span class="sxs-lookup"><span data-stu-id="6cad3-125">Install an AD FS federation server role.</span></span> <span data-ttu-id="6cad3-126">有关详细信息, 请参阅 Active Directory 联合身份验证服务2.0 部署指南, 网址为<http://go.microsoft.com/fwlink/p/?linkid=267511></span><span class="sxs-lookup"><span data-stu-id="6cad3-126">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511></span></span>

2.  <span data-ttu-id="6cad3-127">为 AD FS 创建证书。</span><span class="sxs-lookup"><span data-stu-id="6cad3-127">Create certificates for AD FS.</span></span> <span data-ttu-id="6cad3-128">有关详细信息, 请参阅用于的计划和部署 AD FS 的 "联合身份验证服务器证书" 部分以与的单一登录主题配合[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)使用。</span><span class="sxs-lookup"><span data-stu-id="6cad3-128">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="6cad3-129">从 Windows PowerShell 命令行界面中, 运行以下命令:</span><span class="sxs-lookup"><span data-stu-id="6cad3-129">From the Windows PowerShell command-line interface, run the following command:</span></span>
    
        add-pssnapin Microsoft.Adfs.powershell

4.  <span data-ttu-id="6cad3-130">通过运行以下命令来建立合作关系：</span><span class="sxs-lookup"><span data-stu-id="6cad3-130">Establish a partnership by running the following command:</span></span>
    
        Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml

5.  <span data-ttu-id="6cad3-131">设置以下信赖方规则：</span><span class="sxs-lookup"><span data-stu-id="6cad3-131">Set the following relying party rules:</span></span>
    
       ```
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'
        $IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="branchcache-configuration"></a><span data-ttu-id="6cad3-132">BranchCache 配置</span><span class="sxs-lookup"><span data-stu-id="6cad3-132">BranchCache Configuration</span></span>

<span data-ttu-id="6cad3-133">Windows 7 和 Windows Server 2008 R2 中的 BranchCache 功能可能会干扰 Lync Web App web 组件。</span><span class="sxs-lookup"><span data-stu-id="6cad3-133">The BranchCache feature in Windows 7 and Windows Server 2008 R2 can interfere with Lync Web App web components.</span></span> <span data-ttu-id="6cad3-134">若要防止 Lync Web App 用户出现问题, 请确保未启用 "BranchCache"。</span><span class="sxs-lookup"><span data-stu-id="6cad3-134">To prevent issues for Lync Web App users, make sure that BranchCache is not enabled.</span></span>

<span data-ttu-id="6cad3-135">有关禁用 BranchCache 的详细信息, 请参阅 "BranchCache 部署指南", 该指南在 Windows Server 2008 R2 技术库[http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788)中的 Microsoft 下载中心和 HTML 格式的 Word 格式中均提供[http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789)。</span><span class="sxs-lookup"><span data-stu-id="6cad3-135">For details about disabling BranchCache, see the BranchCache Deployment Guide, which is available in Word format at the Microsoft Download Center at [http://go.microsoft.com/fwlink/p/?LinkId=268788](http://go.microsoft.com/fwlink/p/?linkid=268788) and in HTML format in the Windows Server 2008 R2 Technical Library at [http://go.microsoft.com/fwlink/p/?LinkId=268789](http://go.microsoft.com/fwlink/p/?linkid=268789).</span></span>

</div>

<div>

## <a name="verifying-lync-web-app-deployment"></a><span data-ttu-id="6cad3-136">验证 Lync Web App 部署</span><span class="sxs-lookup"><span data-stu-id="6cad3-136">Verifying Lync Web App Deployment</span></span>

<span data-ttu-id="6cad3-137">你可以使用 Test-CsUcwaConference cmdlet 来验证一对测试用户是否可以使用统一通信 Web API (UCWA) 参加会议。</span><span class="sxs-lookup"><span data-stu-id="6cad3-137">You can use the Test-CsUcwaConference cmdlet to verify that a pair of test users can participate in a conference using the Unified Communications Web API (UCWA).</span></span> <span data-ttu-id="6cad3-138">有关此 cmdlet 的详细信息, 请参阅 Lync Server Management Shell 文档中的[Test CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) 。</span><span class="sxs-lookup"><span data-stu-id="6cad3-138">For details about this cmdlet, see [Test-CsUcwaConference](https://docs.microsoft.com/powershell/module/skype/Test-CsUcwaConference) in the Lync Server Management Shell documentation.</span></span>

</div>

<div>

## <a name="troubleshooting-plug-in-installation-on-windows-server2008r2"></a><span data-ttu-id="6cad3-139">Windows Server 2008 R2 上的插件安装疑难解答</span><span class="sxs-lookup"><span data-stu-id="6cad3-139">Troubleshooting Plug-in Installation on Windows Server 2008 R2</span></span>

<span data-ttu-id="6cad3-140">如果在运行 Windows Server 2008 R2 的计算机上安装插件失败, 可能需要修改 Internet Explorer 安全设置或 DisableMSI 注册表项设置。</span><span class="sxs-lookup"><span data-stu-id="6cad3-140">If installation of the plug-in fails on a computer running Windows Server 2008 R2, you may need to modify the Internet Explorer security setting or the DisableMSI registry key setting.</span></span>

<span data-ttu-id="6cad3-141">**修改 Internet Explorer 中的安全设置**</span><span class="sxs-lookup"><span data-stu-id="6cad3-141">**To modify the security setting in Internet Explorer**</span></span>

1.  <span data-ttu-id="6cad3-142">打开 Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="6cad3-142">Open Internet Explorer.</span></span>

2.  <span data-ttu-id="6cad3-143">依次单击 **“工具”**、**“Internet 选项”** 和 **“高级”**。</span><span class="sxs-lookup"><span data-stu-id="6cad3-143">Click **Tools**, click **Internet Options**, and then click **Advanced**.</span></span>

3.  <span data-ttu-id="6cad3-144">向下滚动至 **“安全”** 部分。</span><span class="sxs-lookup"><span data-stu-id="6cad3-144">Scroll down to the **Security** section.</span></span>

4.  <span data-ttu-id="6cad3-145">清除 **“不将加密的页存盘”**，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="6cad3-145">Clear **Do not save encrypted pages to disk**, and then click **OK**.</span></span>
    
    <div class=" ">
    

    > [!NOTE]  
    > <span data-ttu-id="6cad3-146">如果选中此设置, 则当尝试从 Lync Web App 下载附件时, 此设置也会导致错误。</span><span class="sxs-lookup"><span data-stu-id="6cad3-146">If selected, this setting will also cause an error when trying to download an attachment from Lync Web App.</span></span>

    
    </div>

5.  <span data-ttu-id="6cad3-147">重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="6cad3-147">Rejoin the meeting.</span></span> <span data-ttu-id="6cad3-148">插件应该可以无误地下载。</span><span class="sxs-lookup"><span data-stu-id="6cad3-148">The plug-in should download without errors.</span></span>

<span data-ttu-id="6cad3-149">**修改 DisableMSI 注册表设置**</span><span class="sxs-lookup"><span data-stu-id="6cad3-149">**To modify the DisableMSI Registry setting**</span></span>

1.  <span data-ttu-id="6cad3-150">单击 **“开始”**，然后单击 **“运行”**。</span><span class="sxs-lookup"><span data-stu-id="6cad3-150">Click **Start**, and then click **Run**.</span></span>

2.  <span data-ttu-id="6cad3-151">要访问注册表编辑器，请键入 **regedit**。</span><span class="sxs-lookup"><span data-stu-id="6cad3-151">To access the Registry Editor, type **regedit**.</span></span>

3.  <span data-ttu-id="6cad3-152">导航到 HKEY\_本地\_计算机\\软件\\策略\\Microsoft\\Windows\\Installer。</span><span class="sxs-lookup"><span data-stu-id="6cad3-152">Navigate to HKEY\_LOCAL\_MACHINE\\Software\\Policies\\Microsoft\\Windows\\Installer.</span></span>

4.  <span data-ttu-id="6cad3-153">编辑或添加 "REG\_DWORD" 类型的 DisableMSI 注册表项, 并将其设置为 "0"。</span><span class="sxs-lookup"><span data-stu-id="6cad3-153">Edit or add the DisableMSI registry key of type REG\_DWORD and set it to 0.</span></span>

5.  <span data-ttu-id="6cad3-154">重新加入会议。</span><span class="sxs-lookup"><span data-stu-id="6cad3-154">Rejoin the meeting.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="6cad3-155">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6cad3-155">See Also</span></span>


[<span data-ttu-id="6cad3-156">在 Lync Server 2013 中配置与会页面</span><span class="sxs-lookup"><span data-stu-id="6cad3-156">Configuring the meeting join page in Lync Server 2013</span></span>](lync-server-2013-configuring-the-meeting-join-page.md)  
[<span data-ttu-id="6cad3-157">Lync Web App 支持的 Lync Server 2013 平台</span><span class="sxs-lookup"><span data-stu-id="6cad3-157">Lync Web App supported platforms for Lync Server 2013</span></span>](lync-server-2013-lync-web-app-supported-platforms.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

