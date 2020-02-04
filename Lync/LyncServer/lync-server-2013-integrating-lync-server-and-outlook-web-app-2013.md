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
ms.openlocfilehash: faa75694ecaac662a643d331a4efdf91b41223e5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41725828"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="integrating-microsoft-lync-server-2013-and-microsoft-outlook-web-app-2013"></a><span data-ttu-id="edd2f-102">集成 Microsoft Lync Server 2013 和 Microsoft Outlook Web App 2013</span><span class="sxs-lookup"><span data-stu-id="edd2f-102">Integrating Microsoft Lync Server 2013 and Microsoft Outlook Web App 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="edd2f-103">_**主题上次修改时间：** 2013-02-03_</span><span class="sxs-lookup"><span data-stu-id="edd2f-103">_**Topic Last Modified:** 2013-02-03_</span></span>

<span data-ttu-id="edd2f-104">除了与 Microsoft Outlook 2013 集成，Microsoft Lync Server 2013 还可以与 Microsoft Outlook Web App 2013 完全集成;在其他情况下，这将向 Outlook Web App 添加即时消息和状态，并使你的统一联系人列表在 Outlook Web App 和 Microsoft Lync 2013 之间共享。</span><span class="sxs-lookup"><span data-stu-id="edd2f-104">In addition to integrating with Microsoft Outlook 2013, Microsoft Lync Server 2013 can be fully integrated with Microsoft Outlook Web App 2013; among other things, this adds instant messaging and presence to Outlook Web App, and enables your unified contact list to be shared between Outlook Web App and Microsoft Lync 2013.</span></span> <span data-ttu-id="edd2f-105">为了集成 Lync Server 2013 和 Outlook Web App，必须首先验证您的 Microsoft Exchange Server 2013 后端服务器中是否已安装统一通信托管 API 4.0 运行时。</span><span class="sxs-lookup"><span data-stu-id="edd2f-105">In order to integrate Lync Server 2013 and Outlook Web App, you must first verify that the Unified Communications Managed API 4.0 Runtime has been installed in your Microsoft Exchange Server 2013 backend server.</span></span> <span data-ttu-id="edd2f-106">您可以通过确定存在以下注册表值来实现此目的：</span><span class="sxs-lookup"><span data-stu-id="edd2f-106">You can do this by looking for the existence of the following registry value:</span></span>

<span data-ttu-id="edd2f-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span><span class="sxs-lookup"><span data-stu-id="edd2f-107">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Services\\MSExchange OWA\\InstantMessaging\\ImplementationDLLPath</span></span>

<span data-ttu-id="edd2f-108">ImplementationDLLPath 应指向文件 Microsoft.Rtc.Internal.Ucweb.dll 的文件夹位置。</span><span class="sxs-lookup"><span data-stu-id="edd2f-108">The ImplementationDLLPath should point to the folder location for the file Microsoft.Rtc.Internal.Ucweb.dll.</span></span> <span data-ttu-id="edd2f-109">如果不存在，或者注册表值不存在，则应从 Microsoft 下载中心下载并安装 UCMA 运行时设置程序<http://www.microsoft.com/en-us/download/details.aspx?id=34992>。</span><span class="sxs-lookup"><span data-stu-id="edd2f-109">If it does not, or if the registry value does not exist, then you should download and install the UCMA Runtime setup program from the Microsoft Download Center at <http://www.microsoft.com/en-us/download/details.aspx?id=34992>.</span></span> <span data-ttu-id="edd2f-110">有关如何安装 UCMA 运行时的信息可在该相同网页上找到。</span><span class="sxs-lookup"><span data-stu-id="edd2f-110">Information on how to install the UCMA Runtime can be found on that same web page.</span></span>

<span data-ttu-id="edd2f-111">**向后兼容性**</span><span class="sxs-lookup"><span data-stu-id="edd2f-111">**Backward Compatibility**</span></span>

