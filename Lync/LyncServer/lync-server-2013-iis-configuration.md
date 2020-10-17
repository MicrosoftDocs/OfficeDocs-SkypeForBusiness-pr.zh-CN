---
title: Lync Server 2013： IIS 配置
description: Lync Server 2013： IIS 配置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 901aca7bf5ff8824b54e93754569a6ef5defc10e
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554868"
---
# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="24b10-103">Lync Server 2013 中的 IIS 配置</span><span class="sxs-lookup"><span data-stu-id="24b10-103">IIS configuration in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="24b10-104">_**上次修改的主题：** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="24b10-104">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="24b10-105">若要成功完成此过程，您应至少以本地管理员和域用户的身份登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="24b10-105">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="24b10-106">在为 Lync Server 2013、Standard Edition 或第一台前端服务器配置和安装 Lync server 的前端服务器之前，请为 Internet 信息服务 (IIS) 安装和配置服务器角色和 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="24b10-106">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="24b10-107">如果您的组织要求在除系统驱动器之外的驱动器上查找 IIS 和所有 Web 服务，则在最初安装 Lync Server 2013 管理工具时，可以在 "安装程序" 对话框中更改 Lync Server 2013 文件的安装位置路径。</span><span class="sxs-lookup"><span data-stu-id="24b10-107">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="24b10-108">安装 IIS 之前安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="24b10-108">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="24b10-109">如果将安装文件安装到此路径（包括 OCSCore.msi），则其余的 Lync Server 2013 文件也将部署到此驱动器。</span><span class="sxs-lookup"><span data-stu-id="24b10-109">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="24b10-110">有关 dtails，请参阅 <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理工具</A>。</span><span class="sxs-lookup"><span data-stu-id="24b10-110">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="24b10-111">有关如何在安装 IIS 时重新定位由 Windows Server Manager 部署的 INETPUB 的详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。</span><span class="sxs-lookup"><span data-stu-id="24b10-111">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="24b10-112">下表指示必需的 IIS 7.5 角色服务。</span><span class="sxs-lookup"><span data-stu-id="24b10-112">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="24b10-113">IIS 7.5 角色服务</span><span class="sxs-lookup"><span data-stu-id="24b10-113">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24b10-114">角色标题</span><span class="sxs-lookup"><span data-stu-id="24b10-114">Role Heading</span></span></th>
<th><span data-ttu-id="24b10-115">角色服务</span><span class="sxs-lookup"><span data-stu-id="24b10-115">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24b10-116">已安装常见 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-116">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="24b10-117">静态内容</span><span class="sxs-lookup"><span data-stu-id="24b10-117">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-118">已安装常见 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-118">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="24b10-119">默认文档</span><span class="sxs-lookup"><span data-stu-id="24b10-119">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-120">已安装常见 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-120">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="24b10-121">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="24b10-121">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-122">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-122">Application development</span></span></p></td>
<td><p><span data-ttu-id="24b10-123">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="24b10-123">ASP.NET</span></span></p>
<p><span data-ttu-id="24b10-124">Windows Server 2012 还需要安装 ASP. NET 4。5</span><span class="sxs-lookup"><span data-stu-id="24b10-124">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-125">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-125">Application development</span></span></p></td>
<td><p><span data-ttu-id="24b10-126">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="24b10-126">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-127">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-127">Application development</span></span></p></td>
<td><p><span data-ttu-id="24b10-128">Internet Server API (ISAPI) 扩展</span><span class="sxs-lookup"><span data-stu-id="24b10-128">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-129">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-129">Application development</span></span></p></td>
<td><p><span data-ttu-id="24b10-130">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="24b10-130">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-131">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="24b10-131">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="24b10-132">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="24b10-132">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-133">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="24b10-133">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="24b10-134">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="24b10-134">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-135">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="24b10-135">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="24b10-136">追踪</span><span class="sxs-lookup"><span data-stu-id="24b10-136">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-137">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-137">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-138">默认情况下，安装并启用匿名身份验证 () </span><span class="sxs-lookup"><span data-stu-id="24b10-138">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-139">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-139">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-140">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="24b10-140">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-141">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-141">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-142">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="24b10-142">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-143">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-143">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-144">请求筛选</span><span class="sxs-lookup"><span data-stu-id="24b10-144">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-145">性能</span><span class="sxs-lookup"><span data-stu-id="24b10-145">Performance</span></span></p></td>
<td><p><span data-ttu-id="24b10-146">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="24b10-146">Static content compression</span></span></p>
<p><span data-ttu-id="24b10-147">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="24b10-147">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-148">管理工具</span><span class="sxs-lookup"><span data-stu-id="24b10-148">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="24b10-149">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="24b10-149">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-150">管理工具</span><span class="sxs-lookup"><span data-stu-id="24b10-150">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="24b10-151">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="24b10-151">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24b10-152">在 Windows Server 2008 R2 SP1 x64 操作系统上，您可以使用 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="24b10-152">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="24b10-153">必须先导入 ServerManager 模块，然后再安装 IIS 7.5 角色和角色服务。</span><span class="sxs-lookup"><span data-stu-id="24b10-153">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="24b10-154">默认情况下，将使用 IIS 服务器角色安装匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="24b10-154">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="24b10-155">您可以在安装 IIS 之后管理匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="24b10-155">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="24b10-156">有关详细信息，请参阅中的 "启用匿名身份验证 (IIS 7) " <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> 。</span><span class="sxs-lookup"><span data-stu-id="24b10-156">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="24b10-157">下表指示 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服务。</span><span class="sxs-lookup"><span data-stu-id="24b10-157">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="24b10-158">对于 Windows Server 2012 和 Windows Server 2012 R2，Add-WindowsFeature cmdlet 已被 Install-WindowsFeature cmdlet 替代。</span><span class="sxs-lookup"><span data-stu-id="24b10-158">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="24b10-159">有关详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-add-windowsfeature</A>。</span><span class="sxs-lookup"><span data-stu-id="24b10-159">For details, see <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="24b10-160">IIS 8.0 和 IIS 8.5 角色服务</span><span class="sxs-lookup"><span data-stu-id="24b10-160">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="24b10-161">角色标题</span><span class="sxs-lookup"><span data-stu-id="24b10-161">Role Heading</span></span></th>
<th><span data-ttu-id="24b10-162">角色服务</span><span class="sxs-lookup"><span data-stu-id="24b10-162">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="24b10-163">Web 服务器 (IIS)</span><span class="sxs-lookup"><span data-stu-id="24b10-163">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="24b10-164">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="24b10-164">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-165">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-165">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-166">默认文档</span><span class="sxs-lookup"><span data-stu-id="24b10-166">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-167">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-167">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-168">目录浏览</span><span class="sxs-lookup"><span data-stu-id="24b10-168">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-169">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-169">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-170">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="24b10-170">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-171">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-171">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-172">静态内容</span><span class="sxs-lookup"><span data-stu-id="24b10-172">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-173">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-173">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-174">HTTP 重定向</span><span class="sxs-lookup"><span data-stu-id="24b10-174">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-175">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="24b10-175">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="24b10-176">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="24b10-176">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-177">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="24b10-177">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="24b10-178">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="24b10-178">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-179">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="24b10-179">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="24b10-180">请求监视器</span><span class="sxs-lookup"><span data-stu-id="24b10-180">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-181">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="24b10-181">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="24b10-182">追踪</span><span class="sxs-lookup"><span data-stu-id="24b10-182">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-183">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-183">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-184">请求筛选</span><span class="sxs-lookup"><span data-stu-id="24b10-184">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-185">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-185">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-186">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="24b10-186">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-187">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-187">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-188">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="24b10-188">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-189">安全性</span><span class="sxs-lookup"><span data-stu-id="24b10-189">Security</span></span></p></td>
<td><p><span data-ttu-id="24b10-190">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="24b10-190">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-191">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-191">Application Development</span></span></p></td>
<td><p><span data-ttu-id="24b10-192">.Net 扩展性3。5</span><span class="sxs-lookup"><span data-stu-id="24b10-192">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-193">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-193">Application Development</span></span></p></td>
<td><p><span data-ttu-id="24b10-194">.Net 扩展性4。5</span><span class="sxs-lookup"><span data-stu-id="24b10-194">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-195">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-195">Application Development</span></span></p></td>
<td><p><span data-ttu-id="24b10-196">ASP.Net 3。5</span><span class="sxs-lookup"><span data-stu-id="24b10-196">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-197">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-197">Application Development</span></span></p></td>
<td><p><span data-ttu-id="24b10-198">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="24b10-198">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-199">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-199">Application Development</span></span></p></td>
<td><p><span data-ttu-id="24b10-200">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="24b10-200">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-201">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-201">Application Development</span></span></p></td>
<td><p><span data-ttu-id="24b10-202">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="24b10-202">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-203">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="24b10-203">Application Development</span></span></p></td>
<td><p><span data-ttu-id="24b10-204">服务器端包括</span><span class="sxs-lookup"><span data-stu-id="24b10-204">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-205">管理工具</span><span class="sxs-lookup"><span data-stu-id="24b10-205">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="24b10-206">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="24b10-206">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-207">管理工具</span><span class="sxs-lookup"><span data-stu-id="24b10-207">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="24b10-208">IIS 6 元数据库兼容性</span><span class="sxs-lookup"><span data-stu-id="24b10-208">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-209">管理工具</span><span class="sxs-lookup"><span data-stu-id="24b10-209">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="24b10-210">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="24b10-210">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-211">.Net 3.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-211">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-212">.Net 3.5 Framework</span><span class="sxs-lookup"><span data-stu-id="24b10-212">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-213">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-213">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-214">.Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="24b10-214">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-215">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-215">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-216">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="24b10-216">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-217">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-217">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-218">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="24b10-218">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-219">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="24b10-219">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="24b10-220">TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="24b10-220">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-221">后台智能传输服务</span><span class="sxs-lookup"><span data-stu-id="24b10-221">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="24b10-222">IIS 服务器扩展</span><span class="sxs-lookup"><span data-stu-id="24b10-222">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-223">墨迹和手写服务</span><span class="sxs-lookup"><span data-stu-id="24b10-223">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="24b10-224">墨迹和手写服务</span><span class="sxs-lookup"><span data-stu-id="24b10-224">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-225">媒体基础</span><span class="sxs-lookup"><span data-stu-id="24b10-225">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="24b10-226">媒体基础</span><span class="sxs-lookup"><span data-stu-id="24b10-226">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-227">用户界面和基础结构</span><span class="sxs-lookup"><span data-stu-id="24b10-227">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="24b10-228">图形管理工具和基础结构</span><span class="sxs-lookup"><span data-stu-id="24b10-228">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-229">用户界面和基础结构</span><span class="sxs-lookup"><span data-stu-id="24b10-229">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="24b10-230">桌面体验</span><span class="sxs-lookup"><span data-stu-id="24b10-230">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-231">用户界面和基础结构</span><span class="sxs-lookup"><span data-stu-id="24b10-231">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="24b10-232">服务器图形命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="24b10-232">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-233">Windows Identity Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="24b10-233">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="24b10-234">Windows Identity Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="24b10-234">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="24b10-235">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="24b10-235">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="24b10-236">进程模型</span><span class="sxs-lookup"><span data-stu-id="24b10-236">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="24b10-237">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="24b10-237">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="24b10-238">配置 Api</span><span class="sxs-lookup"><span data-stu-id="24b10-238">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="24b10-239">在 Windows Server 2012 和 Windows Server 2012 R2 中，可以使用 Windows PowerShell 3.0 安装 IIS 要求。</span><span class="sxs-lookup"><span data-stu-id="24b10-239">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="24b10-240">使用 Windows PowerShell 3.0 中的 ServerManager 模块，请键入：</span><span class="sxs-lookup"><span data-stu-id="24b10-240">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="24b10-241">Windows Server 2012 的新版本是用于定义可在何处找到 Windows Server 2012 源媒体的– Source 参数。</span><span class="sxs-lookup"><span data-stu-id="24b10-241">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="24b10-242">可以将媒体定义为 DVD 驱动器 (例如，D:\Sources\Sxs) 或网络共享（媒体文件已复制） (例如， \\ fileserver\windows2012\sources\Sxs) 。</span><span class="sxs-lookup"><span data-stu-id="24b10-242">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="24b10-243">另请参阅</span><span class="sxs-lookup"><span data-stu-id="24b10-243">See Also</span></span>


[<span data-ttu-id="24b10-244">Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="24b10-244">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

