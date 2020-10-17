---
title: Lync Server 2013： Internet 信息服务 (IIS) 要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Internet Information Services (IIS) requirements
ms:assetid: 4f57a605-a8a9-4c5a-9a18-05ecb3d9ab6b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398321(v=OCS.15)
ms:contentKeyID: 48184128
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3b0c1c9966945554af6d1d9cec02a17dd884a857
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48498479"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="1d815-102">Lync Server 2013 中的 Internet 信息服务 (IIS) 要求</span><span class="sxs-lookup"><span data-stu-id="1d815-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1d815-103">_**上次修改的主题：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="1d815-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="1d815-104">多个 Lync Server 2013 组件需要 Internet 信息服务 (IIS) 。</span><span class="sxs-lookup"><span data-stu-id="1d815-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="1d815-105">本主题介绍支持 Lync Server 所需的特定 IIS 功能。</span><span class="sxs-lookup"><span data-stu-id="1d815-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="1d815-106">本节中的主题介绍 IIS 特定组件的要求。</span><span class="sxs-lookup"><span data-stu-id="1d815-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="1d815-p102">在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，将默认安装多种角色服务。下表介绍在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，必须安装的其他角色服务。</span><span class="sxs-lookup"><span data-stu-id="1d815-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1d815-109">角色服务</span><span class="sxs-lookup"><span data-stu-id="1d815-109">Role service</span></span></th>
<th><span data-ttu-id="1d815-110">功能</span><span class="sxs-lookup"><span data-stu-id="1d815-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1d815-111">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="1d815-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="1d815-112">HTTP 重定向</span><span class="sxs-lookup"><span data-stu-id="1d815-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d815-113">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="1d815-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d815-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="1d815-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d815-115">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="1d815-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d815-116">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="1d815-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d815-117">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="1d815-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d815-118">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="1d815-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d815-119">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="1d815-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="1d815-120">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="1d815-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d815-121">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="1d815-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d815-122">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="1d815-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d815-123">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="1d815-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="1d815-124">追踪</span><span class="sxs-lookup"><span data-stu-id="1d815-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d815-125">安全性</span><span class="sxs-lookup"><span data-stu-id="1d815-125">Security</span></span></p></td>
<td><p><span data-ttu-id="1d815-126">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="1d815-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d815-127">安全性</span><span class="sxs-lookup"><span data-stu-id="1d815-127">Security</span></span></p></td>
<td><p><span data-ttu-id="1d815-128">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="1d815-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1d815-129">管理工具</span><span class="sxs-lookup"><span data-stu-id="1d815-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="1d815-130">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="1d815-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1d815-131">管理工具</span><span class="sxs-lookup"><span data-stu-id="1d815-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="1d815-132">IIS 6 管理兼容性</span><span class="sxs-lookup"><span data-stu-id="1d815-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" /><span data-ttu-id="1d815-134">安全说明：</span><span class="sxs-lookup"><span data-stu-id="1d815-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="1d815-135">如果您在 Windows Server 2008 操作系统上使用 IIS 7.0，Lync Server 安装程序将在 IIS 中禁用内核模式身份验证。</span><span class="sxs-lookup"><span data-stu-id="1d815-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="1d815-136">本部分内容</span><span class="sxs-lookup"><span data-stu-id="1d815-136">In This Section</span></span>

  - [<span data-ttu-id="1d815-137">Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="1d815-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

