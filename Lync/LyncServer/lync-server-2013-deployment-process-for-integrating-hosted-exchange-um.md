---
title: Lync Server 2013：集成托管 Exchange UM 的部署过程
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
ms.openlocfilehash: f55e8f573b4000d56a002adb9bd40d03b2021cba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42137171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-integrating-hosted-exchange-um-with-lync-server-2013"></a><span data-ttu-id="406c3-102">将托管 Exchange UM 与 Lync Server 2013 集成在一起的部署过程</span><span class="sxs-lookup"><span data-stu-id="406c3-102">Deployment process for integrating hosted Exchange UM with Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="406c3-103">_**上次修改的主题：** 2012-09-25_</span><span class="sxs-lookup"><span data-stu-id="406c3-103">_**Topic Last Modified:** 2012-09-25_</span></span>

<span data-ttu-id="406c3-104">若要有效地规划如何将 Lync Server 2013 与托管 Exchange 统一消息（UM）集成，需要考虑以下事项：</span><span class="sxs-lookup"><span data-stu-id="406c3-104">Effective planning for integrating Lync Server 2013 with hosted Exchange Unified Messaging (UM) requires that you take into account the following:</span></span>

  - <span data-ttu-id="406c3-105">将 Lync Server 2013 与托管 Exchange UM 集成的先决条件</span><span class="sxs-lookup"><span data-stu-id="406c3-105">Prerequisites for integrating Lync Server 2013 with hosted Exchange UM</span></span>

  - <span data-ttu-id="406c3-106">集成过程中所需的步骤</span><span class="sxs-lookup"><span data-stu-id="406c3-106">Steps required during the integration process</span></span>

<div>

## <a name="deployment-prerequisites-for-integrating-with-hosted-exchange-um"></a><span data-ttu-id="406c3-107">与托管 Exchange UM 集成的部署先决条件</span><span class="sxs-lookup"><span data-stu-id="406c3-107">Deployment Prerequisites for Integrating with Hosted Exchange UM</span></span>

<span data-ttu-id="406c3-108">您必须已部署了 Lync Server 2013 （至少是前端池或 Standard Edition 服务器）、边缘服务器以及 Lync 2013 或 Lync 2010 客户端，然后才能开始集成过程。</span><span class="sxs-lookup"><span data-stu-id="406c3-108">Before you can begin the integration process, you must already have deployed Lync Server 2013 (at a minimum, a Front End pool or a Standard Edition server), an Edge Server, and Lync 2013 or Lync 2010 clients.</span></span>

</div>

<div>

## <a name="integration-process"></a><span data-ttu-id="406c3-109">集成过程</span><span class="sxs-lookup"><span data-stu-id="406c3-109">Integration Process</span></span>

