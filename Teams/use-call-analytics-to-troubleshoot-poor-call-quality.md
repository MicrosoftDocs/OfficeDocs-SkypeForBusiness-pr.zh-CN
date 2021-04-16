---
title: 使用呼叫分析排查通话质量不佳的问题
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
description: 使用有关设备、网络和连接的用户通话分析详细信息来排查 Microsoft Teams 呼叫和会议的用户问题。
ms.openlocfilehash: 4732cf68624b824a452455fc779b22ae7eb32d56
ms.sourcegitcommit: ca2230a981a1e3c03437d1ecb8727d66ad6967f9
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760556"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="b79b5-103">使用呼叫分析排查通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="b79b5-103">Use call analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="b79b5-104">本文介绍如果你是 Teams 管理员或 Teams 通信支持专家或工程师，如何使用呼叫分析来排查个别用户的 Microsoft Teams 通话或会议质量不佳的问题。</span><span class="sxs-lookup"><span data-stu-id="b79b5-104">This article explains how to use call analytics to troubleshoot poor Microsoft Teams call or meeting quality for individual users if you're a Teams admin or a Teams communications support specialist or engineer.</span></span>

## <a name="call-analytics-permissions"></a><span data-ttu-id="b79b5-105">调用分析权限</span><span class="sxs-lookup"><span data-stu-id="b79b5-105">Call Analytics permissions</span></span>

<span data-ttu-id="b79b5-106">本文假定你已设置呼叫分析。</span><span class="sxs-lookup"><span data-stu-id="b79b5-106">This article assumes that you've already set up call analytics.</span></span> <span data-ttu-id="b79b5-107">如果没有，请阅读为 Teams [设置呼叫分析](set-up-call-analytics.md)。</span><span class="sxs-lookup"><span data-stu-id="b79b5-107">If you haven't, read [Set up call analytics for Teams](set-up-call-analytics.md).</span></span>

## <a name="introduction-to-call-analytics"></a><span data-ttu-id="b79b5-108">调用分析简介</span><span class="sxs-lookup"><span data-stu-id="b79b5-108">Introduction to call analytics</span></span>

<span data-ttu-id="b79b5-109">通话分析显示有关 Office 365 帐户中每个用户的 Teams 通话和会议的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-109">Call analytics shows detailed information about Teams calls and meetings for each user in your Office 365 account.</span></span> <span data-ttu-id="b79b5-110">它包括有关设备、网络、连接和呼叫质量的信息 (其中任何一项都可能是导致呼叫或会议质量不佳) 。</span><span class="sxs-lookup"><span data-stu-id="b79b5-110">It includes information about devices, networks, connectivity, and call quality (any of these can be a factor in poor call or meeting quality).</span></span> <span data-ttu-id="b79b5-111">如果上载建筑物、网站和租户信息，则每次呼叫和会议也会显示此信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-111">If you upload building, site, and tenant information, this information will also be shown for each call and meeting.</span></span> <span data-ttu-id="b79b5-112">使用呼叫分析帮助您找出用户通话或会议体验不佳的原因。</span><span class="sxs-lookup"><span data-stu-id="b79b5-112">Use call analytics to help you figure out why a user had a poor call or meeting experience.</span></span>

<span data-ttu-id="b79b5-113">呼叫分析显示呼叫或会议的每一段 - 例如，从一个参与者到另一个参与者。</span><span class="sxs-lookup"><span data-stu-id="b79b5-113">Call analytics shows you each leg of a call or meeting - for example, from one participant to a second participant.</span></span> <span data-ttu-id="b79b5-114">通过分析这些详细信息，Teams 管理员可以隔离问题区域，并确定质量不佳的根本原因。</span><span class="sxs-lookup"><span data-stu-id="b79b5-114">By analyzing these details, a Teams admin can isolate problem areas and identify the root cause for poor quality.</span></span>

