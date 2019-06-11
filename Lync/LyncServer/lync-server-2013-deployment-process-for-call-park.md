---
title: 'Lync Server 2013: 呼叫寄存的部署过程'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bab02c8cfbf0f1ca71aff85c8a71a2bcb20ee3fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830480"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="bc32c-102">Lync Server 2013 中的呼叫寄存的部署过程</span><span class="sxs-lookup"><span data-stu-id="bc32c-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bc32c-103">_**主题上次修改时间:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="bc32c-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="bc32c-104">本部分概述了部署通话寄存应用程序时所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="bc32c-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="bc32c-105">您必须先部署企业版或具有企业语音的标准版, 然后才能配置呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="bc32c-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="bc32c-106">部署 "企业语音" 时, 将安装并启用 "呼叫寄存" 所需的组件。</span><span class="sxs-lookup"><span data-stu-id="bc32c-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="bc32c-107">呼叫寄存部署过程</span><span class="sxs-lookup"><span data-stu-id="bc32c-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bc32c-108">阶段</span><span class="sxs-lookup"><span data-stu-id="bc32c-108">Phase</span></span></th>
<th><span data-ttu-id="bc32c-109">步骤</span><span class="sxs-lookup"><span data-stu-id="bc32c-109">Steps</span></span></th>
<th><span data-ttu-id="bc32c-110">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="bc32c-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="bc32c-111">部署文档</span><span class="sxs-lookup"><span data-stu-id="bc32c-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bc32c-112">在通道表中配置呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="bc32c-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="bc32c-113">使用 Lync Server 控制面板或<strong>CSCallParkOrbit</strong> cmdlet 在 "呼叫公园轨道" 表中创建轨道范围, 并将它们与托管呼叫寄存应用程序的应用程序服务相关联。</span><span class="sxs-lookup"><span data-stu-id="bc32c-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bc32c-p102">为与现有拨号计划进行无缝集成，通道范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存通道表中的通道号码。</span><span class="sxs-lookup"><span data-stu-id="bc32c-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="bc32c-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bc32c-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bc32c-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc32c-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">在 Lync Server 2013 中创建或修改呼叫寄存的轨道范围</a></span><span class="sxs-lookup"><span data-stu-id="bc32c-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc32c-121">配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="bc32c-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="bc32c-122">使用<strong>CsCpsConfiguration</strong> Cmdlet 配置呼叫寄存设置。</span><span class="sxs-lookup"><span data-stu-id="bc32c-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="bc32c-123">我们建议你将<strong>OnTimeoutURI</strong>选项配置为配置备用目标以在停止通话超时时使用。您还可以配置以下设置:</span><span class="sxs-lookup"><span data-stu-id="bc32c-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="bc32c-124">（可选）配置 <strong>EnableMusicOnHold</strong> 以启用或禁用保持音乐。</span><span class="sxs-lookup"><span data-stu-id="bc32c-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="bc32c-125">（可选）配置 <strong>MaxCallPickupAttempts</strong> 以确定将寄存呼叫转接到回退统一资源标识符 (URI) 之前该呼叫回拨应答电话的次数。</span><span class="sxs-lookup"><span data-stu-id="bc32c-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="bc32c-126">（可选）配置 <strong>CallPickupTimeoutThreshold</strong> 以确定呼叫寄存后到回拨应答该呼叫的电话之前等待的时间。</span><span class="sxs-lookup"><span data-stu-id="bc32c-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="bc32c-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bc32c-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bc32c-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc32c-131"><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中配置呼叫寄存设置</a></span><span class="sxs-lookup"><span data-stu-id="bc32c-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc32c-132">（可选）自定义保持音乐</span><span class="sxs-lookup"><span data-stu-id="bc32c-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="bc32c-133">使用 <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet 自定义并上载音频文件（如果不使用默认的保持音乐）。</span><span class="sxs-lookup"><span data-stu-id="bc32c-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="bc32c-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bc32c-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bc32c-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc32c-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">在 Lync Server 2013 中自定义呼叫寄存音乐处于暂停状态</a></span><span class="sxs-lookup"><span data-stu-id="bc32c-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc32c-139">配置语音策略以为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="bc32c-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="bc32c-140">使用 "Lync Server 控制面板" 或<strong>CSVoicePolicy</strong> Cmdlet 和<strong>EnableCallPark</strong>选项为语音策略中的用户启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="bc32c-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="bc32c-141">默认情况下, 将对所有用户禁用 "呼叫寄存"。</span><span class="sxs-lookup"><span data-stu-id="bc32c-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="bc32c-142">如果具有多个语音策略，请确保为每个语音策略（而不只是默认策略）设置 EnableCallPark 属性。</span><span class="sxs-lookup"><span data-stu-id="bc32c-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="bc32c-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bc32c-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bc32c-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc32c-147"><a href="lync-server-2013-enable-call-park-for-users.md">在 Lync Server 2013 中为用户启用呼叫寄存</a></span><span class="sxs-lookup"><span data-stu-id="bc32c-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bc32c-148">验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="bc32c-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="bc32c-p104">不能对呼叫寄存通道进行规范化。验证规范化规则是否未包含任何通道范围。如有必要，创建其他规范化规则以阻止对通道进行规范化。</span><span class="sxs-lookup"><span data-stu-id="bc32c-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="bc32c-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="bc32c-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="bc32c-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="bc32c-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="bc32c-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="bc32c-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">在 Lync Server 2013 中验证呼叫寄存的规范化规则</a></span><span class="sxs-lookup"><span data-stu-id="bc32c-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bc32c-157">验证您的电话寄存部署</span><span class="sxs-lookup"><span data-stu-id="bc32c-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="bc32c-158">测试寄存和取回呼叫以确保配置按预期工作。</span><span class="sxs-lookup"><span data-stu-id="bc32c-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="bc32c-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">可选在 Lync Server 2013 中验证呼叫寄存部署</a></span><span class="sxs-lookup"><span data-stu-id="bc32c-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

