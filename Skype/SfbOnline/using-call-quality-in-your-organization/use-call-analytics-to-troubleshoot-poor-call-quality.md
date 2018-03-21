---
title: "使用调用分析诊断较差企业的 Skype 通话质量"
ms.author: lolaj
author: LolaJacobsen
manager: serdars
ms.reviewer: mikedav, wlooney
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 66945036-ae87-4c08-a0bb-984e50d6b009
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Reporting
description: "使用调用分析有关设备、 网络和连接的详细信息来解决用户的问题与 Skype 进行业务联络和会议。"
ms.openlocfilehash: cbb728c14c58393a5ec71cc538ad958ba58fb947
ms.sourcegitcommit: 371a699df0c13f44d2cb6511ba7eaafe047be92c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2018
---
# <a name="use-call-analytics-to-troubleshoot-poor-skype-for-business-call-quality"></a><span data-ttu-id="35374-103">使用调用分析诊断较差企业的 Skype 通话质量</span><span class="sxs-lookup"><span data-stu-id="35374-103">Use Call Analytics to troubleshoot poor Skype for Business call quality</span></span>

<span data-ttu-id="35374-104">调用分析可帮助您诊断有关业务 Skype 呼叫或连接问题。</span><span class="sxs-lookup"><span data-stu-id="35374-104">Call Analytics helps you to troubleshoot call or connection problems with Skype for Business.</span></span> <span data-ttu-id="35374-105">调用分析显示在您的企业往来帐户的 Skype 有关设备、 网络和电话和会议的每个用户的连接的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="35374-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Skype for Business account.</span></span> <span data-ttu-id="35374-106">如果构建，站点，和租户信息已添加到调用的分析，它也将显示为每个调用和会话。</span><span class="sxs-lookup"><span data-stu-id="35374-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="35374-107">通过调用分析提供的信息可帮助您找出为什么用户会有不良的调用或会议体验。</span><span class="sxs-lookup"><span data-stu-id="35374-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
    > [!NOTE]
    > Call Analytics is currently in preview. Text and images described here may not match your experience. 
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="35374-108">使用调用分析通话质量问题的疑难解答</span><span class="sxs-lookup"><span data-stu-id="35374-108">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="35374-109">分配给您的权限级别决定什么类型的信息您调用分析中有权：</span><span class="sxs-lookup"><span data-stu-id="35374-109">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="35374-110">**Skype 业务管理员**： 您有权访问所有信息，在调用分析和业务管理中心为 Skype。</span><span class="sxs-lookup"><span data-stu-id="35374-110">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="35374-111">**帮助台代理使用第 1 层权限**： 看到一组有限的数据调用分析中。</span><span class="sxs-lookup"><span data-stu-id="35374-111">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="35374-112">您可以解决调用，但将移交问题会议到第 2 层工程师。</span><span class="sxs-lookup"><span data-stu-id="35374-112">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="35374-113">您没有访问 Skype 的其余部分的业务管理中心。</span><span class="sxs-lookup"><span data-stu-id="35374-113">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="35374-114">**帮助台代理使用第 2 层权限**： 请参见调用分析中的所有可用数据，能够帮助您解决问题的呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="35374-114">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="35374-115">您没有访问 Skype 的其余部分的业务管理中心。</span><span class="sxs-lookup"><span data-stu-id="35374-115">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="35374-116">如果您需要使用的权限的帮助，请参阅您 Skype 的业务管理。</span><span class="sxs-lookup"><span data-stu-id="35374-116">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="35374-117">**为第 1 层或 2 层支持人员代理打开调用分析**</span><span class="sxs-lookup"><span data-stu-id="35374-117">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="35374-118">请转到 Office 365 管理中心并使用您的工作或学校的帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="35374-118">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="35374-119">然后在 web 浏览器转到*https://adminportal.services.skypeforbusiness.com*。</span><span class="sxs-lookup"><span data-stu-id="35374-119">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="35374-120">在**用户搜索**，键入您想要解决问题，然后从列表中选择用户的呼叫的用户的名称或 sip 地址。</span><span class="sxs-lookup"><span data-stu-id="35374-120">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![在业务管理中心为 Skype 呼叫分析用户的搜索框的屏幕快照。](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="35374-122">在**通话记录**，选择您要排查故障的电话或会议。</span><span class="sxs-lookup"><span data-stu-id="35374-122">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![屏幕抓图显示信息用户的联系人的详细信息，如 7 天质量和为会议和联络活动的摘要和概述日期和时间、 收件人和音频质量，具有权限的用户调用历史页](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="35374-124">选择**高级**选项卡，然后查找黄色和红色指示较差的呼叫质量或连接问题的项目。</span><span class="sxs-lookup"><span data-stu-id="35374-124">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="35374-125">对于每个调用或会议会话的详细信息，小问题中出现的黄色。</span><span class="sxs-lookup"><span data-stu-id="35374-125">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="35374-126">（例如，在下面的屏幕快照的值是以黄色为平均抖动、 最大抖动和平均数据包丢失率。）如果什么东西是黄色的超出正常范围，以及它可能会造成问题，但它不可能是问题的主要原因。</span><span class="sxs-lookup"><span data-stu-id="35374-126">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="35374-127">如果什么东西是红色的很重要的问题，并很可能为此会话较差的呼叫质量的主要原因。</span><span class="sxs-lookup"><span data-stu-id="35374-127">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![屏幕抓图显示用户的通话记录的高级选项卡进行入站的网络一部分展开以显示平均抖动、 最大的抖动和平均的数据包丢失率的数据所示的颜色为黄色，表示它们次要问题。](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="35374-129">在极少数情况下，经验数据的质量不会接收到音频会话。</span><span class="sxs-lookup"><span data-stu-id="35374-129">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="35374-130">通常这被由于调用放和连接与客户端终止。</span><span class="sxs-lookup"><span data-stu-id="35374-130">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="35374-131">在这种情况下，会话评级为"不可用"。</span><span class="sxs-lookup"><span data-stu-id="35374-131">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="35374-132">对于音频会话具有质量 (QoE) 的经验数据下, 表描述了确认为"较差"。 一个会话的主要问题</span><span class="sxs-lookup"><span data-stu-id="35374-132">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="35374-133">**问题**</span><span class="sxs-lookup"><span data-stu-id="35374-133">**Issue**</span></span>|<span data-ttu-id="35374-134">**区域**</span><span class="sxs-lookup"><span data-stu-id="35374-134">**Area**</span></span>|<span data-ttu-id="35374-135">**说明**</span><span class="sxs-lookup"><span data-stu-id="35374-135">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="35374-136">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="35374-136">Call setup</span></span>  <br/> |<span data-ttu-id="35374-137">会话</span><span class="sxs-lookup"><span data-stu-id="35374-137">Session</span></span>  <br/> |<span data-ttu-id="35374-138">Ms 诊断 20-29 的错误代码指示调用安装程序失败。</span><span class="sxs-lookup"><span data-stu-id="35374-138">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="35374-139">用户无法加入电话或会议。</span><span class="sxs-lookup"><span data-stu-id="35374-139">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="35374-140">音频网络分类较差的呼叫</span><span class="sxs-lookup"><span data-stu-id="35374-140">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="35374-141">会话</span><span class="sxs-lookup"><span data-stu-id="35374-141">Session</span></span>  <br/> |<span data-ttu-id="35374-142">网络质量问题遇到诸如数据包丢失、 抖动、 NMOS 降级，RTT，或隐藏比率。</span><span class="sxs-lookup"><span data-stu-id="35374-142">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="35374-143">有关用于分类较差的呼叫的条件的详细信息，请参阅以下[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。</span><span class="sxs-lookup"><span data-stu-id="35374-143">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="35374-144">设备无法正常工作</span><span class="sxs-lookup"><span data-stu-id="35374-144">Device not functioning</span></span>  <br/> |<span data-ttu-id="35374-145">设备</span><span class="sxs-lookup"><span data-stu-id="35374-145">Device</span></span>  <br/> | <span data-ttu-id="35374-146">设备运行不正常。</span><span class="sxs-lookup"><span data-stu-id="35374-146">A device isn't functioning correctly.</span></span> <span data-ttu-id="35374-147">设备无法正常工作的比率如下：</span><span class="sxs-lookup"><span data-stu-id="35374-147">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="35374-148">DeviceRenderNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="35374-148">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="35374-149">DeviceCaptureNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="35374-149">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="35374-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="35374-150">Related topics</span></span>
[<span data-ttu-id="35374-151">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="35374-151">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="35374-152">通话分析与通话质量仪表板之间有何区别？</span><span class="sxs-lookup"><span data-stu-id="35374-152">What's the difference between Call Analytics and Call Quality Dashboard?</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

## <a name="feedback"></a><span data-ttu-id="35374-153">反馈意见？</span><span class="sxs-lookup"><span data-stu-id="35374-153">Feedback?</span></span>
<span data-ttu-id="35374-154">提供产品反馈意见或让我们知道我们所执行的信息，请参阅[Skype 业务反馈](https://www.skypefeedback.com)。</span><span class="sxs-lookup"><span data-stu-id="35374-154">To provide product feedback or to let us know how we're doing, see [Skype for Business Feedback](https://www.skypefeedback.com).</span></span>