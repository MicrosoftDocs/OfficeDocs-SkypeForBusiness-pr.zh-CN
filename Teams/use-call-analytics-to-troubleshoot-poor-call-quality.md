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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.directrouting.callanalytics
- ms.teamsadmincenter.users.activity.audioqualitycolumn
ms.custom:
- Reporting
description: 使用呼叫分析有关设备、 网络和连接的详细信息解决用户问题与 Microsoft 团队和 Skype 业务呼叫和会议。
ms.openlocfilehash: e437401f759e92aa13c0d6680ef30eabd20ffc56
ms.sourcegitcommit: 70d4d02a3cc894f2f197aeea459ac079cde63877
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2019
ms.locfileid: "30543180"
---
# <a name="use-call-analytics-to-troubleshoot-poor-call-quality"></a><span data-ttu-id="60ecf-103">使用通话分析来排查通话质量不良问题</span><span class="sxs-lookup"><span data-stu-id="60ecf-103">Use Call Analytics to troubleshoot poor call quality</span></span>

<span data-ttu-id="60ecf-104">呼叫分析可帮助您解决的 Microsoft 团队和 for Business 的 Skype 调用或连接问题。</span><span class="sxs-lookup"><span data-stu-id="60ecf-104">Call Analytics helps you troubleshoot call or connection problems with Microsoft Teams and Skype for Business.</span></span> <span data-ttu-id="60ecf-105">呼叫分析您的 Office 365 帐户中显示有关设备、 网络和连接的呼叫和会议的每个用户的详细的信息。</span><span class="sxs-lookup"><span data-stu-id="60ecf-105">Call Analytics shows detailed information about the devices, networks, and connectivity for the calls and meetings of each user in your Office 365 account.</span></span> <span data-ttu-id="60ecf-106">如果生成，网站，并租户信息已添加到呼叫分析，它还会显示为每个呼叫和会话。</span><span class="sxs-lookup"><span data-stu-id="60ecf-106">If building, site, and tenant information has been added to Call Analytics, it will also be shown for each call and session.</span></span> <span data-ttu-id="60ecf-107">可通过调用分析获得的信息可帮助您明白为什么用户具有质量欠佳的呼叫或会议体验。</span><span class="sxs-lookup"><span data-stu-id="60ecf-107">Information available via Call Analytics can help you figure out why a user had a poor call or meeting experience.</span></span> 
  
## <a name="call-analytics-permissions"></a><span data-ttu-id="60ecf-108">呼叫分析权限</span><span class="sxs-lookup"><span data-stu-id="60ecf-108">Call Analytics permissions</span></span>

<span data-ttu-id="60ecf-109">作为管理员，您获取的呼叫分析的所有功能的完全访问权限。</span><span class="sxs-lookup"><span data-stu-id="60ecf-109">As the admin, you get full access to all the features of Call Analytics.</span></span> <span data-ttu-id="60ecf-110">此外，您可以分配支持人员的 Azure Active Directory 角色。</span><span class="sxs-lookup"><span data-stu-id="60ecf-110">In addition, you can assign Azure Active Directory roles to support staff.</span></span> <span data-ttu-id="60ecf-111">团队 communications 支持专家角色分配用户应具有有限的呼叫分析视图。</span><span class="sxs-lookup"><span data-stu-id="60ecf-111">Assign the Teams communications support specialist role to users who should have a limited view of Call Analytics.</span></span> <span data-ttu-id="60ecf-112">团队 communications 支持工程师角色分配用户需要访问呼叫分析的全部功能。</span><span class="sxs-lookup"><span data-stu-id="60ecf-112">Assign the Teams communications support engineer role to users who need access to the full functionality of Call Analytics.</span></span> <span data-ttu-id="60ecf-113">这两个权限级别防止对其余的 Microsoft 团队管理中心的访问。</span><span class="sxs-lookup"><span data-stu-id="60ecf-113">Both permission levels prevent access to the rest of the Microsoft Teams admin center.</span></span>

