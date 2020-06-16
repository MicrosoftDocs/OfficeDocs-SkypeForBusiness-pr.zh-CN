---
title: 验证配置设置
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2430fe82aa424571405def33139ba315677ffcc7
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44755596"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a><span data-ttu-id="f7606-102">验证配置设置</span><span class="sxs-lookup"><span data-stu-id="f7606-102">Verify configuration settings</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f7606-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="f7606-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="f7606-104">在合并拓扑并运行**CsLegacyConfiguration** cmdlet 之后，请验证是否已将 Office 通信服务器 2007 R2 策略和设置导入到 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="f7606-104">After you merge the topology and run the **Import-CsLegacyConfiguration** cmdlet, verify that your Office Communications Server 2007 R2 policies and settings were imported to Lync Server 2013.</span></span> <span data-ttu-id="f7606-105">下表列出了应确认的策略和设置。</span><span class="sxs-lookup"><span data-stu-id="f7606-105">The following table lists the policies and settings that you should verify.</span></span>

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a><span data-ttu-id="f7606-106">迁移后要确认的策略和设置</span><span class="sxs-lookup"><span data-stu-id="f7606-106">Policies and Settings to Verify after Migration</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7606-107">如果使用该工作负荷：</span><span class="sxs-lookup"><span data-stu-id="f7606-107">If you use this workload:</span></span></th>
<th><span data-ttu-id="f7606-108">确认这些策略和设置：</span><span class="sxs-lookup"><span data-stu-id="f7606-108">Verify these policies and settings:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7606-109">即时消息 (IM) 和会议</span><span class="sxs-lookup"><span data-stu-id="f7606-109">Instant messaging (IM) and conferencing</span></span></p></td>
<td><p><span data-ttu-id="f7606-110">状态策略</span><span class="sxs-lookup"><span data-stu-id="f7606-110">Presence policy</span></span></p>
<p><span data-ttu-id="f7606-111">会议策略</span><span class="sxs-lookup"><span data-stu-id="f7606-111">Conferencing policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-112">电话拨入式会议</span><span class="sxs-lookup"><span data-stu-id="f7606-112">Dial-in conferencing</span></span></p></td>
<td><p><span data-ttu-id="f7606-113">拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="f7606-113">Dial-in access numbers</span></span></p>
<p><span data-ttu-id="f7606-114">拨号计划</span><span class="sxs-lookup"><span data-stu-id="f7606-114">Dial plans</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7606-115">企业语音</span><span class="sxs-lookup"><span data-stu-id="f7606-115">Enterprise Voice</span></span></p></td>
<td><p><span data-ttu-id="f7606-116">语音策略</span><span class="sxs-lookup"><span data-stu-id="f7606-116">Voice policy</span></span></p>
<p><span data-ttu-id="f7606-117">语音路由</span><span class="sxs-lookup"><span data-stu-id="f7606-117">Voice routes</span></span></p>
<p><span data-ttu-id="f7606-118">拨号计划</span><span class="sxs-lookup"><span data-stu-id="f7606-118">Dial plans</span></span></p>
<p><span data-ttu-id="f7606-119">PSTN 用法设置</span><span class="sxs-lookup"><span data-stu-id="f7606-119">PSTN usage settings</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-120">Communicator Web Access</span><span class="sxs-lookup"><span data-stu-id="f7606-120">Communicator Web Access</span></span></p></td>
<td><p><span data-ttu-id="f7606-121">简单 URL</span><span class="sxs-lookup"><span data-stu-id="f7606-121">Simple URLs</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7606-122">外部用户</span><span class="sxs-lookup"><span data-stu-id="f7606-122">External users</span></span></p></td>
<td><p><span data-ttu-id="f7606-123">外部访问策略</span><span class="sxs-lookup"><span data-stu-id="f7606-123">External access policies</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-124">存档</span><span class="sxs-lookup"><span data-stu-id="f7606-124">Archiving</span></span></p></td>
<td><p><span data-ttu-id="f7606-125">存档策略</span><span class="sxs-lookup"><span data-stu-id="f7606-125">Archiving policy</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a><span data-ttu-id="f7606-126">确认策略和设置</span><span class="sxs-lookup"><span data-stu-id="f7606-126">To verify policies and settings</span></span>

