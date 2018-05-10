---
title: 部署 Skype for Business Online 电话
description: 了解获取正确的固件，如果需要对其进行更新、 分配许可证和为公用区域电话配置设置的部署步骤。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.date: 01/22/2018
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
- Strat_SB_PSTN
ms.openlocfilehash: 453f9db6a022e924406594c567ea564b10f58694
ms.sourcegitcommit: 7ec95ea34422e635661f3659bbc43a7a3484ff99
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/09/2018
---
## <a name="common-area-phones"></a><span data-ttu-id="871a8-103">公用区域电话</span><span class="sxs-lookup"><span data-stu-id="871a8-103">Common Area Phones</span></span>
<span data-ttu-id="871a8-104">公用区域电话或盖，通常放置在共享区域并不与单个用户关联。</span><span class="sxs-lookup"><span data-stu-id="871a8-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="871a8-105">例如，接收区域电话，门电话或会议室电话，大写设置为设备，而不是用户和自动登录到网络。</span><span class="sxs-lookup"><span data-stu-id="871a8-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="871a8-106">在下面的步骤中，我们将帮助您为 Microsoft 电话系统与调用计划设置帐户，然后部署帽。</span><span class="sxs-lookup"><span data-stu-id="871a8-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="871a8-107">公用区域电话的先决条件</span><span class="sxs-lookup"><span data-stu-id="871a8-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="871a8-108">确认您具有以下内容：</span><span class="sxs-lookup"><span data-stu-id="871a8-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="871a8-109">购买公共区域电话 SKU</span><span class="sxs-lookup"><span data-stu-id="871a8-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="871a8-110">更新的固件 （请参阅支持固件主题中https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="871a8-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="871a8-111">批准 （查看在列表的电话https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="871a8-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 


## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="871a8-112">检查您的电话的固件</span><span class="sxs-lookup"><span data-stu-id="871a8-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="871a8-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="871a8-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="871a8-114">**Yealink 电话** ，请转到电话主屏幕上的" **状态** "。</span><span class="sxs-lookup"><span data-stu-id="871a8-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="871a8-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="871a8-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="871a8-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="871a8-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="871a8-117">固件更新由 Skype for Business 服务管理。</span><span class="sxs-lookup"><span data-stu-id="871a8-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="871a8-118">每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。</span><span class="sxs-lookup"><span data-stu-id="871a8-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="871a8-119">根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。</span><span class="sxs-lookup"><span data-stu-id="871a8-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="871a8-120">您可以通过使用[Set CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet 并将_EnableDeviceUpdate_参数设置为禁用设备更新设置`false`。</span><span class="sxs-lookup"><span data-stu-id="871a8-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="871a8-121">创建盖</span><span class="sxs-lookup"><span data-stu-id="871a8-121">Create CAP</span></span>
<span data-ttu-id="871a8-122">通过配置之前设置物理电话的设置创建帽。</span><span class="sxs-lookup"><span data-stu-id="871a8-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="871a8-123">购买公共区域电话 SKU。</span><span class="sxs-lookup"><span data-stu-id="871a8-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="871a8-124">设置公用区域电话<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="871a8-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="871a8-125">**创建用户**</span><span class="sxs-lookup"><span data-stu-id="871a8-125">**Create user**</span></span> 
1. <span data-ttu-id="871a8-126">分配公用区域电话 SKU</span><span class="sxs-lookup"><span data-stu-id="871a8-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="871a8-127">分配调用规划 （如果与调用计划使用 Microsoft 电话系统）。</span><span class="sxs-lookup"><span data-stu-id="871a8-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="871a8-128">分配 Business Admin Center Skype 中可用的电话号码或请求新的电话号码。</span><span class="sxs-lookup"><span data-stu-id="871a8-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="871a8-129">**创建新用户**</span><span class="sxs-lookup"><span data-stu-id="871a8-129">**Create New User**</span></span>

1. <span data-ttu-id="871a8-130">在设置窗格中，存在一个选项，输入名字和姓氏名称 (例如，接收 Main)。</span><span class="sxs-lookup"><span data-stu-id="871a8-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="871a8-131">输入显示名称 （必需），例如，"Main 接收。"</span><span class="sxs-lookup"><span data-stu-id="871a8-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="871a8-132">输入用户名 （必需），例如"MainReception"@"域"（公司或企业名称）</span><span class="sxs-lookup"><span data-stu-id="871a8-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="871a8-133">输入位置 （国家/地区）。</span><span class="sxs-lookup"><span data-stu-id="871a8-133">Enter Location (country).</span></span>

