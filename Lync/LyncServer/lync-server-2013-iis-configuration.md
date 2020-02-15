---
title: Lync Server 2013： IIS 配置
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
ms.openlocfilehash: 65d9d4f61fabdca7a3f9cb4808efe952ec7ce3b2
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037874"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a><span data-ttu-id="57d85-102">Lync Server 2013 中的 IIS 配置</span><span class="sxs-lookup"><span data-stu-id="57d85-102">IIS configuration in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="57d85-103">_**上次修改的主题：** 2014-02-17_</span><span class="sxs-lookup"><span data-stu-id="57d85-103">_**Topic Last Modified:** 2014-02-17_</span></span>

<span data-ttu-id="57d85-104">若要成功完成此过程，您应至少以本地管理员和域用户的身份登录到服务器。</span><span class="sxs-lookup"><span data-stu-id="57d85-104">To successfully complete this procedure, you should be logged on to the server minimally as a local administrator and a domain user.</span></span>

<span data-ttu-id="57d85-105">在为 Lync Server 2013、Standard Edition 或第一台前端服务器配置和安装前端服务器之前，请为 Internet Information Services （IIS）安装和配置服务器角色和 Web 服务。</span><span class="sxs-lookup"><span data-stu-id="57d85-105">Before you configure and install the Front End Server for Lync Server 2013, Standard Edition or the first Front End Server in a pool, you install and configure the server role and Web Services for Internet Information Services (IIS).</span></span>

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="57d85-106">如果您的组织要求在除系统驱动器之外的驱动器上查找 IIS 和所有 Web 服务，则在最初安装 Lync Server 2013 时，可以在 "安装程序" 对话框中更改 Lync Server 2013 文件的安装位置路径。管理工具。</span><span class="sxs-lookup"><span data-stu-id="57d85-106">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server 2013 files in the Setup dialog box when you initially install the Lync Server 2013 Administrative tools.</span></span> <span data-ttu-id="57d85-107">安装 IIS 之前安装管理工具。</span><span class="sxs-lookup"><span data-stu-id="57d85-107">You install the Administrative tools before installing IIS.</span></span> <span data-ttu-id="57d85-108">如果将安装文件安装到此路径（包括 OCSCore），则其余的 Lync Server 2013 文件也将部署到此驱动器。</span><span class="sxs-lookup"><span data-stu-id="57d85-108">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server 2013 files will be deployed to this drive as well.</span></span> <span data-ttu-id="57d85-109">有关 dtails，请参阅<A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 管理工具</A>。</span><span class="sxs-lookup"><span data-stu-id="57d85-109">For dtails, see <A href="lync-server-2013-install-lync-server-administrative-tools.md">Install Lync Server 2013 administrative tools</A>.</span></span> <span data-ttu-id="57d85-110">有关如何在安装 IIS 时重新定位由 Windows Server Manager 部署的 INETPUB 的详细信息<A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>，请参阅。</span><span class="sxs-lookup"><span data-stu-id="57d85-110">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>



</div>

<span data-ttu-id="57d85-111">下表指示必需的 IIS 7.5 角色服务。</span><span class="sxs-lookup"><span data-stu-id="57d85-111">The following table indicates the required IIS 7.5 role services.</span></span>

