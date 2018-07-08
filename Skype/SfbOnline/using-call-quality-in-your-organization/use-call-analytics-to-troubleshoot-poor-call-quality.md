---
title: 使用通话分析解决通话质量不佳的问题
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
description: 使用设备、 网络和连接的呼叫分析信息解决用户问题与 Skype 的业务呼叫和会议。
ms.openlocfilehash: 3610aff4b82f7d1fb0016a8934ec0feb640cc8ff
ms.sourcegitcommit: abc0f95ef0efe15a8c38cc27a3991abf7480c30e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/08/2018
ms.locfileid: "20211002"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="38645-103">使用通话分析解决通话质量不佳的问题</span><span class="sxs-lookup"><span data-stu-id="38645-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="38645-104">呼叫分析可帮助您解决的 Microsoft 团队和 for Business 的 Skype 调用或连接问题。</span><span class="sxs-lookup"><span data-stu-id="38645-104">Call Analytics helps you to troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="38645-105">呼叫分析您的 Office 365 帐户中显示有关设备、 网络和连接的呼叫和会议的每个用户的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="38645-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="38645-106">如果生成，网站，并租户信息已添加到呼叫分析，它还会显示为每个呼叫和会话。</span><span class="sxs-lookup"><span data-stu-id="38645-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="38645-107">可通过调用分析获得的信息可帮助您明白为什么用户具有质量欠佳的呼叫或会议体验。</span><span class="sxs-lookup"><span data-stu-id="38645-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
<span data-ttu-id="38645-108">**呼叫分析现已推出中的 Microsoft 团队和 Skype 的业务 Admin Center。**</span><span class="sxs-lookup"><span data-stu-id="38645-108">**Call Analytics is now available in the Microsoft Teams and Skype for Business Admin Center.**</span></span> <span data-ttu-id="38645-109">若要查看的所有呼叫信息和用户的数据，请使用**通话记录**选项卡。您可以通过仪表板用户可以搜索用户的配置文件页上查找或**用户**的左侧导航中查找用户执行此操作。</span><span class="sxs-lookup"><span data-stu-id="38645-109">To see all of the call information and data for a user, use the **Call History** tab. You can do this by looking on the user's profile page by either searching for the user from the dashboard or finding the user from **Users** in the left navigation.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="38645-110">帮助台代理权限和网络拓扑上载中将提供新的管理门户在几个月。</span><span class="sxs-lookup"><span data-stu-id="38645-110">Helpdesk agent permissions and network topology upload will be available in the new admin portal in the coming months.</span></span> <span data-ttu-id="38645-111">同时，您可以继续使用https://adminportal.services.skypeforbusiness.com1 层和第 2 层帮助台访问。</span><span class="sxs-lookup"><span data-stu-id="38645-111">In the meantime, you can continue to use  https://adminportal.services.skypeforbusiness.com for Tier 1 and Tier 2 helpdesk access.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="38645-112">解决使用调用分析的呼叫质量问题</span><span class="sxs-lookup"><span data-stu-id="38645-112">Troubleshoot call quality problems using Call Analytics</span></span>

<span data-ttu-id="38645-113">分配给您的权限级别决定哪些类型的信息您调用分析中有权访问：</span><span class="sxs-lookup"><span data-stu-id="38645-113">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="38645-114">**针对业务管理员 Skype**： 和业务管理中心的 Skype 调用分析中，您有权访问所有信息。</span><span class="sxs-lookup"><span data-stu-id="38645-114">**Skype for Business admin**: You have access to all the information in Call Analytics and in the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="38645-115">**帮助台代理具有 1 层权限**： 您看到一组有限的呼叫分析中的数据。</span><span class="sxs-lookup"><span data-stu-id="38645-115">**Helpdesk agent with Tier 1 permissions**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="38645-116">您可以解决呼叫，但将交给会议问题的第 2 层代理。</span><span class="sxs-lookup"><span data-stu-id="38645-116">You can troubleshoot calls, but you'll hand off problems with meetings to a Tier 2 agent.</span></span> <span data-ttu-id="38645-117">您无需访问业务 Admin center Skype 的其余部分。</span><span class="sxs-lookup"><span data-stu-id="38645-117">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
- <span data-ttu-id="38645-118">**第 2 层权限的帮助台代理**： 请参阅呼叫分析中的所有可用的数据并帮助解决问题呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="38645-118">**Helpdesk agent with Tier 2 permissions**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="38645-119">您无需访问业务 Admin center Skype 的其余部分。</span><span class="sxs-lookup"><span data-stu-id="38645-119">You don't have access to the rest of the Skype for Business Admin center.</span></span>
    
<span data-ttu-id="38645-120">如果您需要具有权限的帮助，请参阅 Business admin 您 Skype。</span><span class="sxs-lookup"><span data-stu-id="38645-120">See your Skype for Business admin if you need help with permissions.</span></span>
  
 <span data-ttu-id="38645-121">**打开呼叫分析作为层 1 或 2 层帮助台代理**</span><span class="sxs-lookup"><span data-stu-id="38645-121">**Open Call Analytics as a Tier 1 or Tier 2 helpdesk agent**</span></span>
  
1. <span data-ttu-id="38645-122">转到 Office 365 管理中心，并使用工作或学校帐户登录。</span><span class="sxs-lookup"><span data-stu-id="38645-122">Go to the Office 365 admin center and sign in using your work or school account.</span></span> <span data-ttu-id="38645-123">在 web 浏览器前往*https://adminportal.services.skypeforbusiness.com*。</span><span class="sxs-lookup"><span data-stu-id="38645-123">Then in your web browser go to *https://adminportal.services.skypeforbusiness.com*.</span></span>
    
