---
title: Lync Server 2013：其他软件要求
description: Lync Server 2013：其他软件要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Additional software requirements
ms:assetid: 87b318e3-03ae-41f7-af5e-29bb294f6af0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398686(v=OCS.15)
ms:contentKeyID: 48184731
ms.date: 12/09/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fbc36f23a2246c9d653e47954064182c756f0dff
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553038"
---
# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="b954b-103">Lync Server 2013 的其他软件要求</span><span class="sxs-lookup"><span data-stu-id="b954b-103">Additional software requirements for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b954b-104">_**上次修改的主题：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="b954b-104">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="b954b-105">除了服务器平台的硬件和操作系统要求之外，Lync Server 2013 还需要在部署的服务器上安装其他软件。</span><span class="sxs-lookup"><span data-stu-id="b954b-105">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="b954b-106">若要详细了解运行 Lync Server 的服务器的平台要求，请参阅 lync server 2013 中的 Lync Server 2013 和<A href="lync-server-2013-server-and-tools-operating-system-support.md">服务器和工具操作系统支持</A>的<A href="lync-server-2013-server-hardware-platforms.md">服务器硬件平台</A>。</span><span class="sxs-lookup"><span data-stu-id="b954b-106">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="b954b-107">有关客户端计算机和设备的系统要求的详细信息，请参阅规划文档中的在 <A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中规划客户端和设备</A> 。</span><span class="sxs-lookup"><span data-stu-id="b954b-107">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="b954b-108">有关管理工具的软件要求的详细信息，请参阅 <A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的管理工具软件要求</A>。</span><span class="sxs-lookup"><span data-stu-id="b954b-108">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="b954b-109">所有内部服务器角色所需的其他软件</span><span class="sxs-lookup"><span data-stu-id="b954b-109">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="b954b-110">本节列出了所有内部服务器角色必需的软件，这些角色是除边缘服务器之外的所有 Lync Server 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="b954b-110">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="b954b-111">边缘服务器和边缘池的要求在本主题后面的 **其他软件的边缘服务器**下列出。</span><span class="sxs-lookup"><span data-stu-id="b954b-111">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="b954b-112">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="b954b-112">Windows PowerShell 3.0</span></span>

