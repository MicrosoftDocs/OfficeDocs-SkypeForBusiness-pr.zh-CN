---
title: Lync Server 2013：呼叫寄存的部署过程
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deployment process for Call Park
ms:assetid: 2000d672-a85f-4262-9d69-0bee9ae3709a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398283(v=OCS.15)
ms:contentKeyID: 48183586
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a6e11f85cb929cdd3dbddcab23caaffcf434f303
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213538"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deployment-process-for-call-park-in-lync-server-2013"></a><span data-ttu-id="abbfa-102">Lync Server 2013 中呼叫寄存的部署过程</span><span class="sxs-lookup"><span data-stu-id="abbfa-102">Deployment process for Call Park in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="abbfa-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="abbfa-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="abbfa-104">本节概述了部署呼叫寄存应用程序所涉及的步骤。</span><span class="sxs-lookup"><span data-stu-id="abbfa-104">This section provides an overview of the steps involved in deploying the Call Park application.</span></span> <span data-ttu-id="abbfa-105">在配置呼叫寄存之前，必须使用 Enterprise Voice 部署 Enterprise Edition 或 Standard Edition。</span><span class="sxs-lookup"><span data-stu-id="abbfa-105">You must deploy Enterprise Edition or Standard Edition with Enterprise Voice before you configure Call Park.</span></span> <span data-ttu-id="abbfa-106">当您部署企业语音时，会安装并启用呼叫寄存所需的组件。</span><span class="sxs-lookup"><span data-stu-id="abbfa-106">The components required by Call Park are installed and enabled when you deploy Enterprise Voice.</span></span>

### <a name="call-park-deployment-process"></a><span data-ttu-id="abbfa-107">呼叫寄存部署过程</span><span class="sxs-lookup"><span data-stu-id="abbfa-107">Call Park Deployment Process</span></span>

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="abbfa-108">阶段</span><span class="sxs-lookup"><span data-stu-id="abbfa-108">Phase</span></span></th>
<th><span data-ttu-id="abbfa-109">步骤</span><span class="sxs-lookup"><span data-stu-id="abbfa-109">Steps</span></span></th>
<th><span data-ttu-id="abbfa-110">所需的组和角色</span><span class="sxs-lookup"><span data-stu-id="abbfa-110">Required groups and roles</span></span></th>
<th><span data-ttu-id="abbfa-111">部署文档</span><span class="sxs-lookup"><span data-stu-id="abbfa-111">Deployment documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="abbfa-112">在通道表中配置呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="abbfa-112">Configure the call park orbit ranges in the orbit table</span></span></p></td>
<td><p><span data-ttu-id="abbfa-113">使用 Lync Server 控制面板或<strong>CSCallParkOrbit</strong> cmdlet 可以在呼叫寄存通道表中创建轨道范围，并将它们与承载呼叫寄存应用程序的应用程序服务相关联。</span><span class="sxs-lookup"><span data-stu-id="abbfa-113">Use Lync Server Control Panel or the <strong>New-CSCallParkOrbit</strong> cmdlet to create the orbit ranges in the call park orbit table and associate them with the Application service that hosts the Call Park application.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abbfa-p102">为与现有拨号计划进行无缝集成，通道范围通常配置为虚拟分机块。不支持将外线直拨分机 (DID) 号码分配为呼叫寄存通道表中的通道号码。</span><span class="sxs-lookup"><span data-stu-id="abbfa-p102">For seamless integration with existing dial plans, orbit ranges are typically configured as a block of virtual extensions. Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the call park orbit table is not supported.</span></span>


