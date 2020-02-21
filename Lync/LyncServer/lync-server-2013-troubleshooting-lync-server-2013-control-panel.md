---
title: Lync Server 2013： Lync Server 2013 控制面板故障排除
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Troubleshooting Lync Server 2013 Control Panel
ms:assetid: 54e7ab57-34ce-4a07-bcc9-643379eb4eb7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg195689(v=OCS.15)
ms:contentKeyID: 48184145
ms.date: 07/28/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 629fa8ea52148e25bd37fa448d9762fbfd557788
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42193375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="troubleshooting-lync-server-2013-control-panel"></a><span data-ttu-id="ad194-102">Lync Server 2013 控制面板疑难解答</span><span class="sxs-lookup"><span data-stu-id="ad194-102">Troubleshooting Lync Server 2013 Control Panel</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ad194-103">_**上次修改的主题：** 2016-07-28_</span><span class="sxs-lookup"><span data-stu-id="ad194-103">_**Topic Last Modified:** 2016-07-28_</span></span>

<span data-ttu-id="ad194-104">本主题提供的信息和过程可帮助您对 Lync Server 2013 控制面板的访问进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="ad194-104">This topic provides information and procedures that can help you troubleshoot access to Lync Server 2013 Control Panel.</span></span>

<div>

## <a name="internet-browser-requirements"></a><span data-ttu-id="ad194-105">Internet 浏览器要求</span><span class="sxs-lookup"><span data-stu-id="ad194-105">Internet Browser Requirements</span></span>

<span data-ttu-id="ad194-106">Lync Server 控制面板要求安装 Microsoft Silverlight 浏览器插件版本4.0.50524.0 或最新版本。</span><span class="sxs-lookup"><span data-stu-id="ad194-106">Lync Server Control Panel requires that Microsoft Silverlight browser plug-in version 4.0.50524.0 or latest version is installed.</span></span> <span data-ttu-id="ad194-107">如果未安装 Silverlight 或者安装了早期版本，请按照邮件中的说明安装所需的版本。</span><span class="sxs-lookup"><span data-stu-id="ad194-107">If Silverlight is not installed or if an earlier version is installed, follow the instructions in the message to install the required version.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="ad194-108">Lync Server 控制面板的其他软件要求适用于可安装 Lync Server 控制面板和所有其他 Lync Server 2013 管理工具的操作系统。</span><span class="sxs-lookup"><span data-stu-id="ad194-108">Other software requirements for Lync Server Control Panel pertain to the operating system on which Lync Server Control Panel and all other Lync Server 2013 administrative tools can be installed.</span></span> <span data-ttu-id="ad194-109">有关详细信息，请参阅可支持性文档中的<A href="lync-server-2013-server-and-tools-operating-system-support.md">Lync server 2013 中的服务器和工具操作系统支持</A>。</span><span class="sxs-lookup"><span data-stu-id="ad194-109">For details, see <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A> in the Supportability documentation.</span></span>



</div>

<span data-ttu-id="ad194-110">如果你的 Internet 浏览器由于安全考虑而阻止安装 Silverlight，请将打开 Lync Server 控制面板的统一资源定位器（URL）添加到受信任的网站列表中。</span><span class="sxs-lookup"><span data-stu-id="ad194-110">If your Internet browser blocks installation of Silverlight due to security considerations, add the Uniform Resource Locator (URL) that opens Lync Server Control Panel to the list of trusted sites.</span></span> <span data-ttu-id="ad194-111">在 Internet Explorer 安全设置中，确保“运行 ActiveX 控件和插件”\*\*\*\* 设置为“已启用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad194-111">In Internet Explorer security settings, ensure that **Run ActiveX controls and plug-ins** is set to **Enabled**.</span></span> <span data-ttu-id="ad194-112">有关详细信息， [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060)请参阅。</span><span class="sxs-lookup"><span data-stu-id="ad194-112">For details, see [https://go.microsoft.com/fwlink/p/?linkId=214060](https://go.microsoft.com/fwlink/p/?linkid=214060).</span></span> <span data-ttu-id="ad194-113">此外，请确保浏览器配置为使用 SSL 3.0。</span><span class="sxs-lookup"><span data-stu-id="ad194-113">Furthermore, ensure that the browser is configured to use SSL 3.0.</span></span>