2. <span data-ttu-id="38645-124">在**用户搜索**，开始键入您想要解决，然后从列表中选择用户其呼叫的用户的名称或 sip 地址。</span><span class="sxs-lookup"><span data-stu-id="38645-124">In **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot and then select the user from the list.</span></span>
    
    ![在 Business Admin Center Skype 调用分析的用户搜索框的屏幕截图。](../images/db52efc5-dac1-4623-ba72-41e42f0a0fb4.png)
  
3. <span data-ttu-id="38645-126">在**呼叫历史记录**，请选择您想要解决该呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="38645-126">In **Call history**, select the call or meeting that you want to troubleshoot.</span></span>
    
    ![屏幕快照显示了具有用户的联系人的详细信息，如汇总 7 天质量和活动的会议和呼叫，以及的日期和时间、 收件人和音频质量，概述的信息的用户的呼叫历史记录页](../images/aef80e09-3b37-46db-8e7b-8cf71712349b.png)
  
4. <span data-ttu-id="38645-128">选择**高级**选项卡，然后查找的黄色和红色项目指示质量欠佳的呼叫质量或连接问题。</span><span class="sxs-lookup"><span data-stu-id="38645-128">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="38645-129">在每个呼叫或会议的会话详细信息，次要问题都显示在黄色。</span><span class="sxs-lookup"><span data-stu-id="38645-129">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="38645-130">（例如，在下面的屏幕快照，值为黄色的平均抖动、 最大抖动和平均数据包丢失率。）如果内容为黄色，外部正常范围和它可能会造成的问题，但它不太可能出现问题的主要原因。</span><span class="sxs-lookup"><span data-stu-id="38645-130">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="38645-131">如果内容为红色，很重要的问题，并且可能此会话质量欠佳的呼叫质量的主要原因。</span><span class="sxs-lookup"><span data-stu-id="38645-131">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![屏幕截图显示用户的呼叫历史记录高级选项卡与入站的网络部分展开以显示平均抖动、 最大抖动和平均数据包丢失率的数据所示为黄色，这意味着它们次要问题。](../images/13f314ce-97cf-4bd0-a147-14b177d07040.png)
  
<span data-ttu-id="38645-133">在极少数情况下，体验质量数据不接收到音频会话。</span><span class="sxs-lookup"><span data-stu-id="38645-133">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="38645-134">通常这是由呼叫放和连接导致与客户端终止。</span><span class="sxs-lookup"><span data-stu-id="38645-134">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="38645-135">发生这种情况，会话分级时"不可用"。</span><span class="sxs-lookup"><span data-stu-id="38645-135">When this occurs, the session rating is "unavailable".</span></span>
  
<span data-ttu-id="38645-136">有体验 (QoE) 数据质量的音频会话下, 表介绍限定为"差。"的会话的主要问题</span><span class="sxs-lookup"><span data-stu-id="38645-136">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as "poor."</span></span>
  
|<span data-ttu-id="38645-137">**问题**</span><span class="sxs-lookup"><span data-stu-id="38645-137">**Issue**</span></span>|<span data-ttu-id="38645-138">**区域**</span><span class="sxs-lookup"><span data-stu-id="38645-138">**Area**</span></span>|<span data-ttu-id="38645-139">**说明**</span><span class="sxs-lookup"><span data-stu-id="38645-139">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="38645-140">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="38645-140">Call setup</span></span>  <br/> |<span data-ttu-id="38645-141">会话</span><span class="sxs-lookup"><span data-stu-id="38645-141">Session</span></span>  <br/> |<span data-ttu-id="38645-142">Ms 诊断 20 29 的错误代码指示呼叫安装失败。</span><span class="sxs-lookup"><span data-stu-id="38645-142">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="38645-143">用户无法加入呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="38645-143">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="38645-144">音频网络分类质量欠佳的呼叫</span><span class="sxs-lookup"><span data-stu-id="38645-144">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="38645-145">会话</span><span class="sxs-lookup"><span data-stu-id="38645-145">Session</span></span>  <br/> |<span data-ttu-id="38645-146">网络质量问题中数据包丢失、 抖动 NMOS 下降，RTT，这些方面遇到或隐藏比率。</span><span class="sxs-lookup"><span data-stu-id="38645-146">Network quality issues were encountered in areas such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio.</span></span> <span data-ttu-id="38645-147">有关用于分类质量欠佳的呼叫的条件的详细信息，请参阅此[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。</span><span class="sxs-lookup"><span data-stu-id="38645-147">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="38645-148">设备无法正常工作</span><span class="sxs-lookup"><span data-stu-id="38645-148">Device not functioning</span></span>  <br/> |<span data-ttu-id="38645-149">设备</span><span class="sxs-lookup"><span data-stu-id="38645-149">Device</span></span>  <br/> | <span data-ttu-id="38645-150">设备未正常工作。</span><span class="sxs-lookup"><span data-stu-id="38645-150">A device isn't functioning correctly.</span></span> <span data-ttu-id="38645-151">设备无法正常工作的比率是：</span><span class="sxs-lookup"><span data-stu-id="38645-151">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="38645-152">DeviceRenderNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="38645-152">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="38645-153">DeviceCaptureNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="38645-153">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="38645-154">相关主题</span><span class="sxs-lookup"><span data-stu-id="38645-154">Related topics</span></span>
[<span data-ttu-id="38645-155">设置 Skype for Business 通话分析</span><span class="sxs-lookup"><span data-stu-id="38645-155">Set up Skype for Business Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="38645-156">呼叫分析和呼叫质量仪表板</span><span class="sxs-lookup"><span data-stu-id="38645-156">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
