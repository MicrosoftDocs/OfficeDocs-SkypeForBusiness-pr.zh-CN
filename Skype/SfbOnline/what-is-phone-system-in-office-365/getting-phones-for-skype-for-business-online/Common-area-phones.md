---
title: 设置公用区域电话
description: 了解获取正确的固件，如果需要对其进行更新、 分配许可证和为公用区域电话配置设置的部署步骤。
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
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
ms.openlocfilehash: 12ed7d5c24649903f7cd3020d66ee4e9fcb77b6f
ms.sourcegitcommit: b394b394e6c51fe0d75b1eec47f6ada1b0265b63
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2018
---
# <a name="set-up-common-area-phones"></a><span data-ttu-id="029c7-103">设置公用区域电话</span><span class="sxs-lookup"><span data-stu-id="029c7-103">Set up Common Area Phones</span></span>

<span data-ttu-id="029c7-104">公用区域电话或盖，通常放置在共享区域并不与单个用户关联。</span><span class="sxs-lookup"><span data-stu-id="029c7-104">A common area phone, or CAP, is typically placed in a shared area and not associated with an individual user.</span></span> <span data-ttu-id="029c7-105">例如，接收区域电话，门电话或会议室电话，大写设置为设备，而不是用户和自动登录到网络。</span><span class="sxs-lookup"><span data-stu-id="029c7-105">For example, a reception area phone, door phone or meeting room phone, CAPs are set up as devices rather than users and automatically  sign in to the network.</span></span> <span data-ttu-id="029c7-106">在下面的步骤中，我们将帮助您为 Microsoft 电话系统与调用计划设置帐户，然后部署帽。</span><span class="sxs-lookup"><span data-stu-id="029c7-106">In the steps below, we’ll help you set up an account for Microsoft Phone System with Calling Plans and then deploy a CAP.</span></span>

## <a name="prerequisites-for-common-area-phones"></a><span data-ttu-id="029c7-107">公用区域电话的先决条件</span><span class="sxs-lookup"><span data-stu-id="029c7-107">Prerequisites for Common Area Phones</span></span>

