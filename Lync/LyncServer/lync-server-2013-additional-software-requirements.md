---
title: Lync Server 2013：其他软件要求
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
ms.openlocfilehash: fc650b4c427640398af1748e86c7bca9d76c703d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41738005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="additional-software-requirements-for-lync-server-2013"></a><span data-ttu-id="77cae-102">Lync Server 2013 的其他软件要求</span><span class="sxs-lookup"><span data-stu-id="77cae-102">Additional software requirements for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="77cae-103">_**主题上次修改时间：** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="77cae-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="77cae-104">除了服务器平台的硬件和操作系统要求之外，Lync Server 2013 还需要在部署的服务器上安装其他软件。</span><span class="sxs-lookup"><span data-stu-id="77cae-104">In addition to the hardware and operating system requirements for server platforms, Lync Server 2013 requires the installation of additional software on the servers that you deploy.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="77cae-105">有关运行 Lync Server 的服务器的平台要求的详细信息，请参阅 Lync server <A href="lync-server-2013-server-hardware-platforms.md">2013 的服务器硬件平台</A>和<A href="lync-server-2013-server-and-tools-operating-system-support.md">lync server 2013 中的服务器和工具操作系统支持</A>。</span><span class="sxs-lookup"><span data-stu-id="77cae-105">For details about the platform requirements for servers running Lync Server, see <A href="lync-server-2013-server-hardware-platforms.md">Server hardware platforms for Lync Server 2013</A> and <A href="lync-server-2013-server-and-tools-operating-system-support.md">Server and tools operating system support in Lync Server 2013</A>.</span></span> <span data-ttu-id="77cae-106">有关客户端计算机和设备的系统要求的详细信息，请参阅规划文档中<A href="lync-server-2013-planning-for-clients-and-devices.md">Lync Server 2013 中的客户端和设备规划</A>。</span><span class="sxs-lookup"><span data-stu-id="77cae-106">For details about system requirements for client computers and devices, see <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and devices in Lync Server 2013</A> in the Planning documentation.</span></span> <span data-ttu-id="77cae-107">有关管理工具的软件要求的详细信息，请参阅<A href="lync-server-2013-administrative-tools-software-requirements.md">Lync Server 2013 中的管理工具软件要求</A>。</span><span class="sxs-lookup"><span data-stu-id="77cae-107">For details about software requirements for administrative tools, see <A href="lync-server-2013-administrative-tools-software-requirements.md">Administrative tools software requirements in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="additional-software-necessary-for-all-internal-server-roles"></a><span data-ttu-id="77cae-108">所有内部服务器角色所需的其他软件</span><span class="sxs-lookup"><span data-stu-id="77cae-108">Additional Software Necessary for All Internal Server Roles</span></span>

<span data-ttu-id="77cae-109">本部分列出了所有内部服务器角色所必需的软件，这些角色是除 Edge 服务器之外的所有 Lync Server 服务器角色。</span><span class="sxs-lookup"><span data-stu-id="77cae-109">This section lists software necessary on all internal server roles, which are all Lync Server server roles except for Edge Server.</span></span> <span data-ttu-id="77cae-110">有关 Edge 服务器和边缘池的要求将在本主题的 "**其他软件适用于边缘服务器**" 下列出。</span><span class="sxs-lookup"><span data-stu-id="77cae-110">The requirements for the Edge Servers and Edge pools are listed later in this topic under **Additional Software for Edge Servers**.</span></span>

</div>

<div>

## <a name="windows-powershell-30"></a><span data-ttu-id="77cae-111">Windows PowerShell 3.0</span><span class="sxs-lookup"><span data-stu-id="77cae-111">Windows PowerShell 3.0</span></span>

<span data-ttu-id="77cae-112">运行 Lync Server 2013 的每台服务器必须安装正确版本的 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="77cae-112">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="77cae-113">有关详细信息，请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="77cae-113">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

</div>

<div>

## <a name="microsoft-net-framework-45"></a><span data-ttu-id="77cae-114">Microsoft .NET Framework 4.5</span><span class="sxs-lookup"><span data-stu-id="77cae-114">Microsoft .NET Framework 4.5</span></span>

