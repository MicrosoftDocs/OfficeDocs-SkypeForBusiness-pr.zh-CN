---
title: 用于电话拨入式会议的 Lync Server 2013 部署清单
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment checklist for dial-in conferencing
ms:assetid: 9c8d3ebe-0d70-4a61-9bd0-522286cddd9a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412726(v=OCS.15)
ms:contentKeyID: 48184987
ms.date: 10/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 084686c33482e4828378db76c2a5ca1c834bacf3
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42205845"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-checklist-for-dial-in-conferencing-in-lync-server-2013"></a><span data-ttu-id="2b51c-102">Lync Server 2013 中的电话拨入式会议的部署清单</span><span class="sxs-lookup"><span data-stu-id="2b51c-102">Deployment checklist for dial-in conferencing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b51c-103">_**上次修改的主题：** 2014-10-03_</span><span class="sxs-lookup"><span data-stu-id="2b51c-103">_**Topic Last Modified:** 2014-10-03_</span></span>

<span data-ttu-id="2b51c-104">部署会议工作负荷时，将部署电话拨入式会议所需的组件。</span><span class="sxs-lookup"><span data-stu-id="2b51c-104">The components required for dial-in conferencing are deployed when you deploy the conferencing workload.</span></span> <span data-ttu-id="2b51c-105">在配置电话拨入式会议之前，需要部署企业语音或中介服务器和公用电话交换网（PSTN）网关。</span><span class="sxs-lookup"><span data-stu-id="2b51c-105">Before you can configure dial-in conferencing, you need to deploy either Enterprise Voice or a Mediation Server and a public switched telephone network (PSTN) gateway.</span></span>

<span data-ttu-id="2b51c-106">用户必须先执行下表中的所有步骤，然后才能通过从 PSTN 拨号加入音频/视频会议。</span><span class="sxs-lookup"><span data-stu-id="2b51c-106">All the steps in the following table must be performed before users can dial in from the PSTN to join an audio/video conference.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b51c-107">如果要从 Office 通信服务器 2007 R2 进行迁移，则必须在部署电话拨入式会议之前，将最新的更新应用到 Office 通信服务器 2007 R2 环境。</span><span class="sxs-lookup"><span data-stu-id="2b51c-107">If you are migrating from Office Communications Server 2007 R2, you must apply the latest updates to your Office Communications Server 2007 R2 environment before deploying dial-in conferencing.</span></span>



</div>

### <a name="dial-in-conferencing-deployment-process"></a><span data-ttu-id="2b51c-108">电话拨入式会议部署过程</span><span class="sxs-lookup"><span data-stu-id="2b51c-108">Dial-in Conferencing Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="2b51c-109">阶段</span><span class="sxs-lookup"><span data-stu-id="2b51c-109">Phase</span></span></th>
<th><span data-ttu-id="2b51c-110">步骤</span><span class="sxs-lookup"><span data-stu-id="2b51c-110">Steps</span></span></th>
<th><span data-ttu-id="2b51c-111">权限</span><span class="sxs-lookup"><span data-stu-id="2b51c-111">Permissions</span></span></th>
<th><span data-ttu-id="2b51c-112">部署文档</span><span class="sxs-lookup"><span data-stu-id="2b51c-112">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="2b51c-113"><strong>创建包含会议工作负荷（包括中介服务器和 PSTN 网关）的拓扑，并部署前端池或 Standard Edition 服务器</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-113"><strong>Create a topology that includes the Conferencing workload, including a Mediation Server and PSTN gateway, and deploy the Front End pool or Standard Edition server</strong></span></span></p></td>
<td><ol>
<li><p><span data-ttu-id="2b51c-114">运行拓扑生成器以配置拓扑。</span><span class="sxs-lookup"><span data-stu-id="2b51c-114">Run Topology Builder to configure your topology.</span></span> <span data-ttu-id="2b51c-115">配置拓扑时，请选择电话拨入式会议选项。</span><span class="sxs-lookup"><span data-stu-id="2b51c-115">While configuring the topology, select the dial-in conferencing option.</span></span></p></li>
<li><p><span data-ttu-id="2b51c-116">发布拓扑并部署前端池或 Standard Edition server。</span><span class="sxs-lookup"><span data-stu-id="2b51c-116">Publish the topology and deploy the Front End pool or Standard Edition server.</span></span></p></li>
<li><p><span data-ttu-id="2b51c-117">如有必要，请创建独立的中介服务器，并将其与 PSTN 网关相关联。</span><span class="sxs-lookup"><span data-stu-id="2b51c-117">If necessary, create a stand-alone Mediation Server and associate it with a PSTN gateway.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2b51c-118">仅当您不部署企业语音且不并置使用 Enterprise EditionFront server server 或 Standard Edition server 的中介服务器时，才需要执行此步骤。</span><span class="sxs-lookup"><span data-stu-id="2b51c-118">This step is required only if you do not deploy Enterprise Voice and do not collocate the Mediation Server with the Enterprise EditionFront End Server or Standard Edition server.</span></span> <span data-ttu-id="2b51c-119">如果部署企业语音，则在企业语音部署过程中安装并配置中介服务器和 PSTN 网关。</span><span class="sxs-lookup"><span data-stu-id="2b51c-119">If you deploy Enterprise Voice, you install and configure Mediation Servers and PSTN gateways as part of the Enterprise Voice deployment.</span></span> <span data-ttu-id="2b51c-120">如果您并置中介服务器，则需要在前端池或 Standard Edition server 部署的一部分中安装和配置中介服务器。</span><span class="sxs-lookup"><span data-stu-id="2b51c-120">If you collocate the Mediation Server, you install and configure the Mediation Server as part of the Front End pool or Standard Edition server deployment.</span></span>