<span data-ttu-id="edd2f-112">Lync Server 2013 可以与统一消息和 Outlook Web App 的 Microsoft Exchange Server 2010 版本集成。</span><span class="sxs-lookup"><span data-stu-id="edd2f-112">Lync Server 2013 can be integrated with the Microsoft Exchange Server 2010 versions of both unified messaging and Outlook Web App.</span></span> <span data-ttu-id="edd2f-113">有关详细信息，请参阅部署本地 Exchange UM 以在[http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md)其上提供 Lync Server 2010 语音邮件的文章。</span><span class="sxs-lookup"><span data-stu-id="edd2f-113">For more information, see the article Deploying On-Premises Exchange UM to Provide Lync Server 2010 Voice Mail at [http://technet.microsoft.com/en-us/library/gg398768.aspx](lync-server-2013-deploying-on-premises-exchange-um-to-provide-lync-server-2013-voice-mail.md).</span></span> <span data-ttu-id="edd2f-114">如果您与 Exchange 2010 集成，则不会具有 Lync Server 特定功能，如 "统一联系人存储" 和 "Lync 到 Exchange 存档"。</span><span class="sxs-lookup"><span data-stu-id="edd2f-114">If you integrate with Exchange 2010 you will not have Lync Server specific features such as the unified contact store and Lync-to-Exchange archiving.</span></span>

<span data-ttu-id="edd2f-115">Microsoft Lync 2013 还可以与 Exchange 2010 和 Outlook 2010 结合使用。</span><span class="sxs-lookup"><span data-stu-id="edd2f-115">Microsoft Lync 2013 can also be used in conjunction with Exchange 2010 and Outlook 2010.</span></span> <span data-ttu-id="edd2f-116">但是，同样，"统一联系人存储" 和 "高分辨率" 照片等新功能将不会提供给 Lync 2013 用户。</span><span class="sxs-lookup"><span data-stu-id="edd2f-116">Once again, however, new functionality such as the unified contact store and high-resolution photos will not be available to Lync 2013 users.</span></span> <span data-ttu-id="edd2f-117">这些新功能需要 Lync Server 2013 和 Exchange 2013。</span><span class="sxs-lookup"><span data-stu-id="edd2f-117">These new capabilities require both Lync Server 2013 and Exchange 2013.</span></span>

<span data-ttu-id="edd2f-118">**为 Outlook Web App 创建受信任应用程序池**</span><span class="sxs-lookup"><span data-stu-id="edd2f-118">**Creating a Trusted Application Pool for Outlook Web App**</span></span>

<span data-ttu-id="edd2f-119">如果在同一台计算机上安装了 Microsoft Exchange 统一消息呼叫路由器服务和 Microsoft Exchange 统一消息服务，则无需为 Outlook Web App 创建受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="edd2f-119">If you have installed the Microsoft Exchange Unified Messaging Call Router service and the Microsoft Exchange Unified Messaging service on the same computer then there is no need to create a trusted application pool for Outlook Web App.</span></span> <span data-ttu-id="edd2f-120">（这假设所述服务器托管 SipName UM 拨号计划。）如果你使用一台计算机来托管这两个服务，则可以跳转到标题为 **"在 Outlook Web App 上启用即时消息**" 的本文档部分。</span><span class="sxs-lookup"><span data-stu-id="edd2f-120">(This assumes that the server in question is hosting a SipName UM dial plan.) If you are using a single computer to host both of these services then you can skip to the section of this document titled **Enabling Instant Messaging on Outlook Web App**.</span></span>

<span data-ttu-id="edd2f-121">Lync Server 2013 可以自动发现任何托管 SipName UM 拨号计划的 Exchange 服务器;这些服务器将自动添加到 "Lync Server 已知服务器" 列表。</span><span class="sxs-lookup"><span data-stu-id="edd2f-121">Lync Server 2013 can autodiscover any Exchange servers that host a SipName UM dial plan; these servers are automatically added to the Lync Server Known Servers List.</span></span> <span data-ttu-id="edd2f-122">无需创建受信任应用程序池并将这些服务器添加到已知服务器列表中。</span><span class="sxs-lookup"><span data-stu-id="edd2f-122">There is no need to create a trusted application pool and add these servers to the Known Servers List.</span></span> <span data-ttu-id="edd2f-123">事实上，这样做将导致 Outlook Web App 集成停止工作。</span><span class="sxs-lookup"><span data-stu-id="edd2f-123">In fact, doing so will cause Outlook Web App integration to stop working.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="edd2f-124">这是因为 Lync Server 拓扑现在将为同一台计算机提供两个条目： autodiscovered 条目和手动添加的条目。</span><span class="sxs-lookup"><span data-stu-id="edd2f-124">This is due to the fact that the Lync Server topology will now have two entries for the same computer: the autodiscovered entry, and the manually-added entry.</span></span> <span data-ttu-id="edd2f-125">若要解决此问题并使 Outlook Web App 再次工作，请使用 Windows PowerShell 来移除服务器的受信任池和受信任应用程序条目。</span><span class="sxs-lookup"><span data-stu-id="edd2f-125">To fix the problem, and to get Outlook Web App working again, use Windows PowerShell to remove the trusted pool and trusted application entries for the server.</span></span> <span data-ttu-id="edd2f-126">有关详细信息，请参阅 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> 和 <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlet 的帮助主题。</span><span class="sxs-lookup"><span data-stu-id="edd2f-126">See the help topics for the <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplicationPool">Remove-CsTrustedApplicationPool</A> and <A href="https://docs.microsoft.com/powershell/module/skype/Remove-CsTrustedApplication">Remove-CsTrustedApplication</A> cmdlets for more information.</span></span>



</div>

<span data-ttu-id="edd2f-127">如果这两个服务在单独的计算机上运行，则在验证统一通信托管 API 4.0 运行时已安装后，必须创建一个 Lync Server 受信任的应用程序池和与之关联的受信任的应用程序Outlook Web App;这会将服务器添加到 "已知服务器" 列表。</span><span class="sxs-lookup"><span data-stu-id="edd2f-127">If these two services are running on separate computers then, after you have verified that the Unified Communications Managed API 4.0 Runtime has been installed, you must create a Lync Server trusted application pool and a trusted application associated with Outlook Web App; that will add the server to the Known Servers List.</span></span> <span data-ttu-id="edd2f-128">若要执行此操作，请首先在 Lync Server Management Shell 中运行类似下面的命令：</span><span class="sxs-lookup"><span data-stu-id="edd2f-128">To do that, first run a command similar to this from within the Lync Server Management Shell:</span></span>

    New-CsTrustedApplicationPool -Identity atl-owa-001.litwareinc.com -Registrar atl-cs-001.litwareinc.com -Site Redmond -RequiresReplication $False

<span data-ttu-id="edd2f-129">在上面的命令中，atl-owa-001.litwareinc.com 是 Outlook Web App 池的完全限定域名；此名称必须与提供对 Outlook Web App 的访问权的证书的“使用者名称”和“使用者替代名称 (SAN)”字段中显示的名称相同。</span><span class="sxs-lookup"><span data-stu-id="edd2f-129">In the preceding command, atl-owa-001.litwareinc.com is the fully qualified domain name of the Outlook Web App pool; this must be the same name that appears in the Subject Name and Subject Alternative Name (SAN) fields of the certificate that provides access to Outlook Web App.</span></span> <span data-ttu-id="edd2f-130">同样，atl-cs-001.litwareinc.com 是 Lync Server 2013 池的完全限定域名，该域名将托管新的受信任的应用程序池。</span><span class="sxs-lookup"><span data-stu-id="edd2f-130">Likewise, atl-cs-001.litwareinc.com is the fully qualified domain name of the Lync Server 2013 pool that will host the new trusted application pool.</span></span> <span data-ttu-id="edd2f-131">请注意，指定的站点（Redmond）表示 Lync Server 网站的 SiteID。</span><span class="sxs-lookup"><span data-stu-id="edd2f-131">Note, too that the specified site, Redmond, represents the SiteID of the Lync Server site.</span></span> <span data-ttu-id="edd2f-132">SiteID 不一定与网站的 DisplayName 相同;你可以通过从 Lync Server Management Shell 运行以下命令来检索 Lync Server 站点的 SiteIDs：</span><span class="sxs-lookup"><span data-stu-id="edd2f-132">The SiteID is not necessarily the same as the site's DisplayName; you can retrieve SiteIDs for your Lync Server sites by running the following command from the Lync Server Management Shell:</span></span>

    Get-CsSite | Select-Object DisplayName, SiteID

<span data-ttu-id="edd2f-133">在创建受信任应用程序池后，可使用类似于以下命令的命令为 Outlook Web App 配置应用程序标识和端口：</span><span class="sxs-lookup"><span data-stu-id="edd2f-133">After creating the trusted application pool, use a command similar to the following to configure an application Identity and a port for Outlook Web App:</span></span>

    New-CsTrustedApplication -ApplicationId OutlookWebApp -TrustedApplicationPoolFqdn atl-owa-001.litwareinc.com  -Port 5199

<span data-ttu-id="edd2f-p110">在上面的命令中，ApplicationID 只是一个用于区分各个受信任应用程序的友好标识符。ApplicationID 可以是任何不包含空格或其他禁用字符的文本字符串。（为了确保您创建有效标识符，建议您在指定 ApplicationId 时仅使用字母和数字。）赋给 Port 参数的值也将由管理员处理：它可以是任何可用网络端口。</span><span class="sxs-lookup"><span data-stu-id="edd2f-p110">In the preceding command, the ApplicationID is simply a friendly identifier used to distinguish trusted applications. The ApplicationID can be any text string that does not include blank spaces or other prohibited characters. (To ensure that you create a valid identifier, it is recommended that you use only letters and numbers when specifying an ApplicationId.) The value assigned to the Port parameter is also left to the administrator's discretion: this can be any available network port.</span></span>

<span data-ttu-id="edd2f-137">创建受信任的应用程序后，必须运行以下命令以启用对 Lync Server 拓扑的更改：</span><span class="sxs-lookup"><span data-stu-id="edd2f-137">After creating the trusted application you must run the following command to enable the changes to your Lync Server topology:</span></span>

    Enable-CsTopology

<span data-ttu-id="edd2f-138">请注意，你还必须将 Exchange 客户端访问和邮箱服务器添加到你的所有 SIP Uri 拨号计划。</span><span class="sxs-lookup"><span data-stu-id="edd2f-138">Note that you must also add your Exchange client access and mailbox server to all of your SIP Uri dial plans.</span></span> <span data-ttu-id="edd2f-139">然后，这会将服务器配置为受信任的 SIP 对等以及 Lync Server 的 ExUmRouting 拓扑。</span><span class="sxs-lookup"><span data-stu-id="edd2f-139">In turn, this will configure the servers as trusted SIP peers with the ExUmRouting topology for Lync Server.</span></span>

<span data-ttu-id="edd2f-140">**在 Outlook Web App 上启用即时消息**</span><span class="sxs-lookup"><span data-stu-id="edd2f-140">**Enabling Instant Messaging on Outlook Web App**</span></span>

<span data-ttu-id="edd2f-141">成功配置 Lync Server 后，即可开始配置 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="edd2f-141">With Lync Server correctly configured you can then begin to configure Outlook Web App.</span></span> <span data-ttu-id="edd2f-142">该过程的第一步是对前端服务器上的所有 Outlook Web App 虚拟目录启用即时消息。</span><span class="sxs-lookup"><span data-stu-id="edd2f-142">The first step in that process is to enable instant messaging on all your Outlook Web App virtual directories on your front end servers.</span></span> <span data-ttu-id="edd2f-143">（无需为后端服务器上的虚拟目录启用即时消息。</span><span class="sxs-lookup"><span data-stu-id="edd2f-143">(There is no need to enable instant messaging for the virtual directories on your backend servers.</span></span> <span data-ttu-id="edd2f-144">事实上，建议不要在后端服务器上启用即时消息。通过在 Exchange 命令行管理器中运行以下命令，可以在客户端访问服务器上启用即时消息：</span><span class="sxs-lookup"><span data-stu-id="edd2f-144">In fact, it is recommended that you do not enable instant messaging on your backend servers.) Instant messaging can be enabled on the client access servers by running the following command from within the Exchange Management Shell:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $True -InstantMessagingType OCS

<div>


> [!NOTE]  
> <span data-ttu-id="edd2f-p113">默认情况下，在您安装 Outlook Web App 时会启用即时消息；也就是说，InstantMessagingEnabled 属性设置为 True。不过，您仍必须运行上面的命令才能将即时消息类型设置为 OCS。默认情况下，InstantMessagingType 设置为 None。</span><span class="sxs-lookup"><span data-stu-id="edd2f-p113">By default, instant messaging is enabled when you install Outlook Web App; that is, the InstantMessagingEnabled property is set to True. However, you must still run the preceding command in order to set the instant messaging type to OCS. By default, InstantMessagingType is set to None.</span></span>



</div>

<span data-ttu-id="edd2f-148">接下来，你必须将以下两行添加到 Outlook Web App web.config 文件（此文件通常位于\\文件夹 C：程序文件\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa）中。</span><span class="sxs-lookup"><span data-stu-id="edd2f-148">Next you must add the following two lines to Outlook Web App Web.config file (this file is typically located in the folder C:\\Program Files\\Microsoft\\Exchange Server\\V15\\ClientAccess\\Owa).</span></span> <span data-ttu-id="edd2f-149">这两行应添加到 web.config 文件\<中\>的 AppSettings 节点下，此过程应仅在安装了 Outlook Web App 的后端服务器上执行：</span><span class="sxs-lookup"><span data-stu-id="edd2f-149">These two lines should be added under the \<AppSettings\> node in the Web.config file, and this procedure should be carried out only on the backend servers where Outlook Web App has been installed:</span></span>

    <add key="IMCertificateThumbprint" value="EA5A332496CC05DA69B75B66111C0F78A110D22d"/>
    <add key="IMServerName" value="atl-cs-001.litwareinc.com"/>

<span data-ttu-id="edd2f-150">在前面的示例中，IMCertificateThumbprint 的值必须是安装在后端服务器上的 Exchange 2013 证书的指纹。</span><span class="sxs-lookup"><span data-stu-id="edd2f-150">In the preceding example, the value for IMCertificateThumbprint must be the thumbprint for the Exchange 2013 certificate that is installed on your backend servers.</span></span> <span data-ttu-id="edd2f-151">你可以通过从 Exchange 命令行管理程序运行以下命令来检索该信息：</span><span class="sxs-lookup"><span data-stu-id="edd2f-151">You can retrieve that information by running the following command from the Exchange Management Shell:</span></span>

    Get-ExchangeCertificate

<span data-ttu-id="edd2f-152">注意，分配给 IMServerName 的值同样是 Lync 服务器池的完全限定的域名，您可以在其中创建 Outlook Web App 的受信任应用程序池。</span><span class="sxs-lookup"><span data-stu-id="edd2f-152">Note, too that the value assigned to IMServerName is the fully qualified domain name of the Lync Server pool where you created the trusted application pool for Outlook Web App.</span></span>

<span data-ttu-id="edd2f-153">用于 Outlook Web App 的证书必须是由 Lync Server 信任的证书。</span><span class="sxs-lookup"><span data-stu-id="edd2f-153">The certificate that you use for Outlook Web App must be a certificate that is trusted by Lync Server.</span></span> <span data-ttu-id="edd2f-154">确保证书受 Lync Server 和 Exchange 信任的一种方法是使用内部证书颁发机构在邮箱服务器上创建证书，确保服务器 FQDN 用于使用者名称，并且该 FQDN 显示在 t 中。"证书备用名称" 字段。</span><span class="sxs-lookup"><span data-stu-id="edd2f-154">One way to ensure that the certificate will be trusted by both Lync Server and Exchange is to use your internal certificate authority to create a certificate on the mailbox server, making sure that the server FQDN is used for the subject name and that this FQDN appears in the certificate alternate name field.</span></span> <span data-ttu-id="edd2f-155">在创建证书之后，可以将证书导入到后端服务器。</span><span class="sxs-lookup"><span data-stu-id="edd2f-155">After the certificate has been created it can then be imported to your backend servers.</span></span> <span data-ttu-id="edd2f-156">最终结果是，相同的证书用于两个目的：1） Exchange 统一消息和 Lync 服务器之间的通信;和2） Outlook Web App 与 Lync Server 之间的集成。</span><span class="sxs-lookup"><span data-stu-id="edd2f-156">The net result is that the same certificate is used for two purposes: 1) communication between Exchange unified messaging and Lync Server; and, 2) the integration between Outlook Web App and Lync Server.</span></span>