1.  <span data-ttu-id="f7606-127">在 Office 通信服务器 2007 R2 环境中，除了用于 Communicator Web Access 的 Url 之外，请记下拨号计划的名称（以前称为位置配置文件）、电话拨入访问号码（会议助理访问电话号码和区域）、语音路由以及上表中列出的策略。</span><span class="sxs-lookup"><span data-stu-id="f7606-127">In your Office Communications Server 2007 R2 environment, make note of the names of dial plans (formerly known as location profiles), dial-in access numbers (Conferencing Attendant access phone numbers and regions), voice routes, and the policies listed in the preceding table, in addition to the URLs used for Communicator Web Access.</span></span>

2.  <span data-ttu-id="f7606-128">在 Lync Server 2013 前端服务器上，打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f7606-128">On the Lync Server 2013 Front End server, open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="f7606-129">若要验证导入的会议策略，请在左窗格中，单击 "**会议**"，单击 "**会议策略**"，然后验证 Office 通信服务器 2007 R2 环境中的所有会议策略是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="f7606-129">To verify imported conferencing policies, in the left pane, click **Conferencing**, click **Conferencing Policy**, and then verify that all the conferencing policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7606-130">以前版本的 Office 通信服务器的<STRONG>会议</STRONG>策略现在称为 Lync Server 2013 中的会议策略。</span><span class="sxs-lookup"><span data-stu-id="f7606-130">The <STRONG>Meeting</STRONG> policy from previous versions of Office Communications Server is now known as the conferencing policy in Lync Server 2013.</span></span> <span data-ttu-id="f7606-131">此外，以前版本的 Office 通信服务器的<STRONG>匿名 Particpants</STRONG>设置现在是 Lync Server 2013 会议策略中的设置。</span><span class="sxs-lookup"><span data-stu-id="f7606-131">Additionally, the <STRONG>Anonymous Particpants</STRONG> setting from previous versions of Office Communications Server is now a setting in the Lync Server 2013 conferencing policy.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7606-132">在 Office 通信服务器 2007 R2 中，如果未将会议策略设置为 "<STRONG>每用户使用</STRONG>"，则只导入全局策略设置。</span><span class="sxs-lookup"><span data-stu-id="f7606-132">In Office Communications Server 2007 R2, if the conferencing policy is not set to <STRONG>use per user</STRONG>, only global policy settings are imported.</span></span> <span data-ttu-id="f7606-133">这种情况下不会导入其他会议策略。</span><span class="sxs-lookup"><span data-stu-id="f7606-133">No other conference policies are imported in this situation.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7606-134">如果在 Office 通信服务器 2007 R2 会议策略中将<STRONG>匿名参与者</STRONG>设置为<STRONG>按用户强制实施</STRONG>，则迁移过程中将创建两个会议策略：一个将<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>设置为<STRONG>True</STRONG> ，另一个设置为<STRONG>AllowAnonymousParticipantsInMeetings</STRONG>设置为<STRONG>False</STRONG>。</span><span class="sxs-lookup"><span data-stu-id="f7606-134">If <STRONG>Anonymous Participants</STRONG> is set to <STRONG>Enforce per user</STRONG> in your Office Communications Server 2007 R2 conferencing policy, two conferencing policies are created during migration: one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>True</STRONG> and one with <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> set to <STRONG>False</STRONG>.</span></span>

    
    </div>

4.  <span data-ttu-id="f7606-135">若要确认导入的拨号计划，请依次单击“语音路由”\*\*\*\* 和“拨号计划”\*\*\*\*，然后确认 Office Communicator 2007 R2 环境中的所有拨号计划都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="f7606-135">To verify imported dial plans, click **Voice Routing**, click **Dial Plan**, and then verify that all the dial plans in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7606-136">在 Lync Server 2013 中，<STRONG>位置配置文件</STRONG>现在称为 "<STRONG>拨号计划</STRONG>"。</span><span class="sxs-lookup"><span data-stu-id="f7606-136">In Lync Server 2013, <STRONG>location profiles</STRONG> are now referred to as <STRONG>dial-plans</STRONG>.</span></span>

    
    </div>

