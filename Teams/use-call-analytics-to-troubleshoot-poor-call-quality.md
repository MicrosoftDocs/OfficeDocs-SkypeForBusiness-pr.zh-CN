---
title: 使用呼叫分析解决较差的通话质量
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.reviewer: mikedav, vkorlep
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- M365-voice
search.appverid: MET150
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
- Reporting
description: 使用有关设备、网络和连接的每用户呼叫分析详细信息，解决与 Microsoft 团队通话和会议有关的用户问题。
ms.openlocfilehash: 8bee41e79f2610adcb9a1fed3f895c728526f5ea
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/06/2020
ms.locfileid: "46583621"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="32c69-103">使用呼叫分析解决较差的通话质量</span><span class="sxs-lookup"><span data-stu-id="32c69-103">Use call analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="32c69-104">本文介绍如果你是团队管理员或团队沟通支持专家或工程师，如何使用呼叫分析来解决对单个用户的不良 Microsoft 团队通话或会议质量问题。</span><span class="sxs-lookup"><span data-stu-id="32c69-104">This article explains how to use call analytics to troubleshoot poor Microsoft Teams call or meeting quality for individual users if you're a Teams admin or a Teams communications support specialist or engineer.</span></span>


  
## <a name="call-analytics-permissions"></a><span data-ttu-id="32c69-105">调用分析权限</span><span class="sxs-lookup"><span data-stu-id="32c69-105">Call Analytics permissions</span></span>

<span data-ttu-id="32c69-106">本文假定你已设置呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="32c69-106">This article assumes that you've already set up call analytics.</span></span> <span data-ttu-id="32c69-107">如果您没有，请阅读[为团队设置呼叫分析](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="32c69-107">If you haven't, read [Set up call analytics for Teams](set-up-call-analytics.md).</span></span>

## <a name="introduction-to-call-analytics"></a><span data-ttu-id="32c69-108">通话分析简介</span><span class="sxs-lookup"><span data-stu-id="32c69-108">Introduction to call analytics</span></span>

<span data-ttu-id="32c69-109">通话分析显示有关团队使用 Office 365 帐户中的每个用户的呼叫和会议的详细信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-109">Call analytics shows detailed information about Teams calls and meetings for each user in your Office 365 account.</span></span> <span data-ttu-id="32c69-110">其中包括有关设备、网络、连接和通话质量的信息 (其中任何一项都可能是较差的通话或会议质量) 因素。</span><span class="sxs-lookup"><span data-stu-id="32c69-110">It includes information about devices, networks, connectivity, and call quality (any of these can be a factor in poor call or meeting quality).</span></span> <span data-ttu-id="32c69-111">如果你上载建筑物、网站和租户信息，还将为每个呼叫和会议显示此信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-111">If you upload building, site, and tenant information, this information will also be shown for each call and meeting.</span></span> <span data-ttu-id="32c69-112">使用呼叫分析可帮助你了解为什么用户通话或会议体验不佳的原因。</span><span class="sxs-lookup"><span data-stu-id="32c69-112">Use call analytics to help you figure out why a user had a poor call or meeting experience.</span></span>

<span data-ttu-id="32c69-113">"呼叫分析" 显示通话或会议的每个腿，例如，从一个参与者到第二个参与者。</span><span class="sxs-lookup"><span data-stu-id="32c69-113">Call analytics shows you each leg of a call or meeting - for example, from one participant to a second participant.</span></span> <span data-ttu-id="32c69-114">通过分析这些详细信息，团队管理员可以隔离问题区域并确定质量较差的根本原因。</span><span class="sxs-lookup"><span data-stu-id="32c69-114">By analyzing these details, a Teams admin can isolate problem areas and identify the root cause for poor quality.</span></span>
   
<span data-ttu-id="32c69-115">作为团队管理员，您可以完全访问每个用户的所有呼叫分析数据。</span><span class="sxs-lookup"><span data-stu-id="32c69-115">As the Teams admin, you get full access to all call analytics data for each user.</span></span> <span data-ttu-id="32c69-116">此外，你可以将 Azure Active Directory 角色分配给支持人员。</span><span class="sxs-lookup"><span data-stu-id="32c69-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="32c69-117">若要了解有关这些角色的详细信息，请参阅[向支持人员和帮助台人员提供权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。</span><span class="sxs-lookup"><span data-stu-id="32c69-117">To learn more about these roles, read [Give permission to support and helpdesk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).</span></span> <span data-ttu-id="32c69-118">不要错过[每个团队支持 "角色" 的功能](#what-does-each-teams-support-role-do)。</span><span class="sxs-lookup"><span data-stu-id="32c69-118">Don't miss [What does each Teams Support role do?](#what-does-each-teams-support-role-do) below.</span></span>