<span data-ttu-id="edd2f-157">更新 Web.config 文件后，您应该在 Exchange 后端服务器上运行以下命令，以便回收 Outlook Web App 池：</span><span class="sxs-lookup"><span data-stu-id="edd2f-157">After you have updated the Web.config file you should then run the following command on the Exchange backend server in order to recycle the Outlook Web App pool:</span></span>

    C:\Windows\System32\Inetsrv\Appcmd.exe recycle apppool /apppool.name:"MSExchangeOWAAppPool"

<span data-ttu-id="edd2f-158">如果循环操作成功，您将在 Exchange 命令行管理程序中看到以下消息：</span><span class="sxs-lookup"><span data-stu-id="edd2f-158">If the recycle operation succeeds you will see the following message in the Exchange Management Shell:</span></span>

    "MSExchangeOWAAppPool" successfully recycled

<span data-ttu-id="edd2f-159">**配置 Outlook Web App 邮箱策略**</span><span class="sxs-lookup"><span data-stu-id="edd2f-159">**Configuring Outlook Web App Mailbox Policies**</span></span>

<span data-ttu-id="edd2f-p117">此时，您可以使用以下命令为一个或多个相应 Outlook Web App 邮箱策略配置即时消息。例如，在您的某个邮箱服务器上运行的以下命令将为 Default 策略启用即时消息：</span><span class="sxs-lookup"><span data-stu-id="edd2f-p117">At this point you can use the following command to configure instant messaging on the appropriate Outlook Web App mailbox policy (or policies). For example, this command, run on one of your mailbox servers, enables instant messaging on the Default policy:</span></span>

    Set-OwaMailboxPolicy -Identity "Default" -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="edd2f-162">以下命令将为您的所有 Outlook Web App 邮箱策略启用即时消息：</span><span class="sxs-lookup"><span data-stu-id="edd2f-162">And this command enables instant messaging for all your Outlook Web App mailbox policies:</span></span>

    Get-OwaMailboxPolicy | Set-OwaMailboxPolicy -InstantMessagingEnabled $True -InstantMessagingType "OCS"