</div></li>
</ol></td>
<td><p><span data-ttu-id="2b51c-121">Domain Admins</span><span class="sxs-lookup"><span data-stu-id="2b51c-121">Domain Admins</span></span></p>
<p><span data-ttu-id="2b51c-122">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-122">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-123">管理员</span><span class="sxs-lookup"><span data-stu-id="2b51c-123">Administrator</span></span></p></td>
<td><ul>
<li><p><span data-ttu-id="2b51c-124"><a href="lync-server-2013-deploying-lync-server.md">部署 Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-124"><a href="lync-server-2013-deploying-lync-server.md">Deploying Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="2b51c-125">创建独立的中介服务器池：<a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">在 Lync server 2013 中部署中介服务器和定义对等方</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-125">To create a stand-alone Mediation Server pool: <a href="lync-server-2013-deploying-mediation-servers-and-defining-peers.md">Deploying Mediation Servers and defining peers in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b51c-126"><strong>配置拨号计划</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-126"><strong>Configure dial plans</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-127">拨号计划是一组电话号码规范化规则，它将从特定位置拨打的电话号码转换为单一的标准 (E.164) 格式，以便进行电话授权和呼叫路由。</span><span class="sxs-lookup"><span data-stu-id="2b51c-127">A dial plan is a set of phone number normalization rules that translate phone numbers dialed from a specific location to a single standard (E.164) format for purposes of phone authorization and call routing.</span></span> <span data-ttu-id="2b51c-128">从不同位置拨打的同一电话号码可以基于各自的拨号计划针对每个具体位置解析为不同的 E.164 号码。</span><span class="sxs-lookup"><span data-stu-id="2b51c-128">The same phone number dialed from different locations can, based on the respective dial plans, resolve to different E.164 numbers, as appropriate to each location.</span></span> <span data-ttu-id="2b51c-129">如果部署企业语音，请将拨号计划设置为部署的一部分，并且需要确保拨号计划也能容纳电话拨入式会议。</span><span class="sxs-lookup"><span data-stu-id="2b51c-129">If you deploy Enterprise Voice, you set up dial plans as part of that deployment, and you need to make sure that the dial plans also accommodate dial-in conferencing.</span></span> <span data-ttu-id="2b51c-130">如果不部署企业语音，则需要为电话拨入式会议设置拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2b51c-130">If you do not deploy Enterprise Voice, you need to set up dial plans for dial-in conferencing.</span></span></p>
<p><span data-ttu-id="2b51c-131">使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序设置拨号计划，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2b51c-131">Use the Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial plans as follows:</span></span></p>
<ol>
<li><p><span data-ttu-id="2b51c-132">创建一个或多个用于路由拨入访问电话号码的拨号计划。</span><span class="sxs-lookup"><span data-stu-id="2b51c-132">Create one or more dial plans for routing dial-in access phone numbers.</span></span></p></li>
<li><p><span data-ttu-id="2b51c-p105">为每个池分配一个默认的拨号计划。将“电话拨入式会议区域”<strong></strong>设为应用拨号计划的地理位置。该区域会将拨号计划与拨入访问号码相关联。</span><span class="sxs-lookup"><span data-stu-id="2b51c-p105">Assign a default dial plan to each pool. Set the <strong>Dial-in conferencing region</strong> to the geographic location to which the dial plan applies. The region associates the dial plan with dial-in access numbers.</span></span></p></li>
</ol></td>
<td><p><span data-ttu-id="2b51c-136">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-136">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-137">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-137">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-138">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-138">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-139">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-139">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">在 Lync Server 2013 中配置电话拨入式会议的拨号计划</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-140"><a href="lync-server-2013-configure-dial-plans-for-dial-in-conferencing.md">Configure dial plans for dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b51c-141"><strong>请确保已为拨号计划分配区域</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-141"><strong>Make sure that dial plans are assigned regions</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-142">运行<strong>grant-csdialplan</strong>和<strong>grant-csdialplan</strong> cmdlet，以确保所有拨号计划都分配了一个区域。</span><span class="sxs-lookup"><span data-stu-id="2b51c-142">Run the <strong>Get-CsDialPlan</strong> and <strong>Set-CsDialPlan</strong> cmdlets to make sure that all dial plans have a region assigned.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-145">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-145">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">确保拨号计划 Lync Server 2013 已分配区域</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-147"><a href="lync-server-2013-make-sure-dial-plans-have-assigned-regions.md">Make sure dial plans Lync Server 2013 have assigned regions</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b51c-148"><strong>（可选）验证或修改用户个人标识号 (PIN) 要求</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-148"><strong>(Optional) Verify or modify user personal identification number (PIN) requirements</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-149">使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序查看或修改会议<strong>PIN 策略</strong>。</span><span class="sxs-lookup"><span data-stu-id="2b51c-149">Use Lync Server 2013 Control Panel or Lync Server Management Shell to view or modify the Conferencing <strong>PIN Policy</strong>.</span></span> <span data-ttu-id="2b51c-150">可以指定最小 PIN 长度、最大登录尝试次数、PIN 到期时间以及是否允许使用通用模式。</span><span class="sxs-lookup"><span data-stu-id="2b51c-150">You can specify minimum PIN length, maximum number of logon attempts, PIN expiration, and whether common patterns are allowable.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-151">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-151">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-152">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-152">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-153">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-153">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">Optional验证 Lync Server 2013 中的 PIN 策略设置</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-154"><a href="lync-server-2013-optional-verify-pin-policy-settings.md">(Optional) Verify PIN policy settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b51c-155"><strong>配置会议策略以支持电话拨入式会议</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-155"><strong>Configure conferencing policy to support dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-156">使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序配置<strong>会议策略</strong>设置。</span><span class="sxs-lookup"><span data-stu-id="2b51c-156">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure <strong>Conferencing Policy</strong> settings.</span></span> <span data-ttu-id="2b51c-157">指定：</span><span class="sxs-lookup"><span data-stu-id="2b51c-157">Specify whether:</span></span></p>
<ul>
<li><p><span data-ttu-id="2b51c-158">是否启用 PSTN 会议拨入。</span><span class="sxs-lookup"><span data-stu-id="2b51c-158">PSTN conference dial-in is enabled.</span></span></p></li>
<li><p><span data-ttu-id="2b51c-159">用户能否邀请匿名参与者。</span><span class="sxs-lookup"><span data-stu-id="2b51c-159">Users can invite anonymous participants.</span></span></p></li>
<li><p><span data-ttu-id="2b51c-p108">未经身份验证的用户能否通过拨出式电话加入会议。通过拨出式电话，会议服务器会呼叫用户，用户接听电话即可加入会议。</span><span class="sxs-lookup"><span data-stu-id="2b51c-p108">Unauthenticated users can join a conference by using dial-out phoning. With dial-out phoning, the conference server calls the user, and the user answers the phone to join the conference.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="2b51c-162">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-162">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-163">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-163">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-164">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-164">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">在 Lync Server 2013 中配置电话拨入式会议策略</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-165"><a href="lync-server-2013-configure-conferencing-policy-for-dial-in.md">Configure conferencing policy for dial-in in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b51c-166"><strong>配置拨入访问号码</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-166"><strong>Configure dial-in access numbers</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-167">使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序设置用户拨打会议的拨入访问号码，并指定将访问号码与相应的拨号计划相关联的区域。</span><span class="sxs-lookup"><span data-stu-id="2b51c-167">Use Lync Server 2013 Control Panel or Lync Server Management Shell to set up dial-in access numbers that users call to dial in to a conference, and specify the regions that associate the access number with the appropriate dial plans.</span></span> <span data-ttu-id="2b51c-168">组织者拨号计划指定的区域的前三个访问号码包含在会议邀请中。</span><span class="sxs-lookup"><span data-stu-id="2b51c-168">The first three access numbers for the region specified by the organizer's dial plan are included in the conference invitation.</span></span> <span data-ttu-id="2b51c-169">"电话拨入式会议设置" 页上提供了所有访问号码。</span><span class="sxs-lookup"><span data-stu-id="2b51c-169">All access numbers are available on the Dial-in Conferencing Settings page.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="2b51c-170">在创建电话拨入访问号码之后，可以使用<STRONG>set-csdialinconferencingaccessnumber</STRONG> Cmdlet 修改 Active Directory contact 对象的显示名称，以便用户可以更轻松地识别正确的访问号码。</span><span class="sxs-lookup"><span data-stu-id="2b51c-170">After you create dial-in access numbers, you can use the <STRONG>Set-CsDialInConferencingAccessNumber</STRONG> cmdlet to modify the display name of the Active Directory contact objects so that users can more easily identify the correct access number.</span></span>