<span data-ttu-id="60ecf-114">Communications 支持专家处理基本呼叫质量问题。</span><span class="sxs-lookup"><span data-stu-id="60ecf-114">Communications support specialists handle basic call-quality problems.</span></span> <span data-ttu-id="60ecf-115">他们不调查与会议的问题。</span><span class="sxs-lookup"><span data-stu-id="60ecf-115">They don't investigate issues with meetings.</span></span> <span data-ttu-id="60ecf-116">相反，它们收集相关的信息，然后升级到 communications 支持工程师。</span><span class="sxs-lookup"><span data-stu-id="60ecf-116">Instead, they collect related information and then escalate to a communications support engineer.</span></span> <span data-ttu-id="60ecf-117">Communications 支持工程师请参阅详细的呼叫日志的已隐藏从通信支持专家的信息。</span><span class="sxs-lookup"><span data-stu-id="60ecf-117">Communications support engineers see information in detailed call logs that's hidden from communications support specialists.</span></span> <span data-ttu-id="60ecf-118">下表提供的信息概述了对通信支持专家和通信支持工程师使用调用分析时。</span><span class="sxs-lookup"><span data-stu-id="60ecf-118">The following table gives an overview of information available to communications support specialists and communications support engineers when they use Call Analytics.</span></span>

<span data-ttu-id="60ecf-119">分配给您的权限级别决定哪些类型的信息您调用分析中有权访问：</span><span class="sxs-lookup"><span data-stu-id="60ecf-119">The permissions level assigned to you determines what type of information you have access to in Call Analytics:</span></span>
  
- <span data-ttu-id="60ecf-120">**团队服务管理员或团队 communications 管理员**： 呼叫分析中的和 Microsoft 团队管理中心中，您可以访问的所有信息。</span><span class="sxs-lookup"><span data-stu-id="60ecf-120">**Teams service administrator or Teams communications administrator**: You have access to all the information in Call Analytics and in the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="60ecf-121">**团队 communications 支持专员**： 请参阅一组有限的呼叫分析中的数据。</span><span class="sxs-lookup"><span data-stu-id="60ecf-121">**Teams communications support specialist**: You see a limited set of data in Call Analytics.</span></span> <span data-ttu-id="60ecf-122">您可以解决呼叫，但将交给会议问题的团队 communications 支持工程师。</span><span class="sxs-lookup"><span data-stu-id="60ecf-122">You can troubleshoot calls, but you'll hand off problems with meetings to a Teams communications support engineer.</span></span> <span data-ttu-id="60ecf-123">您无需对其余的 Microsoft 团队管理中心的访问。</span><span class="sxs-lookup"><span data-stu-id="60ecf-123">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
- <span data-ttu-id="60ecf-124">**团队 communications 支持工程师**： 请参阅呼叫分析中的所有可用的数据并帮助解决问题呼叫和会议。</span><span class="sxs-lookup"><span data-stu-id="60ecf-124">**Teams communications support engineer**: You see all available data in Call Analytics and can help troubleshoot problems with both calls and meetings.</span></span> <span data-ttu-id="60ecf-125">您无需对其余的 Microsoft 团队管理中心的访问。</span><span class="sxs-lookup"><span data-stu-id="60ecf-125">You don't have access to the rest of the Microsoft Teams admin center.</span></span>
    
> [!NOTE]
> <span data-ttu-id="60ecf-126">Communications 支持专家角色等同于第 1 层支持它等效于第 2 层支持 communications 支持工程师角色。</span><span class="sxs-lookup"><span data-stu-id="60ecf-126">The communications support specialist role is equivalent to tier 1 support and the communications support engineer role is equivalent to tier 2 support.</span></span>