<span data-ttu-id="edd2f-163">启用邮箱策略后，由该策略管理的所有用户都将在 Lync Server 和 Outlook Web App 之间具有完全集成，前提是：</span><span class="sxs-lookup"><span data-stu-id="edd2f-163">After the mailbox policy has been enabled then all users managed by that policy will have full integration between Lync Server and Outlook Web App, provided that:</span></span>

  - <span data-ttu-id="edd2f-164">用户在 Exchange 2013 上有邮箱。</span><span class="sxs-lookup"><span data-stu-id="edd2f-164">The user has a mailbox on Exchange 2013.</span></span>

  - <span data-ttu-id="edd2f-165">用户已针对 Lync Server 2013 启用。</span><span class="sxs-lookup"><span data-stu-id="edd2f-165">The user has been enabled for Lync Server 2013.</span></span>

  - <span data-ttu-id="edd2f-166">用户具有有效的 SIP 代理地址。</span><span class="sxs-lookup"><span data-stu-id="edd2f-166">The user has a valid SIP proxy address.</span></span>

<span data-ttu-id="edd2f-167">**在 Outlook Web App 中禁用即时消息**</span><span class="sxs-lookup"><span data-stu-id="edd2f-167">**Disabling Instant Messaging in Outlook Web App**</span></span>