## <a name="where-to-find-per-user-call-analytics"></a><span data-ttu-id="32c69-119">在哪里可以找到每用户呼叫分析</span><span class="sxs-lookup"><span data-stu-id="32c69-119">Where to find per-user call analytics</span></span>

<span data-ttu-id="32c69-120">若要查看用户的所有呼叫信息和数据，请转到[团队管理中心](https://admin.teams.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="32c69-120">To see all call information and data for a user, go to the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="32c69-121">在 "**用户**" 下，选择用户，然后在用户的配置文件页面上打开 "**通话记录**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="32c69-121">Under **Users**, select a user and then open the **Call History** tab on the user's profile page.</span></span> <span data-ttu-id="32c69-122">在这里，你将在过去30天内找到该用户的所有通话和会议。</span><span class="sxs-lookup"><span data-stu-id="32c69-122">Here you'll find all calls and meetings for that user for the last 30 days.</span></span>

![所有分析用户数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="32c69-124">若要获取有关给定会话的其他信息（包括详细的媒体和网络统计信息），请单击某个会话以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-124">To get additional information about a given session, including detailed media and networking statistics, click a session to see the details.</span></span>

![呼叫分析用户会话数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)
  
## <a name="what-does-each-teams-support-role-do"></a><span data-ttu-id="32c69-126">每个团队支持什么角色？</span><span class="sxs-lookup"><span data-stu-id="32c69-126">What does each Teams Support role do?</span></span>

<span data-ttu-id="32c69-127">**团队通信支持专家** (第1层支持) 处理基本的通话质量问题。</span><span class="sxs-lookup"><span data-stu-id="32c69-127">The **Teams communications support specialist** (Tier 1 support) handles basic call-quality problems.</span></span> <span data-ttu-id="32c69-128">他们不会调查会议问题。</span><span class="sxs-lookup"><span data-stu-id="32c69-128">They don't investigate issues with meetings.</span></span> <span data-ttu-id="32c69-129">而是收集相关信息，然后升级到通信支持工程师。</span><span class="sxs-lookup"><span data-stu-id="32c69-129">Instead, they collect related information and then escalate to a communications support engineer.</span></span> 

<span data-ttu-id="32c69-130">**团队通信支持工程师** (第2层支持) 可查看来自团队通信支持专家隐藏的详细呼叫日志中的信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-130">The **Teams communications support engineer** (Tier 2 support) sees information in detailed call logs that are hidden from the Teams communications support specialist.</span></span> <span data-ttu-id="32c69-131">下表列出了每个团队通信支持角色可用的信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-131">The table below lists the information available to each Teams communication support role.</span></span>

<span data-ttu-id="32c69-132">下表告诉你每个用户的信息对每个通信支持角色可用。</span><span class="sxs-lookup"><span data-stu-id="32c69-132">The following table tells you what per-user information is available for each communications support role.</span></span>

|<span data-ttu-id="32c69-133">**活动**</span><span class="sxs-lookup"><span data-stu-id="32c69-133">**Activity**</span></span>|<span data-ttu-id="32c69-134">**信息**</span><span class="sxs-lookup"><span data-stu-id="32c69-134">**Information**</span></span>|<span data-ttu-id="32c69-135">通信支持**专家**可以看到的内容</span><span class="sxs-lookup"><span data-stu-id="32c69-135">What the communications support **specialist** sees</span></span>|<span data-ttu-id="32c69-136">通信支持**工程师**看到的内容</span><span class="sxs-lookup"><span data-stu-id="32c69-136">What the communications support **engineer** sees</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32c69-137">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="32c69-137">**Calls**</span></span> <br/> |<span data-ttu-id="32c69-138">呼叫者姓名</span><span class="sxs-lookup"><span data-stu-id="32c69-138">Caller name</span></span>  <br/> |<span data-ttu-id="32c69-139">仅限代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="32c69-139">Only the name of the user for whom the agent searched.</span></span>  <br/> |<span data-ttu-id="32c69-140">用户名。</span><span class="sxs-lookup"><span data-stu-id="32c69-140">User name.</span></span>  <br/> |
||<span data-ttu-id="32c69-141">收件人姓名</span><span class="sxs-lookup"><span data-stu-id="32c69-141">Recipient name</span></span>  <br/> |<span data-ttu-id="32c69-142">显示为内部用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="32c69-142">Shows as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="32c69-143">收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="32c69-143">Recipient name.</span></span>  <br/> |
||<span data-ttu-id="32c69-144">主叫方电话号码</span><span class="sxs-lookup"><span data-stu-id="32c69-144">Caller phone number</span></span>  <br/> |<span data-ttu-id="32c69-145">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="32c69-145">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="32c69-146">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="32c69-146">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="32c69-147">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="32c69-147">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="32c69-148">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="32c69-148">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="32c69-149">收件人电话号码</span><span class="sxs-lookup"><span data-stu-id="32c69-149">Recipient phone number</span></span>  <br/> |<span data-ttu-id="32c69-150">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="32c69-150">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="32c69-151">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="32c69-151">For example, 15552823\*\*\*.</span></span>  <br/> |<span data-ttu-id="32c69-152">除最后三位数字之外的整个电话号码都被用星号符号混淆。</span><span class="sxs-lookup"><span data-stu-id="32c69-152">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="32c69-153">例如，15552823 \* \* \*。</span><span class="sxs-lookup"><span data-stu-id="32c69-153">For example, 15552823\*\*\*.</span></span>  <br/> |
||<span data-ttu-id="32c69-154">**通话详情**  > "**高级**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="32c69-154">**Call Details** > **Advanced** tab</span></span> <br/> |<span data-ttu-id="32c69-155">未显示信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-155">Information not shown.</span></span>  <br/> |<span data-ttu-id="32c69-156">显示所有详细信息，如设备名称、IP 地址、子网映射等。</span><span class="sxs-lookup"><span data-stu-id="32c69-156">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>  <br/> |
||<span data-ttu-id="32c69-157">**通话详情**  > **高级**  > "**调试**" 选项卡</span><span class="sxs-lookup"><span data-stu-id="32c69-157">**Call Details** > **Advanced** > **Debug** tab</span></span> <br/> |<span data-ttu-id="32c69-158">未显示信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-158">Information not shown.</span></span>  <br/> |<span data-ttu-id="32c69-159">显示所有详细信息，如 DNS 后缀和 SSID。</span><span class="sxs-lookup"><span data-stu-id="32c69-159">All details shown, such as DNS suffix and SSID.</span></span>  <br/> |
|<span data-ttu-id="32c69-160">**会议**</span><span class="sxs-lookup"><span data-stu-id="32c69-160">**Meetings**</span></span> <br/> |<span data-ttu-id="32c69-161">参与者姓名</span><span class="sxs-lookup"><span data-stu-id="32c69-161">Participant names</span></span>  <br/> |<span data-ttu-id="32c69-162">仅限代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="32c69-162">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="32c69-163">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="32c69-163">Other participants identified as Internal User or External User.</span></span>  <br/> |<span data-ttu-id="32c69-164">显示所有名称。</span><span class="sxs-lookup"><span data-stu-id="32c69-164">All names shown.</span></span>  <br/> |
||<span data-ttu-id="32c69-165">参与者计数</span><span class="sxs-lookup"><span data-stu-id="32c69-165">Participant count</span></span>  <br/> |<span data-ttu-id="32c69-166">参与者的数量。</span><span class="sxs-lookup"><span data-stu-id="32c69-166">Number of participants.</span></span>  <br/> |<span data-ttu-id="32c69-167">参与者的数量。</span><span class="sxs-lookup"><span data-stu-id="32c69-167">Number of participants.</span></span>  <br/> |
||<span data-ttu-id="32c69-168">会话详细信息</span><span class="sxs-lookup"><span data-stu-id="32c69-168">Session details</span></span>  <br/> |<span data-ttu-id="32c69-169">与异常一起显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-169">Session details shown with exceptions.</span></span> <span data-ttu-id="32c69-170">仅显示对其进行代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="32c69-170">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="32c69-171">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="32c69-171">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="32c69-172">用星号符号进行混淆的电话号码的最后三位数字。</span><span class="sxs-lookup"><span data-stu-id="32c69-172">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |<span data-ttu-id="32c69-173">显示的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-173">Session details shown.</span></span> <span data-ttu-id="32c69-174">显示的用户名和会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="32c69-174">User names and session details shown.</span></span> <span data-ttu-id="32c69-175">用星号符号进行混淆的电话号码的最后三位数字。</span><span class="sxs-lookup"><span data-stu-id="32c69-175">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>  <br/> |
||||
  
## <a name="troubleshoot-user-call-quality-problems"></a><span data-ttu-id="32c69-176">解决用户呼叫质量问题</span><span class="sxs-lookup"><span data-stu-id="32c69-176">Troubleshoot user call quality problems</span></span> 

1. <span data-ttu-id="32c69-177">打开 "团队管理中心" (https://admin.teams.microsoft.com) 并通过团队通信支持或团队管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="32c69-177">Open the Teams admin center (https://admin.teams.microsoft.com) and sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="32c69-178">在**仪表板**上的 "**用户搜索**" 中，开始键入要对其进行故障排除的用户的名称或 SIP 地址，或选择 "**查看用户**" 以查看用户列表。</span><span class="sxs-lookup"><span data-stu-id="32c69-178">On the **Dashboard**, in **User Search**, start typing either the name or SIP address of the user whose calls you want to troubleshoot, or select **View users** to see a list of users.</span></span>

3. <span data-ttu-id="32c69-179">从列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="32c69-179">Select the user from the list.</span></span>

4. <span data-ttu-id="32c69-180">选择 "**呼叫历史记录**"，然后选择要进行故障排除的呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="32c69-180">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
5. <span data-ttu-id="32c69-181">选择 "**高级**" 选项卡，然后查找表示通话质量不佳或连接问题的黄色和红色项目。</span><span class="sxs-lookup"><span data-stu-id="32c69-181">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="32c69-182">在每个通话或会议的 "会话详细信息" 中，小问题显示为黄色。</span><span class="sxs-lookup"><span data-stu-id="32c69-182">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="32c69-183">如果某个内容为黄色，则它不在正常范围内，它可能会导致问题，但不太可能是问题的主要原因。</span><span class="sxs-lookup"><span data-stu-id="32c69-183">If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="32c69-184">如果出现红色，这是一个重大问题，这很可能是本次会议的通话质量不佳的主要原因。</span><span class="sxs-lookup"><span data-stu-id="32c69-184">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
      
<span data-ttu-id="32c69-185">在极少数情况下，音频会话的体验数据质量未收到。</span><span class="sxs-lookup"><span data-stu-id="32c69-185">In rare cases, Quality of Experience data isn't received for audio sessions.</span></span> <span data-ttu-id="32c69-186">这通常是由于断开的呼叫或与客户端的连接终止所致。</span><span class="sxs-lookup"><span data-stu-id="32c69-186">Often this is caused by the a dropped call or when the connection with the client terminates.</span></span> <span data-ttu-id="32c69-187">出现这种情况时，**无法使用**"会话分级"。</span><span class="sxs-lookup"><span data-stu-id="32c69-187">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="32c69-188">对于具有经验 (QoE) 数据的音频会话，下表介绍了将会话限定为**差**的主要问题。</span><span class="sxs-lookup"><span data-stu-id="32c69-188">For audio sessions that do have Quality of Experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="32c69-189">**问题**</span><span class="sxs-lookup"><span data-stu-id="32c69-189">**Issue**</span></span>|<span data-ttu-id="32c69-190">**区域**</span><span class="sxs-lookup"><span data-stu-id="32c69-190">**Area**</span></span>|<span data-ttu-id="32c69-191">**说明**</span><span class="sxs-lookup"><span data-stu-id="32c69-191">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="32c69-192">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="32c69-192">Call setup</span></span>  <br/> |<span data-ttu-id="32c69-193">Session</span><span class="sxs-lookup"><span data-stu-id="32c69-193">Session</span></span>  <br/> |<span data-ttu-id="32c69-194">错误代码 Ms-诊断20-29 指示呼叫设置失败。</span><span class="sxs-lookup"><span data-stu-id="32c69-194">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="32c69-195">用户无法加入呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="32c69-195">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="32c69-196">音频网络分类差通话</span><span class="sxs-lookup"><span data-stu-id="32c69-196">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="32c69-197">Session</span><span class="sxs-lookup"><span data-stu-id="32c69-197">Session</span></span>  <br/> |<span data-ttu-id="32c69-198">遇到 (的网络质量问题，例如数据包丢失、抖动、NMOS 下降、RTT 或隐藏比率) 。</span><span class="sxs-lookup"><span data-stu-id="32c69-198">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span>  <br/> |
|<span data-ttu-id="32c69-199">设备不起作用</span><span class="sxs-lookup"><span data-stu-id="32c69-199">Device not functioning</span></span>  <br/> |<span data-ttu-id="32c69-200">Device</span><span class="sxs-lookup"><span data-stu-id="32c69-200">Device</span></span>  <br/> | <span data-ttu-id="32c69-201">设备不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="32c69-201">A device isn't functioning correctly.</span></span> <span data-ttu-id="32c69-202">设备的运行比率为：</span><span class="sxs-lookup"><span data-stu-id="32c69-202">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="32c69-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="32c69-203">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="32c69-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="32c69-204">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   

## <a name="related-topics"></a><span data-ttu-id="32c69-205">相关主题</span><span class="sxs-lookup"><span data-stu-id="32c69-205">Related topics</span></span>

[<span data-ttu-id="32c69-206">设置每用户呼叫分析</span><span class="sxs-lookup"><span data-stu-id="32c69-206">Set up per-user call analytics</span></span>](set-up-call-analytics.md)



  
 
