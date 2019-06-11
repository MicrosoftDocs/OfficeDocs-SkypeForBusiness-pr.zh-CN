---
title: 前端池和 Standard Edition 服务器的 IIS 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS requirements for Front End pools and Standard Edition servers
ms:assetid: e8a6c7ac-b6d5-4c7e-abe9-d8ea5eedbc62
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399038(v=OCS.15)
ms:contentKeyID: 48185888
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d804df614eab49eeabe82cca9d304e082d9ced3
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830040"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-requirements-for-front-end-pools-and-standard-edition-servers-in-lync-server-2013"></a><span data-ttu-id="b09c6-102">Lync Server 2013 中前端池和 Standard Edition 服务器的 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="b09c6-102">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b09c6-103">_**主题上次修改时间:** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="b09c6-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="b09c6-104">对于标准版服务器和前端服务器以及控制器, Lync Server 2013 安装程序将在 Internet Information Services (IIS) 中创建虚拟目录, 以实现以下目的:</span><span class="sxs-lookup"><span data-stu-id="b09c6-104">For Standard Edition servers and Front End Servers, and Directors, the Lync Server 2013 installer creates virtual directories in Internet Information Services (IIS) for the following purposes:</span></span>

  - <span data-ttu-id="b09c6-105">允许用户从通讯簿服务下载文件</span><span class="sxs-lookup"><span data-stu-id="b09c6-105">To enable users to download files from the Address Book Service</span></span>

  - <span data-ttu-id="b09c6-106">启用客户端以获取更新</span><span class="sxs-lookup"><span data-stu-id="b09c6-106">To enable clients to obtain updates</span></span>

  - <span data-ttu-id="b09c6-107">启用会议</span><span class="sxs-lookup"><span data-stu-id="b09c6-107">To enable conferencing</span></span>

  - <span data-ttu-id="b09c6-108">允许用户下载会议内容</span><span class="sxs-lookup"><span data-stu-id="b09c6-108">To enable users to download meeting content</span></span>

  - <span data-ttu-id="b09c6-109">使用户能够展开通讯组</span><span class="sxs-lookup"><span data-stu-id="b09c6-109">To enable users to expand distribution groups</span></span>

  - <span data-ttu-id="b09c6-110">启用电话会议</span><span class="sxs-lookup"><span data-stu-id="b09c6-110">To enable phone conferencing</span></span>

  - <span data-ttu-id="b09c6-111">启用响应组功能</span><span class="sxs-lookup"><span data-stu-id="b09c6-111">To enable response group features</span></span>

<span data-ttu-id="b09c6-112">此外, Lync Server 2010 的累积更新: 2011 安装程序在 IIS 中创建虚拟目录的目的如下:</span><span class="sxs-lookup"><span data-stu-id="b09c6-112">In addition, the cumulative update for Lync Server 2010: November 2011 installer creates virtual directories in IIS for the following purposes:</span></span>

  - <span data-ttu-id="b09c6-113">在移动设备上支持移动功能的前端服务器或标准版服务器 (如即时消息 (IM) 和联机状态)</span><span class="sxs-lookup"><span data-stu-id="b09c6-113">On Front End Servers or Standard Edition servers to support mobility functionality, such as instant messaging (IM) and presence, on mobile devices</span></span>

  - <span data-ttu-id="b09c6-114">在前端服务器或标准版服务器和控制器上, 使移动设备能够自动发现移动资源</span><span class="sxs-lookup"><span data-stu-id="b09c6-114">On Front End Servers or Standard Edition servers and on Directors to enable mobile devices to automatically discover mobility resources</span></span>



> [!NOTE]
> <span data-ttu-id="b09c6-115">如果要部署移动性, 建议使用 IIS 7.5。</span><span class="sxs-lookup"><span data-stu-id="b09c6-115">If you are deploying mobility, we recommend that you use IIS 7.5.</span></span> <span data-ttu-id="b09c6-116">Lync Server 移动服务安装程序设置一些 ASP.NET 标志以提高性能。</span><span class="sxs-lookup"><span data-stu-id="b09c6-116">The Lync Server Mobility Service installer sets some ASP.NET flags to improve performance.</span></span> <span data-ttu-id="b09c6-117">默认情况下, IIS 7.5 在 Windows Server 2008 R2 上安装, 移动服务安装程序会自动更改 ASP.NET 设置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-117">IIS 7.5 is installed by default on Windows Server 2008 R2, and the Mobility Service installer automatically changes the ASP.NET settings.</span></span> <span data-ttu-id="b09c6-118">如果在 Windows Server 2008 上使用 IIS 7.0, 则需要手动更改这些设置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-118">If you use IIS 7.0 on Windows Server 2008, you need to manually change these settings.</span></span>



