---
title: Lync Server 2013： Internet 信息服务 (IIS) 要求
description: Lync Server 2013： Internet 信息服务 (IIS) 要求。
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
ms.openlocfilehash: dd8de55fa4611c3ab29eac7d7c28c522b418e77d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48543988"
---
# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="3734d-103">Lync Server 2013 中的 Internet 信息服务 (IIS) 要求</span><span class="sxs-lookup"><span data-stu-id="3734d-103">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3734d-104">_**上次修改的主题：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="3734d-104">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="3734d-105">多个 Lync Server 2013 组件需要 Internet 信息服务 (IIS) 。</span><span class="sxs-lookup"><span data-stu-id="3734d-105">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="3734d-106">本主题介绍支持 Lync Server 所需的特定 IIS 功能。</span><span class="sxs-lookup"><span data-stu-id="3734d-106">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="3734d-107">本节中的主题介绍 IIS 特定组件的要求。</span><span class="sxs-lookup"><span data-stu-id="3734d-107">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="3734d-p102">在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，将默认安装多种角色服务。下表介绍在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，必须安装的其他角色服务。</span><span class="sxs-lookup"><span data-stu-id="3734d-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3734d-110">角色服务</span><span class="sxs-lookup"><span data-stu-id="3734d-110">Role service</span></span></th>
<th><span data-ttu-id="3734d-111">功能</span><span class="sxs-lookup"><span data-stu-id="3734d-111">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3734d-112">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="3734d-112">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="3734d-113">HTTP 重定向</span><span class="sxs-lookup"><span data-stu-id="3734d-113">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3734d-114">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="3734d-114">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3734d-115">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="3734d-115">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3734d-116">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="3734d-116">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3734d-117">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="3734d-117">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3734d-118">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="3734d-118">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3734d-119">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="3734d-119">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3734d-120">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="3734d-120">Application Development</span></span></p></td>
<td><p><span data-ttu-id="3734d-121">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="3734d-121">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3734d-122">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="3734d-122">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3734d-123">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="3734d-123">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3734d-124">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="3734d-124">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="3734d-125">追踪</span><span class="sxs-lookup"><span data-stu-id="3734d-125">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3734d-126">安全性</span><span class="sxs-lookup"><span data-stu-id="3734d-126">Security</span></span></p></td>
<td><p><span data-ttu-id="3734d-127">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="3734d-127">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3734d-128">安全性</span><span class="sxs-lookup"><span data-stu-id="3734d-128">Security</span></span></p></td>
<td><p><span data-ttu-id="3734d-129">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="3734d-129">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3734d-130">管理工具</span><span class="sxs-lookup"><span data-stu-id="3734d-130">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="3734d-131">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="3734d-131">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3734d-132">管理工具</span><span class="sxs-lookup"><span data-stu-id="3734d-132">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="3734d-133">IIS 6 管理兼容性</span><span class="sxs-lookup"><span data-stu-id="3734d-133">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" /><span data-ttu-id="3734d-135">安全说明：</span><span class="sxs-lookup"><span data-stu-id="3734d-135">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="3734d-136">如果您在 Windows Server 2008 操作系统上使用 IIS 7.0，Lync Server 安装程序将在 IIS 中禁用内核模式身份验证。</span><span class="sxs-lookup"><span data-stu-id="3734d-136">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="3734d-137">本部分内容</span><span class="sxs-lookup"><span data-stu-id="3734d-137">In This Section</span></span>

  - [<span data-ttu-id="3734d-138">Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="3734d-138">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

