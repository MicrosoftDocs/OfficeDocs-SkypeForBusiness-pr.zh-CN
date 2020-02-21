---
title: Lync Server 2013：移动客户端部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobile client deployment process
ms:assetid: 6498235b-2fa9-421d-bfa0-0ccc09508dbd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690982(v=OCS.15)
ms:contentKeyID: 51541484
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14acbf4a8be4d453fc1a0c5dc4da303136433e0c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42185025"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="mobile-client-deployment-process-in-lync-server-2013"></a><span data-ttu-id="98b87-102">Lync Server 2013 中的移动客户端部署过程</span><span class="sxs-lookup"><span data-stu-id="98b87-102">Mobile client deployment process in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="98b87-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="98b87-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="98b87-104">在 Microsoft Lync Server 2013 的部署完成后，用户可以从他们习惯于其特定设备使用的移动市场安装 Lync 2013 应用程序。</span><span class="sxs-lookup"><span data-stu-id="98b87-104">After a deployment of Microsoft Lync Server 2013 has been completed, users can install the Lync 2013 app from the mobile marketplace that they are accustomed to using for their specific device.</span></span>

<div>

## <a name="lync-mobile-deployment-process"></a><span data-ttu-id="98b87-105">Lync 移动部署过程</span><span class="sxs-lookup"><span data-stu-id="98b87-105">Lync Mobile Deployment Process</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="98b87-106">阶段</span><span class="sxs-lookup"><span data-stu-id="98b87-106">Phase</span></span></th>
<th><span data-ttu-id="98b87-107">步骤</span><span class="sxs-lookup"><span data-stu-id="98b87-107">Steps</span></span></th>
<th><span data-ttu-id="98b87-108">权限</span><span class="sxs-lookup"><span data-stu-id="98b87-108">Permissions</span></span></th>
<th><span data-ttu-id="98b87-109">文档</span><span class="sxs-lookup"><span data-stu-id="98b87-109">Documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="98b87-110">执行预安装任务。</span><span class="sxs-lookup"><span data-stu-id="98b87-110">Perform pre-setup tasks.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="98b87-111">验证 Lync Server 2013 部署。</span><span class="sxs-lookup"><span data-stu-id="98b87-111">Verify Lync Server 2013 deployment.</span></span></p></li>
<li><p><span data-ttu-id="98b87-112">验证证书要求。</span><span class="sxs-lookup"><span data-stu-id="98b87-112">Verify certificate requirements.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98b87-113">管理员</span><span class="sxs-lookup"><span data-stu-id="98b87-113">Administrator</span></span></p></td>
<td><p><span data-ttu-id="98b87-114">在服务器规划文档中<a href="lync-server-2013-planning-for-mobility.md">规划 Lync Server 2013 中的移动性</a>。</span><span class="sxs-lookup"><span data-stu-id="98b87-114"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a> in the server planning documentation.</span></span></p>
<p><span data-ttu-id="98b87-115">在服务器部署文档中<a href="lync-server-2013-deploying-mobility.md">部署 Lync Server 2013</a>中的移动功能。</span><span class="sxs-lookup"><span data-stu-id="98b87-115"><a href="lync-server-2013-deploying-mobility.md">Deploying mobility in Lync Server 2013</a> in the server deployment documentation.</span></span></p>
<p><span data-ttu-id="98b87-116">服务器规划文档中<a href="lync-server-2013-certificate-infrastructure-requirements.md">Lync Server 2013 的证书基础结构要求</a>。</span><span class="sxs-lookup"><span data-stu-id="98b87-116"><a href="lync-server-2013-certificate-infrastructure-requirements.md">Certificate infrastructure requirements for Lync Server 2013</a> in the server planning documentation.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b87-117">在测试设备上安装 Lync 应用程序。</span><span class="sxs-lookup"><span data-stu-id="98b87-117">Install the Lync application on a test device.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="98b87-118">安装必备组件。</span><span class="sxs-lookup"><span data-stu-id="98b87-118">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="98b87-119">从特定于移动设备的市场安装。</span><span class="sxs-lookup"><span data-stu-id="98b87-119">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98b87-120">管理员</span><span class="sxs-lookup"><span data-stu-id="98b87-120">Administrator</span></span></p></td>
<td><p><span data-ttu-id="98b87-121">在<a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署移动客户端</a>的移动设备专用的安装说明。</span><span class="sxs-lookup"><span data-stu-id="98b87-121">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b87-122">配置客户端。</span><span class="sxs-lookup"><span data-stu-id="98b87-122">Configure the client.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="98b87-123">配置登录设置和服务器信息。</span><span class="sxs-lookup"><span data-stu-id="98b87-123">Configure sign-in settings and server information.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="98b87-124">管理员</span><span class="sxs-lookup"><span data-stu-id="98b87-124">Administrator</span></span></p></td>
<td><p><span data-ttu-id="98b87-125"><a href="lync-server-2013-deploying-mobile-clients.md">在 Lync Server 2013 中部署移动客户端</a></span><span class="sxs-lookup"><span data-stu-id="98b87-125"><a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="98b87-126">测试移动应用场景。</span><span class="sxs-lookup"><span data-stu-id="98b87-126">Test mobile scenarios.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="98b87-127">测试即时消息（IM）和状态。</span><span class="sxs-lookup"><span data-stu-id="98b87-127">Test instant messaging (IM) and presence.</span></span></p></li>
<li><p><span data-ttu-id="98b87-128">测试拨出式会议。</span><span class="sxs-lookup"><span data-stu-id="98b87-128">Test dial-out conferencing.</span></span></p></li>
<li><p><span data-ttu-id="98b87-129">搜索公司目录中的联系人。</span><span class="sxs-lookup"><span data-stu-id="98b87-129">Search for a contact in the corporate directory.</span></span></p></li>
<li><p><span data-ttu-id="98b87-130">测试推送通知。</span><span class="sxs-lookup"><span data-stu-id="98b87-130">Test push notifications.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98b87-131">管理员</span><span class="sxs-lookup"><span data-stu-id="98b87-131">Administrator</span></span></p></td>
<td><p><span data-ttu-id="98b87-132">在<a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署移动客户端</a>的移动设备专用的验证说明。</span><span class="sxs-lookup"><span data-stu-id="98b87-132">Verification instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="98b87-133">在移动电话上安装 Lync 应用程序。</span><span class="sxs-lookup"><span data-stu-id="98b87-133">Install the Lync application on mobile phones.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="98b87-134">安装必备组件。</span><span class="sxs-lookup"><span data-stu-id="98b87-134">Install prerequisites.</span></span></p></li>
<li><p><span data-ttu-id="98b87-135">从特定于移动设备的市场安装。</span><span class="sxs-lookup"><span data-stu-id="98b87-135">Install from the marketplace specific to the mobile device.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="98b87-136">用户</span><span class="sxs-lookup"><span data-stu-id="98b87-136">User</span></span></p></td>
<td><p><span data-ttu-id="98b87-137">在<a href="lync-server-2013-deploying-mobile-clients.md">Lync Server 2013 中部署移动客户端</a>的移动设备专用的安装说明。</span><span class="sxs-lookup"><span data-stu-id="98b87-137">Installation instructions specific to the mobile device in <a href="lync-server-2013-deploying-mobile-clients.md">Deploying mobile clients in Lync Server 2013</a>.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