<span data-ttu-id="b79b5-115">作为 Teams 管理员，你可以完全访问每个用户的所有呼叫分析数据。</span><span class="sxs-lookup"><span data-stu-id="b79b5-115">As the Teams admin, you get full access to all call analytics data for each user.</span></span> <span data-ttu-id="b79b5-116">此外，还可以为支持人员分配 Azure Active Directory 角色。</span><span class="sxs-lookup"><span data-stu-id="b79b5-116">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="b79b5-117">若要详细了解这些角色，请阅读 [授予支持和支持人员的权限](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff)。</span><span class="sxs-lookup"><span data-stu-id="b79b5-117">To learn more about these roles, read [Give permission to support and helpdesk staff](set-up-call-analytics.md#give-permission-to-support-and-helpdesk-staff).</span></span> <span data-ttu-id="b79b5-118">请勿错过下面的每个[Teams 支持角色的作用是什么？](#what-does-each-teams-support-role-do)</span><span class="sxs-lookup"><span data-stu-id="b79b5-118">Don't miss [What does each Teams Support role do?](#what-does-each-teams-support-role-do) below.</span></span>

## <a name="where-to-find-per-user-call-analytics"></a><span data-ttu-id="b79b5-119">在何处查找按用户调用分析</span><span class="sxs-lookup"><span data-stu-id="b79b5-119">Where to find per-user call analytics</span></span>

<span data-ttu-id="b79b5-120">若要查看用户的所有呼叫信息和数据，请转到 [Teams 管理中心](https://admin.teams.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="b79b5-120">To see all call information and data for a user, go to the [Teams admin center](https://admin.teams.microsoft.com).</span></span> <span data-ttu-id="b79b5-121">在 **"用户**"下，选择一个用户，然后打开&个人资料页上的"会议"选项卡。</span><span class="sxs-lookup"><span data-stu-id="b79b5-121">Under **Users**, select a user and then open the **Meetings & Calls** tab on the user's profile page.</span></span> <span data-ttu-id="b79b5-122">可在此处找到该用户过去 30 天的所有呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="b79b5-122">Here you'll find all calls and meetings for that user for the last 30 days.</span></span>

![所有分析用户数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image1.png)

<span data-ttu-id="b79b5-124">若要获取有关给定会话的其他信息，包括详细的媒体和网络统计信息，请单击会话以查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-124">To get additional information about a given session, including detailed media and networking statistics, click a session to see the details.</span></span>

![调用分析用户会话数据的屏幕截图](media/teams-difference-between-call-analytics-and-call-quality-dashboard-image2.png)

## <a name="what-does-each-teams-support-role-do"></a><span data-ttu-id="b79b5-126">每个 Teams 支持角色的作用是什么？</span><span class="sxs-lookup"><span data-stu-id="b79b5-126">What does each Teams Support role do?</span></span>

<span data-ttu-id="b79b5-127">Teams **通信支持专家 (** 第 1 层) 处理基本呼叫质量问题。</span><span class="sxs-lookup"><span data-stu-id="b79b5-127">The **Teams communications support specialist** (Tier 1 support) handles basic call-quality problems.</span></span> <span data-ttu-id="b79b5-128">它们不调查会议问题。</span><span class="sxs-lookup"><span data-stu-id="b79b5-128">They don't investigate issues with meetings.</span></span> <span data-ttu-id="b79b5-129">相反，他们收集相关信息，然后上报给通信支持工程师。</span><span class="sxs-lookup"><span data-stu-id="b79b5-129">Instead, they collect related information and then escalate to a communications support engineer.</span></span>

<span data-ttu-id="b79b5-130">Teams **通信支持工程师** (第 2 层) 团队在详细呼叫日志中查看对 Teams 通信支持专家隐藏的信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-130">The **Teams communications support engineer** (Tier 2 support) sees information in detailed call logs that are hidden from the Teams communications support specialist.</span></span> <span data-ttu-id="b79b5-131">下表列出了每个 Teams 通信支持角色可用的信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-131">The table below lists the information available to each Teams communication support role.</span></span>

<span data-ttu-id="b79b5-132">下表显示了每个通信支持角色可用的每用户信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-132">The following table tells you what per-user information is available for each communications support role.</span></span>

|<span data-ttu-id="b79b5-133">活动</span><span class="sxs-lookup"><span data-stu-id="b79b5-133">Activity</span></span>|<span data-ttu-id="b79b5-134">信息</span><span class="sxs-lookup"><span data-stu-id="b79b5-134">Information</span></span>|<span data-ttu-id="b79b5-135">通信内容</span><span class="sxs-lookup"><span data-stu-id="b79b5-135">What the communications</span></span><br><span data-ttu-id="b79b5-136">支持 *专家* 参阅</span><span class="sxs-lookup"><span data-stu-id="b79b5-136">support *specialist* sees</span></span>|<span data-ttu-id="b79b5-137">通信内容</span><span class="sxs-lookup"><span data-stu-id="b79b5-137">What the communications</span></span><br><span data-ttu-id="b79b5-138">支持 *工程师* 看到</span><span class="sxs-lookup"><span data-stu-id="b79b5-138">support *engineer* sees</span></span>|
|---|---|---|---|
|<span data-ttu-id="b79b5-139">**呼叫**</span><span class="sxs-lookup"><span data-stu-id="b79b5-139">**Calls**</span></span>|<span data-ttu-id="b79b5-140">呼叫者姓名</span><span class="sxs-lookup"><span data-stu-id="b79b5-140">Caller name</span></span>|<span data-ttu-id="b79b5-141">仅代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="b79b5-141">Only the name of the user for whom the agent searched.</span></span>|<span data-ttu-id="b79b5-142">用户名。</span><span class="sxs-lookup"><span data-stu-id="b79b5-142">User name.</span></span>|
||<span data-ttu-id="b79b5-143">收件人姓名</span><span class="sxs-lookup"><span data-stu-id="b79b5-143">Recipient name</span></span>|<span data-ttu-id="b79b5-144">显示为内部用户或外部用户。</span><span class="sxs-lookup"><span data-stu-id="b79b5-144">Shows as Internal User or External User.</span></span>|<span data-ttu-id="b79b5-145">收件人姓名。</span><span class="sxs-lookup"><span data-stu-id="b79b5-145">Recipient name.</span></span>|
||<span data-ttu-id="b79b5-146">主叫方电话号码</span><span class="sxs-lookup"><span data-stu-id="b79b5-146">Caller phone number</span></span>|<span data-ttu-id="b79b5-147">除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="b79b5-147">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b79b5-148">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="b79b5-148">For example, 15552823\*\*\*.</span></span>|<span data-ttu-id="b79b5-149">除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="b79b5-149">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b79b5-150">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="b79b5-150">For example, 15552823\*\*\*.</span></span>|
||<span data-ttu-id="b79b5-151">收件人电话号码</span><span class="sxs-lookup"><span data-stu-id="b79b5-151">Recipient phone number</span></span>|<span data-ttu-id="b79b5-152">除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="b79b5-152">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b79b5-153">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="b79b5-153">For example, 15552823\*\*\*.</span></span>|<span data-ttu-id="b79b5-154">除最后三位数字外的全部电话号码都使用星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="b79b5-154">Entire phone number except last three digits are obfuscated with asterisk symbols.</span></span> <span data-ttu-id="b79b5-155">例如，15552823 \* \* \* 。</span><span class="sxs-lookup"><span data-stu-id="b79b5-155">For example, 15552823\*\*\*.</span></span>|
||<span data-ttu-id="b79b5-156">**呼叫详细信息** \>**"高级"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="b79b5-156">**Call Details** \> **Advanced** tab</span></span>|<span data-ttu-id="b79b5-157">未显示信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-157">Information not shown.</span></span>|<span data-ttu-id="b79b5-158">显示的所有详细信息，例如设备名称、IP 地址、子网映射等。</span><span class="sxs-lookup"><span data-stu-id="b79b5-158">All details shown, such as device names, IP address, subnet mapping, and more.</span></span>|
||<span data-ttu-id="b79b5-159">**呼叫详细信息** \>**高级** \>**"调试"** 选项卡</span><span class="sxs-lookup"><span data-stu-id="b79b5-159">**Call Details** \> **Advanced** \> **Debug** tab</span></span>|<span data-ttu-id="b79b5-160">未显示信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-160">Information not shown.</span></span>|<span data-ttu-id="b79b5-161">显示的所有详细信息，例如 DNS 后缀和 SSID。</span><span class="sxs-lookup"><span data-stu-id="b79b5-161">All details shown, such as DNS suffix and SSID.</span></span>|
|<span data-ttu-id="b79b5-162">**会议**</span><span class="sxs-lookup"><span data-stu-id="b79b5-162">**Meetings**</span></span>|<span data-ttu-id="b79b5-163">参与者姓名</span><span class="sxs-lookup"><span data-stu-id="b79b5-163">Participant names</span></span>|<span data-ttu-id="b79b5-164">仅代理搜索的用户的名称。</span><span class="sxs-lookup"><span data-stu-id="b79b5-164">Only the name of the user for whom the agent searched.</span></span> <span data-ttu-id="b79b5-165">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="b79b5-165">Other participants identified as Internal User or External User.</span></span>|<span data-ttu-id="b79b5-166">显示的所有名称。</span><span class="sxs-lookup"><span data-stu-id="b79b5-166">All names shown.</span></span>|
||<span data-ttu-id="b79b5-167">参与者计数</span><span class="sxs-lookup"><span data-stu-id="b79b5-167">Participant count</span></span>|<span data-ttu-id="b79b5-168">参与者数。</span><span class="sxs-lookup"><span data-stu-id="b79b5-168">Number of participants.</span></span>|<span data-ttu-id="b79b5-169">参与者数。</span><span class="sxs-lookup"><span data-stu-id="b79b5-169">Number of participants.</span></span>|
||<span data-ttu-id="b79b5-170">会话详细信息</span><span class="sxs-lookup"><span data-stu-id="b79b5-170">Session details</span></span>|<span data-ttu-id="b79b5-171">显示异常的会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-171">Session details shown with exceptions.</span></span> <span data-ttu-id="b79b5-172">只显示代理搜索的用户名。</span><span class="sxs-lookup"><span data-stu-id="b79b5-172">Only the name of the user for whom the agent searched is shown.</span></span> <span data-ttu-id="b79b5-173">标识为内部用户或外部用户的其他参与者。</span><span class="sxs-lookup"><span data-stu-id="b79b5-173">Other participants identified as Internal User or External User.</span></span> <span data-ttu-id="b79b5-174">电话号码的最后三位数字，用星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="b79b5-174">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>|<span data-ttu-id="b79b5-175">显示会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-175">Session details shown.</span></span> <span data-ttu-id="b79b5-176">显示用户名和会话详细信息。</span><span class="sxs-lookup"><span data-stu-id="b79b5-176">User names and session details shown.</span></span> <span data-ttu-id="b79b5-177">电话号码的最后三位数字，用星号符号进行模糊处理。</span><span class="sxs-lookup"><span data-stu-id="b79b5-177">Last three digits of telephone number obfuscated with asterisk symbols.</span></span>|
||||

## <a name="troubleshoot-user-call-quality-problems"></a><span data-ttu-id="b79b5-178">排查用户呼叫质量问题</span><span class="sxs-lookup"><span data-stu-id="b79b5-178">Troubleshoot user call quality problems</span></span>

1. <span data-ttu-id="b79b5-179">打开 Teams 管理中心 () Teams <https://admin.teams.microsoft.com> 通信支持或 Teams 管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="b79b5-179">Open the Teams admin center (<https://admin.teams.microsoft.com>) and sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="b79b5-180">在 **仪表板** 上的"用户 **搜索**"中，开始键入要排查其呼叫问题的用户的姓名或 SIP 地址，或选择"查看用户"以查看用户列表。</span><span class="sxs-lookup"><span data-stu-id="b79b5-180">On the **Dashboard**, in **User Search**, start typing either the name or SIP address of the user whose calls you want to troubleshoot, or select **View users** to see a list of users.</span></span>

3. <span data-ttu-id="b79b5-181">从列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="b79b5-181">Select the user from the list.</span></span>

4. <span data-ttu-id="b79b5-182">选择 **"呼叫** 历史记录"，然后选择要排除故障的呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="b79b5-182">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>

5. <span data-ttu-id="b79b5-183">选择" **高级"** 选项卡，然后查找指示通话质量不佳或连接问题的黄色和红色项目。</span><span class="sxs-lookup"><span data-stu-id="b79b5-183">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>

   <span data-ttu-id="b79b5-184">在每个呼叫或会议会话详细信息中，次要问题以黄色显示。</span><span class="sxs-lookup"><span data-stu-id="b79b5-184">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="b79b5-185">如果某些内容为黄色，则超出正常范围，并且可能导致问题，但不太可能是问题的主要原因。</span><span class="sxs-lookup"><span data-stu-id="b79b5-185">If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="b79b5-186">如果某些内容为红色，则这是一个严重问题，这很可能是导致此会话通话质量差的主要原因。</span><span class="sxs-lookup"><span data-stu-id="b79b5-186">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span>

<span data-ttu-id="b79b5-187">在极少数情况下，未收到音频会话的体验质量数据。</span><span class="sxs-lookup"><span data-stu-id="b79b5-187">In rare cases, Quality of Experience data isn't received for audio sessions.</span></span> <span data-ttu-id="b79b5-188">这通常是由丢弃的调用或与客户端的连接终止导致的。</span><span class="sxs-lookup"><span data-stu-id="b79b5-188">Often this is caused by the a dropped call or when the connection with the client terminates.</span></span> <span data-ttu-id="b79b5-189">发生这种情况时，会话分级 **不可用**。</span><span class="sxs-lookup"><span data-stu-id="b79b5-189">When this occurs, the session rating is **unavailable**.</span></span>

<span data-ttu-id="b79b5-190">对于具有 QoE (用户体验质量) 音频会话，下表描述了将会话限定为差 **的关键问题**。</span><span class="sxs-lookup"><span data-stu-id="b79b5-190">For audio sessions that do have Quality of Experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>

|<span data-ttu-id="b79b5-191">问题</span><span class="sxs-lookup"><span data-stu-id="b79b5-191">Issue</span></span>|<span data-ttu-id="b79b5-192">区域</span><span class="sxs-lookup"><span data-stu-id="b79b5-192">Area</span></span>|<span data-ttu-id="b79b5-193">说明</span><span class="sxs-lookup"><span data-stu-id="b79b5-193">Description</span></span>|
|---|---|---|
|<span data-ttu-id="b79b5-194">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="b79b5-194">Call setup</span></span>|<span data-ttu-id="b79b5-195">会话</span><span class="sxs-lookup"><span data-stu-id="b79b5-195">Session</span></span>|<span data-ttu-id="b79b5-196">错误代码 Ms-diag 20-29 指示调用设置失败。</span><span class="sxs-lookup"><span data-stu-id="b79b5-196">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="b79b5-197">用户无法加入呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="b79b5-197">The user couldn't join the call or meeting.</span></span>|
|<span data-ttu-id="b79b5-198">被分类为差的音频网络通话</span><span class="sxs-lookup"><span data-stu-id="b79b5-198">Audio network classified poor call</span></span>|<span data-ttu-id="b79b5-199">会话</span><span class="sxs-lookup"><span data-stu-id="b79b5-199">Session</span></span>|<span data-ttu-id="b79b5-200">遇到数据包 (抖动、NMOS 降级、RTT 或隐藏比率等网络质量问题) 问题。</span><span class="sxs-lookup"><span data-stu-id="b79b5-200">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span>|
|<span data-ttu-id="b79b5-201">设备无法正常工作</span><span class="sxs-lookup"><span data-stu-id="b79b5-201">Device not functioning</span></span>|<span data-ttu-id="b79b5-202">Device</span><span class="sxs-lookup"><span data-stu-id="b79b5-202">Device</span></span>|<span data-ttu-id="b79b5-203">设备无法正常工作。</span><span class="sxs-lookup"><span data-stu-id="b79b5-203">A device isn't functioning correctly.</span></span> <span data-ttu-id="b79b5-204">设备不正常运行的比率包括：</span><span class="sxs-lookup"><span data-stu-id="b79b5-204">Device not functioning ratios are:</span></span> <p> <span data-ttu-id="b79b5-205">DeviceRenderNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="b79b5-205">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br>  <span data-ttu-id="b79b5-206">DeviceCaptureNotFunctioningEventRatio >= 0.005</span><span class="sxs-lookup"><span data-stu-id="b79b5-206">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span>|
||||

## <a name="related-topics"></a><span data-ttu-id="b79b5-207">相关主题</span><span class="sxs-lookup"><span data-stu-id="b79b5-207">Related topics</span></span>

[<span data-ttu-id="b79b5-208">设置按用户调用分析</span><span class="sxs-lookup"><span data-stu-id="b79b5-208">Set up per-user call analytics</span></span>](set-up-call-analytics.md)
