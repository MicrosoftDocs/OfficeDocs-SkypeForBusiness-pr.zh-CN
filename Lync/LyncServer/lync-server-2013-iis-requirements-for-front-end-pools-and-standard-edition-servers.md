---
title: 前端池和 Standard Edition 服务器的 IIS 要求
description: 前端池和 Standard Edition 服务器的 IIS 要求。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f56452c7e47352333ac3ac5a51d649b0828a0ff9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48573338"
---
# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="56215-103">Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="56215-103">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="56215-104">_**上次修改的主题：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="56215-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="56215-105">对于 Standard Edition 服务器和前端服务器以及控制器，Lync Server 2013 安装程序会在 Internet Information Services (IIS) 中创建虚拟目录，以实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="56215-105">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="56215-106">允许用户从通讯簿服务下载文件</span><span class="sxs-lookup"><span data-stu-id="56215-106">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="56215-107">启用客户端以获取更新</span><span class="sxs-lookup"><span data-stu-id="56215-107">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="56215-108">启用会议</span><span class="sxs-lookup"><span data-stu-id="56215-108">To enable conferencing</span></span>

  - <span data-ttu-id="56215-109">允许用户下载会议内容</span><span class="sxs-lookup"><span data-stu-id="56215-109">To enable users to download meeting content</span></span>

  - <span data-ttu-id="56215-110">允许用户扩展通讯组</span><span class="sxs-lookup"><span data-stu-id="56215-110">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="56215-111">启用电话会议</span><span class="sxs-lookup"><span data-stu-id="56215-111">To enable phone conferencing</span></span>

  - <span data-ttu-id="56215-112">启用响应组功能</span><span class="sxs-lookup"><span data-stu-id="56215-112">To enable response group features</span></span>

<span data-ttu-id="56215-113">此外，Lync Server 2010 的累积更新：11月2011安装程序将在 IIS 中创建虚拟目录，以实现以下目的：</span><span class="sxs-lookup"><span data-stu-id="56215-113">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="56215-114">在前端服务器或 Standard Edition 服务器上，支持移动功能（如即时消息 (IM) 和状态）在移动设备上</span><span class="sxs-lookup"><span data-stu-id="56215-114">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="56215-115">在前端服务器或 Standard Edition 服务器和控制器上，使移动设备能够自动发现移动资源</span><span class="sxs-lookup"><span data-stu-id="56215-115">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="56215-116">如果要部署移动性，建议使用 IIS 7.5。</span><span class="sxs-lookup"><span data-stu-id="56215-116">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="56215-117">Lync Server 移动服务安装程序设置一些 ASP.NET 标志以提高性能。</span><span class="sxs-lookup"><span data-stu-id="56215-117">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="56215-118">默认情况下，IIS 7.5 安装在 Windows Server 2008 R2 上，并且 Mobility Service 安装程序会自动更改 ASP.NET 设置。</span><span class="sxs-lookup"><span data-stu-id="56215-118">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="56215-119">如果您在 Windows Server 2008 上使用 IIS 7.0，则需要手动更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="56215-119">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="56215-120">Lync Server 要求安装以下 IIS 模块：</span><span class="sxs-lookup"><span data-stu-id="56215-120">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="56215-121">如果您的组织要求在除系统驱动器之外的驱动器上查找 IIS 和所有 Web 服务，则可以在 "安装程序" 对话框中更改 Lync Server 文件的安装位置路径。</span><span class="sxs-lookup"><span data-stu-id="56215-121">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="56215-122">如果将安装文件安装到此路径（包括 OCSCore.msi），则其余的 Lync Server 文件也将部署到此驱动器。</span><span class="sxs-lookup"><span data-stu-id="56215-122">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="56215-123">有关如何在安装 IIS 时重新定位由 Windows Server Manager 部署的 INETPUB 的详细信息，请参阅 <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> 。</span><span class="sxs-lookup"><span data-stu-id="56215-123">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="56215-124">静态内容</span><span class="sxs-lookup"><span data-stu-id="56215-124">Static Content</span></span>

  - <span data-ttu-id="56215-125">默认文档</span><span class="sxs-lookup"><span data-stu-id="56215-125">Default Document</span></span>

  - <span data-ttu-id="56215-126">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="56215-126">HTTP Errors</span></span>

  - <span data-ttu-id="56215-127">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="56215-127">ASP.NET</span></span>

  - <span data-ttu-id="56215-128">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="56215-128">.NET Extensibility</span></span>

  - <span data-ttu-id="56215-129">Internet Server API (ISAPI) 扩展</span><span class="sxs-lookup"><span data-stu-id="56215-129">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="56215-130">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="56215-130">ISAPI Filters</span></span>

  - <span data-ttu-id="56215-131">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="56215-131">HTTP Logging</span></span>

  - <span data-ttu-id="56215-132">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="56215-132">Logging Tools</span></span>

  - <span data-ttu-id="56215-133">追踪</span><span class="sxs-lookup"><span data-stu-id="56215-133">Tracing</span></span>

  - <span data-ttu-id="56215-134">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="56215-134">Windows Authentication</span></span>

  - <span data-ttu-id="56215-135">请求筛选</span><span class="sxs-lookup"><span data-stu-id="56215-135">Request Filtering</span></span>

  - <span data-ttu-id="56215-136">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="56215-136">Static Content Compression</span></span>

  - <span data-ttu-id="56215-137">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="56215-137">Dynamic Content Compression</span></span>

  - <span data-ttu-id="56215-138">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="56215-138">IIS Management Console</span></span>

  - <span data-ttu-id="56215-139">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="56215-139">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="56215-140">匿名身份验证（安装 IIS 时默认安装）</span><span class="sxs-lookup"><span data-stu-id="56215-140">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="56215-141">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="56215-141">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="56215-142">下表列出了用于内部访问的虚拟目录的 URI 及其引用的文件系统资源。</span><span class="sxs-lookup"><span data-stu-id="56215-142">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="56215-143">用于内部访问的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="56215-143">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="56215-144">功能</span><span class="sxs-lookup"><span data-stu-id="56215-144">Feature</span></span></th>