<span data-ttu-id="ad194-p104">如果 Internet 浏览器配置为使用代理浏览器，请验证浏览器是否配置为绕过自动检测为内部站点的代理服务器。或者，将地址添加到代理服务器配置设置中的浏览器例外列表中。</span><span class="sxs-lookup"><span data-stu-id="ad194-p104">If the Internet browser is configured to use a proxy server, verify that the browser is configured to bypass the proxy server for sites that are automatically detected as internal sites. Or, add the address to the browser's exception list in the proxy server configuration settings.</span></span>

</div>

<div>

## <a name="dns-record-and-certificate-requirements-for-the-administrative-access-url"></a><span data-ttu-id="ad194-116">管理访问 URL 的 DNS 记录和证书要求</span><span class="sxs-lookup"><span data-stu-id="ad194-116">DNS Record and Certificate Requirements for the Administrative Access URL</span></span>

<span data-ttu-id="ad194-117">如果您配置了一个简单的 URL 来访问 Lync Server 控制面板，请确保您还配置了使用该管理访问 URL 的静态域名系统（DNS）主机（A）资源记录和证书。</span><span class="sxs-lookup"><span data-stu-id="ad194-117">If you configured a simple URL to access Lync Server Control Panel, ensure that you also configured the static Domain Name System (DNS) host (A) resource record and certificate necessary to use that administrative access URL.</span></span> <span data-ttu-id="ad194-118">如果你随时更改基 URL，请确保更改将反映在相应的 DNS 记录和证书中，并且在每个控制器和前端服务器上运行*CsComputer*以注册更改。</span><span class="sxs-lookup"><span data-stu-id="ad194-118">If you change the base URL at any time, ensure that the change is reflected in the appropriate DNS record and certificate and that you run the *Enable-CsComputer* on each Director and Front End Server to register the change.</span></span> <span data-ttu-id="ad194-119">有关详细信息，请参阅规划文档中的以下主题：</span><span class="sxs-lookup"><span data-stu-id="ad194-119">For details, see the following topics in the Planning documentation:</span></span>

  - [<span data-ttu-id="ad194-120">在 Lync Server 2013 中规划简单 Url</span><span class="sxs-lookup"><span data-stu-id="ad194-120">Planning for simple URLs in Lync Server 2013</span></span>](lync-server-2013-planning-for-simple-urls.md)

  - [<span data-ttu-id="ad194-121">Lync Server 2013 中简单 Url 的 DNS 要求</span><span class="sxs-lookup"><span data-stu-id="ad194-121">DNS requirements for simple URLs in Lync Server 2013</span></span>](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [<span data-ttu-id="ad194-122">Lync Server 2013 中的内部服务器的证书要求</span><span class="sxs-lookup"><span data-stu-id="ad194-122">Certificate requirements for internal servers in Lync Server 2013</span></span>](lync-server-2013-certificate-requirements-for-internal-servers.md)

<span data-ttu-id="ad194-123">有关配置管理访问 URL 的分步过程，请参阅部署文档中的在[Lync Server 2013 中编辑或配置简单 url](lync-server-2013-edit-or-configure-simple-urls.md) 。</span><span class="sxs-lookup"><span data-stu-id="ad194-123">For step-by-step procedures to configure the administrative access URL, see [Edit or configure simple URLs in Lync Server 2013](lync-server-2013-edit-or-configure-simple-urls.md) in the Deployment documentation.</span></span>

</div>

<div>

## <a name="internet-information-services-iis-requirements"></a><span data-ttu-id="ad194-124">Internet Information Services (IIS) 要求</span><span class="sxs-lookup"><span data-stu-id="ad194-124">Internet Information Services (IIS) Requirements</span></span>

<span data-ttu-id="ad194-125">Lync Server 控制面板是需要 Internet 信息服务（IIS）的 Lync Server 2013 组件之一。</span><span class="sxs-lookup"><span data-stu-id="ad194-125">Lync Server Control Panel is one of the components of Lync Server 2013 that requires Internet Information Services (IIS).</span></span> <span data-ttu-id="ad194-126">特别是要确保启用了 HTTP 重定向和 Windows 身份验证功能，并确保 World Wide Web 发布服务 (W3SVC) 正在运行。</span><span class="sxs-lookup"><span data-stu-id="ad194-126">In particular, ensure that HTTP redirection and Windows authentication features are enabled, and that the World Wide Web Publishing Service (W3SVC) is running.</span></span>

<div>

## <a name="world-wide-publishing-service-windows-service-dependency"></a><span data-ttu-id="ad194-127">World Wide Web 发布服务（Windows 服务）依赖关系</span><span class="sxs-lookup"><span data-stu-id="ad194-127">World Wide Publishing Service (Windows Service) Dependency</span></span>

<span data-ttu-id="ad194-128">如果停止万维网发布服务，则无法访问 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad194-128">When the World Wide Web Publishing Service is stopped, you cannot access Lync Server Control Panel.</span></span> <span data-ttu-id="ad194-129">可以使用 Windows 服务 Microsoft 管理控制台 (MMC) 重新启动该服务。</span><span class="sxs-lookup"><span data-stu-id="ad194-129">You can restart the service by using the Windows Services Microsoft Management Console (MMC).</span></span>

<span data-ttu-id="ad194-130">**启动 World Wide Web 发布服务**</span><span class="sxs-lookup"><span data-stu-id="ad194-130">**To start the World Wide Web Publishing Service**</span></span>

1.  <span data-ttu-id="ad194-131">登录到安装了 World Wide Web 发布服务的计算机作为 Internet 信息服务（IIS）的一部分。</span><span class="sxs-lookup"><span data-stu-id="ad194-131">Log on to the computer where the World Wide Web Publishing Service is installed as part of Internet Information Services (IIS).</span></span>

2.  <span data-ttu-id="ad194-132">依次单击“开始”\*\*\*\*、“管理工具”\*\*\*\*，然后单击“服务”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad194-132">Click **Start**, click **Administrative Tools**, and then click **Services**.</span></span>

3.  <span data-ttu-id="ad194-133">右键单击“World Wide Web 发布服务”\*\*\*\*，然后单击“启动”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="ad194-133">Right-click **World Wide Web Publishing Service**, and then click **Start**.</span></span>

</div>

<div>

## <a name="application-pool-mode"></a><span data-ttu-id="ad194-134">应用程序池模式</span><span class="sxs-lookup"><span data-stu-id="ad194-134">Application Pool Mode</span></span>

<span data-ttu-id="ad194-135">配置 IIS 以便 CsManagementAppPool 应用程序池将 Network Service 帐户用作其进程模型标识。</span><span class="sxs-lookup"><span data-stu-id="ad194-135">Configure IIS so that the CsManagementAppPool application pool uses the Network Service account as its process model identity.</span></span>

</div>

</div>

<div>

## <a name="user-rights-and-permissions"></a><span data-ttu-id="ad194-136">用户权限</span><span class="sxs-lookup"><span data-stu-id="ad194-136">User Rights and Permissions</span></span>

<span data-ttu-id="ad194-137">您必须使用作为 CsAdministrator 组成员的域帐户或使用已向其委派用户权限的帐户登录 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad194-137">You must sign in to Lync Server Control Panel either by using a domain account that is a member of the CsAdministrator group or by using an account to which you have delegated user rights and permissions.</span></span> <span data-ttu-id="ad194-138">无法使用本地计算机帐户登录 Lync Server 控制面板。</span><span class="sxs-lookup"><span data-stu-id="ad194-138">You cannot sign in to Lync Server Control Panel by using a local machine account.</span></span> <span data-ttu-id="ad194-139">有关通过基于角色的访问控制（RBAC）委派管理任务的详细信息，请参阅规划文档中的在[Lync Server 2013 中规划基于角色的访问控制](lync-server-2013-planning-for-role-based-access-control.md)。</span><span class="sxs-lookup"><span data-stu-id="ad194-139">For details about delegating administrative tasks through role-based access control (RBAC), see [Planning for role-based access control in Lync Server 2013](lync-server-2013-planning-for-role-based-access-control.md) in the Planning documentation.</span></span>

<span data-ttu-id="ad194-140">如果使用简单 URL 访问 Lync Server 控制面板，请确保将 web 服务器添加到 RTCUniversalServerAdmins 和 RTCUniversalUserAdmins 组。</span><span class="sxs-lookup"><span data-stu-id="ad194-140">If you use a simple URL to access Lync Server Control Panel, ensure that web servers are added to the RTCUniversalServerAdmins and RTCUniversalUserAdmins groups.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="ad194-141">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ad194-141">See Also</span></span>


[<span data-ttu-id="ad194-142">Lync Server 2013 管理工具</span><span class="sxs-lookup"><span data-stu-id="ad194-142">Lync Server 2013 administrative tools</span></span>](lync-server-2013-lync-server-administrative-tools.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