</div></td>
<td><p><span data-ttu-id="abbfa-116">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="abbfa-116">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="abbfa-117">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-117">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-118">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-118">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-119">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-119">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="abbfa-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">在 Lync Server 2013 中创建或修改呼叫寄存通道范围</a></span><span class="sxs-lookup"><span data-stu-id="abbfa-120"><a href="lync-server-2013-create-or-modify-a-call-park-orbit-range.md">Create or modify a Call Park orbit range in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abbfa-121">配置呼叫寄存设置</span><span class="sxs-lookup"><span data-stu-id="abbfa-121">Configure Call Park settings</span></span></p></td>
<td><p><span data-ttu-id="abbfa-122">使用<strong>CsCpsConfiguration</strong> cmdlet 可以配置呼叫寄存设置。</span><span class="sxs-lookup"><span data-stu-id="abbfa-122">Use the <strong>Set-CsCpsConfiguration</strong> cmdlet to configure Call Park settings.</span></span> <span data-ttu-id="abbfa-123">我们建议您至少配置<strong>OnTimeoutURI</strong>选项，以配置在寄存呼叫超时时使用的回退目标。您还可以配置以下设置：</span><span class="sxs-lookup"><span data-stu-id="abbfa-123">At a minimum, we recommend that you configure the <strong>OnTimeoutURI</strong> option to configure the fallback destination to use when a parked call times out. You can also configure the following settings:</span></span></p>
<ul>
<li><p><span data-ttu-id="abbfa-124">（可选）配置 <strong>EnableMusicOnHold</strong> 以启用或禁用保持音乐。</span><span class="sxs-lookup"><span data-stu-id="abbfa-124">(Optional) <strong>EnableMusicOnHold</strong> to enable or disable music on hold.</span></span></p></li>
<li><p><span data-ttu-id="abbfa-125">（可选）配置 <strong>MaxCallPickupAttempts</strong> 以确定将寄存呼叫转接到回退统一资源标识符 (URI) 之前该呼叫回拨应答电话的次数。</span><span class="sxs-lookup"><span data-stu-id="abbfa-125">(Optional) <strong>MaxCallPickupAttempts</strong> to determine the number of times a parked call rings back to the answering phone before forwarding the call to the fallback Uniform Resource Identifier (URI).</span></span></p></li>
<li><p><span data-ttu-id="abbfa-126">（可选）配置 <strong>CallPickupTimeoutThreshold</strong> 以确定呼叫寄存后到回拨应答该呼叫的电话之前等待的时间。</span><span class="sxs-lookup"><span data-stu-id="abbfa-126">(Optional) <strong>CallPickupTimeoutThreshold</strong> to determine the amount of time that elapses after a call has been parked before it rings back to the phone where the call was answered.</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="abbfa-127">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="abbfa-127">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="abbfa-128">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-128">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-129">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-129">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-130">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-130">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="abbfa-131"><a href="lync-server-2013-configure-call-park-settings.md">在 Lync Server 2013 中配置呼叫寄存设置</a></span><span class="sxs-lookup"><span data-stu-id="abbfa-131"><a href="lync-server-2013-configure-call-park-settings.md">Configure Call Park settings in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abbfa-132">（可选）自定义保持音乐</span><span class="sxs-lookup"><span data-stu-id="abbfa-132">Optionally, customize the music on hold</span></span></p></td>
<td><p><span data-ttu-id="abbfa-133">使用 <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet 自定义并上载音频文件（如果不使用默认的保持音乐）。</span><span class="sxs-lookup"><span data-stu-id="abbfa-133">Use the <strong>Set-CsCallParkServiceMusicOnHoldFile</strong> cmdlet to customize and upload an audio file, if you don't want to use the default music on hold.</span></span></p></td>
<td><p><span data-ttu-id="abbfa-134">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="abbfa-134">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="abbfa-135">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-135">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-136">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-136">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-137">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-137">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="abbfa-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">在 Lync Server 2013 中自定义呼叫寄存暂停音乐</a></span><span class="sxs-lookup"><span data-stu-id="abbfa-138"><a href="lync-server-2013-customize-call-park-music-on-hold.md">Customize Call Park music on hold in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abbfa-139">配置语音策略以为用户启用呼叫寄存</span><span class="sxs-lookup"><span data-stu-id="abbfa-139">Configure voice policy to enable Call Park for users</span></span></p></td>
<td><p><span data-ttu-id="abbfa-140">使用 Lync Server 控制面板或带有<strong>EnableCallPark</strong>选项的<strong>set-csvoicepolicy</strong> cmdlet 为语音策略中的用户启用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="abbfa-140">Use Lync Server Control Panel or the <strong>Set-CSVoicePolicy</strong> cmdlet with the <strong>EnableCallPark</strong> option to enable Call Park for users in voice policy.</span></span></p>
<div>