5.  <span data-ttu-id="f7606-137">若要确认导入的语音策略，请依次单击“语音路由”\*\*\*\* 和“语音策略”\*\*\*\*，然后确认 Office Communicator 2007 R2 环境中的所有语音策略都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="f7606-137">To verify imported voice policies, click **Voice Routing**, click **Voice Policy**, and then verify that all the voice policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f7606-138">如果您的 Office 通信服务器 2007 R2 环境中的 "语音策略" 未设置为 "在<STRONG>每个用户使用</STRONG>"，则只导入全局策略设置。</span><span class="sxs-lookup"><span data-stu-id="f7606-138">If voice policy is not set to <STRONG>use per user</STRONG> in your Office Communications Server 2007 R2 environment, only global policy settings are imported.</span></span> <span data-ttu-id="f7606-139">这种情况下不会导入其他语音策略。</span><span class="sxs-lookup"><span data-stu-id="f7606-139">No other voice policies are imported in this situation.</span></span>

    
    </div>

6.  <span data-ttu-id="f7606-140">若要确认导入的语音路由，请依次单击“语音路由”\*\*\*\* 和“路由”\*\*\*\*，然后确认 Office Communicator 2007 R2 环境中的所有语音路由都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="f7606-140">To verify imported voice routes, click **Voice Routing**, click **Route**, and then verify that all the voice routes in your Office Communicator 2007 R2 environment are included in the list.</span></span>

7.  <span data-ttu-id="f7606-141">若要确认导入的 PSTN 用法设置，请依次单击“语音路由”\*\*\*\* 和“PSTN 用法”\*\*\*\*，然后确认 Office Communicator 2007 R2 环境中的 PSTN 用法设置包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="f7606-141">To verify imported PSTN usage settings, click **Voice Routing**, click **PSTN Usage**, and then verify that the PSTN Usage settings from your Office Communicator 2007 R2 environment are included in the list.</span></span>

8.  <span data-ttu-id="f7606-142">若要确认导入的外部访问策略，请依次单击“联盟和外部访问”\*\*\*\* 和“外部访问策略”\*\*\*\*，然后确认 Office Communicator 2007 R2 环境中的所有外部访问策略都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="f7606-142">To verify imported external access policies, click **Federation and External Access**, click **External Access Policy**, and then verify that all the external access policies in your Office Communicator 2007 R2 environment are included in the list.</span></span>

9.  <span data-ttu-id="f7606-143">若要验证存档策略，请单击 "**监视和存档**"，再单击 "**存档策略**"，然后验证 Office 通信服务器 2007 R2 环境中的所有存档策略是否都包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="f7606-143">To verify archiving policies, click **Monitoring and Archiving**, click **Archiving Policy**, and then verify that all the archiving policies in your Office Communications Server 2007 R2 environment are included in the list.</span></span>

10. <span data-ttu-id="f7606-144">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="f7606-144">Open the Lync Server Management Shell.</span></span>

11. <span data-ttu-id="f7606-145">若要验证状态策略，请在命令行中键入：</span><span class="sxs-lookup"><span data-stu-id="f7606-145">To verify presence policies, at the command line, type the following:</span></span>
    
        Get-CsPresencePolicy
    
    <span data-ttu-id="f7606-146">通过查看**Identity**参数中的名称，验证是否已导入 Office 通信服务器 2007 R2 环境中的所有状态策略。</span><span class="sxs-lookup"><span data-stu-id="f7606-146">By looking at the name in the **Identity** parameter, verify that all the presence policies in your Office Communications Server 2007 R2 environment were imported.</span></span>

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a><span data-ttu-id="f7606-147">使用 cmdlet 确认策略和设置</span><span class="sxs-lookup"><span data-stu-id="f7606-147">To verify policies and settings by using cmdlets</span></span>