<span data-ttu-id="77cae-115">Lync Server 要求 Microsoft .NET Framework 4.5 位于所有内部服务器角色和任何运行 Lync Server 管理工具或 Microsoft Lync Server 2013 的计算机上的 "规划工具"。</span><span class="sxs-lookup"><span data-stu-id="77cae-115">Lync Server requires Microsoft .NET Framework 4.5 on all internal server roles and on any computer where you will run the Lync Server administrative tools or Microsoft Lync Server 2013, Planning Tool.</span></span> <span data-ttu-id="77cae-116">对于 Lync Server 2013，必须先在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5，然后再安装 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="77cae-116">For Lync Server 2013, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="77cae-117">若要手动安装，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="77cae-117">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

<div>

## <a name="installing-microsoft-net-framework-45-on-servers-running-windows-server-2012"></a><span data-ttu-id="77cae-118">在运行 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="77cae-118">Installing Microsoft .NET Framework 4.5 on Servers Running Windows Server 2012</span></span>

<span data-ttu-id="77cae-119">在将运行 Lync Server 2013 和 Windows Server 2012 的服务器上安装 Microsoft .NET Framework 4.5 时，必须执行一个附加步骤。</span><span class="sxs-lookup"><span data-stu-id="77cae-119">When you install Microsoft .NET Framework 4.5 on servers that will run Lync Server 2013 and Windows Server 2012, you must perform one additional step.</span></span> <span data-ttu-id="77cae-120">安装 .NET Framework 4.5 后，请使用服务器管理器安装 HTTP 激活。</span><span class="sxs-lookup"><span data-stu-id="77cae-120">After .NET Framework 4.5 is installed, use Server Manager to install HTTP Activation.</span></span>

<span data-ttu-id="77cae-121">**在 Windows Server 2012 上安装 .NET 4.5 HTTP 激活**</span><span class="sxs-lookup"><span data-stu-id="77cae-121">**To Install .NET 4.5 HTTP Activation on Windows Server 2012**</span></span>

1.  <span data-ttu-id="77cae-122">从 "**开始**" 菜单中，单击 "**程序**"，然后单击 "**管理工具**"，然后单击 "**服务器管理器**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-122">From the **Start** menu, click **Programs**, then click **Administrative Tools**, then click **Server Manager**.</span></span>

2.  <span data-ttu-id="77cae-123">在服务器管理器中的 "**功能摘要**" 下，选择 "**添加功能**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-123">In Server Manager, under **Features Summary**, choose **Add Features**.</span></span>

3.  <span data-ttu-id="77cae-124">展开 **.Net Framework 4.5**。</span><span class="sxs-lookup"><span data-stu-id="77cae-124">Expand **.NET Framework 4.5**.</span></span>

4.  <span data-ttu-id="77cae-125">选择 " **WCF 激活**" （如果尚未选中）。</span><span class="sxs-lookup"><span data-stu-id="77cae-125">Select **WCF Activation** if it isn’t already selected.</span></span> <span data-ttu-id="77cae-126">然后选择 " **HTTP 激活**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-126">Then select **HTTP Activation**.</span></span>

5.  <span data-ttu-id="77cae-127">单击 "**下一步**" 并按照提示完成安装。</span><span class="sxs-lookup"><span data-stu-id="77cae-127">Click **Next** and follow the prompts to finish the installation.</span></span>

</div>

</div>

<div>

## <a name="windows-identity-foundation"></a><span data-ttu-id="77cae-128">Windows Identity Foundation</span><span class="sxs-lookup"><span data-stu-id="77cae-128">Windows Identity Foundation</span></span>