> [!NOTE]  
> <span data-ttu-id="abbfa-141">默认情况下，对所有用户禁用呼叫寄存。</span><span class="sxs-lookup"><span data-stu-id="abbfa-141">By default, Call Park is disabled for all users.</span></span>


</div>
<div>

> [!NOTE]  
> <span data-ttu-id="abbfa-142">如果具有多个语音策略，请确保为每个语音策略（而不只是默认策略）设置 EnableCallPark 属性。</span><span class="sxs-lookup"><span data-stu-id="abbfa-142">If you have multiple voice policies, make sure the EnableCallPark property is set for each voice policy, not just for the default policy.</span></span>


</div></td>
<td><p><span data-ttu-id="abbfa-143">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="abbfa-143">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="abbfa-144">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-144">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-145">CsUserAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-145">CsUserAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-146">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-146">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="abbfa-147"><a href="lync-server-2013-enable-call-park-for-users.md">在 Lync Server 2013 中为用户启用呼叫寄存</a></span><span class="sxs-lookup"><span data-stu-id="abbfa-147"><a href="lync-server-2013-enable-call-park-for-users.md">Enable Call Park for users in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="abbfa-148">验证呼叫寄存的规范化规则</span><span class="sxs-lookup"><span data-stu-id="abbfa-148">Verify normalization rules for Call Park</span></span></p></td>
<td><p><span data-ttu-id="abbfa-p104">不能对呼叫寄存通道进行规范化。验证规范化规则是否未包含任何通道范围。如有必要，创建其他规范化规则以阻止对通道进行规范化。</span><span class="sxs-lookup"><span data-stu-id="abbfa-p104">Call park orbits must not be normalized. Verify that your normalization rules do not include any of your orbit ranges. If necessary, create additional normalization rules to prevent orbits being normalized.</span></span></p></td>
<td><p><span data-ttu-id="abbfa-152">RTCUniversalServerAdmins</span><span class="sxs-lookup"><span data-stu-id="abbfa-152">RTCUniversalServerAdmins</span></span></p>
<p><span data-ttu-id="abbfa-153">CsVoiceAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-153">CsVoiceAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-154">CsServerAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-154">CsServerAdministrator</span></span></p>
<p><span data-ttu-id="abbfa-155">CsAdministrator</span><span class="sxs-lookup"><span data-stu-id="abbfa-155">CsAdministrator</span></span></p></td>
<td><p><span data-ttu-id="abbfa-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">在 Lync Server 2013 中验证呼叫寄存的规范化规则</a></span><span class="sxs-lookup"><span data-stu-id="abbfa-156"><a href="lync-server-2013-verify-normalization-rules-for-call-park.md">Verify normalization rules for Call Park in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="abbfa-157">验证您的呼叫寄存部署</span><span class="sxs-lookup"><span data-stu-id="abbfa-157">Verify your Call Park deployment</span></span></p></td>
<td><p><span data-ttu-id="abbfa-158">测试停车和检索调用以确保您的配置按预期方式工作。</span><span class="sxs-lookup"><span data-stu-id="abbfa-158">Test parking and retrieving calls to make sure that your configuration works as expected.</span></span></p></td>
<td><p>-</p></td>
<td><p><span data-ttu-id="abbfa-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">Optional在 Lync Server 2013 中验证呼叫寄存部署</a></span><span class="sxs-lookup"><span data-stu-id="abbfa-159"><a href="lync-server-2013-optional-verify-call-park-deployment.md">(Optional) Verify Call Park deployment in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

