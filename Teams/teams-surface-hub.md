---
title: 曲面集线器部署的 Microsoft 团队
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 12/04/2018
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: jatpatel
description: 配置 Microsoft 团队面中心的管理设置。
localization_priority: Normal
search.appverid: MET150
ms.custom:
- Devices
MS.collection: Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
ms.openlocfilehash: 485e4063c523608421955b86e0be680d5dc10b9a
ms.sourcegitcommit: 5742301cdd28e5e26107920f18e70f41b0f67cfb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2018
ms.locfileid: "27132000"
---
<a name="deploy-microsoft-teams-for-surface-hub"></a><span data-ttu-id="cef6a-103">曲面集线器部署的 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="cef6a-103">Deploy Microsoft Teams for Surface Hub</span></span>
======================================

<span data-ttu-id="cef6a-104">为 Microsoft Surface 集线器部署的 Microsoft 团队之前，请确保您已满足硬件、 操作系统和其他要求。</span><span class="sxs-lookup"><span data-stu-id="cef6a-104">Before you deploy Microsoft Teams for Microsoft Surface Hub, be sure you have met the hardware, operating system, and other requirements.</span></span> <span data-ttu-id="cef6a-105">有关详细信息，请参阅[Microsoft Surface 中心管理指南](https://docs.microsoft.com/surface-hub/)。</span><span class="sxs-lookup"><span data-stu-id="cef6a-105">For more information, see the [Microsoft Surface Hub admin guide](https://docs.microsoft.com/surface-hub/).</span></span>

> [!NOTE]
> <span data-ttu-id="cef6a-106">如果您从 Skype 中的业务联机转换，您需要确认的 Microsoft 团队许可证分配给用户。</span><span class="sxs-lookup"><span data-stu-id="cef6a-106">If you are transitioning from Skype for Business Online, you need to confirm that a Microsoft Teams license is assigned to the user.</span></span>

## <a name="install-teams-for-surface-hub-from-the-microsoft-store"></a><span data-ttu-id="cef6a-107">从 Microsoft 存储的表面集线器安装团队</span><span class="sxs-lookup"><span data-stu-id="cef6a-107">Install Teams for Surface Hub from the Microsoft Store</span></span> 

<span data-ttu-id="cef6a-108">安装 Microsoft 存储中的图面集线器团队供以下说明。</span><span class="sxs-lookup"><span data-stu-id="cef6a-108">These instructions are for installing Teams for Surface Hub from the Microsoft Store.</span></span> 
 
1. <span data-ttu-id="cef6a-109">启动 Microsoft 存储：</span><span class="sxs-lookup"><span data-stu-id="cef6a-109">Start the Microsoft Store:</span></span><br>
   <span data-ttu-id="cef6a-110">a.</span><span class="sxs-lookup"><span data-stu-id="cef6a-110">a.</span></span> <span data-ttu-id="cef6a-111">点击**开始** > **所有应用程序** > **设置**。</span><span class="sxs-lookup"><span data-stu-id="cef6a-111">Tap **Start** > **All Apps** > **Settings**.</span></span><br> <span data-ttu-id="cef6a-112">b.</span><span class="sxs-lookup"><span data-stu-id="cef6a-112">b.</span></span> <span data-ttu-id="cef6a-113">点击**面集线器设备帐户、 管理**。</span><span class="sxs-lookup"><span data-stu-id="cef6a-113">Tap **Surface Hub Device account, management**.</span></span><br>
   <span data-ttu-id="cef6a-114">c.</span><span class="sxs-lookup"><span data-stu-id="cef6a-114">c.</span></span> <span data-ttu-id="cef6a-115">在左侧，点击**应用程序和功能**选项卡。</span><span class="sxs-lookup"><span data-stu-id="cef6a-115">On the left, tap the **Apps & Features** tab.</span></span><br> <span data-ttu-id="cef6a-116">d.</span><span class="sxs-lookup"><span data-stu-id="cef6a-116">d.</span></span> <span data-ttu-id="cef6a-117">在右侧，点击**打开存储**按钮。</span><span class="sxs-lookup"><span data-stu-id="cef6a-117">On the right, tap the **Open Store** button.</span></span> 
2. <span data-ttu-id="cef6a-118">从 Microsoft 存储，搜索*的 Microsoft 团队*。</span><span class="sxs-lookup"><span data-stu-id="cef6a-118">From the Microsoft Store, search for *Microsoft Teams*.</span></span> <span data-ttu-id="cef6a-119">将显示**图面中心的 Microsoft 团队**。</span><span class="sxs-lookup"><span data-stu-id="cef6a-119">The **Microsoft Teams for Surface Hub** will be displayed.</span></span> <span data-ttu-id="cef6a-120">点击**获取应用程序**按钮以安装。</span><span class="sxs-lookup"><span data-stu-id="cef6a-120">Tap the **Get the app** button to install.</span></span>  
3. <span data-ttu-id="cef6a-121">安装完成后，重新启动面集线器。</span><span class="sxs-lookup"><span data-stu-id="cef6a-121">When the installation is complete, restart the Surface Hub.</span></span> 

> [!NOTE]
> <span data-ttu-id="cef6a-122">不点击从商店列表页的**启动**。</span><span class="sxs-lookup"><span data-stu-id="cef6a-122">Do not tap **Launch** from the Store listing page.</span></span>

## <a name="make-teams-the-default-calling-and-meetings-application"></a><span data-ttu-id="cef6a-123">使团队默认呼叫和会议应用程序</span><span class="sxs-lookup"><span data-stu-id="cef6a-123">Make Teams the default calling and meetings application</span></span>
 
<span data-ttu-id="cef6a-124">有两种配置的默认呼叫和会议应用程序策略：</span><span class="sxs-lookup"><span data-stu-id="cef6a-124">There are two options for configuring the default calling and meetings application policy:</span></span> 

- <span data-ttu-id="cef6a-125">**选项 1**： 配置通过 USB 键。</span><span class="sxs-lookup"><span data-stu-id="cef6a-125">**Option 1**: Configure via USB key.</span></span> 
- <span data-ttu-id="cef6a-126">**选项 2**： 通过如 Intune MDM 配置。</span><span class="sxs-lookup"><span data-stu-id="cef6a-126">**Option 2**: Configure via MDM such as Intune.</span></span>
 
### <a name="option-1-configure-via-usb-key"></a><span data-ttu-id="cef6a-127">选项 1： 配置通过 USB 键</span><span class="sxs-lookup"><span data-stu-id="cef6a-127">Option 1: Configure via USB key</span></span> 
 
<span data-ttu-id="cef6a-128">此[下载页](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g)上，可以找到包。</span><span class="sxs-lookup"><span data-stu-id="cef6a-128">The packages can be found on this [download page](https://1drv.ms/f/s!ArcnbnREun0Vnp9Wps9MlWB-UJZw3g).</span></span> <span data-ttu-id="cef6a-129">选择相应的包的安装，并将其复制到 usb 闪存盘您计划。</span><span class="sxs-lookup"><span data-stu-id="cef6a-129">Pick the appropriate one for the package that you're planning to install and copy it to a USB key.</span></span> <span data-ttu-id="cef6a-130">要使用的正确.ppkg 文件取决于您想要应用，如下所示的默认应用程序策略：</span><span class="sxs-lookup"><span data-stu-id="cef6a-130">The correct .ppkg file to use depends on the default application policy you'd like to apply as follows:</span></span> 

|<span data-ttu-id="cef6a-131">数字</span><span class="sxs-lookup"><span data-stu-id="cef6a-131">Number</span></span>  |<span data-ttu-id="cef6a-132">说明</span><span class="sxs-lookup"><span data-stu-id="cef6a-132">Description</span></span>  |
|---------|---------|
|<span data-ttu-id="cef6a-133">0</span><span class="sxs-lookup"><span data-stu-id="cef6a-133">0</span></span>     | <span data-ttu-id="cef6a-134">Skype 团队会议可用的启动屏幕上的首选应用程序</span><span class="sxs-lookup"><span data-stu-id="cef6a-134">Skype preferred app on the Start Screen, Teams Meetings available</span></span>        |
|<span data-ttu-id="cef6a-135">1</span><span class="sxs-lookup"><span data-stu-id="cef6a-135">1</span></span>     | <span data-ttu-id="cef6a-136">团队 Skype 会议可用的启动屏幕上的首选应用程序</span><span class="sxs-lookup"><span data-stu-id="cef6a-136">Teams preferred app on the Start Screen, Skype Meetings available</span></span>        |
|<span data-ttu-id="cef6a-137">2</span><span class="sxs-lookup"><span data-stu-id="cef6a-137">2</span></span>     | <span data-ttu-id="cef6a-138">在开始屏幕 (Skype app 不可用) 团队专用应用程序</span><span class="sxs-lookup"><span data-stu-id="cef6a-138">Teams exclusive app on the Start screen (Skype app not available)</span></span>        |
 
1. <span data-ttu-id="cef6a-139">将 usb 闪存盘附加到面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="cef6a-139">Attach the USB key to the Surface Hub device.</span></span> 
2. <span data-ttu-id="cef6a-140">打开面集线器设备上的**设置**应用程序。</span><span class="sxs-lookup"><span data-stu-id="cef6a-140">Open the **Settings** app on a Surface Hub device.</span></span> 
3. <span data-ttu-id="cef6a-141">**曲面集线器设备帐户管理**打开。</span><span class="sxs-lookup"><span data-stu-id="cef6a-141">Open **Surface Hub Device Account Management**.</span></span>
4. <span data-ttu-id="cef6a-142">打开**设备管理**。</span><span class="sxs-lookup"><span data-stu-id="cef6a-142">Open **Device Management**.</span></span> 
5. <span data-ttu-id="cef6a-143">单击**添加或删除设置包**。</span><span class="sxs-lookup"><span data-stu-id="cef6a-143">Click **Add or Remove a provisioning package**.</span></span> 
6. <span data-ttu-id="cef6a-144">单击**添加包**。</span><span class="sxs-lookup"><span data-stu-id="cef6a-144">Click **Add Package**.</span></span>
7. <span data-ttu-id="cef6a-145">从下拉列表菜单中选择**可移动媒体**选项。</span><span class="sxs-lookup"><span data-stu-id="cef6a-145">Select the **Removable Media** option from the drop-down menu.</span></span> 
8. <span data-ttu-id="cef6a-146">添加适当的<strong>TeamsRTMMode\*.ppkg</strong>包以前复制到 usb 闪存盘。</span><span class="sxs-lookup"><span data-stu-id="cef6a-146">Add the appropriate <strong>TeamsRTMMode\*.ppkg</strong> package that was previously copied to the USB key.</span></span> 
9. <span data-ttu-id="cef6a-147">重新启动面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="cef6a-147">Restart the Surface Hub device.</span></span> 
10. <span data-ttu-id="cef6a-148">设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。</span><span class="sxs-lookup"><span data-stu-id="cef6a-148">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span> 

### <a name="option-2-configure-via-mdm-such-as-intune"></a><span data-ttu-id="cef6a-149">选项 2： 配置通过如 Intune MDM</span><span class="sxs-lookup"><span data-stu-id="cef6a-149">Option 2: Configure via MDM such as Intune</span></span> 

<span data-ttu-id="cef6a-150">使用以下配置通过 Intune 的默认呼叫和会议应用程序策略。</span><span class="sxs-lookup"><span data-stu-id="cef6a-150">Use the following to configure the default calling and meetings application policy via Intune.</span></span> <span data-ttu-id="cef6a-151">另请参阅[Deploy 使用 Intune 的图面集线器应用程序的 Microsoft 团队](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/)的博客。</span><span class="sxs-lookup"><span data-stu-id="cef6a-151">Also see the blog, [Deploy the Microsoft Teams for Surface Hub app using Intune](https://blogs.technet.microsoft.com/y0av/2018/07/16/97/).</span></span>

|<span data-ttu-id="cef6a-152">设置</span><span class="sxs-lookup"><span data-stu-id="cef6a-152">Setting</span></span>   |<span data-ttu-id="cef6a-153">值</span><span class="sxs-lookup"><span data-stu-id="cef6a-153">Value</span></span>    |<span data-ttu-id="cef6a-154">说明</span><span class="sxs-lookup"><span data-stu-id="cef6a-154">Description</span></span>    |
|----------|---------|---------|
|<span data-ttu-id="cef6a-155">路径</span><span class="sxs-lookup"><span data-stu-id="cef6a-155">Path</span></span>      | <span data-ttu-id="cef6a-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span><span class="sxs-lookup"><span data-stu-id="cef6a-156">./Vendor/MSFT/SurfaceHub/Properties/SurfaceHubMeetingMode</span></span>        |
|<span data-ttu-id="cef6a-157">数据类型</span><span class="sxs-lookup"><span data-stu-id="cef6a-157">Data Type</span></span> | <span data-ttu-id="cef6a-158">整数 (0-2)</span><span class="sxs-lookup"><span data-stu-id="cef6a-158">integer (0-2)</span></span>   |<span data-ttu-id="cef6a-159">0-团队会议可用的启动屏幕上的 Skype 首选应用程序</span><span class="sxs-lookup"><span data-stu-id="cef6a-159">0 - Skype preferred app on the Start Screen, Teams Meetings available</span></span><br><span data-ttu-id="cef6a-160">1-团队 Skype 会议可用的启动屏幕上的首选应用程序</span><span class="sxs-lookup"><span data-stu-id="cef6a-160">1 - Teams preferred app on the Start Screen, Skype Meetings available</span></span><br><span data-ttu-id="cef6a-161">2-团队 （不可用 Skype 应用程序） 在开始屏幕上的专用应用程序</span><span class="sxs-lookup"><span data-stu-id="cef6a-161">2 - Teams exclusive app on the Start screen (Skype app not available)</span></span> |
|<span data-ttu-id="cef6a-162">运营</span><span class="sxs-lookup"><span data-stu-id="cef6a-162">Operations</span></span>| <span data-ttu-id="cef6a-163">获取、 设置</span><span class="sxs-lookup"><span data-stu-id="cef6a-163">Get, Set</span></span>        |

|<span data-ttu-id="cef6a-164">设置</span><span class="sxs-lookup"><span data-stu-id="cef6a-164">Setting</span></span>   |<span data-ttu-id="cef6a-165">值</span><span class="sxs-lookup"><span data-stu-id="cef6a-165">Value</span></span>    |
|----------|---------|
|<span data-ttu-id="cef6a-166">路径</span><span class="sxs-lookup"><span data-stu-id="cef6a-166">Path</span></span>      | <span data-ttu-id="cef6a-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span><span class="sxs-lookup"><span data-stu-id="cef6a-167">./Vendor/MSFT/SurfaceHub/Properties/VtcAppPackageId</span></span>        |
|<span data-ttu-id="cef6a-168">数据类型</span><span class="sxs-lookup"><span data-stu-id="cef6a-168">Data Type</span></span> | <span data-ttu-id="cef6a-169">字符串-团队应用程序包 ID 为**Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe 设置字符串 ！团队**</span><span class="sxs-lookup"><span data-stu-id="cef6a-169">string - set string to Teams application package ID as **Microsoft.MicrosoftTeamsforSurfaceHub_8wekyb3d8bbwe!Teams**</span></span> |
|<span data-ttu-id="cef6a-170">运营</span><span class="sxs-lookup"><span data-stu-id="cef6a-170">Operations</span></span>| <span data-ttu-id="cef6a-171">获取、 设置</span><span class="sxs-lookup"><span data-stu-id="cef6a-171">Get, Set</span></span>        |

<span data-ttu-id="cef6a-172">重新启动面集线器设备。</span><span class="sxs-lookup"><span data-stu-id="cef6a-172">Restart the Surface Hub device.</span></span> <span data-ttu-id="cef6a-173">设备重新启动后，您应该能够从开始屏幕中启动团队应用程序并从日历加入会议。</span><span class="sxs-lookup"><span data-stu-id="cef6a-173">After the device restarts, you should be able to start the Teams app from the Start screen and join a meeting from the calendar.</span></span>