<span data-ttu-id="edd2f-168">如上所述，在 Outlook Web App 中，默认启用即时消息。</span><span class="sxs-lookup"><span data-stu-id="edd2f-168">As noted previously, instant messaging is enabled by default in Outlook Web App.</span></span> <span data-ttu-id="edd2f-169">这意味着，如果您不将 Outlook Web App 与 Lync Server 集成，则用户每次登录到 Outlook Web App 时都会看到空白状态图标和错误消息。</span><span class="sxs-lookup"><span data-stu-id="edd2f-169">That means that, if you do not integrate Outlook Web App with Lync Server, users will see blank presence icons and an error message each time they log on to Outlook Web App.</span></span> <span data-ttu-id="edd2f-170">若要避免此问题，请使用以下 Exchange Management Shell 命令在 Outlook web App 中禁用即时消息：</span><span class="sxs-lookup"><span data-stu-id="edd2f-170">To prevent this problem, use the following Exchange Management Shell command to disable instant messaging in Outlook web App:</span></span>

    Get-OwaVirtualDirectory | Set-OwaVirtualDirectory -InstantMessagingEnabled $False

<span data-ttu-id="edd2f-171">**验证与 Outlook Web App 的集成**</span><span class="sxs-lookup"><span data-stu-id="edd2f-171">**Verifying Integration With Outlook Web App**</span></span>

