---
title: Lync Server 2013：部署 Lync Windows 应用商店应用
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Windows Store app
ms:assetid: 9e00aaf4-15f9-4356-9ed7-5a58a2bfa043
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ822971(v=OCS.15)
ms:contentKeyID: 50117635
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4e2abe30cd464b223523df9d5fa878607404f7a3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050664"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-windows-store-app-in-lync-server-2013"></a><span data-ttu-id="d6eee-102">在 Lync Server 2013 中部署 Lync Windows 应用商店应用</span><span class="sxs-lookup"><span data-stu-id="d6eee-102">Deploying Lync Windows Store app in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d6eee-103">_**上次修改的主题：** 2013-12-03_</span><span class="sxs-lookup"><span data-stu-id="d6eee-103">_**Topic Last Modified:** 2013-12-03_</span></span>

<span data-ttu-id="d6eee-104">在使 Lync Windows 应用商店应用程序可供用户使用之前，请确保您的部署满足[Lync Server 2013 的 Lync windows 应用商店应用要求](lync-server-2013-lync-windows-store-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="d6eee-104">Before making Lync Windows Store app available to users, make sure that your deployment meets the [Lync Windows Store app requirements for Lync Server 2013](lync-server-2013-lync-windows-store-app-requirements.md).</span></span> <span data-ttu-id="d6eee-105">有关配置 Lync Server 2013 以支持 Lync Windows 应用商店应用的详细信息，请参阅 NextHop 博客文章： "Lync Server 自动发现和 Lync Windows 应用商店应用[http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966)"，网址为。</span><span class="sxs-lookup"><span data-stu-id="d6eee-105">For details about configuring Lync Server 2013 to support Lync Windows Store app, see the NextHop Blog article, "Lync Server Autodiscover and the Lync Windows Store App," at [http://go.microsoft.com/fwlink/?LinkId=271966](http://go.microsoft.com/fwlink/?linkid=271966).</span></span> <span data-ttu-id="d6eee-106">正确配置服务器环境后，可以通过搜索 "Lync" 引导用户从 Windows 应用商店下载 Lync 应用。</span><span class="sxs-lookup"><span data-stu-id="d6eee-106">After your server environment is configured correctly, you can direct users to download the Lync app from the Windows Store by searching for "Lync."</span></span>

<div>

## <a name="enabling-multi-factor-authentication-for-lync-windows-store-app"></a><span data-ttu-id="d6eee-107">为 Lync Windows 应用商店应用启用多重身份验证</span><span class="sxs-lookup"><span data-stu-id="d6eee-107">Enabling Multi-Factor Authentication for Lync Windows Store app</span></span>

<span data-ttu-id="d6eee-108">Lync Server 2013 的累积更新：六月2013为 Lync Windows 应用商店应用程序客户端添加对多重身份验证的支持。</span><span class="sxs-lookup"><span data-stu-id="d6eee-108">Cumulative Updates for Lync Server 2013: June 2013 adds support for multi-factor authentication for Lync Windows Store app clients.</span></span> <span data-ttu-id="d6eee-109">除了用户名和密码之外，还可以要求其他身份验证方法（如智能卡或 Pin），以便在外部用户登录 Lync 会议时对其进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d6eee-109">In addition to user name and password, you can require additional authentication methods, such as smart cards or PINs, to authenticate external users when they sign in to Lync meetings.</span></span> <span data-ttu-id="d6eee-110">若要启用多重身份验证，请在 Lync Server 2013 中部署 Active Directory 联合身份验证服务（AD FS）联合服务器并启用被动身份验证。</span><span class="sxs-lookup"><span data-stu-id="d6eee-110">To enable multi-factor authentication, you deploy Active Directory Federation Service (AD FS) federation server and enable passive authentication in Lync Server 2013.</span></span> <span data-ttu-id="d6eee-111">配置 AD FS 后，尝试加入 Lync 会议的外部用户将显示一条 AD FS 多重身份验证网页，其中包含用户名和密码质询以及已配置的任何其他身份验证方法.</span><span class="sxs-lookup"><span data-stu-id="d6eee-111">After AD FS is configured, external users who attempt to join Lync meetings are presented with an AD FS multi-factor authentication webpage that contains the user name and password challenge along with any additional authentication methods that you have configured.</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="d6eee-112">如果您计划为 Lync Windows 应用商店应用程序配置针对多重身份验证的 AD FS，请务必考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="d6eee-112">The following are important considerations if you plan to configure AD FS for multi-factor authentication for Lync Windows Store app:</span></span> 
> <UL>
> <LI>
> <P><span data-ttu-id="d6eee-113">Lync Server 2013 （包含适用于 Lync Server 2013 的累积更新：至少需要6月2013）。</span><span class="sxs-lookup"><span data-stu-id="d6eee-113">Lync Server 2013 with Cumulative Updates for Lync Server 2013: June 2013 is required at a minimum.</span></span> <span data-ttu-id="d6eee-114">Lync 2013 桌面客户端不需要 Lync Server 2013 的累积更新：6月2013，因此可能会出现被动身份验证，因为 Lync 2013 客户端能够进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="d6eee-114">Lync 2013 desktop clients do not require Cumulative Updates for Lync Server 2013: June 2013, so it might appear that passive authentication is working because Lync 2013 clients are able to authenticate.</span></span> <span data-ttu-id="d6eee-115">但是，Lync Windows 应用商店应用程序客户端的身份验证过程将无法完成，并且不会显示任何通知或错误消息。</span><span class="sxs-lookup"><span data-stu-id="d6eee-115">However, the authentication process for Lync Windows Store app clients will fail to complete and no notification or error message will display.</span></span></P>
> <LI>
> <P><span data-ttu-id="d6eee-116">必须配置服务器，以便被动身份验证是提供的唯一身份验证类型。</span><span class="sxs-lookup"><span data-stu-id="d6eee-116">The server must be configured so that passive authentication is the only authentication type offered.</span></span></P>
> <LI>
> <P><span data-ttu-id="d6eee-117">如果使用硬件负载平衡器，请在负载平衡器上启用 cookie 持久性，以便来自 Lync Windows 应用商店应用程序客户端的所有请求均由同一前端服务器处理。</span><span class="sxs-lookup"><span data-stu-id="d6eee-117">If you use hardware load balancers, enable cookie persistence on the load balancers so that all requests from the Lync Windows Store app client are handled by the same Front End Server.</span></span></P>
> <LI>
> <P><span data-ttu-id="d6eee-118">当您在 Lync Server 和 AD FS 服务器之间建立信赖方信任时，请分配足够长的令牌有效期，以跨越 Lync 会议的最大长度。</span><span class="sxs-lookup"><span data-stu-id="d6eee-118">When you establish a relying party trust between Lync Server and AD FS servers, assign a token life that is long enough to span the maximum length of your Lync meetings.</span></span> <span data-ttu-id="d6eee-119">通常情况下，令牌寿命为240分钟就足够了。</span><span class="sxs-lookup"><span data-stu-id="d6eee-119">Typically, a token life of 240 minutes is sufficient.</span></span></P></LI></UL>



</div>

<span data-ttu-id="d6eee-120">**配置多重身份验证**</span><span class="sxs-lookup"><span data-stu-id="d6eee-120">**To Configure Multi-Factor Authentication**</span></span>

1.  <span data-ttu-id="d6eee-121">安装 AD FS 联合服务器角色。</span><span class="sxs-lookup"><span data-stu-id="d6eee-121">Install an AD FS federation server role.</span></span> <span data-ttu-id="d6eee-122">有关详细信息，请参阅《 Active Directory 联合身份验证服务<http://go.microsoft.com/fwlink/p/?linkid=267511>2.0 部署指南》。</span><span class="sxs-lookup"><span data-stu-id="d6eee-122">For details, see the Active Directory Federation Services 2.0 Deployment Guide at <http://go.microsoft.com/fwlink/p/?linkid=267511>.</span></span>

2.  <span data-ttu-id="d6eee-123">为 AD FS 创建证书。</span><span class="sxs-lookup"><span data-stu-id="d6eee-123">Create certificates for AD FS.</span></span> <span data-ttu-id="d6eee-124">有关详细信息，请参阅的规划和部署 AD FS 的 "联合服务器证书" 一节，其中的单一登录主题可供使用[http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376)。</span><span class="sxs-lookup"><span data-stu-id="d6eee-124">For more information, see the "Federation server certificates" section of the Plan for and deploy AD FS for use with single sign-on topic at [http://go.microsoft.com/fwlink/p/?LinkId=285376](http://go.microsoft.com/fwlink/p/?linkid=285376).</span></span>

3.  <span data-ttu-id="d6eee-125">从 Windows PowerShell 命令行界面中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d6eee-125">From the Windows PowerShell command-line interface, run the following command:</span></span>
    ```powershell
    add-pssnapin Microsoft.Adfs.powershell
    ```
4.  <span data-ttu-id="d6eee-126">通过运行以下命令建立合作关系：</span><span class="sxs-lookup"><span data-stu-id="d6eee-126">Establish a partnership by running the following command:</span></span>
    ```powershell
    Add-ADFSRelyingPartyTrust -Name ContosoApp -MetadataURL https://lyncpool.contoso.com/passiveauth/federationmetadata/2007-06/federationmetadata.xml
    ```
5.  <span data-ttu-id="d6eee-127">设置以下信赖方规则：</span><span class="sxs-lookup"><span data-stu-id="d6eee-127">Set the following relying party rules:</span></span>
    
       ```powershell
        $IssuanceAuthorizationRules = '@RuleTemplate = "AllowAllAuthzRule" => issue(Type = "http://schemas.contoso.com/authorization/claims/permit", Value = "true");'$IssuanceTransformRules = '@RuleTemplate = "PassThroughClaims" @RuleName = "Sid" c:[Type == "http://schemas.contoso.com/ws/2008/06/identity/claims/primarysid"]=> issue(claim = c);'
       ```
    
       ```powershell
        Set-ADFSRelyingPartyTrust -TargetName ContosoApp -IssuanceAuthorizationRules $IssuanceAuthorizationRules -IssuanceTransformRules $IssuanceTransformRules
       ```
    
       ```powershell
        Set-CsWebServiceConfiguration -UseWsFedPassiveAuth $true -WsFedPassiveMetadataUri https://dc.contoso.com/federationmetadata/2007-06/federationmetadata.xml
       ```

</div>

<div>

## <a name="known-issues-that-can-prevent-sign-in"></a><span data-ttu-id="d6eee-128">可阻止登录的已知问题</span><span class="sxs-lookup"><span data-stu-id="d6eee-128">Known Issues that Can Prevent Sign-in</span></span>

<div>

## <a name="the-time-and-date-are-not-set-accurately-on-the-device-running-lync-windows-store-app"></a><span data-ttu-id="d6eee-129">在运行 Lync Windows 应用商店应用的设备上未准确设置时间和日期</span><span class="sxs-lookup"><span data-stu-id="d6eee-129">The time and date are not set accurately on the device running Lync Windows Store app</span></span>

<span data-ttu-id="d6eee-130">设备上的 "时间" 设置必须与服务器上的 "时间" 设置同步。</span><span class="sxs-lookup"><span data-stu-id="d6eee-130">The time setting on the device must be synchronized with the time setting on the server.</span></span> <span data-ttu-id="d6eee-131">对于 Microsoft Surface 等设备以及其他运行 Windows RT 且未加入域的设备来说，这一点尤其重要。</span><span class="sxs-lookup"><span data-stu-id="d6eee-131">This is particularly important for devices such as Microsoft Surface, and other devices running Windows RT that are not joined to a domain.</span></span> <span data-ttu-id="d6eee-132">若要从时间服务器自动设置这些设备上的时间，请从设备上提升的命令提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d6eee-132">To set the time on these devices automatically from a time server, run the following command from an elevated command prompt on the device:</span></span>
```console
w32tm /resync
```
</div>

<div>

## <a name="lync-windows-store-app-cannot-access-the-lync-server-or-services"></a><span data-ttu-id="d6eee-133">Lync Windows 应用商店应用无法访问 Lync 服务器或服务</span><span class="sxs-lookup"><span data-stu-id="d6eee-133">Lync Windows Store app cannot access the Lync server or services</span></span>

<span data-ttu-id="d6eee-134">Lync Windows 应用商店应用可能无法通过网络适配器（如 4G LTE USB 调制解调器）访问 Lync server 或服务，而不能在 Windows 8 中注册为物理设备。</span><span class="sxs-lookup"><span data-stu-id="d6eee-134">Lync Windows Store app may not be able to access the Lync server or services through network adapters, such as 4G LTE USB modems, that do not register with Windows 8 as physical devices.</span></span> <span data-ttu-id="d6eee-135">即使桌面应用程序和浏览器能够访问其他服务器和网站，Lync Windows 应用商店应用也可能会遇到此问题。</span><span class="sxs-lookup"><span data-stu-id="d6eee-135">Lync Windows Store app may have this issue even when the desktop apps and browsers are able to access other servers and web sites.</span></span>

</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-with-lync-server-2010-and-office-communications-server-2007-r2-edge-server"></a><span data-ttu-id="d6eee-136">Lync Windows 应用商店应用无法使用 Lync Server 2010 和 Office 通信服务器 2007 R2 Edge 服务器进行登录</span><span class="sxs-lookup"><span data-stu-id="d6eee-136">Lync Windows Store app cannot sign in with Lync Server 2010 and Office Communications Server 2007 R2 Edge Server</span></span>

<span data-ttu-id="d6eee-137">如果您的拓扑由 Lync Server 2010 与 Office 通信服务器 2007 R2 Edge 服务器组成，则需要运行 Lync Server 2010 累积更新中提供的更新版本的拓扑生成器：七月2013。</span><span class="sxs-lookup"><span data-stu-id="d6eee-137">If your topology consists of Lync Server 2010 with Office Communications Server 2007 R2 Edge Server, you will need to run the updated version of Topology Builder available in the cumulative update for Lync Server 2010: July 2013.</span></span> <span data-ttu-id="d6eee-138">早期版本的拓扑生成器不会创建 Office 通信服务器2007边缘服务器所需的映射，因此 Lync Windows 应用商店应用客户端无法登录。</span><span class="sxs-lookup"><span data-stu-id="d6eee-138">Earlier versions of Topology Builder do not create the required mapping to Office Communications Server 2007 Edge Server, so Lync Windows Store app clients are unable to sign in.</span></span> <span data-ttu-id="d6eee-139">以下步骤是必需的：</span><span class="sxs-lookup"><span data-stu-id="d6eee-139">The following steps are required:</span></span>

1.  <span data-ttu-id="d6eee-140">在 Lync Server 2010 池和 Lync Server 2010 控制器上安装 Lync Server 2010 的累积更新：7月2013日。</span><span class="sxs-lookup"><span data-stu-id="d6eee-140">Install the cumulative update for Lync Server 2010: July 2013 on Lync Server 2010 pools and Lync Server 2010 Directors.</span></span>

2.  <span data-ttu-id="d6eee-141">通过执行以下操作，更新 Lync 自动发现配置，以指示外部 SIP 入口点为边缘服务器地址：</span><span class="sxs-lookup"><span data-stu-id="d6eee-141">Update the Lync AutoDiscover configuration to indicate that the external SIP entry point is the Edge server address by doing the following:</span></span>
    
    1.  <span data-ttu-id="d6eee-142">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="d6eee-142">Open Lync Server Management Shell.</span></span>
    
    2.  <span data-ttu-id="d6eee-143">运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d6eee-143">Run the following command:</span></span>
        ```powershell
        Set-CsAutodiscoverConfiguration -ExternalSipClientAccessFqdn <FQDN of server used for external client access> -ExternalSipClientAccessPort 443
        ```
</div>

<div>

## <a name="lync-windows-store-app-cannot-sign-in-due-to-a-certificate-name-validation-failure"></a><span data-ttu-id="d6eee-144">由于证书名称验证失败，Lync Windows 应用商店应用无法登录</span><span class="sxs-lookup"><span data-stu-id="d6eee-144">Lync Windows Store App cannot sign in due to a certificate name validation failure</span></span>

<span data-ttu-id="d6eee-145">未运行最新版本的 Lync Windows 应用商店应用程序的 Office 365 用户可能会发生登录问题。</span><span class="sxs-lookup"><span data-stu-id="d6eee-145">A sign-in issue can occur for Office 365 users who are not running the latest version of Lync Windows Store app.</span></span> <span data-ttu-id="d6eee-146">此问题通常发生在使用多个域（例如，SIP URI 为**userA@domainZ.com** ，但边缘服务器为**sip.domainX.com**）时。</span><span class="sxs-lookup"><span data-stu-id="d6eee-146">This issue generally occurs when using multiple domains (for example, when the SIP URI is **userA@domainZ.com** but the Edge Server is **sip.domainX.com**).</span></span> <span data-ttu-id="d6eee-147">若要解决此问题，用户应安装最新版本的 Lync Windows 应用商店应用，这也需要 Windows 8.1。</span><span class="sxs-lookup"><span data-stu-id="d6eee-147">To fix the issue, users should install the latest version of Lync Windows Store app, which also requires Windows 8.1.</span></span>

</div>

</div>

<div>

## <a name="use-lync-windows-store-app-logs-to-troubleshoot-issues"></a><span data-ttu-id="d6eee-148">使用 Lync Windows 应用商店应用日志解决问题</span><span class="sxs-lookup"><span data-stu-id="d6eee-148">Use Lync Windows Store app logs to troubleshoot issues</span></span>

<span data-ttu-id="d6eee-149">您可以使用设备上生成的日志来解决问题。</span><span class="sxs-lookup"><span data-stu-id="d6eee-149">You can use the logs generated on the device to troubleshoot issues.</span></span> <span data-ttu-id="d6eee-150">日志存储在以下文件夹中：</span><span class="sxs-lookup"><span data-stu-id="d6eee-150">The logs are stored in the following folder:</span></span>

<span data-ttu-id="d6eee-151">% LocalAppData%\\程序包\\LyncMX\_8wekyb3d8bbwe\\LocalState\\跟踪</span><span class="sxs-lookup"><span data-stu-id="d6eee-151">%LocalAppData%\\Packages\\Microsoft.LyncMX\_8wekyb3d8bbwe\\LocalState\\Tracing</span></span>

<span data-ttu-id="d6eee-152">在从用户获取日志之前，请确保已启用日志记录，然后要求用户保存日志，以便存储在内存中的所有信息也保存在硬盘上的文件中。</span><span class="sxs-lookup"><span data-stu-id="d6eee-152">Before you get the logs from a user, make sure that logging is turned on, and then ask the user to save the logs so that all the information stored in memory is also saved to files on the hard drive.</span></span>

<span data-ttu-id="d6eee-153">**启用日志记录**</span><span class="sxs-lookup"><span data-stu-id="d6eee-153">**To turn on logging**</span></span>

1.  <span data-ttu-id="d6eee-154">在设备上打开 Lync Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="d6eee-154">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="d6eee-155">从屏幕右侧轻扫。</span><span class="sxs-lookup"><span data-stu-id="d6eee-155">Swipe from the right side of the screen.</span></span> <span data-ttu-id="d6eee-156">如果使用的是鼠标，请指向屏幕右上角，然后将鼠标指针在屏幕上向下移动。</span><span class="sxs-lookup"><span data-stu-id="d6eee-156">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

3.  <span data-ttu-id="d6eee-157">选择 "**设置**"，选择 "**选项**"，然后将 "**诊断日志**" 设置为 **"打开"**。</span><span class="sxs-lookup"><span data-stu-id="d6eee-157">Select **Settings**, select **Options**, and then set **Diagnostic Logs** to **On**.</span></span>

4.  <span data-ttu-id="d6eee-158">如果以前的**诊断日志**已关闭，则必须重新启动 Lync。</span><span class="sxs-lookup"><span data-stu-id="d6eee-158">If **Diagnostic Logs** was off previously, you must restart Lync.</span></span> <span data-ttu-id="d6eee-159">若要重新启动 Lync，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="d6eee-159">To restart Lync, do one of the following:</span></span>
    
      - <span data-ttu-id="d6eee-160">重新启动设备。</span><span class="sxs-lookup"><span data-stu-id="d6eee-160">Restart the device.</span></span>
    
      - <span data-ttu-id="d6eee-161">结束 Lync 任务并再次启动应用程序。</span><span class="sxs-lookup"><span data-stu-id="d6eee-161">End the Lync task and launch the app again.</span></span> <span data-ttu-id="d6eee-162">若要结束任务，请打开 Windows 任务管理器，选择 " **Lync**"，然后点击 "**结束任务**"。</span><span class="sxs-lookup"><span data-stu-id="d6eee-162">To end the task, open the Windows Task Manager, select **Lync**, and then tap **End task**.</span></span> <span data-ttu-id="d6eee-163">如果未列出 Lync，请点击 "**更多详细信息**"，并在 "**后台流程**" 下查找 Lync。</span><span class="sxs-lookup"><span data-stu-id="d6eee-163">If Lync is not listed, tap **More details** and look for Lync under **Background processes**.</span></span>

<span data-ttu-id="d6eee-164">**保存日志**</span><span class="sxs-lookup"><span data-stu-id="d6eee-164">**To save the logs**</span></span>

1.  <span data-ttu-id="d6eee-165">在设备上打开 Lync Windows 应用商店应用。</span><span class="sxs-lookup"><span data-stu-id="d6eee-165">Open Lync Windows Store app on the device.</span></span>

2.  <span data-ttu-id="d6eee-166">尝试登录。</span><span class="sxs-lookup"><span data-stu-id="d6eee-166">Try signing in.</span></span>

3.  <span data-ttu-id="d6eee-167">从屏幕右侧轻扫。</span><span class="sxs-lookup"><span data-stu-id="d6eee-167">Swipe from the right side of the screen.</span></span> <span data-ttu-id="d6eee-168">如果使用的是鼠标，请指向屏幕右上角，然后将鼠标指针在屏幕上向下移动。</span><span class="sxs-lookup"><span data-stu-id="d6eee-168">If you’re using a mouse, point to the upper-right corner of the screen and then move the mouse pointer down the screen.</span></span>

4.  <span data-ttu-id="d6eee-169">选择 "**设置**"，选择 "**关于**"，然后选择 "**保存日志**"。</span><span class="sxs-lookup"><span data-stu-id="d6eee-169">Select **Settings**, select **About**, and then select **Save logs**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

