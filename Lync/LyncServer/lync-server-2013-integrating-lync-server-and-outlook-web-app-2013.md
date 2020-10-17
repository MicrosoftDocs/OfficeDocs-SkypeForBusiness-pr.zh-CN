---
title: Lync Server 2013：集成 Lync Server 和 Outlook Web App 2013
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Integrating Lync Server 2013 and Outlook Web App 2013
ms:assetid: 513d4cc7-aa87-4f68-b99d-d58b63bdf242
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688055(v=OCS.15)
ms:contentKeyID: 49733649
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7f822afb4ba0f3dabfd133caf92a434eadac82fa
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48534751"
---
# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="457a0-102">集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="457a0-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="457a0-103">_**上次修改的主题：** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="457a0-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="457a0-104">除了与 Microsoft Outlook 2013 集成之外，Microsoft Lync Server 2013 还可以与 Microsoft Outlook Web App 2013 完全集成;此外，这将为 Outlook Web App 添加即时消息和状态，并使您的统一联系人列表在 Outlook Web App 和 Microsoft Lync 2013 之间共享。</span><span class="sxs-lookup"><span data-stu-id="457a0-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="457a0-105">为了集成 Lync Server 2013 和 Outlook Web App，您必须首先验证是否已在 Microsoft Exchange Server 2013 后端服务器中安装统一通信托管 API 4.0 运行时。</span><span class="sxs-lookup"><span data-stu-id="457a0-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="457a0-106">您可以通过查找是否存在以下注册表值来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="457a0-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="457a0-107">HKEY \_ LOCAL \_ MACHINE \\ SYSTEM \\ CurrentControlSet \\ Services \\ MSExchange OWA \\ InstantMessaging \\ ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="457a0-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="457a0-108">ImplementationDLLPath 应指向文件 Microsoft.Rtc.Internal.Ucweb.dll 的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="457a0-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="457a0-109">如果没有，或者如果注册表值不存在，则应从 Microsoft 下载中心下载并安装 UCMA 运行时安装程序 <https://www.microsoft.com/download/details.aspx?id=34992> 。</span><span class="sxs-lookup"><span data-stu-id="457a0-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <https://www.microsoft.com/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="457a0-110">有关如何安装 UCMA 运行时的信息，可以在同一网页上找到。</span><span class="sxs-lookup"><span data-stu-id="457a0-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="457a0-111">**向后兼容性**</span><span class="sxs-lookup"><span data-stu-id="457a0-111">**Backward Compatibility**</span></span>