<span data-ttu-id="edd2f-172">若要验证即时消息和状态是否已与 Outlook Web App 集成，请登录到 Outlook Web App 2013。</span><span class="sxs-lookup"><span data-stu-id="edd2f-172">To verify that instant messaging and presence have been integrated with Outlook Web App, sign on to Outlook Web App 2013.</span></span> <span data-ttu-id="edd2f-173">在屏幕的右上角，您将看到 Exchange 显示名称。</span><span class="sxs-lookup"><span data-stu-id="edd2f-173">In the upper right-hand corner of the screen, you will see your Exchange display name.</span></span> <span data-ttu-id="edd2f-174">如果你的名称旁边有 "状态" 图标（例如，绿色图标指示你的当前状态可用），表示你已成功集成 Lync Server 和 Outlook Web App。</span><span class="sxs-lookup"><span data-stu-id="edd2f-174">If there is a presence icon next to your name (for example, a green icon indicating that your current status is Available) that indicates that you have successfully integrated Lync Server and Outlook Web App.</span></span>

<span data-ttu-id="edd2f-175">在初次登录到 Outlook Web App 之后，请检查以了解具有事件 ID 112（和源 MSExchange OWA）的事件是否已写入到邮箱服务器上的事件日志中。</span><span class="sxs-lookup"><span data-stu-id="edd2f-175">After the initial sign-on to Outlook Web App, check to see if an event with the Event ID 112 (and the source MSExchange OWA) has been written to the event log on the mailbox server.</span></span> <span data-ttu-id="edd2f-176">此事件指示已成功初始化 Instant Messaging Endpoint Manager。</span><span class="sxs-lookup"><span data-stu-id="edd2f-176">This event indicates that the Instant Messaging Endpoint Manager was successfully initialized.</span></span> <span data-ttu-id="edd2f-177">如果即时消息看起来没有正常工作，请在邮箱服务器\\上的 "文件夹 C：程序文件\\" 中查找日志文件 Microsoft\\Exchange server\\V15\\记录\\OWA\\InstantMessaging。</span><span class="sxs-lookup"><span data-stu-id="edd2f-177">If instant messaging does not appear to be working then, on the mailbox server, look for log files in the folder C:\\Program Files\\Microsoft\\Exchange server\\V15\\Logging\\OWA\\InstantMessaging.</span></span> <span data-ttu-id="edd2f-178">如果 Logging 或 InstantMessaging 文件夹不存在，则指示集成失败。</span><span class="sxs-lookup"><span data-stu-id="edd2f-178">If either the Logging or the InstantMessaging folders do not exist that indicates that integration has failed.</span></span> <span data-ttu-id="edd2f-179">在这种情况下，你可以使用 Lync Server 上的 SIPStack 跟踪（所有级别和所有标志）尝试并确定集成失败的原因。</span><span class="sxs-lookup"><span data-stu-id="edd2f-179">In that case, you can use SIPStack tracing on Lync Server (All Levels and All Flags) to try and determine why integration failed.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