### <a name="iis-75-role-services"></a><span data-ttu-id="57d85-112">IIS 7.5 角色服务</span><span class="sxs-lookup"><span data-stu-id="57d85-112">IIS 7.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57d85-113">角色标题</span><span class="sxs-lookup"><span data-stu-id="57d85-113">Role Heading</span></span></th>
<th><span data-ttu-id="57d85-114">角色服务</span><span class="sxs-lookup"><span data-stu-id="57d85-114">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57d85-115">已安装常见 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-115">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="57d85-116">静态内容</span><span class="sxs-lookup"><span data-stu-id="57d85-116">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-117">已安装常见 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-117">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="57d85-118">默认文档</span><span class="sxs-lookup"><span data-stu-id="57d85-118">Default document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-119">已安装常见 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-119">Common HTTP features installed</span></span></p></td>
<td><p><span data-ttu-id="57d85-120">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="57d85-120">HTTP errors</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-121">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-121">Application development</span></span></p></td>
<td><p><span data-ttu-id="57d85-122">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="57d85-122">ASP.NET</span></span></p>
<p><span data-ttu-id="57d85-123">Windows Server 2012 还需要安装 ASP. NET 4。5</span><span class="sxs-lookup"><span data-stu-id="57d85-123">Windows Server 2012 also requires ASP.NET4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-124">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-124">Application development</span></span></p></td>
<td><p><span data-ttu-id="57d85-125">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="57d85-125">.NET extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-126">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-126">Application development</span></span></p></td>
<td><p><span data-ttu-id="57d85-127">Internet Server API （ISAPI）扩展</span><span class="sxs-lookup"><span data-stu-id="57d85-127">Internet Server API (ISAPI) extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-128">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-128">Application development</span></span></p></td>
<td><p><span data-ttu-id="57d85-129">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="57d85-129">ISAPI filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-130">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="57d85-130">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="57d85-131">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="57d85-131">HTTP logging</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-132">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="57d85-132">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="57d85-133">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="57d85-133">Logging tools</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-134">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="57d85-134">Health and diagnostics</span></span></p></td>
<td><p><span data-ttu-id="57d85-135">追踪</span><span class="sxs-lookup"><span data-stu-id="57d85-135">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-136">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-136">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-137">匿名身份验证（默认情况下已安装并启用）</span><span class="sxs-lookup"><span data-stu-id="57d85-137">Anonymous authentication (installed and enabled by default)</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-138">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-138">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-139">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="57d85-139">Windows authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-140">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-140">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-141">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="57d85-141">Client Certificate Mapping authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-142">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-142">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-143">请求筛选</span><span class="sxs-lookup"><span data-stu-id="57d85-143">Request filtering</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-144">性能</span><span class="sxs-lookup"><span data-stu-id="57d85-144">Performance</span></span></p></td>
<td><p><span data-ttu-id="57d85-145">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="57d85-145">Static content compression</span></span></p>
<p><span data-ttu-id="57d85-146">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="57d85-146">Dynamic content compression</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-147">管理工具</span><span class="sxs-lookup"><span data-stu-id="57d85-147">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="57d85-148">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="57d85-148">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-149">管理工具</span><span class="sxs-lookup"><span data-stu-id="57d85-149">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="57d85-150">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="57d85-150">IIS Management Scripts and Tools</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="57d85-151">在 Windows Server 2008 R2 SP1 x64 操作系统上，您可以使用 Windows PowerShell 2.0。</span><span class="sxs-lookup"><span data-stu-id="57d85-151">On the Windows Server 2008 R2 SP1 x64 operating system, you can use Windows PowerShell 2.0.</span></span> <span data-ttu-id="57d85-152">必须先导入 ServerManager 模块，然后再安装 IIS 7.5 角色和角色服务。</span><span class="sxs-lookup"><span data-stu-id="57d85-152">You must first import the ServerManager module, and then install the IIS 7.5 role and role services.</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="57d85-153">默认情况下，将使用 IIS 服务器角色安装匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="57d85-153">Anonymous authentication is installed by default with the IIS server role.</span></span> <span data-ttu-id="57d85-154">您可以在安装 IIS 之后管理匿名身份验证。</span><span class="sxs-lookup"><span data-stu-id="57d85-154">You can manage anonymous authentication after the installation of IIS.</span></span> <span data-ttu-id="57d85-155">有关详细信息，请参阅处<A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>的 "启用匿名身份验证（IIS 7）"。</span><span class="sxs-lookup"><span data-stu-id="57d85-155">For details, see “Enable Anonymous Authentication (IIS 7)” at <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>.</span></span>



</div>

<span data-ttu-id="57d85-156">下表指示 Windows Server 2012 和 Windows Server 2012 R2 所需的 IIS 8.0 和 IIS 8.5 角色服务。</span><span class="sxs-lookup"><span data-stu-id="57d85-156">The following table indicates the required IIS 8.0 and IIS 8.5 role services for Windows Server 2012 and Windows Server 2012 R2.</span></span>

<div class=" ">


> [!NOTE]  
> <span data-ttu-id="57d85-157">对于 Windows Server 2012 和 Windows Server 2012 R2，已将 add-windowsfeature cmdlet 替换为 Install cmdlet。</span><span class="sxs-lookup"><span data-stu-id="57d85-157">For Windows Server 2012 and Windows Server 2012 R2, the Add-WindowsFeature cmdlet has been replaced by the Install-WindowsFeature cmdlet.</span></span> <span data-ttu-id="57d85-158">有关详细信息，请参阅<A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-add-windowsfeature</A>。</span><span class="sxs-lookup"><span data-stu-id="57d85-158">For details, see <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.</span></span>



</div>