<span data-ttu-id="457a0-112">Lync Server 2013 可以与统一消息和 Outlook Web App 的 Microsoft Exchange Server 2010 版本集成。</span><span class="sxs-lookup"><span data-stu-id="457a0-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="457a0-113">有关详细信息，请参阅部署本地 Exchange UM 以在中提供 Lync Server 2010 语音邮件一文 [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md) 。</span><span class="sxs-lookup"><span data-stu-id="457a0-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [https://technet.microsoft.com/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="457a0-114">如果与 Exchange 2010 集成，则不会具有 Lync Server 特定功能，例如统一联系人存储和 Lync 到 Exchange 存档。</span><span class="sxs-lookup"><span data-stu-id="457a0-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="457a0-115">Microsoft Lync 2013 还可以与 Exchange 2010 和 Outlook 2010 结合使用。</span><span class="sxs-lookup"><span data-stu-id="457a0-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="457a0-116">但同样，新功能（例如统一联系人存储和高分辨率照片）将不适用于 Lync 2013 用户。</span><span class="sxs-lookup"><span data-stu-id="457a0-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="457a0-117">这些新功能需要同时具有 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="457a0-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="457a0-118">**为 Outlook Web App 创建受信任的应用程序池**</span><span class="sxs-lookup"><span data-stu-id="457a0-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="457a0-119">如果已在同一台计算机上安装了 Microsoft Exchange 统一消息呼叫路由器服务和 Microsoft Exchange 统一消息服务，则无需为 Outlook Web App 创建受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="457a0-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="457a0-120"> (此示例假定有问题的服务器承载 SipName UM 拨号计划。 ) 如果您使用一台计算机来托管这两个服务，则可以跳到本文档中标题为 **"在 Outlook Web App 上启用即时消息**" 的部分。</span><span class="sxs-lookup"><span data-stu-id="457a0-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="457a0-121">Lync Server 2013 可以自动发现任何承载 SipName UM 拨号计划的 Exchange 服务器;这些服务器将自动添加到 "Lync Server 已知服务器" 列表中。</span><span class="sxs-lookup"><span data-stu-id="457a0-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="457a0-122">无需创建受信任的应用程序池，并将这些服务器添加到已知服务器列表中。</span><span class="sxs-lookup"><span data-stu-id="457a0-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="457a0-123">事实上，这样做会导致 Outlook Web App 集成停止工作。</span><span class="sxs-lookup"><span data-stu-id="457a0-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="457a0-124">这是因为 Lync Server 拓扑现在将为同一台计算机提供两个条目： autodiscovered 条目和手动添加的条目。</span><span class="sxs-lookup"><span data-stu-id="457a0-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="457a0-125">若要解决此问题，并再次使用 Outlook Web App，请使用 Windows PowerShell 删除服务器的受信任池和受信任的应用程序条目。</span><span class="sxs-lookup"><span data-stu-id="457a0-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="457a0-126">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">CsTrustedApplicationPool</A> 和 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">CsTrustedApplication</A> cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="457a0-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="457a0-127">如果这两个服务在单独的计算机上运行，则在确认已安装统一通信托管 API 4.0 运行时之后，必须创建一个与 Outlook Web App 关联的 Lync Server 受信任应用程序池和受信任的应用程序;将服务器添加到已知服务器列表中。</span><span class="sxs-lookup"><span data-stu-id="457a0-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="457a0-128">若要执行此操作，请首先在 Lync Server Management Shell 中运行与以下内容类似的命令：</span><span class="sxs-lookup"><span data-stu-id="457a0-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="457a0-129">在上面的命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 池的完全限定的域名;此名称必须与提供对 Outlook Web App 的访问权限的证书的 "使用者名称" 和 "主题替代名称" 字段中显示的名称相同（ (SAN) 字段）。</span><span class="sxs-lookup"><span data-stu-id="457a0-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="457a0-130">同样，atl-cs-001.litwareinc.com 是将承载新的受信任应用程序池的 Lync Server 2013 池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="457a0-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="457a0-131">请注意，指定的 site （Redmond）表示 Lync Server 网站的 SiteID。</span><span class="sxs-lookup"><span data-stu-id="457a0-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="457a0-132">SiteID 不一定与网站的 DisplayName 相同;您可以通过在 Lync Server 命令行管理程序中运行以下命令来检索您的 Lync Server 站点的 SiteIDs：</span><span class="sxs-lookup"><span data-stu-id="457a0-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="457a0-133">创建受信任的应用程序池后，请使用与以下内容类似的命令为 Outlook Web App 配置应用程序标识和端口：</span><span class="sxs-lookup"><span data-stu-id="457a0-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="457a0-134">在上面的命令中，ApplicationID 只是一个用于区分受信任应用程序的友好标识符。</span><span class="sxs-lookup"><span data-stu-id="457a0-134">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications.</span></span> <span data-ttu-id="457a0-135">ApplicationID 可以是任何不包含空格或其他禁止字符的文本字符串。</span><span class="sxs-lookup"><span data-stu-id="457a0-135">The ApplicationID can be any text string that does not include blank spaces or other prohibited characters.</span></span> <span data-ttu-id="457a0-136"> (若要确保创建有效的标识符，建议在指定 ApplicationId 时仅使用字母和数字。 ) 分配给 Port 参数的值也保留给管理员的决定：这可以是任何可用的网络端口。</span><span class="sxs-lookup"><span data-stu-id="457a0-136">(To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="457a0-137">在创建受信任的应用程序后，您必须运行以下命令来启用对 Lync Server 拓扑的更改：</span><span class="sxs-lookup"><span data-stu-id="457a0-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="457a0-138">请注意，还必须将 Exchange 客户端访问和邮箱服务器添加到所有 SIP Uri 拨号计划中。</span><span class="sxs-lookup"><span data-stu-id="457a0-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="457a0-139">反过来，这会将服务器配置为受信任的 SIP 对等方以及 Lync Server 的 ExUmRouting 拓扑。</span><span class="sxs-lookup"><span data-stu-id="457a0-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="457a0-140">**在 Outlook Web App 上启用即时消息**</span><span class="sxs-lookup"><span data-stu-id="457a0-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="457a0-141">在 Lync Server 配置正确后，即可开始配置 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="457a0-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="457a0-142">该过程中的第一步是在前端服务器上的所有 Outlook Web App 虚拟目录上启用即时消息。</span><span class="sxs-lookup"><span data-stu-id="457a0-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="457a0-143"> (不需要为后端服务器上的虚拟目录启用即时消息。</span><span class="sxs-lookup"><span data-stu-id="457a0-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="457a0-144">事实上，建议您不要在后端服务器上启用即时消息。通过在 Exchange 命令行管理程序中运行以下命令，可以在客户端访问服务器上启用 ) 即时消息：</span><span class="sxs-lookup"><span data-stu-id="457a0-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="457a0-145">默认情况下，在安装 Outlook Web App 时将启用即时消息;也就是说，InstantMessagingEnabled 属性设置为 True。</span><span class="sxs-lookup"><span data-stu-id="457a0-145">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True.</span></span> <span data-ttu-id="457a0-146">但是，仍必须运行前面的命令，才能将即时消息类型设置为 OCS。</span><span class="sxs-lookup"><span data-stu-id="457a0-146">However, you must still run the preceding command in order to set the instant messaging type to OCS.</span></span> <span data-ttu-id="457a0-147">默认情况下，InstantMessagingType 设置为 None。</span><span class="sxs-lookup"><span data-stu-id="457a0-147">By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="457a0-148">接下来，您必须将以下两行添加到 Outlook Web App Web.config 文件中， (此文件通常位于文件夹 C： \\ Program Files \\ Microsoft \\ Exchange Server \\ V15 \\ ClientAccess \\ Owa) 中。</span><span class="sxs-lookup"><span data-stu-id="457a0-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="457a0-149">应在 Web.config 文件中的节点下添加这两行 \<AppSettings\> ，并且应仅在安装了 Outlook Web App 的后端服务器上执行此过程：</span><span class="sxs-lookup"><span data-stu-id="457a0-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="457a0-150">在上面的示例中，IMCertificateThumbprint 的值必须是安装在后端服务器上的 Exchange 2013 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="457a0-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="457a0-151">您可以通过在 Exchange 命令行管理程序中运行以下命令来检索该信息：</span><span class="sxs-lookup"><span data-stu-id="457a0-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="457a0-152">请注意，分配给 IMServerName 的值也是您在其中为 Outlook Web App 创建受信任应用程序池的 Lync Server 池的完全限定域名。</span><span class="sxs-lookup"><span data-stu-id="457a0-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="457a0-153">用于 Outlook Web App 的证书必须是由 Lync Server 信任的证书。</span><span class="sxs-lookup"><span data-stu-id="457a0-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="457a0-154">若要确保 Lync Server 和 Exchange 都能信任证书的一种方法是使用内部证书颁发机构在邮箱服务器上创建证书，请确保服务器 FQDN 用于使用者名称，并且此 FQDN 出现在 "证书备用名称" 字段中。</span><span class="sxs-lookup"><span data-stu-id="457a0-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="457a0-155">创建证书之后，可以将其导入到后端服务器。</span><span class="sxs-lookup"><span data-stu-id="457a0-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="457a0-156">最终结果是，相同的证书用于两个目的： 1) Exchange 统一消息和 Lync Server 之间的通信;2) Outlook Web App 和 Lync Server 之间的集成。</span><span class="sxs-lookup"><span data-stu-id="457a0-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="457a0-157">更新 Web.config 文件后，应在 Exchange 后端服务器上运行以下命令，以便回收 Outlook Web App 池：</span><span class="sxs-lookup"><span data-stu-id="457a0-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="457a0-158">如果回收操作成功，您将在 Exchange 命令行管理程序中看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="457a0-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="457a0-159">**配置 Outlook Web App 邮箱策略**</span><span class="sxs-lookup"><span data-stu-id="457a0-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="457a0-160">此时，您可以使用以下命令在相应的 Outlook Web App 邮箱策略 (或策略) 上配置即时消息。</span><span class="sxs-lookup"><span data-stu-id="457a0-160">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies).</span></span> <span data-ttu-id="457a0-161">例如，此命令在您的某个邮箱服务器上运行，并在默认策略上启用即时消息：</span><span class="sxs-lookup"><span data-stu-id="457a0-161">For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="457a0-162">此命令将为您的所有 Outlook Web App 邮箱策略启用即时消息：</span><span class="sxs-lookup"><span data-stu-id="457a0-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="457a0-163">启用邮箱策略之后，由该策略管理的所有用户都将在 Lync Server 和 Outlook Web App 之间实现完全集成，前提是：</span><span class="sxs-lookup"><span data-stu-id="457a0-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="457a0-164">用户在 Exchange 2013 上拥有邮箱。</span><span class="sxs-lookup"><span data-stu-id="457a0-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="457a0-165">已为用户启用 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="457a0-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="457a0-166">用户具有有效的 SIP 代理地址。</span><span class="sxs-lookup"><span data-stu-id="457a0-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="457a0-167">**在 Outlook Web App 中禁用即时消息**</span><span class="sxs-lookup"><span data-stu-id="457a0-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="457a0-168">如前所述，默认情况下，在 Outlook Web App 中启用即时消息。</span><span class="sxs-lookup"><span data-stu-id="457a0-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="457a0-169">这意味着，如果不将 Outlook Web App 与 Lync Server 集成，则用户将在每次登录到 Outlook Web App 时看到空白的状态图标和错误消息。</span><span class="sxs-lookup"><span data-stu-id="457a0-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="457a0-170">若要避免此问题，请使用以下 Exchange 命令行管理程序命令在 Outlook web App 中禁用即时消息：</span><span class="sxs-lookup"><span data-stu-id="457a0-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="457a0-171">**验证与 Outlook Web App 的集成**</span><span class="sxs-lookup"><span data-stu-id="457a0-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="457a0-172">若要验证即时消息和状态是否已与 Outlook Web App 集成，请登录到 Outlook Web App 2013。</span><span class="sxs-lookup"><span data-stu-id="457a0-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="457a0-173">在屏幕的右上角，将看到您的 Exchange 显示名称。</span><span class="sxs-lookup"><span data-stu-id="457a0-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="457a0-174">如果您的姓名旁边有 "状态" 图标 (例如，绿色图标，指示您的当前状态是可用的) 表明您已成功集成 Lync Server 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="457a0-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="457a0-175">在首次登录到 Outlook Web App 后，检查以查看是否有事件 ID 为112的事件 (和源 MSExchange OWA) 是否已写入邮箱服务器上的事件日志。</span><span class="sxs-lookup"><span data-stu-id="457a0-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="457a0-176">此事件表示即时消息终结点管理器已成功初始化。</span><span class="sxs-lookup"><span data-stu-id="457a0-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="457a0-177">如果即时消息似乎不起作用，则在邮箱服务器上，在文件夹 C： \\ Program files \\ Microsoft \\ Exchange server \\ V15 \\ 日志记录 \\ OWA \\ InstantMessaging 中查找日志文件。</span><span class="sxs-lookup"><span data-stu-id="457a0-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="457a0-178">如果日志记录或 InstantMessaging 文件夹不存在，则表示集成失败。</span><span class="sxs-lookup"><span data-stu-id="457a0-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="457a0-179">在这种情况下，可以在 Lync Server 上使用 SIPStack 跟踪 (所有级别和所有标志) 尝试并确定集成失败的原因。</span><span class="sxs-lookup"><span data-stu-id="457a0-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