<span data-ttu-id="b954b-113">每台运行 Lync Server 2013 的服务器必须安装正确版本的 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="b954b-113">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="b954b-114">有关详细信息，请参阅 [安装适用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="b954b-114">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="b954b-115">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="b954b-115">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="b954b-116">Lync Server 需要 Microsoft .NET Framework 4.5 在所有内部服务器角色上和运行 Lync Server 管理工具或 Microsoft Lync Server 2013 的任何计算机上，规划工具。</span><span class="sxs-lookup"><span data-stu-id="b954b-116">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="b954b-117">对于 Lync Server 2013，在安装 Lync Server 2013 之前，必须在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="b954b-117">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="b954b-118">若要手动安装它，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="b954b-118">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="b954b-119">在运行 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="b954b-119">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="b954b-120">当您在将运行 Lync Server 2013 和 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4.5 时，您必须执行一个额外的步骤。</span><span class="sxs-lookup"><span data-stu-id="b954b-120">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="b954b-121">安装 .NET Framework 4.5 后，请使用服务器管理器安装 HTTP 激活。</span><span class="sxs-lookup"><span data-stu-id="b954b-121">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="b954b-122">**在 Windows Server 2012 上安装 .NET 4.5 HTTP 激活**</span><span class="sxs-lookup"><span data-stu-id="b954b-122">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="b954b-123">从 " **开始** " 菜单中，单击 " **程序**"，再单击 " **管理工具**"，然后单击 " **服务器管理器**"。</span><span class="sxs-lookup"><span data-stu-id="b954b-123">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="b954b-124">在服务器管理器中的 " **功能摘要**" 下，选择 " **添加功能**"。</span><span class="sxs-lookup"><span data-stu-id="b954b-124">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="b954b-125">展开 **.Net Framework 4.5**。</span><span class="sxs-lookup"><span data-stu-id="b954b-125">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="b954b-126">选择 " **WCF 激活** " （如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="b954b-126">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="b954b-127">然后选择 " **HTTP 激活**"。</span><span class="sxs-lookup"><span data-stu-id="b954b-127">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="b954b-128">单击 " **下一步** " 并按照提示完成安装。</span><span class="sxs-lookup"><span data-stu-id="b954b-128">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="b954b-129">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="b954b-129">Windows Identity Foundation</span></span>

<span data-ttu-id="b954b-130">Lync Server 2013 中的**Windows Identity foundation**要求安装 Windows identity foundation，以便支持服务器到服务器身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="b954b-130">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="b954b-131">Windows Server 2008 R2 和 Windows Server 2012 需要不同的过程来安装 Windows 识别基础。</span><span class="sxs-lookup"><span data-stu-id="b954b-131">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="b954b-132">从以下列表中选择您的服务器操作系统：</span><span class="sxs-lookup"><span data-stu-id="b954b-132">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="b954b-133">Windows server 2008 R2 For Windows Server 2008 R2，请检查是否已在您的计算机上安装了它。</span><span class="sxs-lookup"><span data-stu-id="b954b-133">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="b954b-134">若要执行此操作，请转到 " **添加/删除程序**"， **查看已安装的更新**，并查看 **Windows** for THE entry \*\*windows Identity Foundation (KB974405) \*\*。</span><span class="sxs-lookup"><span data-stu-id="b954b-134">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="b954b-135">有关安装 Windows Identity Foundation 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="b954b-135">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="b954b-136">Windows Server 2012 For Windows Server 2012，可使用 **服务器管理器** 安装 Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="b954b-136">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="b954b-137">在服务器管理器 " **添加角色和功能" 向导**中，选择 " **功能**"。</span><span class="sxs-lookup"><span data-stu-id="b954b-137">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="b954b-138">从列表中选择 " **Windows Identity Foundation 3.5** "。</span><span class="sxs-lookup"><span data-stu-id="b954b-138">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="b954b-139">单击 " **下一步**"，然后单击 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="b954b-139">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="b954b-140">适用于所有前端服务器和 Standard Edition 服务器的其他软件</span><span class="sxs-lookup"><span data-stu-id="b954b-140">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="b954b-141">所有前端服务器和 Standard Edition 服务器还必须在特定模块 (IIS) 上运行 Internet 信息服务。</span><span class="sxs-lookup"><span data-stu-id="b954b-141">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="b954b-142">此外，部署了会议、呼叫寄存应用程序、公告或响应组的所有前端服务器和 Standard Edition 服务器都必须运行 Windows Media Format Runtime。</span><span class="sxs-lookup"><span data-stu-id="b954b-142">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="b954b-143">Internet Information Services (IIS)</span><span class="sxs-lookup"><span data-stu-id="b954b-143">Internet Information Services (IIS)</span></span>

<span data-ttu-id="b954b-144">前端服务器和 Standard Edition 服务器必须使用以下模块运行 Internet 信息服务 (IIS) ：</span><span class="sxs-lookup"><span data-stu-id="b954b-144">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="b954b-145">静态内容</span><span class="sxs-lookup"><span data-stu-id="b954b-145">Static Content</span></span>

  - <span data-ttu-id="b954b-146">默认文档</span><span class="sxs-lookup"><span data-stu-id="b954b-146">Default Document</span></span>

  - <span data-ttu-id="b954b-147">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="b954b-147">HTTP Errors</span></span>

  - <span data-ttu-id="b954b-148">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b954b-148">ASP.NET</span></span>

  - <span data-ttu-id="b954b-149">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="b954b-149">.NET Extensibility</span></span>

  - <span data-ttu-id="b954b-150">Internet Server API (ISAPI) 扩展</span><span class="sxs-lookup"><span data-stu-id="b954b-150">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="b954b-151">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="b954b-151">ISAPI Filters</span></span>

  - <span data-ttu-id="b954b-152">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="b954b-152">HTTP Logging</span></span>

  - <span data-ttu-id="b954b-153">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="b954b-153">Logging Tools</span></span>

  - <span data-ttu-id="b954b-154">追踪</span><span class="sxs-lookup"><span data-stu-id="b954b-154">Tracing</span></span>

  - <span data-ttu-id="b954b-155">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="b954b-155">Windows Authentication</span></span>

  - <span data-ttu-id="b954b-156">请求筛选</span><span class="sxs-lookup"><span data-stu-id="b954b-156">Request Filtering</span></span>

  - <span data-ttu-id="b954b-157">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="b954b-157">Static Content Compression</span></span>

  - <span data-ttu-id="b954b-158">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="b954b-158">Dynamic Content Compression</span></span>

  - <span data-ttu-id="b954b-159">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="b954b-159">IIS Management Console</span></span>

  - <span data-ttu-id="b954b-160">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="b954b-160">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="b954b-161">匿名身份验证 (安装 IIS 时，默认情况下会安装此身份验证。 ) </span><span class="sxs-lookup"><span data-stu-id="b954b-161">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="b954b-162">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="b954b-162">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="b954b-163">Windows Media Format Runtime 和 Windows 桌面体验</span><span class="sxs-lookup"><span data-stu-id="b954b-163">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="b954b-164">**Windows 桌面体验** 将部署会议的所有前端服务器和 Standard Edition 服务器必须安装 Windows Media Format Runtime，除了 Windows Server 2012 安装在 Windows 桌面体验中之外。</span><span class="sxs-lookup"><span data-stu-id="b954b-164">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="b954b-165">Windows Server 2012 需要 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="b954b-165">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="b954b-166">Windows Media Format Runtime 是运行呼叫寄存、通知和响应组应用程序播放通知和音乐时使用的 Windows Media 音频 (.wma) 文件所必需的软件。</span><span class="sxs-lookup"><span data-stu-id="b954b-166">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="b954b-167">建议您在安装 Lync Server 2013 之前安装 Windows 桌面体验。</span><span class="sxs-lookup"><span data-stu-id="b954b-167">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="b954b-168">如果 Lync Server 2013 在服务器上找不到此软件，它将提示您安装它，然后您必须重新启动服务器才能完成安装。</span><span class="sxs-lookup"><span data-stu-id="b954b-168">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="b954b-169">在 Windows Server 2012 上运行的前端服务器和 Standard Edition 服务器的其他软件</span><span class="sxs-lookup"><span data-stu-id="b954b-169">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="b954b-170">前端服务器要求安装 .NET 3.5，这在 Windows Server 2012 中默认不会安装。</span><span class="sxs-lookup"><span data-stu-id="b954b-170">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="b954b-171">若要安装它，请将 Windows Server 2012 安装介质放在驱动器 D 中，并键入以下命令：</span><span class="sxs-lookup"><span data-stu-id="b954b-171">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="b954b-172">有关在运行 Windows Server 2012 的服务器上安装 .NET 3.5 的详细信息，请参阅在上的 "Microsoft .NET Framework 3.5 部署注意事项" <https://go.microsoft.com/fwlink/p/?linkid=275032> 。</span><span class="sxs-lookup"><span data-stu-id="b954b-172">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="b954b-173">控制器的其他软件</span><span class="sxs-lookup"><span data-stu-id="b954b-173">Additional Software for Directors</span></span>

<span data-ttu-id="b954b-174">控制器必须使用以下模块 (IIS) 运行 Internet 信息服务：</span><span class="sxs-lookup"><span data-stu-id="b954b-174">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="b954b-175">静态内容</span><span class="sxs-lookup"><span data-stu-id="b954b-175">Static Content</span></span>

  - <span data-ttu-id="b954b-176">默认文档</span><span class="sxs-lookup"><span data-stu-id="b954b-176">Default Document</span></span>

  - <span data-ttu-id="b954b-177">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="b954b-177">HTTP Errors</span></span>

  - <span data-ttu-id="b954b-178">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b954b-178">ASP.NET</span></span>

  - <span data-ttu-id="b954b-179">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="b954b-179">.NET Extensibility</span></span>

  - <span data-ttu-id="b954b-180">Internet Server API (ISAPI) 扩展</span><span class="sxs-lookup"><span data-stu-id="b954b-180">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="b954b-181">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="b954b-181">ISAPI Filters</span></span>

  - <span data-ttu-id="b954b-182">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="b954b-182">HTTP Logging</span></span>

  - <span data-ttu-id="b954b-183">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="b954b-183">Logging Tools</span></span>

  - <span data-ttu-id="b954b-184">追踪</span><span class="sxs-lookup"><span data-stu-id="b954b-184">Tracing</span></span>

  - <span data-ttu-id="b954b-185">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="b954b-185">Windows Authentication</span></span>

  - <span data-ttu-id="b954b-186">请求筛选</span><span class="sxs-lookup"><span data-stu-id="b954b-186">Request Filtering</span></span>

  - <span data-ttu-id="b954b-187">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="b954b-187">Static Content Compression</span></span>

  - <span data-ttu-id="b954b-188">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="b954b-188">IIS Management Console</span></span>

  - <span data-ttu-id="b954b-189">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="b954b-189">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="b954b-190">匿名身份验证（安装 IIS 时默认安装。）</span><span class="sxs-lookup"><span data-stu-id="b954b-190">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="b954b-191">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="b954b-191">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="b954b-192">持久聊天前端服务器的其他软件</span><span class="sxs-lookup"><span data-stu-id="b954b-192">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="b954b-193">持久聊天前端服务器必须运行消息队列 (也称为 MSMQ) ，后者是 Windows Server 的一个组件。</span><span class="sxs-lookup"><span data-stu-id="b954b-193">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="b954b-194">若要了解如何启用 MSMQ，请 [单击此处。](https://technet.microsoft.com/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="b954b-194">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="b954b-195">其他适用于边缘服务器的软件</span><span class="sxs-lookup"><span data-stu-id="b954b-195">Additional Software for Edge Servers</span></span>

<span data-ttu-id="b954b-196">边缘服务器需要以下软件：</span><span class="sxs-lookup"><span data-stu-id="b954b-196">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="b954b-197">每台运行 Lync Server 2013 的服务器必须安装正确版本的 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="b954b-197">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="b954b-198">有关详细信息，请参阅 [安装适用于 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="b954b-198">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="b954b-199">Lync Server 要求安装 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="b954b-199">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="b954b-200">对于安装在 Windows Server 2008 R2 上的 Lync Server 2013，必须先在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5，然后再安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="b954b-200">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="b954b-201">若要手动安装它，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="b954b-201">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="b954b-202">Lync Server 2013 中的**Windows Identity foundation**要求安装 Windows identity foundation，以便支持服务器到服务器身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="b954b-202">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="b954b-203">Windows Server 2008 R2 和 Windows Server 2012 需要不同的过程来安装 Windows 识别基础。</span><span class="sxs-lookup"><span data-stu-id="b954b-203">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="b954b-204">从以下列表中选择您的服务器操作系统：</span><span class="sxs-lookup"><span data-stu-id="b954b-204">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="b954b-205">Windows server 2008 R2 For Windows Server 2008 R2，请检查是否已在您的计算机上安装了它。</span><span class="sxs-lookup"><span data-stu-id="b954b-205">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="b954b-206">若要执行此操作，请转到 " **添加/删除程序**"， **查看已安装的更新**，并查看 **Windows** for THE entry \*\*windows Identity Foundation (KB974405) \*\*。</span><span class="sxs-lookup"><span data-stu-id="b954b-206">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="b954b-207">有关安装 Windows Identity Foundation 的详细信息，请参阅 [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657) 。</span><span class="sxs-lookup"><span data-stu-id="b954b-207">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="b954b-208">Windows Server 2012 For Windows Server 2012，可使用 **服务器管理器** 安装 Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="b954b-208">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="b954b-209">在服务器管理器 " **添加角色和功能" 向导**中，选择 " **功能**"。</span><span class="sxs-lookup"><span data-stu-id="b954b-209">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="b954b-210">从列表中选择 " **Windows Identity Foundation 3.5** "。</span><span class="sxs-lookup"><span data-stu-id="b954b-210">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="b954b-211">单击 " **下一步**"，然后单击 " **安装**"。</span><span class="sxs-lookup"><span data-stu-id="b954b-211">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="b954b-212">不要在媒体服务器上安装分层套接字提供程序</span><span class="sxs-lookup"><span data-stu-id="b954b-212">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="b954b-213">请勿在任何前端服务器或独立中介服务器上安装任何 Microsoft Internet 安全性和加速 (ISA) Server 客户端软件或任何其他 Winsock 分层服务提供程序 (LSP) 软件。</span><span class="sxs-lookup"><span data-stu-id="b954b-213">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="b954b-214">安装此软件可能会导致媒体流量下降。</span><span class="sxs-lookup"><span data-stu-id="b954b-214">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b954b-215">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b954b-215">See Also</span></span>


[<span data-ttu-id="b954b-216">Lync Server 2013 中的管理工具软件要求</span><span class="sxs-lookup"><span data-stu-id="b954b-216">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

