---
title: 已知的问题
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 4/17/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 本文讨论有关 Skype 会议室系统 v2 当前分支版本的已知的问题。
ms.openlocfilehash: 9214a1b198431decda70687d7e1dd3aa08069554
ms.sourcegitcommit: e577b4bdf3827fdfaf4482928adde177a64e4406
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="known-issues"></a><span data-ttu-id="1527e-103">已知的问题</span><span class="sxs-lookup"><span data-stu-id="1527e-103">Known issues</span></span> 
 
<span data-ttu-id="1527e-104">本文列出了 Skype 会议室系统 v2，按功能区域的已知的问题。</span><span class="sxs-lookup"><span data-stu-id="1527e-104">This article lists the known issues for Skype Room Systems v2, by feature area.</span></span>
<span data-ttu-id="1527e-105"><!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"></a> ##更新</span><span class="sxs-lookup"><span data-stu-id="1527e-105"><!-- If we get word that one of these issues no longer applies, contact meerak@microsoft.com or msmets@microsoft.com and let them know to EoL the corresponding KB  -->

<a name="update"> </a> ## Update</span></span> 

| <span data-ttu-id="1527e-106">问题标题</span><span class="sxs-lookup"><span data-stu-id="1527e-106">Issue title</span></span> |  <span data-ttu-id="1527e-107">行为\/症状</span><span class="sxs-lookup"><span data-stu-id="1527e-107">Behavior \/ Symptom</span></span> | <span data-ttu-id="1527e-108">已知的解决方法</span><span class="sxs-lookup"><span data-stu-id="1527e-108">Known workaround</span></span> | <span data-ttu-id="1527e-109">知识库文章</span><span class="sxs-lookup"><span data-stu-id="1527e-109">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|  <span data-ttu-id="1527e-110">过期的应用程序</span><span class="sxs-lookup"><span data-stu-id="1527e-110">App out of date</span></span>         |    <span data-ttu-id="1527e-111">Skype 会议室系统 v2 控制台将显示"系统配置过期"错误。</span><span class="sxs-lookup"><span data-stu-id="1527e-111">The Skype Room Systems v2 console shows a "system config out of date" error.</span></span>                |   [<span data-ttu-id="1527e-112">使用 Skype 会议室系统 v2 恢复工具</span><span class="sxs-lookup"><span data-stu-id="1527e-112">Use the Skype Room Systems v2 recovery tool</span></span>](recovery-tool.md)             |  <span data-ttu-id="1527e-113">无</span><span class="sxs-lookup"><span data-stu-id="1527e-113">None</span></span> |


<span data-ttu-id="1527e-114"><a name="OS-conflicts"> </a></span><span class="sxs-lookup"><span data-stu-id="1527e-114"></span></span>  
## <a name="user-interface"></a><span data-ttu-id="1527e-115">用户界面</span><span class="sxs-lookup"><span data-stu-id="1527e-115">User interface</span></span> 

