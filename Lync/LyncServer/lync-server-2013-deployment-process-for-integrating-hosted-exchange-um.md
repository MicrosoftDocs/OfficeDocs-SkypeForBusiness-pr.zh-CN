---
title: Lync Server 2013：集成托管 Exchange UM 的部署过程
description: Lync Server 2013：集成托管 Exchange UM 的部署过程。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for integrating hosted Exchange UM with Lync Server
ms:assetid: dbec9c38-7f66-419d-b8c3-c61380052cac
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398968(v=OCS.15)
ms:contentKeyID: 48185586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 83239c6534dfdaa65109c8880cc4cb4946bffab6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48542608"
---
# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="88f49-103">将托管 Exchange UM 与 Lync Server 2013 集成在一起的部署过程</span><span class="sxs-lookup"><span data-stu-id="88f49-103">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="88f49-104">_**上次修改的主题：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="88f49-104">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="88f49-105">若要有效地规划如何将 Lync Server 2013 与托管 Exchange 统一消息集成 (UM) ，需要考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="88f49-105">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="88f49-106">将 Lync Server 2013 与托管 Exchange UM 集成的先决条件</span><span class="sxs-lookup"><span data-stu-id="88f49-106">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="88f49-107">集成过程中所需的步骤</span><span class="sxs-lookup"><span data-stu-id="88f49-107">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="88f49-108">与托管 Exchange UM 集成的部署先决条件</span><span class="sxs-lookup"><span data-stu-id="88f49-108">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="88f49-109">您必须已部署至少一个前端池或 Standard Edition server) 、边缘服务器以及 Lync 2013 或 Lync 2010 客户端，然后才能开始集成过程，您必须已部署 Lync Server 2013 (。</span><span class="sxs-lookup"><span data-stu-id="88f49-109">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="88f49-110">集成过程</span><span class="sxs-lookup"><span data-stu-id="88f49-110">Integration Process</span></span>

<span data-ttu-id="88f49-111">下表提供了托管 Exchange UM 集成过程的概述。</span><span class="sxs-lookup"><span data-stu-id="88f49-111">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="88f49-112">有关部署步骤的详细信息，请参阅部署文档中的在 [托管 EXCHANGE UM 上提供 Lync Server 2013 用户语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) 。</span><span class="sxs-lookup"><span data-stu-id="88f49-112">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="88f49-113">阶段</span><span class="sxs-lookup"><span data-stu-id="88f49-113">Phase</span></span></th>
<th><span data-ttu-id="88f49-114">步骤</span><span class="sxs-lookup"><span data-stu-id="88f49-114">Steps</span></span></th>
<th><span data-ttu-id="88f49-115">权利和权限</span><span class="sxs-lookup"><span data-stu-id="88f49-115">Rights and permissions</span></span></th>
<th><span data-ttu-id="88f49-116">部署文档</span><span class="sxs-lookup"><span data-stu-id="88f49-116">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="88f49-117">配置边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="88f49-117">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="88f49-118">配置边缘服务器以进行联盟。</span><span class="sxs-lookup"><span data-stu-id="88f49-118">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="88f49-119">手动将数据复制到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="88f49-119">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="88f49-120">在边缘服务器上配置托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="88f49-120">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="88f49-121">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="88f49-121">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="88f49-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">配置边缘服务器以与托管 Exchange UM 集成</a></span><span class="sxs-lookup"><span data-stu-id="88f49-122"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88f49-123">配置托管的语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="88f49-123">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="88f49-124">修改全局托管的语音邮件策略，或使用网站或 Per-User 范围创建新的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="88f49-124">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="88f49-125">对于 Per-User 作用域的策略，请将策略分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="88f49-125">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="88f49-126">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="88f49-126">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="88f49-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理托管的语音邮件策略</a></span><span class="sxs-lookup"><span data-stu-id="88f49-127"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="88f49-128">为用户启用托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="88f49-128">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="88f49-129">为其邮箱位于托管 Exchange 服务上的用户配置用户帐户。</span><span class="sxs-lookup"><span data-stu-id="88f49-129">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="88f49-130">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="88f49-130">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="88f49-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中为用户启用托管语音邮件</a></span><span class="sxs-lookup"><span data-stu-id="88f49-131"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="88f49-132">配置托管的 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="88f49-132">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="88f49-133">为托管 Exchange UM 创建自动助理联系人对象。</span><span class="sxs-lookup"><span data-stu-id="88f49-133">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="88f49-134">为托管 Exchange UM 创建订阅者访问联系人对象。</span><span class="sxs-lookup"><span data-stu-id="88f49-134">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="88f49-135">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="88f49-135">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="88f49-136">若要创建、修改或删除 contact 对象，运行 CsExUmContact、Set-CsExUmContact 或 Remove-CsExUmContact cmdlet 的用户必须具有在其中存储新联系人对象的 Active Directory 组织单位的正确权限。</span><span class="sxs-lookup"><span data-stu-id="88f49-136">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="88f49-137">可以通过运行 Grant-CsOUPermission cmdlet 授予此权限。</span><span class="sxs-lookup"><span data-stu-id="88f49-137">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="88f49-138">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="88f49-138">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="88f49-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象</a></span><span class="sxs-lookup"><span data-stu-id="88f49-139"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