<span data-ttu-id="b09c6-119">Lync Server 要求安装以下 IIS 模块:</span><span class="sxs-lookup"><span data-stu-id="b09c6-119">Lync Server requires the following IIS modules to be installed:</span></span>


> [!IMPORTANT]
> <span data-ttu-id="b09c6-120">如果你的组织要求在除系统驱动器之外的驱动器上找到 IIS 和所有 Web 服务, 则可以在 "设置" 对话框中更改 Lync Server 文件的安装位置路径。</span><span class="sxs-lookup"><span data-stu-id="b09c6-120">If your organization requires that you locate IIS and all Web Services on a drive other than the system drive, you can change the installation location path for the Lync Server files in the Setup dialog box.</span></span> <span data-ttu-id="b09c6-121">如果将安装文件安装到此路径 (包括 OCSCore), 则其他 Lync Server 文件也将同时部署到此驱动器。</span><span class="sxs-lookup"><span data-stu-id="b09c6-121">If you install the Setup files to this path, including OCSCore.msi, the rest of the Lync Server files will be deployed to this drive as well.</span></span> <span data-ttu-id="b09c6-122">有关如何重新定位 Windows Server Manager 在安装 IIS 时部署的 INETPUB 的详细信息, <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>请参阅。</span><span class="sxs-lookup"><span data-stu-id="b09c6-122">For details about how to relocate the INETPUB deployed by Windows Server Manager when installing IIS, see <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>.</span></span>


  - <span data-ttu-id="b09c6-123">静态内容</span><span class="sxs-lookup"><span data-stu-id="b09c6-123">Static Content</span></span>

  - <span data-ttu-id="b09c6-124">默认文档</span><span class="sxs-lookup"><span data-stu-id="b09c6-124">Default Document</span></span>

  - <span data-ttu-id="b09c6-125">HTTP 错误</span><span class="sxs-lookup"><span data-stu-id="b09c6-125">HTTP Errors</span></span>

  - <span data-ttu-id="b09c6-126">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="b09c6-126">ASP.NET</span></span>

  - <span data-ttu-id="b09c6-127">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="b09c6-127">.NET Extensibility</span></span>

  - <span data-ttu-id="b09c6-128">Internet 服务器 API (ISAPI) 扩展</span><span class="sxs-lookup"><span data-stu-id="b09c6-128">Internet Server API (ISAPI) Extensions</span></span>

  - <span data-ttu-id="b09c6-129">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="b09c6-129">ISAPI Filters</span></span>

  - <span data-ttu-id="b09c6-130">HTTP 日志记录</span><span class="sxs-lookup"><span data-stu-id="b09c6-130">HTTP Logging</span></span>

  - <span data-ttu-id="b09c6-131">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="b09c6-131">Logging Tools</span></span>

  - <span data-ttu-id="b09c6-132">跟踪</span><span class="sxs-lookup"><span data-stu-id="b09c6-132">Tracing</span></span>

  - <span data-ttu-id="b09c6-133">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="b09c6-133">Windows Authentication</span></span>

  - <span data-ttu-id="b09c6-134">请求筛选</span><span class="sxs-lookup"><span data-stu-id="b09c6-134">Request Filtering</span></span>

  - <span data-ttu-id="b09c6-135">静态内容压缩</span><span class="sxs-lookup"><span data-stu-id="b09c6-135">Static Content Compression</span></span>

  - <span data-ttu-id="b09c6-136">动态内容压缩</span><span class="sxs-lookup"><span data-stu-id="b09c6-136">Dynamic Content Compression</span></span>

  - <span data-ttu-id="b09c6-137">IIS 管理控制台</span><span class="sxs-lookup"><span data-stu-id="b09c6-137">IIS Management Console</span></span>

  - <span data-ttu-id="b09c6-138">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="b09c6-138">IIS Management Scripts and Tools</span></span>

  - <span data-ttu-id="b09c6-139">匿名身份验证 (安装 IIS 时默认安装)</span><span class="sxs-lookup"><span data-stu-id="b09c6-139">Anonymous Authentication (installed by default when IIS is installed)</span></span>

  - <span data-ttu-id="b09c6-140">客户端证书映射身份验证</span><span class="sxs-lookup"><span data-stu-id="b09c6-140">Client Certificate Mapping Authentication</span></span>

