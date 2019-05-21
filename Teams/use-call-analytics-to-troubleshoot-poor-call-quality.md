---
title: 使用通话分析来排查通话质量不良问题
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 03/08/2019
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.collection:
- Teams_ITAdmin_Help
- M365-collaboration
search.appverid: MET150
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: 使用有关设备、网络和连接的呼叫分析详细信息来解决与 Microsoft 团队和 Skype for business 通话和会议有关的用户问题。
ms.openlocfilehash: 2255afa0c2af8e1c672c2830009cfb34921ceed9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2019
ms.locfileid: "34288193"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="cb6ac-103">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="cb6ac-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="cb6ac-104">呼叫分析可帮助你解决 Microsoft 团队和 Skype for business 的通话或连接问题。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="cb6ac-105">"呼叫分析" 显示有关 Office 365 帐户中每个用户的呼叫和会议的设备、网络和连接的详细信息。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="cb6ac-106">如果 "生成"、"网站" 和 "租户" 信息已添加到调用分析, 则它还将针对每个通话和会话显示。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="cb6ac-107">通过呼叫分析提供的信息可以帮助你了解为什么用户的通话或会议体验不佳的原因。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="cb6ac-108">调用分析权限</span><span class="sxs-lookup"><span data-stu-id="cb6ac-108">Call Analytics permissions</span></span>

<span data-ttu-id="cb6ac-109">作为管理员, 你可以完全访问呼叫分析的所有功能。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="cb6ac-110">此外, 你可以将 Azure Active Directory 角色分配给支持人员。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="cb6ac-111">将团队通信支持专家角色分配给应具有有限视图的调用分析的用户。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="cb6ac-112">将团队通信支持工程师角色分配给需要访问调用分析的完整功能的用户。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="cb6ac-113">这两个权限级别阻止访问 Microsoft 团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="cb6ac-114">通信支持专家处理基本的通话质量问题。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="cb6ac-115">他们不会调查会议问题。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="cb6ac-116">而是收集相关信息, 然后升级到通信支持工程师。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="cb6ac-117">通信支持工程师查看有关通信支持专家隐藏的详细通话记录中的信息。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="cb6ac-118">下表简要介绍了在使用呼叫分析时, 通信支持专家和通信支持工程师可使用的信息。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="cb6ac-119">分配给你的权限级别确定在呼叫分析中你有权访问的信息类型:</span><span class="sxs-lookup"><span data-stu-id="cb6ac-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="cb6ac-120">**团队服务管理员或团队通信管理员**: 您有权访问呼叫分析和 Microsoft 团队管理中心中的所有信息。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="cb6ac-121">**团队通信支持专家**: 在 "调用分析" 中看到一组有限的数据。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="cb6ac-122">你可以对通话进行故障排除, 但你将向团队通信支持工程师分发会议问题。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="cb6ac-123">您无法访问 Microsoft 团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="cb6ac-124">**团队通信支持工程师**: 查看呼叫分析中的所有可用数据, 并可帮助解决与通话和会议有关的问题。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="cb6ac-125">您无法访问 Microsoft 团队管理中心的其余部分。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="cb6ac-126">通信支持专家角色等效于第1层支持, 而通信支持工程师角色等效于第2层支持。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="cb6ac-127">有关团队管理员角色的详细信息, 请参阅[使用 Microsoft 团队管理员角色管理团队](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="cb6ac-128">有关团队通信支持专家和团队通信支持工程师角色的详细比较, 请参阅[设置呼叫分析](set-up-call-analytics.md#set-call-analytics-permissions)</span><span class="sxs-lookup"><span data-stu-id="cb6ac-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="cb6ac-129">如果需要有关权限的帮助, 请查看你的团队和 Skype for business 管理员。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="cb6ac-130">使用呼叫分析解决通话质量问题</span><span class="sxs-lookup"><span data-stu-id="cb6ac-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="cb6ac-131">通过团队通信支持或团队管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="cb6ac-132">在 web 浏览器中, *https://admin.teams.microsoft.com*转到。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-132">In your web browser go to *https://admin.teams.microsoft.com*.</span></span>
    