<span data-ttu-id="871a8-134">**分配公用区域电话 SKU**在 Office 365 管理中心，转到**帐单 > 购买服务**并将其添加**公用区域电话**</span><span class="sxs-lookup"><span data-stu-id="871a8-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="871a8-135">**分配呼叫帽 SKU 中的计划**</span><span class="sxs-lookup"><span data-stu-id="871a8-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="871a8-136">选择调用计划启用电话。</span><span class="sxs-lookup"><span data-stu-id="871a8-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="871a8-137">添加业务 Online 计划 2 中帽 SKU 中启用电话系统和 Skype 的帽。</span><span class="sxs-lookup"><span data-stu-id="871a8-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="871a8-138">**分配电话号码**</span><span class="sxs-lookup"><span data-stu-id="871a8-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="871a8-139">检查下可用的电话号码**语音 > 电话号码**。</span><span class="sxs-lookup"><span data-stu-id="871a8-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="871a8-140">从可用的电话号码的号码列表中选择一个号码。</span><span class="sxs-lookup"><span data-stu-id="871a8-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="871a8-141">确认您的选择通过选择**语音**和**电话号码**。</span><span class="sxs-lookup"><span data-stu-id="871a8-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="871a8-142">[注意]语音用户仅显示是否他们所应用，电话系统许可，尽管甚至应用后，可能需要刷新的时间。</span><span class="sxs-lookup"><span data-stu-id="871a8-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="871a8-143">当时重新 Skype 打开业务管理中心帮助。</span><span class="sxs-lookup"><span data-stu-id="871a8-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="871a8-144">配置电话</span><span class="sxs-lookup"><span data-stu-id="871a8-144">Configure Phone</span></span>

<span data-ttu-id="871a8-145">**准备物理电话**</span><span class="sxs-lookup"><span data-stu-id="871a8-145">**Prepare the physical phones**</span></span> 

<span data-ttu-id="871a8-146">所选的电话需要有公用区域电话模式。</span><span class="sxs-lookup"><span data-stu-id="871a8-146">Your selected phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="871a8-147">***示例 Polycom VVX 电话***</span><span class="sxs-lookup"><span data-stu-id="871a8-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="871a8-148">通过执行以下步骤来启用 Polycom VVX 公共区域电话模式：</span><span class="sxs-lookup"><span data-stu-id="871a8-148">Enable Common Area Phone Mode on Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="871a8-149">在浏览器中，使用 web 界面启用 VVX 帽模式</span><span class="sxs-lookup"><span data-stu-id="871a8-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="871a8-150">转至**设置**业务设置选项 Skype 中，选择**公用区域电话**。</span><span class="sxs-lookup"><span data-stu-id="871a8-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="871a8-151">单击**保存**以保存您的配置设置。</span><span class="sxs-lookup"><span data-stu-id="871a8-151">Click **Save** to save your configuration settings.</span></span>

<span data-ttu-id="871a8-152">既然帽电话模式已启用，则设置使用电话的显示电话。</span><span class="sxs-lookup"><span data-stu-id="871a8-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span>

1. <span data-ttu-id="871a8-153">在设置，选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="871a8-153">In the Settings, select **Advanced**.</span></span>
2. <span data-ttu-id="871a8-154">输入密码。</span><span class="sxs-lookup"><span data-stu-id="871a8-154">Enter password.</span></span>
3. <span data-ttu-id="871a8-155">在管理设置中，选择**公共区域电话设置**。</span><span class="sxs-lookup"><span data-stu-id="871a8-155">In Administration settings, select **Common Area Phone Settings**.</span></span>
4. <span data-ttu-id="871a8-156">启用 Common Area Phone and 帽管理</span><span class="sxs-lookup"><span data-stu-id="871a8-156">Enable Common Area Phone and CAP Admin</span></span>
5. <span data-ttu-id="871a8-157">选择**保存配置**。</span><span class="sxs-lookup"><span data-stu-id="871a8-157">Select **Save Config**.</span></span>

<span data-ttu-id="871a8-158">您的电话登录在主屏幕上时将创建以下情况下已准备好进行设置。</span><span class="sxs-lookup"><span data-stu-id="871a8-158">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="871a8-159">通过选择登录**设置 > 功能 > for Business 的 Skype。**</span><span class="sxs-lookup"><span data-stu-id="871a8-159">Sign in by selecting **settings > features > Skype for Business.**</span></span>
2. <span data-ttu-id="871a8-160">选择用户凭据，然后选择选择**web 登录助手 （帽）**生成代码正在</span><span class="sxs-lookup"><span data-stu-id="871a8-160">Select User Credentials, and select select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="871a8-161">转到设置门户http://aka.ms/skypecap，并以**管理员身份**登录。</span><span class="sxs-lookup"><span data-stu-id="871a8-161">Go to the provisioning portal http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="871a8-162">输入显示名称 （例如，Main 接收） 以查看您帽。</span><span class="sxs-lookup"><span data-stu-id="871a8-162">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="871a8-163">[注意]如果"为公用区域电话的搜索"被选中，清除该复选框，并再次进行搜索。</span><span class="sxs-lookup"><span data-stu-id="871a8-163">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="871a8-164">在配对的代码窗口中，输入电话上显示的代码，并单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="871a8-164">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="871a8-165">预缴税金此最后一步，电话应自动登录。</span><span class="sxs-lookup"><span data-stu-id="871a8-165">Wht this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="871a8-166">了解有关在可用电话[](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)。</span><span class="sxs-lookup"><span data-stu-id="871a8-166">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