1.  <span data-ttu-id="f7606-148">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="f7606-148">Open the Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="f7606-149">运行下表中的 cmdlet 以确认策略和设置。</span><span class="sxs-lookup"><span data-stu-id="f7606-149">Run the cmdlets in the following table to verify policies and settings.</span></span>
    
    <span data-ttu-id="f7606-150">这些 cmdlet 的语法如以下示例所示：</span><span class="sxs-lookup"><span data-stu-id="f7606-150">The syntax of these cmdlets is like the following example:</span></span>
    
        Get-CsConferencingPolicy
    
    <span data-ttu-id="f7606-151">有关这些 cmdlet 的详细信息，请运行：</span><span class="sxs-lookup"><span data-stu-id="f7606-151">For details about these cmdlets, run:</span></span>
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f7606-152">对于该策略或设置：</span><span class="sxs-lookup"><span data-stu-id="f7606-152">For this policy or setting:</span></span></th>
<th><span data-ttu-id="f7606-153">使用该 cmdlet：</span><span class="sxs-lookup"><span data-stu-id="f7606-153">Use this cmdlet:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f7606-154">状态策略</span><span class="sxs-lookup"><span data-stu-id="f7606-154">Presence policy</span></span></p></td>
<td><p><span data-ttu-id="f7606-155"><strong>CsPresencePolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-155"><strong>Get-CsPresencePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-156">会议策略</span><span class="sxs-lookup"><span data-stu-id="f7606-156">Conferencing policy</span></span></p></td>
<td><p><span data-ttu-id="f7606-157"><strong>Set-csconferencingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-157"><strong>Get-CsConferencingPolicy</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7606-158">拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="f7606-158">Dial-in access numbers</span></span></p></td>
<td><p><span data-ttu-id="f7606-159"><strong>Set-csdialinconferencingaccessnumber</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-159"><strong>Get-CsDialInConferencingAccessNumber</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-160">拨号计划</span><span class="sxs-lookup"><span data-stu-id="f7606-160">Dial plans</span></span></p></td>
<td><p><span data-ttu-id="f7606-161"><strong>Grant-csdialplan</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-161"><strong>Get-CsDialPlan</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7606-162">语音策略</span><span class="sxs-lookup"><span data-stu-id="f7606-162">Voice policy</span></span></p></td>
<td><p><span data-ttu-id="f7606-163"><strong>Set-csvoicepolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-163"><strong>Get-CsVoicePolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-164">语音路由</span><span class="sxs-lookup"><span data-stu-id="f7606-164">Voice routes</span></span></p></td>
<td><p><span data-ttu-id="f7606-165"><strong>CsVoiceRoute</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-165"><strong>Get-CsVoiceRoute</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7606-166">PSTN 用法</span><span class="sxs-lookup"><span data-stu-id="f7606-166">PSTN Usage</span></span></p></td>
<td><p><span data-ttu-id="f7606-167"><strong>CsPstnUsage</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-167"><strong>Get-CsPstnUsage</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-168">URL</span><span class="sxs-lookup"><span data-stu-id="f7606-168">URLs</span></span></p></td>
<td><p><span data-ttu-id="f7606-169"><strong>CsSimpleUrlConfiguration</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-169"><strong>Get-CsSimpleUrlConfiguration</strong></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f7606-170">外部访问策略</span><span class="sxs-lookup"><span data-stu-id="f7606-170">External access policies</span></span></p></td>
<td><p><span data-ttu-id="f7606-171"><strong>Set-csexternalaccesspolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-171"><strong>Get-CsExternalAccessPolicy</strong></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f7606-172">存档策略</span><span class="sxs-lookup"><span data-stu-id="f7606-172">Archiving policy</span></span></p></td>
<td><p><span data-ttu-id="f7606-173"><strong>New-csarchivingpolicy</strong></span><span class="sxs-lookup"><span data-stu-id="f7606-173"><strong>Get-CsArchivingPolicy</strong></span></span></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