<th><span data-ttu-id="56215-145">虚拟目录 URI</span><span class="sxs-lookup"><span data-stu-id="56215-145">Virtual directory URI</span></span></th>
<th><span data-ttu-id="56215-146">引用</span><span class="sxs-lookup"><span data-stu-id="56215-146">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="56215-147">通讯簿服务器</span><span class="sxs-lookup"><span data-stu-id="56215-147">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="56215-148">https:// &lt; 内部 FQDN &gt; /ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="56215-148">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="56215-149">用于内部用户的通讯簿服务器下载文件的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-149">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56215-150">自动发现服务</span><span class="sxs-lookup"><span data-stu-id="56215-150">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="56215-151">https:// &lt; 内部 FQDN &gt; /Autodiscover</span><span class="sxs-lookup"><span data-stu-id="56215-151">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="56215-152">为内部移动设备用户查找移动性资源的 Lync Server 自动发现服务的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-152">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56215-153">客户端更新</span><span class="sxs-lookup"><span data-stu-id="56215-153">Client updates</span></span></p></td>
<td><p><span data-ttu-id="56215-154">http:// &lt; 内部 FQDN &gt; /AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="56215-154">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="56215-155">用于内部基于计算机的客户端的更新文件的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-155">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56215-156">会议</span><span class="sxs-lookup"><span data-stu-id="56215-156">Conf</span></span></p></td>
<td><p><span data-ttu-id="56215-157">http:// &lt; 内部 FQDN &gt; /Conf/Int</span><span class="sxs-lookup"><span data-stu-id="56215-157">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="56215-158">用于内部用户的会议资源的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-158">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56215-159">设备更新</span><span class="sxs-lookup"><span data-stu-id="56215-159">Device updates</span></span></p></td>
<td><p><span data-ttu-id="56215-160">http:// &lt; 内部 FQDN &gt; /DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="56215-160">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="56215-161">用于内部 UC 设备的统一通信 (UC) 设备更新文件的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-161">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56215-162">要求</span><span class="sxs-lookup"><span data-stu-id="56215-162">Meeting</span></span></p></td>
<td><p><span data-ttu-id="56215-163">http:// &lt; 内部 FQDN &gt; /etc/place/null</span><span class="sxs-lookup"><span data-stu-id="56215-163">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="56215-164">用于内部用户的会议内容的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-164">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56215-165">Mobility Service</span><span class="sxs-lookup"><span data-stu-id="56215-165">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="56215-166">https:// &lt; 内部 FQDN &gt; /Mcx</span><span class="sxs-lookup"><span data-stu-id="56215-166">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="56215-167">用于内部移动设备用户的 Mobility Service 资源的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-167">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56215-168">组扩展和通讯簿 Web 查询服务</span><span class="sxs-lookup"><span data-stu-id="56215-168">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="56215-169">http:// &lt; 内部 FQDN &gt; /GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="56215-169">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="56215-170">为内部用户启用组扩展的 Web 服务的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-170">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="56215-171">此外，将全局地址列表信息提供给内部 Lync Mobile Microsoft Lync 2010 移动客户端的通讯簿 Web 查询服务的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-171">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56215-172">电话会议</span><span class="sxs-lookup"><span data-stu-id="56215-172">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="56215-173">http:// &lt; 内部 FQDN &gt; /PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="56215-173">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="56215-174">用于内部用户的电话会议数据的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-174">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="56215-175">设备更新</span><span class="sxs-lookup"><span data-stu-id="56215-175">Device updates</span></span></p></td>
<td><p><span data-ttu-id="56215-176">http:// &lt; 内部 FQDN &gt; /RequestHandler</span><span class="sxs-lookup"><span data-stu-id="56215-176">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="56215-177">用于启用内部 UC 设备以便上载日志以及检查更新的设备更新 Web 服务请求处理程序的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-177">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="56215-178">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="56215-178">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="56215-179">http:// &lt; 内部 FQDN &gt; /RgsConfig</span><span class="sxs-lookup"><span data-stu-id="56215-179">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="56215-180">http:// &lt; 内部 FQDN &gt; /RgsClients</span><span class="sxs-lookup"><span data-stu-id="56215-180">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="56215-181">响应组配置工具的位置。</span><span class="sxs-lookup"><span data-stu-id="56215-181">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="56215-182">对于合并配置中的前端池，您必须先部署 IIS，然后才能将服务器添加到池。</span><span class="sxs-lookup"><span data-stu-id="56215-182">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" /><span data-ttu-id="56215-184">安全说明：</span><span class="sxs-lookup"><span data-stu-id="56215-184">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="56215-185">必须使用 IIS 管理性管理单元分配由 IIS Web 组件服务器使用的证书。</span><span class="sxs-lookup"><span data-stu-id="56215-185">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