| <span data-ttu-id="1527e-116">问题标题</span><span class="sxs-lookup"><span data-stu-id="1527e-116">Issue title</span></span> |  <span data-ttu-id="1527e-117">行为\/症状</span><span class="sxs-lookup"><span data-stu-id="1527e-117">Behavior \/ Symptom</span></span> | <span data-ttu-id="1527e-118">已知的解决方法</span><span class="sxs-lookup"><span data-stu-id="1527e-118">Known workaround</span></span> | <span data-ttu-id="1527e-119">知识库文章</span><span class="sxs-lookup"><span data-stu-id="1527e-119">KB Article</span></span> |
|  ---        |      ---             |   ---            | --- |
|<span data-ttu-id="1527e-120">虚拟键盘缺少</span><span class="sxs-lookup"><span data-stu-id="1527e-120">Virtual keyboard missing</span></span>   | <span data-ttu-id="1527e-121">当您需要在 Skype 会议室系统 v2 中输入信息时，不显示虚拟键盘。</span><span class="sxs-lookup"><span data-stu-id="1527e-121">The virtual keyboard doesn't appear when you need to enter information in Skype Room Systems v2.</span></span> <span data-ttu-id="1527e-122">在其运行 Skype 会议室系统 v2 Surface Pro 4 上安装 Windows 10 创建者更新 （版本 1703年） 后，将发生此问题。</span><span class="sxs-lookup"><span data-stu-id="1527e-122">This issue occurs after the Windows 10 Creators Update (version 1703) is installed on the Surface Pro 4 on which Skype Room Systems v2 is running.</span></span> | <span data-ttu-id="1527e-123">若要解决此问题，请手动打开虚拟键盘。</span><span class="sxs-lookup"><span data-stu-id="1527e-123">To work around this issue, manually open the virtual keyboard.</span></span> <span data-ttu-id="1527e-124">若要执行此操作，请按照以下步骤：</span><span class="sxs-lookup"><span data-stu-id="1527e-124">To do this, follow these steps:</span></span><br><br> <span data-ttu-id="1527e-125">**1。** 点击和保留任务栏，然后点击**显示触摸键盘**按钮。</span><span class="sxs-lookup"><span data-stu-id="1527e-125">**1.** Tap and hold the task bar, and then tap **Show touch keyboard** button.</span></span> <span data-ttu-id="1527e-126">键盘图标应显示在任务条形图的右侧。</span><span class="sxs-lookup"><span data-stu-id="1527e-126">A keyboard icon should appear on the right side of the task bar.</span></span> <br><br> <span data-ttu-id="1527e-127">**2。** 点击键盘图标以打开虚拟键盘。</span><span class="sxs-lookup"><span data-stu-id="1527e-127">**2.** Tap the keyboard icon to open the virtual keyboard.</span></span> | [<span data-ttu-id="1527e-128">KB4037694</span><span class="sxs-lookup"><span data-stu-id="1527e-128">KB4037694</span></span>](https://support.microsoft.com/en-us/help/4037694/virtual-keyboard-missing-in-skype-room-systems-v2) | 
   

<span data-ttu-id="1527e-129"><a name="Hardware"> </a></span><span class="sxs-lookup"><span data-stu-id="1527e-129"></span></span>  
## <a name="hardware"></a><span data-ttu-id="1527e-130">硬件</span><span class="sxs-lookup"><span data-stu-id="1527e-130">Hardware</span></span>