<span data-ttu-id="60ecf-127">有关团队管理员角色的详细信息，请参阅[管理团队使用的 Microsoft 团队管理角色](using-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="60ecf-127">For more information about Teams admin roles, see [Use Microsoft Teams admin roles to manage Teams](using-admin-roles.md).</span></span> <span data-ttu-id="60ecf-128">团队通信支持的详细比较专员和团队通信支持工程师角色，请参阅[Set up 呼叫分析](set-up-call-analytics.md#set-call-analytics-permissions)</span><span class="sxs-lookup"><span data-stu-id="60ecf-128">For a detailed comparison of the Teams communications support specialist and Teams communications support engineer roles, see [Set up Call Analytics](set-up-call-analytics.md#set-call-analytics-permissions)</span></span> 
  
<span data-ttu-id="60ecf-129">请参阅工作组和 Skype 业务管理员如果您需要具有权限的帮助。</span><span class="sxs-lookup"><span data-stu-id="60ecf-129">See your Teams and Skype for Business admin if you need help with permissions.</span></span>
  
## <a name="troubleshoot-call-quality-problems-using-call-analytics"></a><span data-ttu-id="60ecf-130">解决使用调用分析的呼叫质量问题</span><span class="sxs-lookup"><span data-stu-id="60ecf-130">Troubleshoot call quality problems using Call Analytics</span></span>

1. <span data-ttu-id="60ecf-131">使用您的团队通信支持或团队管理员凭据登录。</span><span class="sxs-lookup"><span data-stu-id="60ecf-131">Sign in with your Teams communications support or Teams admin credentials.</span></span>

2. <span data-ttu-id="60ecf-132">在 web 浏览器中，转到*https://admin.teams.microsoft.com*。</span><span class="sxs-lookup"><span data-stu-id="60ecf-132">In your web browser go to *https://admin.teams.microsoft.com*.</span></span>
    
3. <span data-ttu-id="60ecf-133">在**仪表板**，在**用户搜索**，开始键入名称或您想要解决或选中**查看用户**的用户列表，请参阅其呼叫用户的 sip 地址。</span><span class="sxs-lookup"><span data-stu-id="60ecf-133">On the **Dashboard**, in **User Search**, start typing either the name or sip address of the user whose calls you want to troubleshoot or select **View users** to see a list of users.</span></span>
    
    ![呼叫的分析 Microsoft 团队管理中心中的用户搜索框的屏幕截图。](media/use-call-analytics-to-troubleshoot-image-1.png)
  
4. <span data-ttu-id="60ecf-135">从列表中选择用户。</span><span class="sxs-lookup"><span data-stu-id="60ecf-135">Select the user from the list.</span></span>

5. <span data-ttu-id="60ecf-136">选择**呼叫历史记录**，，然后选择您想要解决该呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="60ecf-136">Select **Call history**, and then select the call or meeting that you want to troubleshoot.</span></span>
    
    ![屏幕快照显示了用户的呼叫历史记录页。](media/use-call-analytics-to-troubleshoot-image-2.png)
  
6. <span data-ttu-id="60ecf-138">选择**高级**选项卡，然后查找的黄色和红色项目指示质量欠佳的呼叫质量或连接问题。</span><span class="sxs-lookup"><span data-stu-id="60ecf-138">Select the **Advanced** tab, and then look for yellow and red items which indicate poor call quality or connection problems.</span></span>
    
    <span data-ttu-id="60ecf-139">在每个呼叫或会议的会话详细信息，次要问题都显示在黄色。</span><span class="sxs-lookup"><span data-stu-id="60ecf-139">In the session details for each call or meeting, minor issues appear in yellow.</span></span> <span data-ttu-id="60ecf-140">（例如，在下面的屏幕快照，值为黄色的平均抖动、 最大抖动和平均数据包丢失率。）如果内容为黄色，外部正常范围和它可能会造成的问题，但它不太可能出现问题的主要原因。</span><span class="sxs-lookup"><span data-stu-id="60ecf-140">(For example, in the following screenshot, the values are in yellow for Average jitter, Max jitter, and Average packet loss rate.) If something is yellow, it's outside of normal range, and it may be contributing to the problem, but it's unlikely to be the main cause of the problem.</span></span> <span data-ttu-id="60ecf-141">如果内容为红色，很重要的问题，并且可能此会话质量欠佳的呼叫质量的主要原因。</span><span class="sxs-lookup"><span data-stu-id="60ecf-141">If something is red, it's a significant problem, and it's likely the main cause of the poor call quality for this session.</span></span> 
    
    ![<span data-ttu-id="60ecf-142">屏幕快照显示了用户的呼叫历史记录高级选项卡</span><span class="sxs-lookup"><span data-stu-id="60ecf-142">Screenshot shows the Advanced tab of a user's Call history</span></span> ](media/use-call-analytics-to-troubleshoot-image-3.png)
  
<span data-ttu-id="60ecf-143">在极少数情况下，体验质量数据不接收到音频会话。</span><span class="sxs-lookup"><span data-stu-id="60ecf-143">In rare cases, quality of experience data isn't received for audio sessions.</span></span> <span data-ttu-id="60ecf-144">通常这是由呼叫放和连接导致与客户端终止。</span><span class="sxs-lookup"><span data-stu-id="60ecf-144">Often this is caused by the call dropping and connection with the client terminating.</span></span> <span data-ttu-id="60ecf-145">**如果发生这种情况，会话分级不可用。**</span><span class="sxs-lookup"><span data-stu-id="60ecf-145">When this occurs, the session rating is **unavailable**.</span></span>
  
<span data-ttu-id="60ecf-146">对于具有的用户体验 (QoE) 数据质量的音频会话下, 表介绍限定为**质量欠佳**的会话的主要问题。</span><span class="sxs-lookup"><span data-stu-id="60ecf-146">For audio sessions that do have quality of experience (QoE) data, the following table describes major issues that qualify a session as **poor**.</span></span>
  
|<span data-ttu-id="60ecf-147">**问题**</span><span class="sxs-lookup"><span data-stu-id="60ecf-147">**Issue**</span></span>|<span data-ttu-id="60ecf-148">**区域**</span><span class="sxs-lookup"><span data-stu-id="60ecf-148">**Area**</span></span>|<span data-ttu-id="60ecf-149">**说明**</span><span class="sxs-lookup"><span data-stu-id="60ecf-149">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="60ecf-150">呼叫设置</span><span class="sxs-lookup"><span data-stu-id="60ecf-150">Call setup</span></span>  <br/> |<span data-ttu-id="60ecf-151">会话</span><span class="sxs-lookup"><span data-stu-id="60ecf-151">Session</span></span>  <br/> |<span data-ttu-id="60ecf-152">Ms 诊断 20 29 的错误代码指示呼叫安装失败。</span><span class="sxs-lookup"><span data-stu-id="60ecf-152">The error code Ms-diag 20-29 indicates the call setup failed.</span></span> <span data-ttu-id="60ecf-153">用户无法加入呼叫或会议。</span><span class="sxs-lookup"><span data-stu-id="60ecf-153">The user couldn't join the call or meeting.</span></span>  <br/> |
|<span data-ttu-id="60ecf-154">音频网络分类质量欠佳的呼叫</span><span class="sxs-lookup"><span data-stu-id="60ecf-154">Audio network classified poor call</span></span>  <br/> |<span data-ttu-id="60ecf-155">会话</span><span class="sxs-lookup"><span data-stu-id="60ecf-155">Session</span></span>  <br/> |<span data-ttu-id="60ecf-156">遇到网络质量问题 （如数据包丢失、 抖动、 NMOS 下降，RTT 或隐藏的比率）。</span><span class="sxs-lookup"><span data-stu-id="60ecf-156">Network quality issues (such as packet loss, jitter, NMOS degradation, RTT, or concealed ratio) were encountered.</span></span> <span data-ttu-id="60ecf-157">有关用于分类质量欠佳的呼叫的条件的详细信息，请参阅此[Microsoft 博客文章](https://go.microsoft.com/fwlink/p/?linkid=852133)。</span><span class="sxs-lookup"><span data-stu-id="60ecf-157">For more information about the conditions used to classify poor calls, see this [Microsoft blog post](https://go.microsoft.com/fwlink/p/?linkid=852133).</span></span>  <br/> |
|<span data-ttu-id="60ecf-158">设备无法正常工作</span><span class="sxs-lookup"><span data-stu-id="60ecf-158">Device not functioning</span></span>  <br/> |<span data-ttu-id="60ecf-159">设备</span><span class="sxs-lookup"><span data-stu-id="60ecf-159">Device</span></span>  <br/> | <span data-ttu-id="60ecf-160">设备未正常工作。</span><span class="sxs-lookup"><span data-stu-id="60ecf-160">A device isn't functioning correctly.</span></span> <span data-ttu-id="60ecf-161">设备无法正常工作的比率是：</span><span class="sxs-lookup"><span data-stu-id="60ecf-161">Device not functioning ratios are :</span></span> <br/>  <span data-ttu-id="60ecf-162">DeviceRenderNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="60ecf-162">DeviceRenderNotFunctioningEventRatio >= 0.005</span></span> <br/>  <span data-ttu-id="60ecf-163">DeviceCaptureNotFunctioningEventRatio > = 0.005</span><span class="sxs-lookup"><span data-stu-id="60ecf-163">DeviceCaptureNotFunctioningEventRatio >= 0.005</span></span> <br/> |
   
## <a name="related-topics"></a><span data-ttu-id="60ecf-164">相关主题</span><span class="sxs-lookup"><span data-stu-id="60ecf-164">Related topics</span></span>
[<span data-ttu-id="60ecf-165">设置通话分析</span><span class="sxs-lookup"><span data-stu-id="60ecf-165">Set up Call Analytics</span></span>](set-up-call-analytics.md)

[<span data-ttu-id="60ecf-166">通话分析和通话质量仪表板</span><span class="sxs-lookup"><span data-stu-id="60ecf-166">Call Analytics and Call Quality Dashboard</span></span>](difference-between-call-analytics-and-call-quality-dashboard.md)

  
 
