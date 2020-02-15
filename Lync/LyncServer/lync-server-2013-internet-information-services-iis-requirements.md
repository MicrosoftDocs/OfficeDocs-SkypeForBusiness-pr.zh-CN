---
title: Lync Server 2013： Internet Information Services （IIS）要求
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
ms.openlocfilehash: 9a086713c4c4c1ea5752c7e1b46ce46e48a0ea42
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42040941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="internet-information-services-iis-requirements-in-lync-server-2013"></a><span data-ttu-id="cd27a-102">Lync Server 2013 中的 Internet 信息服务（IIS）要求</span><span class="sxs-lookup"><span data-stu-id="cd27a-102">Internet Information Services (IIS) requirements in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="cd27a-103">_**上次修改的主题：** 2012-06-19_</span><span class="sxs-lookup"><span data-stu-id="cd27a-103">_**Topic Last Modified:** 2012-06-19_</span></span>

<span data-ttu-id="cd27a-104">多个 Lync Server 2013 组件需要 Internet 信息服务（IIS）。</span><span class="sxs-lookup"><span data-stu-id="cd27a-104">Several Lync Server 2013 components require Internet Information Services (IIS).</span></span> <span data-ttu-id="cd27a-105">本主题介绍支持 Lync Server 所需的特定 IIS 功能。</span><span class="sxs-lookup"><span data-stu-id="cd27a-105">This topic describes the specific IIS features required to support Lync Server.</span></span> <span data-ttu-id="cd27a-106">本节中的主题介绍 IIS 特定组件的要求。</span><span class="sxs-lookup"><span data-stu-id="cd27a-106">The topics in this section describe the requirements of specific components for IIS.</span></span>

<span data-ttu-id="cd27a-p102">在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，将默认安装多种角色服务。下表介绍在 Windows Server 2008 中启用 Web 服务器 (IIS) 角色时，必须安装的其他角色服务。</span><span class="sxs-lookup"><span data-stu-id="cd27a-p102">When the Web Server (IIS) role is enabled on Windows Server 2008, various role services are installed by default. The following table describes the additional role services that must be installed when the Web Server (IIS) role is enabled on Windows Server 2008.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="cd27a-109">角色服务</span><span class="sxs-lookup"><span data-stu-id="cd27a-109">Role service</span></span></th>
<th><span data-ttu-id="cd27a-110">功能</span><span class="sxs-lookup"><span data-stu-id="cd27a-110">Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="cd27a-111">常见的 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="cd27a-111">Common HTTP Features</span></span></p></td>
<td><p><span data-ttu-id="cd27a-112">HTTP 重定向</span><span class="sxs-lookup"><span data-stu-id="cd27a-112">HTTP Redirection</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd27a-113">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="cd27a-113">Application Development</span></span></p></td>
<td><p><span data-ttu-id="cd27a-114">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="cd27a-114">ASP.NET</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd27a-115">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="cd27a-115">Application Development</span></span></p></td>
<td><p><span data-ttu-id="cd27a-116">.NET 扩展性</span><span class="sxs-lookup"><span data-stu-id="cd27a-116">.NET Extensibility</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd27a-117">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="cd27a-117">Application Development</span></span></p></td>
<td><p><span data-ttu-id="cd27a-118">ISAPI 扩展</span><span class="sxs-lookup"><span data-stu-id="cd27a-118">ISAPI Extensions</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd27a-119">应用程序开发</span><span class="sxs-lookup"><span data-stu-id="cd27a-119">Application Development</span></span></p></td>
<td><p><span data-ttu-id="cd27a-120">ISAPI 筛选器</span><span class="sxs-lookup"><span data-stu-id="cd27a-120">ISAPI Filters</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd27a-121">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="cd27a-121">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="cd27a-122">日志记录工具</span><span class="sxs-lookup"><span data-stu-id="cd27a-122">Logging Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd27a-123">运行状况和诊断</span><span class="sxs-lookup"><span data-stu-id="cd27a-123">Health and Diagnostics</span></span></p></td>
<td><p><span data-ttu-id="cd27a-124">追踪</span><span class="sxs-lookup"><span data-stu-id="cd27a-124">Tracing</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd27a-125">安全性</span><span class="sxs-lookup"><span data-stu-id="cd27a-125">Security</span></span></p></td>
<td><p><span data-ttu-id="cd27a-126">基本身份验证</span><span class="sxs-lookup"><span data-stu-id="cd27a-126">Basic Authentication</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd27a-127">安全性</span><span class="sxs-lookup"><span data-stu-id="cd27a-127">Security</span></span></p></td>
<td><p><span data-ttu-id="cd27a-128">Windows 身份验证</span><span class="sxs-lookup"><span data-stu-id="cd27a-128">Windows Authentication</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="cd27a-129">管理工具</span><span class="sxs-lookup"><span data-stu-id="cd27a-129">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="cd27a-130">IIS 管理脚本和工具</span><span class="sxs-lookup"><span data-stu-id="cd27a-130">IIS Management Scripts and Tools</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="cd27a-131">管理工具</span><span class="sxs-lookup"><span data-stu-id="cd27a-131">Management Tools</span></span></p></td>
<td><p><span data-ttu-id="cd27a-132">IIS 6 管理兼容性</span><span class="sxs-lookup"><span data-stu-id="cd27a-132">IIS 6 Management Compatibility</span></span></p></td>
</tr>
</tbody>
</table>


<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="保护" alt="security" /><span data-ttu-id="cd27a-134">安全说明：</span><span class="sxs-lookup"><span data-stu-id="cd27a-134">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="cd27a-135">如果您在 Windows Server 2008 操作系统上使用 IIS 7.0，Lync Server 安装程序将在 IIS 中禁用内核模式身份验证。</span><span class="sxs-lookup"><span data-stu-id="cd27a-135">If you are using IIS 7.0 on a Windows Server 2008 operating system, Lync Server Setup disables kernel mode authentication in IIS.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="cd27a-136">本部分内容</span><span class="sxs-lookup"><span data-stu-id="cd27a-136">In This Section</span></span>

  - [<span data-ttu-id="cd27a-137">Lync Server 2013 中的前端池和 Standard Edition 服务器的 IIS 要求</span><span class="sxs-lookup"><span data-stu-id="cd27a-137">IIS requirements for Front End pools and Standard Edition servers in Lync Server 2013</span></span>](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