<span data-ttu-id="406c3-110">下表提供了托管 Exchange UM 集成过程的概述。</span><span class="sxs-lookup"><span data-stu-id="406c3-110">The following table provides an overview of the hosted Exchange UM integration process.</span></span> <span data-ttu-id="406c3-111">有关部署步骤的详细信息，请参阅部署文档中的在[托管 EXCHANGE UM 上提供 Lync Server 2013 用户语音邮件](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md)。</span><span class="sxs-lookup"><span data-stu-id="406c3-111">For details about deployment steps, see [Providing Lync Server 2013 users voice mail on hosted Exchange UM](lync-server-2013-providing-lync-server-users-voice-mail-on-hosted-exchange-um.md) in the Deployment documentation.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="406c3-112">阶段</span><span class="sxs-lookup"><span data-stu-id="406c3-112">Phase</span></span></th>
<th><span data-ttu-id="406c3-113">步骤</span><span class="sxs-lookup"><span data-stu-id="406c3-113">Steps</span></span></th>
<th><span data-ttu-id="406c3-114">权利和权限</span><span class="sxs-lookup"><span data-stu-id="406c3-114">Rights and permissions</span></span></th>
<th><span data-ttu-id="406c3-115">部署文档</span><span class="sxs-lookup"><span data-stu-id="406c3-115">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="406c3-116">配置边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="406c3-116">Configure the Edge Server.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="406c3-117">配置边缘服务器以进行联盟。</span><span class="sxs-lookup"><span data-stu-id="406c3-117">Configure the Edge Server for federation.</span></span></p></li>
<li><p><span data-ttu-id="406c3-118">手动将数据复制到边缘服务器。</span><span class="sxs-lookup"><span data-stu-id="406c3-118">Manually replicate data to the Edge Server.</span></span></p></li>
<li><p><span data-ttu-id="406c3-119">在边缘服务器上配置托管提供程序。</span><span class="sxs-lookup"><span data-stu-id="406c3-119">Configure the hosting provider on the Edge Server.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="406c3-120">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="406c3-120">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="406c3-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">配置边缘服务器以与托管 Exchange UM 集成</a></span><span class="sxs-lookup"><span data-stu-id="406c3-121"><a href="lync-server-2013-configure-the-edge-server-for-integration-with-hosted-exchange-um.md">Configure the Edge Server for integration with hosted Exchange UM</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406c3-122">配置托管的语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="406c3-122">Configure hosted voice mail policy.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="406c3-123">修改全局托管的语音邮件策略，或使用站点或每用户范围创建新的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="406c3-123">Either modify the global hosted voice mail policy or create a new hosted voice mail policy with Site or Per-User scope.</span></span></p></li>
<li><p><span data-ttu-id="406c3-124">对于具有每用户作用域的策略，请将策略分配给用户或组。</span><span class="sxs-lookup"><span data-stu-id="406c3-124">For policies with Per-User scope, assign the policy to users or groups.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="406c3-125">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="406c3-125">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="406c3-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">在 Lync Server 2013 中管理托管的语音邮件策略</a></span><span class="sxs-lookup"><span data-stu-id="406c3-126"><a href="lync-server-2013-manage-hosted-voice-mail-policies.md">Manage hosted voice mail policies in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="406c3-127">为用户启用托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="406c3-127">Enable users for hosted voice mail.</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="406c3-128">为其邮箱位于托管 Exchange 服务上的用户配置用户帐户。</span><span class="sxs-lookup"><span data-stu-id="406c3-128">Configure user accounts for users whose mailboxes are on a hosted Exchange service.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="406c3-129">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="406c3-129">RTCUniversalUserAdmins</span></span></p></td>
<td><p><span data-ttu-id="406c3-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">在 Lync Server 2013 中为用户启用托管语音邮件</a></span><span class="sxs-lookup"><span data-stu-id="406c3-130"><a href="lync-server-2013-enable-users-for-hosted-voice-mail.md">Enable users for hosted voice mail in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="406c3-131">配置托管的 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="406c3-131">Configure hosted contact objects.</span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="406c3-132">为托管 Exchange UM 创建自动助理联系人对象。</span><span class="sxs-lookup"><span data-stu-id="406c3-132">Create auto-attendant Contact objects for hosted Exchange UM.</span></span></p></li>
<li><p><span data-ttu-id="406c3-133">为托管 Exchange UM 创建订阅者访问联系人对象。</span><span class="sxs-lookup"><span data-stu-id="406c3-133">Create Subscriber Access contact objects for hosted Exchange UM.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="406c3-134">RTCUniversalUserAdmins</span><span class="sxs-lookup"><span data-stu-id="406c3-134">RTCUniversalUserAdmins</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="406c3-135">若要创建、修改或删除 contact 对象，运行 CsExUmContact、CsExUmContact 或 CsExUmContact cmdlet 的用户必须具有对存储新的 contact 对象的 Active Directory 组织单位的正确权限。</span><span class="sxs-lookup"><span data-stu-id="406c3-135">To create, modify or remove contact objects, the user who runs the New-CsExUmContact, Set-CsExUmContact or Remove-CsExUmContact cmdlet must have the correct permission to the Active Directory organizational unit where the new contact objects are stored.</span></span> <span data-ttu-id="406c3-136">可以通过运行 Grant-CsOUPermission cmdlet 授予此权限。</span><span class="sxs-lookup"><span data-stu-id="406c3-136">This permission can be granted by running the Grant-CsOUPermission cmdlet.</span></span> <span data-ttu-id="406c3-137">有关详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="406c3-137">For details, see the Lync Server Management Shell documentation.</span></span>


</div></td>
<td><p><span data-ttu-id="406c3-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">在 Lync Server 2013 中为托管 Exchange UM 创建联系人对象</a></span><span class="sxs-lookup"><span data-stu-id="406c3-138"><a href="lync-server-2013-create-contact-objects-for-hosted-exchange-um.md">Create contact objects for hosted Exchange UM in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