<span data-ttu-id="029c7-108">确认您具有以下内容：</span><span class="sxs-lookup"><span data-stu-id="029c7-108">Confirm that you have the following:</span></span>

    - <span data-ttu-id="029c7-109">购买公共区域电话 SKU</span><span class="sxs-lookup"><span data-stu-id="029c7-109">Purchased Common Area Phone SKU</span></span> 
    - <span data-ttu-id="029c7-110">更新的固件 （请参阅支持固件主题中https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="029c7-110">Updated firmware (See Supported Firmware in topichttps://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online)</span></span>
    - <span data-ttu-id="029c7-111">批准 （查看在列表的电话https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span><span class="sxs-lookup"><span data-stu-id="029c7-111">Approved  phones (view the list at https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)</span></span> 

## <a name="check-the-firmware-for-your-phone"></a><span data-ttu-id="029c7-112">检查您的电话的固件</span><span class="sxs-lookup"><span data-stu-id="029c7-112">Check the firmware for your phone</span></span>
- <span data-ttu-id="029c7-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span><span class="sxs-lookup"><span data-stu-id="029c7-113">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
- <span data-ttu-id="029c7-114">**Yealink 电话** ，请转到电话主屏幕上的" **状态** "。</span><span class="sxs-lookup"><span data-stu-id="029c7-114">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
- <span data-ttu-id="029c7-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="029c7-115">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span> 
- <span data-ttu-id="029c7-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span><span class="sxs-lookup"><span data-stu-id="029c7-116">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>

<span data-ttu-id="029c7-117">固件更新由 Skype for Business 服务管理。</span><span class="sxs-lookup"><span data-stu-id="029c7-117">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="029c7-118">每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。</span><span class="sxs-lookup"><span data-stu-id="029c7-118">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> 

<span data-ttu-id="029c7-119">根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。</span><span class="sxs-lookup"><span data-stu-id="029c7-119">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="029c7-120">您可以通过使用[Set CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet 并将_EnableDeviceUpdate_参数设置为禁用设备更新设置`false`。</span><span class="sxs-lookup"><span data-stu-id="029c7-120">You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>

## <a name="create-cap"></a><span data-ttu-id="029c7-121">创建盖</span><span class="sxs-lookup"><span data-stu-id="029c7-121">Create CAP</span></span>
<span data-ttu-id="029c7-122">通过配置之前设置物理电话的设置创建帽。</span><span class="sxs-lookup"><span data-stu-id="029c7-122">You create the CAP by configuring the settings before you set up the physical phone.</span></span>

#### <a name="purchase-the-common-area-phone-sku"></a><span data-ttu-id="029c7-123">购买公共区域电话 SKU。</span><span class="sxs-lookup"><span data-stu-id="029c7-123">Purchase the Common Area Phone SKU.</span></span> 
    In the Office 365 admin center, go to **Billing > Purchase Services**, and add **Common Area Phone**.

#### <a name="set-up-the-common-area-phone-----this-section-could-use-a-screen-shot--"></a><span data-ttu-id="029c7-124">设置公用区域电话<!-- this section could use a screen shot--></span><span class="sxs-lookup"><span data-stu-id="029c7-124">Set up the common area phone  <!-- this section could use a screen shot--></span></span>

<span data-ttu-id="029c7-125">**创建用户**</span><span class="sxs-lookup"><span data-stu-id="029c7-125">**Create user**</span></span> 
1. <span data-ttu-id="029c7-126">分配公用区域电话 SKU</span><span class="sxs-lookup"><span data-stu-id="029c7-126">Assign Common Area Phone SKU</span></span>
2. <span data-ttu-id="029c7-127">分配调用规划 （如果与调用计划使用 Microsoft 电话系统）。</span><span class="sxs-lookup"><span data-stu-id="029c7-127">Assign Calling Plan (if using Microsoft Phone System with Calling Plans).</span></span> 
3. <span data-ttu-id="029c7-128">分配 Business Admin Center Skype 中可用的电话号码或请求新的电话号码。</span><span class="sxs-lookup"><span data-stu-id="029c7-128">Assign an available telephone number in the Skype for Business Admin Center, or request a new telephone number.</span></span>

<span data-ttu-id="029c7-129">**创建新用户**</span><span class="sxs-lookup"><span data-stu-id="029c7-129">**Create New User**</span></span>

1. <span data-ttu-id="029c7-130">在设置窗格中，存在一个选项，输入名字和姓氏名称 (例如，接收 Main)。</span><span class="sxs-lookup"><span data-stu-id="029c7-130">In the provisioning pane, you have an option to enter a first and last name (for example, Reception Main).</span></span>
2. <span data-ttu-id="029c7-131">输入显示名称 （必需），例如，"Main 接收。"</span><span class="sxs-lookup"><span data-stu-id="029c7-131">Enter a display name (required), for example, "Main Reception."</span></span>
3. <span data-ttu-id="029c7-132">输入用户名 （必需），例如"MainReception"@"域"（公司或企业名称）</span><span class="sxs-lookup"><span data-stu-id="029c7-132">Enter a username (required), for example “MainReception” @” domain” (company or enterprise name)</span></span>
4. <span data-ttu-id="029c7-133">输入位置 （国家/地区）。</span><span class="sxs-lookup"><span data-stu-id="029c7-133">Enter Location (country).</span></span>

<span data-ttu-id="029c7-134">**分配公用区域电话 SKU**在 Office 365 管理中心，转到**帐单 > 购买服务**并将其添加**公用区域电话**</span><span class="sxs-lookup"><span data-stu-id="029c7-134">**Assign Common Area Phone SKU** In the Office 365 admin center, go to **Billing > Purchase Services** and add **Common Area Phone**</span></span>

<span data-ttu-id="029c7-135">**分配呼叫帽 SKU 中的计划**</span><span class="sxs-lookup"><span data-stu-id="029c7-135">**Assign Calling Plan in CAP SKU**</span></span>

1. <span data-ttu-id="029c7-136">选择调用计划启用电话。</span><span class="sxs-lookup"><span data-stu-id="029c7-136">Select a Calling Plan to enable the phone.</span></span> 
2. <span data-ttu-id="029c7-137">添加业务 Online 计划 2 中帽 SKU 中启用电话系统和 Skype 的帽。</span><span class="sxs-lookup"><span data-stu-id="029c7-137">Add the CAP to enable the Phone System and Skype for Business Online Plan 2 in the CAP SKU.</span></span> <!-- odd order for step -->

<span data-ttu-id="029c7-138">**分配电话号码**</span><span class="sxs-lookup"><span data-stu-id="029c7-138">**Assign a telephone number**</span></span>
1. <span data-ttu-id="029c7-139">检查下可用的电话号码**语音 > 电话号码**。</span><span class="sxs-lookup"><span data-stu-id="029c7-139">Check for available phone numbers under **Voice > Phone Numbers**.</span></span>
2. <span data-ttu-id="029c7-140">从可用的电话号码的号码列表中选择一个号码。</span><span class="sxs-lookup"><span data-stu-id="029c7-140">Select a number from the available list of phone numbers number.</span></span>
3. <span data-ttu-id="029c7-141">确认您的选择通过选择**语音**和**电话号码**。</span><span class="sxs-lookup"><span data-stu-id="029c7-141">Confirm your selection by selecting **Voice** and **Phone Numbers**.</span></span>

    ><span data-ttu-id="029c7-142">[注意]语音用户仅显示是否他们所应用，电话系统许可，尽管甚至应用后，可能需要刷新的时间。</span><span class="sxs-lookup"><span data-stu-id="029c7-142">[Note] Voice users only show if they have the Phone System licence applied, although even after applying, it can take time to refresh.</span></span> <span data-ttu-id="029c7-143">当时重新 Skype 打开业务管理中心帮助。</span><span class="sxs-lookup"><span data-stu-id="029c7-143">Sometime reopening Skype for Business Admin center helps.</span></span>
    
## <a name="configure-phone"></a><span data-ttu-id="029c7-144">配置电话</span><span class="sxs-lookup"><span data-stu-id="029c7-144">Configure Phone</span></span>

<span data-ttu-id="029c7-145">**准备物理电话**</span><span class="sxs-lookup"><span data-stu-id="029c7-145">**Prepare the physical phones**</span></span>

<span data-ttu-id="029c7-146">选的电话需要有公用区域电话模式。</span><span class="sxs-lookup"><span data-stu-id="029c7-146">Your chosen phone needs to have the Common Area Phone mode.</span></span> 

<span data-ttu-id="029c7-147">***示例 Polycom VVX 电话***</span><span class="sxs-lookup"><span data-stu-id="029c7-147">***Example Polycom VVX phone***</span></span>

<span data-ttu-id="029c7-148">通过执行以下步骤为 Polycom VVX 启用公共区域电话模式：</span><span class="sxs-lookup"><span data-stu-id="029c7-148">Enable Common Area Phone Mode for the Polycom VVX by following these steps:</span></span>
1. <span data-ttu-id="029c7-149">在浏览器中，使用 web 界面启用 VVX 帽模式</span><span class="sxs-lookup"><span data-stu-id="029c7-149">In your browser, use the web interface to enable CAP mode on the VVX</span></span>
2. <span data-ttu-id="029c7-150">转至**设置**业务设置选项 Skype 中，选择**公用区域电话**。</span><span class="sxs-lookup"><span data-stu-id="029c7-150">Go to **Setting**  and in the Skype for Business Setting option, select **Common Area Phone**.</span></span>
3. <span data-ttu-id="029c7-151">单击**是**以保存您的配置设置。</span><span class="sxs-lookup"><span data-stu-id="029c7-151">Click **Yes** to save your configuration settings.</span></span>

<span data-ttu-id="029c7-152">既然帽电话模式已启用，则设置使用电话的显示电话。</span><span class="sxs-lookup"><span data-stu-id="029c7-152">Now that the CAP phone mode is enabled, set up the phone using the phone's display.</span></span> <span data-ttu-id="029c7-153">显示应显示"启用 CaAP。"</span><span class="sxs-lookup"><span data-stu-id="029c7-153">The display should show "CaAP is enabled."</span></span>

1. <span data-ttu-id="029c7-154">单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="029c7-154">Click **Settings**.</span></span>
2. <span data-ttu-id="029c7-155">选择**高级**。</span><span class="sxs-lookup"><span data-stu-id="029c7-155">Select **Advanced**.</span></span>
3. <span data-ttu-id="029c7-156">输入密码。</span><span class="sxs-lookup"><span data-stu-id="029c7-156">Enter the password.</span></span>
4. <span data-ttu-id="029c7-157">在管理设置中，选择**公共区域电话设置**。</span><span class="sxs-lookup"><span data-stu-id="029c7-157">In Administration settings, select **Common Area Phone Settings**.</span></span>
5. <span data-ttu-id="029c7-158">启用**上限**和**帽管理员模式**。</span><span class="sxs-lookup"><span data-stu-id="029c7-158">Enable **CAP** and **CAP Admin Mode**.</span></span>
6. <span data-ttu-id="029c7-159">单击**保存配置**。</span><span class="sxs-lookup"><span data-stu-id="029c7-159">Click **Save Config**.</span></span>

<span data-ttu-id="029c7-160">您的电话登录在主屏幕上时将创建以下情况下已准备好进行设置。</span><span class="sxs-lookup"><span data-stu-id="029c7-160">Your phone is ready to be provisioned, which you'll do when you sign in on the home screen.</span></span>

1. <span data-ttu-id="029c7-161">通过选择**设置**登录 > **功能** > **for Business 的 Skype。**</span><span class="sxs-lookup"><span data-stu-id="029c7-161">Sign in by selecting **Settings** > **Features** > **Skype for Business.**</span></span>
2. <span data-ttu-id="029c7-162">选择**用户凭据**，然后选择**web 登录助手 （帽）**生成代码正在</span><span class="sxs-lookup"><span data-stu-id="029c7-162">Select **User Credentials**, and select **web sign-in (CAP)** to generate a code..</span></span>
3. <span data-ttu-id="029c7-163">转到设置门户网站位于http://aka.ms/skypecap，并以**管理员身份**登录。</span><span class="sxs-lookup"><span data-stu-id="029c7-163">Go to the provisioning portal at http://aka.ms/skypecap, and sign in as **admin**.</span></span>
4. <span data-ttu-id="029c7-164">输入显示名称 （例如，Main 接收） 以查看您帽。</span><span class="sxs-lookup"><span data-stu-id="029c7-164">Enter display name (for example, Main Reception) to view your CAP.</span></span>

><span data-ttu-id="029c7-165">[注意]如果"为公用区域电话的搜索"被选中，清除该复选框，并再次进行搜索。</span><span class="sxs-lookup"><span data-stu-id="029c7-165">[Note] If “Search for Common Area Phones only” is checked, clear the checkbox and search again.</span></span>

5. <span data-ttu-id="029c7-166">在配对的代码窗口中，输入电话上显示的代码，并单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="029c7-166">In the pairing code window, enter the code displayed on the phone and click **Provision**.</span></span>

<span data-ttu-id="029c7-167">以下此最后一步，电话应自动登录。</span><span class="sxs-lookup"><span data-stu-id="029c7-167">Following this last step, the phone should sign in automatically.</span></span>

<span data-ttu-id="029c7-168">了解有关在可用电话[](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones)。</span><span class="sxs-lookup"><span data-stu-id="029c7-168">Learn more about available phones at [](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/deploying-skype-for-business-online-phones).</span></span>