<span data-ttu-id="77cae-129">Lync Server 2013 中的**Windows Identity foundation**需要安装 Windows identity foundation 才能支持服务器到服务器身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="77cae-129">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="77cae-130">Windows Server 2008 R2 和 Windows Server 2012 需要不同的步骤来安装 Windows 识别基础。</span><span class="sxs-lookup"><span data-stu-id="77cae-130">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="77cae-131">从以下列表中选择服务器操作系统：</span><span class="sxs-lookup"><span data-stu-id="77cae-131">Select your server operating system from the following list:</span></span>

  - <span data-ttu-id="77cae-132">Windows server 2008 R2 For Windows Server 2008 R2，请检查它是否已安装在你的计算机上。</span><span class="sxs-lookup"><span data-stu-id="77cae-132">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="77cae-133">若要执行此操作，请转到 "**添加/删除程序**"、"**查看已安装的更新**"，然后在**Windows**中查看 "输入**windows Identity Foundation （KB974405）**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-133">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="77cae-134">有关安装 Windows Identity Foundation 的详细信息， [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。</span><span class="sxs-lookup"><span data-stu-id="77cae-134">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>

  - <span data-ttu-id="77cae-135">Windows server 2012 For Windows Server 2012，可使用**服务器管理器**安装 Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="77cae-135">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="77cae-136">在服务器管理器 "**添加角色和功能" 向导**中，选择 "**功能**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-136">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="77cae-137">从列表中选择**Windows Identity Foundation 3.5** 。</span><span class="sxs-lookup"><span data-stu-id="77cae-137">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="77cae-138">单击 "**下一步**"，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-138">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="additional-software-for-all-front-end-servers-and-standard-edition-servers"></a><span data-ttu-id="77cae-139">适用于所有前端服务器和标准版服务器的其他软件</span><span class="sxs-lookup"><span data-stu-id="77cae-139">Additional Software for All Front End Servers and Standard Edition Servers</span></span>

<span data-ttu-id="77cae-140">所有前端服务器和标准版服务器还必须运行具有特定模块的 Internet 信息服务（IIS）。</span><span class="sxs-lookup"><span data-stu-id="77cae-140">All Front End Servers and Standard Edition servers must also run Internet Information Services (IIS) with certain modules.</span></span> <span data-ttu-id="77cae-141">此外，所有前端服务器和标准版服务器（可在其中部署会议、呼叫驻留应用程序、公告或响应组）都必须运行 Windows Media 格式运行时。</span><span class="sxs-lookup"><span data-stu-id="77cae-141">Additionally, all Front End Servers and Standard Edition servers where conferencing, Call Park application, Announcement, or Response Groups are deployed must run Windows Media Format Runtime.</span></span>

<div>

## <a name="internet-information-services-iis"></a><span data-ttu-id="77cae-142">Internet 信息服务 (IIS)</span><span class="sxs-lookup"><span data-stu-id="77cae-142">Internet Information Services (IIS)</span></span>

<span data-ttu-id="77cae-143">前端服务器和标准版服务器必须运行 Internet 信息服务（IIS），其中包含以下模块：</span><span class="sxs-lookup"><span data-stu-id="77cae-143">Front End Servers and Standard Edition servers must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="77cae-144">静态内容</span><span class="sxs-lookup"><span data-stu-id="77cae-144">Static Content</span></span>

  - <span data-ttu-id="77cae-145">默认文档</span><span class="sxs-lookup"><span data-stu-id="77cae-145">Default Document</span></span>

  - <span data-ttu-id="77cae-146">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="77cae-146">HTTP Errors</span></span>

  - <span data-ttu-id="77cae-147">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="77cae-147">ASP.NET</span></span>

  - <span data-ttu-id="77cae-148">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="77cae-148">.NET Extensibility</span></span>

  - <span data-ttu-id="77cae-149">Internet 服务器 API （ISAPI）扩展</span><span class="sxs-lookup"><span data-stu-id="77cae-149">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="77cae-150">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="77cae-150">ISAPI Filters</span></span>

  - <span data-ttu-id="77cae-151">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="77cae-151">HTTP Logging</span></span>

  - <span data-ttu-id="77cae-152">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="77cae-152">Logging Tools</span></span>

  - <span data-ttu-id="77cae-153">跟踪</span><span class="sxs-lookup"><span data-stu-id="77cae-153">Tracing</span></span>

  - <span data-ttu-id="77cae-154">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="77cae-154">Windows Authentication</span></span>

  - <span data-ttu-id="77cae-155">请求筛选</span><span class="sxs-lookup"><span data-stu-id="77cae-155">Request Filtering</span></span>

  - <span data-ttu-id="77cae-156">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="77cae-156">Static Content Compression</span></span>

  - <span data-ttu-id="77cae-157">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="77cae-157">Dynamic Content Compression</span></span>

  - <span data-ttu-id="77cae-158">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="77cae-158">IIS Management Console</span></span>

  - <span data-ttu-id="77cae-159">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="77cae-159">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="77cae-160">匿名身份验证（在安装 IIS 时默认安装。）</span><span class="sxs-lookup"><span data-stu-id="77cae-160">Anonymous Authentication (this is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="77cae-161">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="77cae-161">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="windows-media-format-runtime-and-windows-desktop-experience"></a><span data-ttu-id="77cae-162">Windows Media 格式运行时和 Windows 桌面体验</span><span class="sxs-lookup"><span data-stu-id="77cae-162">Windows Media Format Runtime and Windows Desktop Experience</span></span>

<span data-ttu-id="77cae-163">**Windows 桌面体验**部署会议的所有前端服务器和标准版服务器都必须安装 Windows Media 格式运行时，但 Windows 桌面体验中安装的 windows Server 2012 除外。</span><span class="sxs-lookup"><span data-stu-id="77cae-163">**Windows Desktop Experience** All Front End Servers and Standard Edition servers where conferencing will be deployed must have the Windows Media Format Runtime installed, which, except for Windows Server 2012 is installed as part of the Windows desktop experience.</span></span> <span data-ttu-id="77cae-164">Windows Server 2012 需要 Microsoft Media Foundation。</span><span class="sxs-lookup"><span data-stu-id="77cae-164">Windows Server 2012 requires Microsoft Media Foundation.</span></span> <span data-ttu-id="77cae-165">若要运行 windows Media 音频（.wma）文件，需要 Windows Media Format Runtime 才能运行通知和音乐的 "呼叫寄存"、"通知" 和 "响应" 组应用程序。</span><span class="sxs-lookup"><span data-stu-id="77cae-165">The Windows Media Format Runtime is required to run the Windows Media Audio (.wma) files that the Call Park, Announcement, and Response Group applications play for announcements and music.</span></span>

<span data-ttu-id="77cae-166">我们建议你在安装 Lync Server 2013 之前安装 Windows 桌面体验。</span><span class="sxs-lookup"><span data-stu-id="77cae-166">We recommend that you install Windows desktop experience before you install Lync Server 2013.</span></span> <span data-ttu-id="77cae-167">如果 Lync Server 2013 在服务器上找不到此软件，它将提示您安装它，然后必须重新启动服务器才能完成安装。</span><span class="sxs-lookup"><span data-stu-id="77cae-167">If Lync Server 2013 does not find this software on the server, it will prompt you to install it, and then you must restart the server to complete installation.</span></span>

</div>

</div>

<div>

## <a name="additional-software-for-front-end-servers-and-standard-edition-servers-running-on-windows-server-2012"></a><span data-ttu-id="77cae-168">在 Windows Server 2012 上运行的前端服务器和标准版服务器的附加软件</span><span class="sxs-lookup"><span data-stu-id="77cae-168">Additional Software for Front End Servers and Standard Edition Servers Running on Windows Server 2012</span></span>

<span data-ttu-id="77cae-169">前端服务器需要安装 .NET 3.5，默认情况下不会在 Windows Server 2012 上安装。</span><span class="sxs-lookup"><span data-stu-id="77cae-169">Front End Servers require .NET 3.5, which is not installed by default on Windows Server 2012.</span></span> <span data-ttu-id="77cae-170">若要安装，请将 Windows Server 2012 安装媒体置于驱动器 D 中，然后键入以下内容：</span><span class="sxs-lookup"><span data-stu-id="77cae-170">To install it, put your Windows Server 2012 installation media in Drive D and type the following:</span></span>

    Add-WindowsFeature RSAT-ADDS, Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Compat, Desktop-Experience, Telnet-Client, BITS -Source D:\sources\sxs

<span data-ttu-id="77cae-171">有关在运行 Windows Server 2012 的服务器上安装 .NET 3.5 的详细信息，请参阅 "Microsoft .NET Framework 3.5 <https://go.microsoft.com/fwlink/p/?linkid=275032>部署注意事项"。</span><span class="sxs-lookup"><span data-stu-id="77cae-171">For details about installing .NET 3.5 on servers running Windows Server 2012, see "Microsoft .NET Framework 3.5 Deployment Considerations" at <https://go.microsoft.com/fwlink/p/?linkid=275032>.</span></span>

</div>

<div>

## <a name="additional-software-for-directors"></a><span data-ttu-id="77cae-172">适用于董事的其他软件</span><span class="sxs-lookup"><span data-stu-id="77cae-172">Additional Software for Directors</span></span>

<span data-ttu-id="77cae-173">Director 必须运行 Internet Information Services （IIS），其中包含以下模块：</span><span class="sxs-lookup"><span data-stu-id="77cae-173">Directors must run Internet Information Services (IIS), with the following modules:</span></span>

  - <span data-ttu-id="77cae-174">静态内容</span><span class="sxs-lookup"><span data-stu-id="77cae-174">Static Content</span></span>

  - <span data-ttu-id="77cae-175">默认文档</span><span class="sxs-lookup"><span data-stu-id="77cae-175">Default Document</span></span>

  - <span data-ttu-id="77cae-176">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="77cae-176">HTTP Errors</span></span>

  - <span data-ttu-id="77cae-177">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="77cae-177">ASP.NET</span></span>

  - <span data-ttu-id="77cae-178">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="77cae-178">.NET Extensibility</span></span>

  - <span data-ttu-id="77cae-179">Internet 服务器 API （ISAPI）扩展</span><span class="sxs-lookup"><span data-stu-id="77cae-179">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="77cae-180">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="77cae-180">ISAPI Filters</span></span>

  - <span data-ttu-id="77cae-181">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="77cae-181">HTTP Logging</span></span>

  - <span data-ttu-id="77cae-182">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="77cae-182">Logging Tools</span></span>

  - <span data-ttu-id="77cae-183">跟踪</span><span class="sxs-lookup"><span data-stu-id="77cae-183">Tracing</span></span>

  - <span data-ttu-id="77cae-184">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="77cae-184">Windows Authentication</span></span>

  - <span data-ttu-id="77cae-185">请求筛选</span><span class="sxs-lookup"><span data-stu-id="77cae-185">Request Filtering</span></span>

  - <span data-ttu-id="77cae-186">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="77cae-186">Static Content Compression</span></span>

  - <span data-ttu-id="77cae-187">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="77cae-187">IIS Management Console</span></span>

  - <span data-ttu-id="77cae-188">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="77cae-188">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="77cae-189">匿名身份验证（在安装 IIS 时默认安装。）</span><span class="sxs-lookup"><span data-stu-id="77cae-189">Anonymous Authentication (This is installed by default when IIS is installed.)</span></span>

  - <span data-ttu-id="77cae-190">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="77cae-190">Client Certificate Mapping Authentication</span></span>

</div>

<div>

## <a name="additional-software-for-persistent-chat-front-end-servers"></a><span data-ttu-id="77cae-191">适用于持久聊天前端服务器的其他软件</span><span class="sxs-lookup"><span data-stu-id="77cae-191">Additional Software for Persistent Chat Front End Servers</span></span>

<span data-ttu-id="77cae-192">持久聊天前端服务器必须运行消息队列（也称为 MSMQ），它是 Windows Server 的一个组件。</span><span class="sxs-lookup"><span data-stu-id="77cae-192">Persistent Chat Front End Servers must run Message Queuing (also known as MSMQ), which is a component of Windows Server.</span></span>

<span data-ttu-id="77cae-193">有关启用 MSMQ 的信息，请[单击此处。](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span><span class="sxs-lookup"><span data-stu-id="77cae-193">For information on enabling MSMQ, [click here.](https://technet.microsoft.com/en-us/library/cc771474.aspx)</span></span>

</div>

<div>

## <a name="additional-software-for-edge-servers"></a><span data-ttu-id="77cae-194">适用于边缘服务器的其他软件</span><span class="sxs-lookup"><span data-stu-id="77cae-194">Additional Software for Edge Servers</span></span>

<span data-ttu-id="77cae-195">边缘服务器需要以下软件：</span><span class="sxs-lookup"><span data-stu-id="77cae-195">Edge Servers require the following software:</span></span>

  - <span data-ttu-id="77cae-196">运行 Lync Server 2013 的每台服务器必须安装正确版本的 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="77cae-196">Each server running Lync Server 2013 must have the correct release of Windows PowerShell 3.0 installed.</span></span> <span data-ttu-id="77cae-197">有关详细信息，请参阅[安装 Lync Server 2013 的 Windows PowerShell 3.0](lync-server-2013-installing-windows-powershell-3-0.md)。</span><span class="sxs-lookup"><span data-stu-id="77cae-197">For details, see [Installing Windows PowerShell 3.0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md).</span></span>

  - <span data-ttu-id="77cae-198">Lync 服务器需要 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="77cae-198">Lync Server requires Microsoft .NET Framework 4.5.</span></span> <span data-ttu-id="77cae-199">对于安装在 Windows Server 2008 R2 上的 Lync Server 2013，必须在安装 Lync Server 2013 之前在服务器上手动安装64位版本的 Microsoft .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="77cae-199">For Lync Server 2013 installed on Windows Server 2008 R2, you must manually install the 64-bit edition of Microsoft .NET Framework 4.5 on the server prior to installing Lync Server 2013.</span></span> <span data-ttu-id="77cae-200">若要手动安装，请从 Microsoft 下载中心下载 Microsoft .NET 4.5 Framework[https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span><span class="sxs-lookup"><span data-stu-id="77cae-200">To manually install it, download the Microsoft .NET 4.5 Framework from the Microsoft Download Center at [https://go.microsoft.com/fwlink/p/?LinkId=268529](https://go.microsoft.com/fwlink/p/?linkid=268529)</span></span>

  - <span data-ttu-id="77cae-201">Lync Server 2013 中的**Windows Identity foundation**需要安装 Windows identity foundation 才能支持服务器到服务器身份验证方案。</span><span class="sxs-lookup"><span data-stu-id="77cae-201">**Windows Identity Foundation** in Lync Server 2013 requires the installation of Windows Identity Foundation in order to support server to server authentication scenarios.</span></span> <span data-ttu-id="77cae-202">Windows Server 2008 R2 和 Windows Server 2012 需要不同的步骤来安装 Windows 识别基础。</span><span class="sxs-lookup"><span data-stu-id="77cae-202">Windows Server 2008 R2 and Windows Server 2012 require different procedures to install the Windows Identify Foundation.</span></span> <span data-ttu-id="77cae-203">从以下列表中选择服务器操作系统：</span><span class="sxs-lookup"><span data-stu-id="77cae-203">Select your server operating system from the following list:</span></span>
    
      - <span data-ttu-id="77cae-204">Windows server 2008 R2 For Windows Server 2008 R2，请检查它是否已安装在你的计算机上。</span><span class="sxs-lookup"><span data-stu-id="77cae-204">Windows Server 2008 R2   For Windows Server 2008 R2, you check to see if it has already been installed on your computer.</span></span> <span data-ttu-id="77cae-205">若要执行此操作，请转到 "**添加/删除程序**"、"**查看已安装的更新**"，然后在**Windows**中查看 "输入**windows Identity Foundation （KB974405）**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-205">To do this, go to **Add/Remove Programs**, **View Installed Updates**, and look under **Windows** for the entry **Windows Identity Foundation (KB974405)**.</span></span> <span data-ttu-id="77cae-206">有关安装 Windows Identity Foundation 的详细信息， [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657)请参阅。</span><span class="sxs-lookup"><span data-stu-id="77cae-206">For details about installing Windows Identity Foundation, see [https://go.microsoft.com/fwlink/p/?linkId=204657](https://go.microsoft.com/fwlink/p/?linkid=204657).</span></span>
    
      - <span data-ttu-id="77cae-207">Windows server 2012 For Windows Server 2012，可使用**服务器管理器**安装 Windows Identity Foundation。</span><span class="sxs-lookup"><span data-stu-id="77cae-207">Windows Server 2012   For Windows Server 2012, you use **Server Manager** to install the Windows Identity Foundation.</span></span> <span data-ttu-id="77cae-208">在服务器管理器 "**添加角色和功能" 向导**中，选择 "**功能**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-208">In the Server Manager **Add Roles and Features Wizard**, select **Features**.</span></span> <span data-ttu-id="77cae-209">从列表中选择**Windows Identity Foundation 3.5** 。</span><span class="sxs-lookup"><span data-stu-id="77cae-209">Select **Windows Identity Foundation 3.5** from the list.</span></span> <span data-ttu-id="77cae-210">单击 "**下一步**"，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="77cae-210">Click **Next**, then click **Install**.</span></span>

</div>

<div>

## <a name="do-not-install-layered-socket-providers-on-media-servers"></a><span data-ttu-id="77cae-211">不要在媒体服务器上安装分层套接字提供程序</span><span class="sxs-lookup"><span data-stu-id="77cae-211">Do Not Install Layered Socket Providers on Media Servers</span></span>

<span data-ttu-id="77cae-212">不要在任何前端服务器或独立的中介服务器上安装任何 Microsoft Internet 安全和加速（ISA）服务器客户端软件或任何其他 Winsock 分层服务提供程序（LSP）软件。</span><span class="sxs-lookup"><span data-stu-id="77cae-212">Do not install any Microsoft Internet Security and Acceleration (ISA) Server client software, or any other Winsock Layered Service Providers (LSP) software, on any Front End Servers or stand-alone Mediation Servers.</span></span> <span data-ttu-id="77cae-213">安装此软件可能会导致媒体流量较差。</span><span class="sxs-lookup"><span data-stu-id="77cae-213">Installing this software could cause poor media traffic performance.</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="77cae-214">另请参阅</span><span class="sxs-lookup"><span data-stu-id="77cae-214">See Also</span></span>


[<span data-ttu-id="77cae-215">Lync Server 2013 中的管理工具软件要求</span><span class="sxs-lookup"><span data-stu-id="77cae-215">Administrative tools software requirements in Lync Server 2013</span></span>](lync-server-2013-administrative-tools-software-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