3. <span data-ttu-id="cb6ac-133">在**仪表板**上的 "**用户搜索**" 中, 开始键入要对其进行故障排除的用户的名称或 sip 地址, 或选择 "**查看用户**" 以查看用户列表。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-133">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![Microsoft 团队管理中心中的调用分析的用户搜索框的屏幕截图。](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. <span data-ttu-id="cb6ac-135">从列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-135">Select the user from the list.</span></span>

5. <span data-ttu-id="cb6ac-136">选择 "**呼叫历史记录**", 然后选择要进行故障排除的呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-136">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
    ![屏幕截图显示用户的 "通话历史记录" 页面。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. <span data-ttu-id="cb6ac-138">选择 "**高级**" 选项卡, 然后查找表示通话质量不佳或连接问题的黄色和红色项目。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-138">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="cb6ac-139">在每个通话或会议的 "会话详细信息" 中, 小问题显示为黄色。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-139">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="cb6ac-140">(例如, 在以下屏幕截图中, 对于平均抖动、最大抖动和平均数据包丢失率, 这些值为黄色。)如果某个内容为黄色, 则它不在正常范围内, 它可能会导致问题, 但不太可能是问题的主要原因。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-140">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="cb6ac-141">如果出现红色, 这是一个重大问题, 这很可能是本次会议的通话质量不佳的主要原因。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-141">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="cb6ac-142">屏幕截图显示用户通话记录的 "高级" 选项卡</span><span class="sxs-lookup"><span data-stu-id="cb6ac-142">Screenshot shows the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="cb6ac-143">在极少数情况下, 音频会话的体验数据质量未收到。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-143">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="cb6ac-144">这通常是由呼叫丢弃并与客户端的连接引起的。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-144">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="cb6ac-145">出现这种情况时,**无法使用**"会话分级"。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-145">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="cb6ac-146">对于具有体验质量 (QoE) 数据的音频会话, 下表介绍了将会话限定为**差**的主要问题。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-146">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="cb6ac-147">**问题**</span><span class="sxs-lookup"><span data-stu-id="cb6ac-147">**Issue**</span></span>|<span data-ttu-id="cb6ac-148">**区域**</span><span class="sxs-lookup"><span data-stu-id="cb6ac-148">**Area**</span></span>|<span data-ttu-id="cb6ac-149">**说明**</span><span class="sxs-lookup"><span data-stu-id="cb6ac-149">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb6ac-150">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="cb6ac-150">Call setup</span></span>  <br/> |<span data-ttu-id="cb6ac-151">Session</span><span class="sxs-lookup"><span data-stu-id="cb6ac-151">Session</span></span>  <br/> |<span data-ttu-id="cb6ac-152">错误代码 Ms-诊断20-29 指示呼叫设置失败。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-152">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="cb6ac-153">用户无法加入呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-153">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="cb6ac-154">音频网络分类差通话</span><span class="sxs-lookup"><span data-stu-id="cb6ac-154">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="cb6ac-155">Session</span><span class="sxs-lookup"><span data-stu-id="cb6ac-155">Session</span></span>  <br/> |<span data-ttu-id="cb6ac-156">遇到网络质量问题 (如数据包丢失、抖动、NMOS 下降、RTT 或隐藏比率)。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-156">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="cb6ac-157">有关用于对不太好的通话进行分类的条件的详细信息, 请参阅此[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-157">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="cb6ac-158">设备不起作用</span><span class="sxs-lookup"><span data-stu-id="cb6ac-158">Device not functioning</span></span>  <br/> |<span data-ttu-id="cb6ac-159">Device</span><span class="sxs-lookup"><span data-stu-id="cb6ac-159">Device</span></span>  <br/> | <span data-ttu-id="cb6ac-160">设备不能正常工作。</span><span class="sxs-lookup"><span data-stu-id="cb6ac-160">A device isn't functioning correctly.</span></span> <span data-ttu-id="cb6ac-161">设备的运行比率为:</span><span class="sxs-lookup"><span data-stu-id="cb6ac-161">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="cb6ac-162">DeviceRenderNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="cb6ac-162">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="cb6ac-163">DeviceCaptureNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="cb6ac-163">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="cb6ac-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="cb6ac-164">Related topics</span></span>
[<span data-ttu-id="cb6ac-165">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="cb6ac-165">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="cb6ac-166">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="cb6ac-166">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