### <a name="iis-80-and-iis-85-role-services"></a><span data-ttu-id="57d85-159">IIS 8.0 和 IIS 8.5 角色服务</span><span class="sxs-lookup"><span data-stu-id="57d85-159">IIS 8.0 and IIS 8.5 Role Services</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="57d85-160">角色标题</span><span class="sxs-lookup"><span data-stu-id="57d85-160">Role Heading</span></span></th>
<th><span data-ttu-id="57d85-161">角色服务</span><span class="sxs-lookup"><span data-stu-id="57d85-161">Role Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="57d85-162">Web 服务器 (IIS)</span><span class="sxs-lookup"><span data-stu-id="57d85-162">Web Server (IIS)</span></span></p></td>
<td><p><span data-ttu-id="57d85-163">Web 服务器</span><span class="sxs-lookup"><span data-stu-id="57d85-163">Web Server</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-164">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-164">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-165">默认文档</span><span class="sxs-lookup"><span data-stu-id="57d85-165">Default Document</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-166">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-166">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-167">目录浏览</span><span class="sxs-lookup"><span data-stu-id="57d85-167">Directory Browsing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-168">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-168">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-169">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="57d85-169">HTTP Errors</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-170">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-170">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-171">静态内容</span><span class="sxs-lookup"><span data-stu-id="57d85-171">Static content</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-172">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-172">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-173">HTTP 重定向</span><span class="sxs-lookup"><span data-stu-id="57d85-173">HTTP Redirection</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-174">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="57d85-174">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="57d85-175">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="57d85-175">HTTP Logging</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-176">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="57d85-176">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="57d85-177">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="57d85-177">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-178">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="57d85-178">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="57d85-179">请求监视器</span><span class="sxs-lookup"><span data-stu-id="57d85-179">Request Monitor</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-180">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="57d85-180">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="57d85-181">追踪</span><span class="sxs-lookup"><span data-stu-id="57d85-181">Tracing</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-182">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-182">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-183">请求筛选</span><span class="sxs-lookup"><span data-stu-id="57d85-183">Request Filtering</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-184">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-184">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-185">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="57d85-185">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-186">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-186">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-187">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="57d85-187">Client Certificate Mapping Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-188">安全性</span><span class="sxs-lookup"><span data-stu-id="57d85-188">Security</span></span></p></td>
<td><p><span data-ttu-id="57d85-189">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="57d85-189">Windows Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-190">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-190">Application Development</span></span></p></td>
<td><p><span data-ttu-id="57d85-191">.Net 扩展性3。5</span><span class="sxs-lookup"><span data-stu-id="57d85-191">.Net Extensibility 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-192">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-192">Application Development</span></span></p></td>
<td><p><span data-ttu-id="57d85-193">.Net 扩展性4。5</span><span class="sxs-lookup"><span data-stu-id="57d85-193">.Net Extensibility 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-194">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-194">Application Development</span></span></p></td>
<td><p><span data-ttu-id="57d85-195">ASP.Net 3。5</span><span class="sxs-lookup"><span data-stu-id="57d85-195">ASP.Net 3.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-196">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-196">Application Development</span></span></p></td>
<td><p><span data-ttu-id="57d85-197">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="57d85-197">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-198">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-198">Application Development</span></span></p></td>
<td><p><span data-ttu-id="57d85-199">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="57d85-199">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-200">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-200">Application Development</span></span></p></td>
<td><p><span data-ttu-id="57d85-201">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="57d85-201">ISAPI Filters</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-202">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="57d85-202">Application Development</span></span></p></td>
<td><p><span data-ttu-id="57d85-203">服务器端包括</span><span class="sxs-lookup"><span data-stu-id="57d85-203">Server Side Includes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-204">管理工具</span><span class="sxs-lookup"><span data-stu-id="57d85-204">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="57d85-205">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="57d85-205">IIS Management Console</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-206">管理工具</span><span class="sxs-lookup"><span data-stu-id="57d85-206">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="57d85-207">IIS 6 元数据库兼容性</span><span class="sxs-lookup"><span data-stu-id="57d85-207">IIS 6 Metabase compatibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-208">管理工具</span><span class="sxs-lookup"><span data-stu-id="57d85-208">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="57d85-209">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="57d85-209">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-210">.Net 3.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-210">.Net 3.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-211">.Net 3.5 Framework</span><span class="sxs-lookup"><span data-stu-id="57d85-211">.Net 3.5 Framework</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-212">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-212">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-213">.Net Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="57d85-213">.Net Framework 4.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-214">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-214">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-215">ASP.Net 4。5</span><span class="sxs-lookup"><span data-stu-id="57d85-215">ASP.Net 4.5</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-216">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-216">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-217">HTTP 激活</span><span class="sxs-lookup"><span data-stu-id="57d85-217">HTTP Activation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-218">.Net 4.5 Framework 功能</span><span class="sxs-lookup"><span data-stu-id="57d85-218">.Net 4.5 Framework Features</span></span></p></td>
<td><p><span data-ttu-id="57d85-219">TCP 端口共享</span><span class="sxs-lookup"><span data-stu-id="57d85-219">TCP Port Sharing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-220">后台智能传输服务</span><span class="sxs-lookup"><span data-stu-id="57d85-220">Background Intelligent Transfer Service</span></span></p></td>
<td><p><span data-ttu-id="57d85-221">IIS 服务器扩展</span><span class="sxs-lookup"><span data-stu-id="57d85-221">IIS Server Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-222">墨迹和手写服务</span><span class="sxs-lookup"><span data-stu-id="57d85-222">Ink and Handwriting Services</span></span></p></td>
<td><p><span data-ttu-id="57d85-223">墨迹和手写服务</span><span class="sxs-lookup"><span data-stu-id="57d85-223">Ink and Handwriting Services</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-224">媒体基础</span><span class="sxs-lookup"><span data-stu-id="57d85-224">Media Foundation</span></span></p></td>
<td><p><span data-ttu-id="57d85-225">媒体基础</span><span class="sxs-lookup"><span data-stu-id="57d85-225">Media Foundation</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-226">用户界面和基础结构</span><span class="sxs-lookup"><span data-stu-id="57d85-226">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="57d85-227">图形管理工具和基础结构</span><span class="sxs-lookup"><span data-stu-id="57d85-227">Graphical Management Tools and Infrastructure</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-228">用户界面和基础结构</span><span class="sxs-lookup"><span data-stu-id="57d85-228">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="57d85-229">桌面体验</span><span class="sxs-lookup"><span data-stu-id="57d85-229">Desktop Experience</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-230">用户界面和基础结构</span><span class="sxs-lookup"><span data-stu-id="57d85-230">User Interfaces and Infrastructure</span></span></p></td>
<td><p><span data-ttu-id="57d85-231">服务器图形命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="57d85-231">Server Graphical Shell</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-232">Windows Identity Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="57d85-232">Windows Identity Foundation 3.5</span></span></p></td>
<td><p><span data-ttu-id="57d85-233">Windows Identity Foundation 3。5</span><span class="sxs-lookup"><span data-stu-id="57d85-233">Windows Identity Foundation 3.5</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="57d85-234">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="57d85-234">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="57d85-235">进程模型</span><span class="sxs-lookup"><span data-stu-id="57d85-235">Process Model</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="57d85-236">Windows Process Activation Service</span><span class="sxs-lookup"><span data-stu-id="57d85-236">Windows Process Activation Service</span></span></p></td>
<td><p><span data-ttu-id="57d85-237">配置 Api</span><span class="sxs-lookup"><span data-stu-id="57d85-237">Configuration APIs</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="57d85-238">在 Windows Server 2012 和 Windows Server 2012 R2 中，可以使用 Windows PowerShell 3.0 安装 IIS 要求。</span><span class="sxs-lookup"><span data-stu-id="57d85-238">In Windows Server 2012 and Windows Server 2012 R2, you can use Windows PowerShell 3.0 to install the IIS Requirements.</span></span> <span data-ttu-id="57d85-239">使用 Windows PowerShell 3.0 中的 ServerManager 模块，请键入：</span><span class="sxs-lookup"><span data-stu-id="57d85-239">Using the ServerManager module in Windows PowerShell 3.0, type:</span></span>

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> <span data-ttu-id="57d85-240">Windows Server 2012 的新版本是用于定义可在何处找到 Windows Server 2012 源媒体的– Source 参数。</span><span class="sxs-lookup"><span data-stu-id="57d85-240">New with Windows Server 2012 is the –Source parameter that defines where the Windows Server 2012 source media can be found.</span></span> <span data-ttu-id="57d85-241">可以将媒体定义为 DVD 驱动器（例如，D:\Sources\Sxs），也可以定义为网络共享媒体文件已复制（例如， \\fileserver\windows2012\sources\Sxs）。</span><span class="sxs-lookup"><span data-stu-id="57d85-241">The media can be defined as a DVD drive (for example, D:\Sources\Sxs), or to a network share that the media files have been copied (for example, \\fileserver\windows2012\sources\Sxs).</span></span>



</div>

<div>

## <a name="see-also"></a><span data-ttu-id="57d85-242">另请参阅</span><span class="sxs-lookup"><span data-stu-id="57d85-242">See Also</span></span>


[<span data-ttu-id="57d85-243">Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="57d85-243">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