| <span data-ttu-id="1527e-131">问题标题</span><span class="sxs-lookup"><span data-stu-id="1527e-131">Issue title</span></span> |  <span data-ttu-id="1527e-132">行为\/症状</span><span class="sxs-lookup"><span data-stu-id="1527e-132">Behavior \/ Symptom</span></span> | <span data-ttu-id="1527e-133">已知的解决方法</span><span class="sxs-lookup"><span data-stu-id="1527e-133">Known workaround</span></span> | <span data-ttu-id="1527e-134">知识库文章</span><span class="sxs-lookup"><span data-stu-id="1527e-134">KB Article</span></span> |
|  ---        |      ---             |   ---            |   --- |
| <span data-ttu-id="1527e-135">未检测到的监视器</span><span class="sxs-lookup"><span data-stu-id="1527e-135">Monitors not detected</span></span> | <span data-ttu-id="1527e-136">当您运行 Surface Pro (模型 2017) 设备上的 Skype 会议室系统 v2 时，监视器未检测到。</span><span class="sxs-lookup"><span data-stu-id="1527e-136">When you run Skype Room Systems v2 on a Surface Pro (Model 2017) device, monitors are not detected.</span></span> |  <span data-ttu-id="1527e-137">20 个或多个秒钟按住 Surface Pro 电源按钮。</span><span class="sxs-lookup"><span data-stu-id="1527e-137">Hold down the Surface Pro power button for 20 or more seconds.</span></span> <span data-ttu-id="1527e-138">这样做，设备会重新启动，并清除图形缓存。</span><span class="sxs-lookup"><span data-stu-id="1527e-138">When you do this, the device restarts and clears the graphics cache.</span></span> |[<span data-ttu-id="1527e-139">KB4055681</span><span class="sxs-lookup"><span data-stu-id="1527e-139">KB4055681</span></span>](https://support.microsoft.com/en-us/help/4055681/monitors-are-not-detected-when-you-run-skype-room-systems-on-a-surface)       | 
          
<span data-ttu-id="1527e-140"><a name="Limits"> </a></span><span class="sxs-lookup"><span data-stu-id="1527e-140"></span></span>
## <a name="limitations-and-expected-behaviors"></a><span data-ttu-id="1527e-141">限制和预期的行为</span><span class="sxs-lookup"><span data-stu-id="1527e-141">Limitations and expected behaviors</span></span>
***
<span data-ttu-id="1527e-142">V2 不支持 HDCP 输入，观察到与 HDMI 会导致问题的 Skype 会议室系统接收功能 （视频、 音频）。</span><span class="sxs-lookup"><span data-stu-id="1527e-142">Skype Room Systems v2 does not support HDCP input, which has been observed to cause issues with HDMI ingest functionality (video, audio).</span></span> <span data-ttu-id="1527e-143">注意确保交换机连接到 Skype 会议室系统 v2 已关闭的 HDCP 选项。</span><span class="sxs-lookup"><span data-stu-id="1527e-143">Take care to ensure that switches connected to Skype Room Systems v2 have HDCP options turned off.</span></span> 
***
<span data-ttu-id="1527e-144">用作会议室前端显示屏的消费者电视需要支持/启用 HDMI 的 Consumer Electronics Control (CEC) 功能，以使其可以自动从待机模式切换至活动视频源。</span><span class="sxs-lookup"><span data-stu-id="1527e-144">A consumer TV used as a front of room display needs to support/enable the Consumer Electronics Control (CEC) feature of HDMI so that it can switch automatically to an active video source from standby mode.</span></span> <span data-ttu-id="1527e-145">并非所有电视都支持此功能。</span><span class="sxs-lookup"><span data-stu-id="1527e-145">This feature is not supported on all TVs.</span></span> 
***
<span data-ttu-id="1527e-146">始终使用有线 1 Gbps 网络连接以确保您将具有所需的带宽。</span><span class="sxs-lookup"><span data-stu-id="1527e-146">Always use a wired 1 Gbps network connection to assure you will have the needed bandwidth.</span></span> 
***
<span data-ttu-id="1527e-147">如果 Skype 会议室系统 v2 设备丢失与 （例如，如果您 Skype 会议室系统 v2 从域中删除后加入域） 域的信任，您将无法进行身份验证到设备，然后打开设置。</span><span class="sxs-lookup"><span data-stu-id="1527e-147">If your Skype Room Systems v2 device loses trust with the domain (for example, if you remove the Skype Room Systems v2 from the domain after it is domain joined), you won't be able to authenticate into the device and open up Settings.</span></span> <span data-ttu-id="1527e-148">解决方法是使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="1527e-148">The workaround is to log in with the local Admin account.</span></span> 
***
<span data-ttu-id="1527e-149">从 Skype 会议室系统 v2 版本 3.0.12.0 （更新 3） 不再支持 64 位版本的 Windows 10 企业周年日 edition （英语、 版本 1607年）。</span><span class="sxs-lookup"><span data-stu-id="1527e-149">The 64-bit version of Windows 10 Enterprise Anniversary edition (English language, version 1607) is no longer supported as of Skype Room Systems v2 release 3.0.12.0 (update 3).</span></span> 
***

<span data-ttu-id="1527e-150"><a name="See"> </a></span><span class="sxs-lookup"><span data-stu-id="1527e-150"></span></span>  
## <a name="see-also"></a><span data-ttu-id="1527e-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1527e-151">See also</span></span>


#### 
[<span data-ttu-id="1527e-152">Skype 会议室系统版本 2 帮助</span><span class="sxs-lookup"><span data-stu-id="1527e-152">Skype Room Systems version 2 help</span></span>](https://support.office.com/en-us/article/Skype-Room-Systems-version-2-help-e667f40e-5aab-40c1-bd68-611fe0002ba2)

[<span data-ttu-id="1527e-153">管理 Skype 会议室系统 v2</span><span class="sxs-lookup"><span data-stu-id="1527e-153">Manage Skype Room Systems v2</span></span>](skype-room-systems-v2.md)