<span data-ttu-id="b09c6-141">下表列出了用于内部访问的虚拟目录的 Uri 以及它们所引用的文件系统资源。</span><span class="sxs-lookup"><span data-stu-id="b09c6-141">The following table lists the URIs for the virtual directories for internal access and the file system resources to which they refer.</span></span>

### <a name="virtual-directories-for-internal-access"></a><span data-ttu-id="b09c6-142">用于内部访问的虚拟目录</span><span class="sxs-lookup"><span data-stu-id="b09c6-142">Virtual Directories for Internal Access</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b09c6-143">功能</span><span class="sxs-lookup"><span data-stu-id="b09c6-143">Feature</span></span></th>
<th><span data-ttu-id="b09c6-144">虚拟目录 URI</span><span class="sxs-lookup"><span data-stu-id="b09c6-144">Virtual directory URI</span></span></th>
<th><span data-ttu-id="b09c6-145">引用</span><span class="sxs-lookup"><span data-stu-id="b09c6-145">Refers to</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b09c6-146">通讯簿服务器</span><span class="sxs-lookup"><span data-stu-id="b09c6-146">Address Book Server</span></span></p></td>
<td><p><span data-ttu-id="b09c6-147">https://&lt;内部 FQDN&gt;/ABS/int/Handler</span><span class="sxs-lookup"><span data-stu-id="b09c6-147">https://&lt;Internal FQDN&gt;/ABS/int/Handler</span></span></p></td>
<td><p><span data-ttu-id="b09c6-148">内部用户的通讯簿服务器下载文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-148">Location of Address Book Server download files for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b09c6-149">自动发现服务</span><span class="sxs-lookup"><span data-stu-id="b09c6-149">Autodiscover Service</span></span></p></td>
<td><p><span data-ttu-id="b09c6-150">https://&lt;内部 FQDN&gt;/Autodiscover</span><span class="sxs-lookup"><span data-stu-id="b09c6-150">https://&lt;Internal FQDN&gt;/Autodiscover</span></span></p></td>
<td><p><span data-ttu-id="b09c6-151">用于查找内部移动设备用户的移动资源的 Lync Server 自动发现服务的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-151">Location of the Lync Server Autodiscover Service that locates mobility resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b09c6-152">客户端更新</span><span class="sxs-lookup"><span data-stu-id="b09c6-152">Client updates</span></span></p></td>
<td><p><span data-ttu-id="b09c6-153">http://&lt;内部 FQDN&gt;/AutoUpdate/Int</span><span class="sxs-lookup"><span data-stu-id="b09c6-153">http://&lt;Internal FQDN&gt;/AutoUpdate/Int</span></span></p></td>
<td><p><span data-ttu-id="b09c6-154">内部基于计算机的客户端的更新文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-154">Location of update files for internal computer-based clients.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b09c6-155">会议</span><span class="sxs-lookup"><span data-stu-id="b09c6-155">Conf</span></span></p></td>
<td><p><span data-ttu-id="b09c6-156">http://&lt;内部 FQDN&gt;/Conf/Int</span><span class="sxs-lookup"><span data-stu-id="b09c6-156">http://&lt;Internal FQDN&gt;/Conf/Int</span></span></p></td>
<td><p><span data-ttu-id="b09c6-157">内部用户的会议资源的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-157">Location of conferencing resources for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b09c6-158">设备更新</span><span class="sxs-lookup"><span data-stu-id="b09c6-158">Device updates</span></span></p></td>
<td><p><span data-ttu-id="b09c6-159">http://&lt;内部 FQDN&gt;/DeviceUpdateFiles_Int</span><span class="sxs-lookup"><span data-stu-id="b09c6-159">http://&lt;Internal FQDN&gt;/DeviceUpdateFiles_Int</span></span></p></td>
<td><p><span data-ttu-id="b09c6-160">适用于内部 UC 设备的统一通信 (UC) 设备更新文件的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-160">Location of unified communications (UC) device update files for internal UC devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b09c6-161">符合</span><span class="sxs-lookup"><span data-stu-id="b09c6-161">Meeting</span></span></p></td>
<td><p><span data-ttu-id="b09c6-162">http://&lt;内部 FQDN&gt;/etc/place/null</span><span class="sxs-lookup"><span data-stu-id="b09c6-162">http://&lt;Internal FQDN&gt;/etc/place/null</span></span></p></td>
<td><p><span data-ttu-id="b09c6-163">内部用户的会议内容的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-163">Location of meeting content for internal users.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b09c6-164">移动服务</span><span class="sxs-lookup"><span data-stu-id="b09c6-164">Mobility Service</span></span></p></td>
<td><p><span data-ttu-id="b09c6-165">https://&lt;内部 FQDN&gt;/Mcx</span><span class="sxs-lookup"><span data-stu-id="b09c6-165">https://&lt;Internal FQDN&gt;/Mcx</span></span></p></td>
<td><p><span data-ttu-id="b09c6-166">适用于内部移动设备用户的移动服务资源的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-166">Location of Mobility Service resources for internal mobile device users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b09c6-167">组扩展和通讯簿 Web 查询服务</span><span class="sxs-lookup"><span data-stu-id="b09c6-167">Group Expansion and Address Book Web Query service</span></span></p></td>
<td><p><span data-ttu-id="b09c6-168">http://&lt;内部 FQDN&gt;/GroupExpansion/int/service.asmx</span><span class="sxs-lookup"><span data-stu-id="b09c6-168">http://&lt;Internal FQDN&gt;/GroupExpansion/int/service.asmx</span></span></p></td>
<td><p><span data-ttu-id="b09c6-169">为内部用户启用组扩展的 Web 服务的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-169">Location of the Web service that enables group expansion for internal users.</span></span> <span data-ttu-id="b09c6-170">此外, 还可向内部 Lync Mobile Microsoft Lync 2010 移动客户端提供全局地址列表信息的通讯簿 Web 查询服务的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-170">Also, the location of the Address Book Web Query service that provides global address list information to internal Lync Mobile Microsoft Lync 2010 Mobile clients.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b09c6-171">电话会议</span><span class="sxs-lookup"><span data-stu-id="b09c6-171">Phone Conferencing</span></span></p></td>
<td><p><span data-ttu-id="b09c6-172">http://&lt;内部 FQDN&gt;/PhoneConferencing/Int</span><span class="sxs-lookup"><span data-stu-id="b09c6-172">http://&lt;Internal FQDN&gt;/PhoneConferencing/Int</span></span></p></td>
<td><p><span data-ttu-id="b09c6-173">内部用户的电话会议数据的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-173">Location of phone conferencing data for internal users.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b09c6-174">设备更新</span><span class="sxs-lookup"><span data-stu-id="b09c6-174">Device updates</span></span></p></td>
<td><p><span data-ttu-id="b09c6-175">http://&lt;内部 FQDN&gt;/RequestHandler</span><span class="sxs-lookup"><span data-stu-id="b09c6-175">http://&lt;Internal FQDN&gt;/RequestHandler</span></span></p></td>
<td><p><span data-ttu-id="b09c6-176">允许内部 UC 设备上传日志和检查更新的设备更新 Web 服务请求处理程序的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-176">Location of the Device Update Web service Request Handler that enables internal UC devices to upload logs and check for updates.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b09c6-177">响应组应用程序</span><span class="sxs-lookup"><span data-stu-id="b09c6-177">Response Group application</span></span></p></td>
<td><p><span data-ttu-id="b09c6-178">http://&lt;内部 FQDN&gt;/RgsConfig</span><span class="sxs-lookup"><span data-stu-id="b09c6-178">http://&lt;Internal FQDN&gt;/RgsConfig</span></span></p>
<p><span data-ttu-id="b09c6-179">http://&lt;内部 FQDN&gt;/RgsClients</span><span class="sxs-lookup"><span data-stu-id="b09c6-179">http://&lt;Internal FQDN&gt;/RgsClients</span></span></p></td>
<td><p><span data-ttu-id="b09c6-180">响应组配置工具的位置。</span><span class="sxs-lookup"><span data-stu-id="b09c6-180">Location of Response Group Configuration Tool.</span></span></p></td>
</tr>
</tbody>
</table>


> [!NOTE]
> <span data-ttu-id="b09c6-181">对于合并配置中的前端池, 必须先部署 IIS, 然后才能将服务器添加到池中。</span><span class="sxs-lookup"><span data-stu-id="b09c6-181">For Front End pools in a consolidated configuration, you must deploy IIS before you can add servers to the pool.</span></span>


<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="安全" alt="security" /><span data-ttu-id="b09c6-183">安全说明:</span><span class="sxs-lookup"><span data-stu-id="b09c6-183">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b09c6-184">必须使用 IIS 管理单元分配 IIS web 组件服务器使用的证书。</span><span class="sxs-lookup"><span data-stu-id="b09c6-184">You must use the IIS administrative snap-in to assign the certificate used by the IIS web component server.</span></span></td>
</tr>
</tbody>
</table>



</div>

<span> </span>

</div>

</div>

</div>