</div></td>
<td><p><span data-ttu-id="2b51c-171">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-171">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-172">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-172">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-173">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-173">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">在 Lync Server 2013 中配置电话拨入式会议访问号码</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-174"><a href="lync-server-2013-configure-dial-in-conferencing-access-numbers.md">Configure dial-in conferencing access numbers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b51c-175"><strong>（可选）验证电话拨入式会议设置</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-175"><strong>(Optional) Verify dial-in conferencing settings</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-176">使用 <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet 搜索具有未被任何访问号码使用的电话拨入式会议区域的拨号计划，以及尚未分配区域的访问号码。</span><span class="sxs-lookup"><span data-stu-id="2b51c-176">Use the <strong>Get-CsDialinConferencingAccessNumber</strong> cmdlet to search for dial plans that have a dial-in conferencing region that is not used by any access number and for access numbers that have no region assigned.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-177">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-177">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-178">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-178">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-179">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-179">CsAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-180">CsViewOnlyAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-180">CsViewOnlyAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-181">CsHelpDesk</span><span class="sxs-lookup"><span data-stu-id="2b51c-181">CsHelpDesk</span></span></p></td>
<td><p><span data-ttu-id="2b51c-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">Optional在 Lync Server 2013 中验证电话拨入式会议设置</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-182"><a href="lync-server-2013-optional-verify-dial-in-conferencing-settings.md">(Optional) Verify dial-in conferencing settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b51c-183"><strong>（可选）修改 DTMF 命令的键映射</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-183"><strong>(Optional) Modify key mapping of DTMF commands</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-184">使用 <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet 修改用于双音多频 (DTMF) 命令的键，参与者可使用这些命令控制会议设置（如静音和取消静音或锁定和解除锁定）。</span><span class="sxs-lookup"><span data-stu-id="2b51c-184">Use the <strong>Set-CsDialinConferencingDtmfConfiguration</strong> cmdlet to modify the keys used for dual-tone multifrequency (DTMF) commands, which participants can use to control conference settings (such as mute and unmute or lock and unlock).</span></span></p></td>
<td><p><span data-ttu-id="2b51c-185">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-185">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-186">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-186">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-187">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-187">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">Optional在 Lync Server 2013 中修改 DTMF 命令的键映射</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-188"><a href="lync-server-2013-optional-modify-key-mapping-for-dtmf-commands.md">(Optional) Modify key mapping for DTMF commands in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b51c-189"><strong>（可选）修改会议加入和离开通知行为</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-189"><strong>(Optional) Modify conference join and leave announcement behavior</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-190">使用 <strong>Set-CsDialinConferencingConfiguration</strong> 更改参与者加入和离开会议时通知的工作方式。</span><span class="sxs-lookup"><span data-stu-id="2b51c-190">Use the <strong>Set-CsDialinConferencingConfiguration</strong> to change how announcements work when participants join and leave conferences.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-191">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-191">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-192">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-192">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-193">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-193">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">Optional在 Lync Server 2013 中启用和禁用会议加入和离开通知</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-194"><a href="lync-server-2013-optional-enable-and-disable-conference-join-and-leave-announcements.md">(Optional) Enable and disable conference join and leave announcements in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b51c-195"><strong>（可选）验证电话拨入式会议</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-195"><strong>(Optional) Verify dial-in conferencing</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-196">使用 <strong>Test-CsDialInConferencing</strong> cmdlet 测试指定池的访问号码是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="2b51c-196">Use the <strong>Test-CsDialInConferencing</strong> cmdlet to test that the access numbers for the specified pool work correctly.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-197">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-197">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-198">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-198">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-199">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-199">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">Optional在 Lync Server 2013 中验证电话拨入式会议</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-200"><a href="lync-server-2013-optional-verify-dial-in-conferencing.md">(Optional) Verify dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b51c-201"><strong>部署 Lync 2013 的联机会议加载项</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-201"><strong>Deploy the Online Meeting Add-in for Lync 2013</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-202">为 Lync 2013 部署联机会议外接程序，以便用户可以安排支持电话拨入式会议的会议。</span><span class="sxs-lookup"><span data-stu-id="2b51c-202">Deploy the Online Meeting Add-in for Lync 2013 so that users can schedule conferences that support dial-in conferencing.</span></span> <span data-ttu-id="2b51c-203">安装 Lync 2013 时，会自动安装 Lync 2013 的联机会议外接程序。</span><span class="sxs-lookup"><span data-stu-id="2b51c-203">The Online Meeting Add-in for Lync 2013 is installed automatically when you install Lync 2013.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-204">管理员</span><span class="sxs-lookup"><span data-stu-id="2b51c-204">Administrators</span></span></p></td>
<td><p><span data-ttu-id="2b51c-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">部署 Lync 2013 的联机会议加载项</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-205"><a href="lync-server-2013-deploy-the-online-meeting-add-in-for-lync-2013.md">Deploy the Online Meeting Add-in for Lync 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b51c-206"><strong>配置用户帐户设置</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-206"><strong>Configure user account settings</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-207">使用 Lync Server 2013 控制面板或 Lync Server 命令行管理程序将电话<strong>线路 URI</strong>配置为唯一的规范化电话号码（例如，电话： + 14255550200）。</span><span class="sxs-lookup"><span data-stu-id="2b51c-207">Use Lync Server 2013 Control Panel or Lync Server Management Shell to configure the telephony <strong>Line URI</strong> as a unique, normalized phone number (for example, tel:+14255550200).</span></span></p></td>
<td><p><span data-ttu-id="2b51c-208">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-208">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="2b51c-209">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-209">CsAdministrator</span></span></p>
<p><span data-ttu-id="2b51c-210">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="2b51c-210">CsUserAdministrator</span></span></p></td>
<td><p><span data-ttu-id="2b51c-211"><a href="lync-server-2013-configure-user-account-settings.md">在 Lync Server 2013 中配置用户帐户设置</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-211"><a href="lync-server-2013-configure-user-account-settings.md">Configure user account settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="2b51c-212">适合配置会议目录</span><span class="sxs-lookup"><span data-stu-id="2b51c-212">(Recommended) Configure conference directories</span></span></p></td>
<td><p><span data-ttu-id="2b51c-213">使用<strong>new-csconferencedirectory</strong> cmdlet 可以为池中的每个999用户创建一个会议目录。</span><span class="sxs-lookup"><span data-stu-id="2b51c-213">Use the <strong>New-CsConferenceDirectory</strong> cmdlet to create one conference directory for every 999 users in the pool.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-214">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-214">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2b51c-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Lync Server 2013 中的电话拨入式会议要求</a> <a href="recommended-create-conference-directories.md">（推荐）创建会议目录</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-215"><a href="lync-server-2013-dial-in-conferencing-requirements.md">Dial-in conferencing requirements in Lync Server 2013</a> <a href="recommended-create-conference-directories.md">(Recommended) Create Conference Directories</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="2b51c-216"><strong>（可选）欢迎用户参加电话拨入式会议并设置初始 PIN</strong></span><span class="sxs-lookup"><span data-stu-id="2b51c-216"><strong>(Optional) Welcome users to dial-in conferencing and set the initial PIN</strong></span></span></p></td>
<td><p><span data-ttu-id="2b51c-217">使用<strong>set-cspinsendcawelcomemail</strong>脚本设置用户的初始 pin，并发送包含初始 PIN 和指向 "电话拨入式会议设置" 页的链接的欢迎电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2b51c-217">Use the <strong>Set-CsPinSendCAWelcomeMail</strong> script to set users' initial PINs and send a welcome email that contains the initial PIN and a link to the Dial-in Conferencing Settings page.</span></span></p></td>
<td><p><span data-ttu-id="2b51c-218">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="2b51c-218">RTCUniversalServerAdmins</span></span></p></td>
<td><p><span data-ttu-id="2b51c-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">OptionalLync Server 2013 中的欢迎用户参加电话拨入式会议</a></span><span class="sxs-lookup"><span data-stu-id="2b51c-219"><a href="lync-server-2013-optional-welcome-users-to-dial-in-conferencing.md">(Optional) Welcome users to dial-in conferencing in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

