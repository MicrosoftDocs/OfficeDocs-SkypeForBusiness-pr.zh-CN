---
title: Teams Android 设备的远程预配和登录
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: prgholve
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: 了解如何为 Teams Android 设备远程预配和登录
ms.openlocfilehash: 43a025c0cc68fb7f10015d69298f8dd75f9003e8
ms.sourcegitcommit: 95386369e2256ba382b4d6e34adb7473de050b26
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "51410325"
---
# <a name="remote-provisioning-and-sign-in-for-teams-android-devices"></a><span data-ttu-id="dfaea-103">Teams Android 设备的远程预配和登录</span><span class="sxs-lookup"><span data-stu-id="dfaea-103">Remote provisioning and sign in for Teams Android devices</span></span>

<span data-ttu-id="dfaea-104">IT 管理员可以远程预配并登录到 Teams Android 设备。</span><span class="sxs-lookup"><span data-stu-id="dfaea-104">IT admins can remotely provision and sign in to a Teams Android device.</span></span> <span data-ttu-id="dfaea-105">若要远程预配设备，管理员需要上传正在预配的设备的 MAC ID 并创建验证码。</span><span class="sxs-lookup"><span data-stu-id="dfaea-105">To provision a device remotely, the admin needs to upload the MAC IDs of the devices being provisioned and create a verification code.</span></span> <span data-ttu-id="dfaea-106">整个过程可以从 Teams 管理中心远程完成。</span><span class="sxs-lookup"><span data-stu-id="dfaea-106">The entire process can be completed remotely from the Teams admin center.</span></span>

## <a name="review-the-supported-devices"></a><span data-ttu-id="dfaea-107">查看支持的设备</span><span class="sxs-lookup"><span data-stu-id="dfaea-107">Review the supported devices</span></span>

<span data-ttu-id="dfaea-108">以下列表显示了 Android 设备固件要求。</span><span class="sxs-lookup"><span data-stu-id="dfaea-108">The following list shows the Android device firmware requirements.</span></span>

|<span data-ttu-id="dfaea-109">设备类别</span><span class="sxs-lookup"><span data-stu-id="dfaea-109">Device category</span></span>|<span data-ttu-id="dfaea-110">设备模型</span><span class="sxs-lookup"><span data-stu-id="dfaea-110">Device model</span></span>|<span data-ttu-id="dfaea-111">固件版本</span><span class="sxs-lookup"><span data-stu-id="dfaea-111">Firmware version</span></span>|
|-|-|-|
|<span data-ttu-id="dfaea-112">Teams 手机</span><span class="sxs-lookup"><span data-stu-id="dfaea-112">Teams phones</span></span>|<span data-ttu-id="dfaea-113">Yealink T55/T56/T58</span><span class="sxs-lookup"><span data-stu-id="dfaea-113">Yealink T55/T56/T58</span></span>|<span data-ttu-id="dfaea-114">58.15.0.124</span><span class="sxs-lookup"><span data-stu-id="dfaea-114">58.15.0.124</span></span>|
|<span data-ttu-id="dfaea-115">Teams 手机</span><span class="sxs-lookup"><span data-stu-id="dfaea-115">Teams phones</span></span>|<span data-ttu-id="dfaea-116">Yealink VP59</span><span class="sxs-lookup"><span data-stu-id="dfaea-116">Yealink VP59</span></span>|<span data-ttu-id="dfaea-117">91.15.0.58</span><span class="sxs-lookup"><span data-stu-id="dfaea-117">91.15.0.58</span></span>|
|<span data-ttu-id="dfaea-118">Teams 手机</span><span class="sxs-lookup"><span data-stu-id="dfaea-118">Teams phones</span></span>|<span data-ttu-id="dfaea-119">Yealink CP960</span><span class="sxs-lookup"><span data-stu-id="dfaea-119">Yealink CP960</span></span>|<span data-ttu-id="dfaea-120">73.15.0.117</span><span class="sxs-lookup"><span data-stu-id="dfaea-120">73.15.0.117</span></span>|
|<span data-ttu-id="dfaea-121">Teams 手机</span><span class="sxs-lookup"><span data-stu-id="dfaea-121">Teams phones</span></span>|<span data-ttu-id="dfaea-122">Yealink MP56/MP54/MP58</span><span class="sxs-lookup"><span data-stu-id="dfaea-122">Yealink MP56/MP54/MP58</span></span>|<span data-ttu-id="dfaea-123">122.15.0.36</span><span class="sxs-lookup"><span data-stu-id="dfaea-123">122.15.0.36</span></span>|
|<span data-ttu-id="dfaea-124">Teams 手机</span><span class="sxs-lookup"><span data-stu-id="dfaea-124">Teams phones</span></span>|<span data-ttu-id="dfaea-125">Crestron UC-2</span><span class="sxs-lookup"><span data-stu-id="dfaea-125">Crestron UC-2</span></span>|<span data-ttu-id="dfaea-126">1.0.3.52</span><span class="sxs-lookup"><span data-stu-id="dfaea-126">1.0.3.52</span></span>|

## <a name="add-a-device-mac-address"></a><span data-ttu-id="dfaea-127">添加设备 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="dfaea-127">Add a device MAC address</span></span>

<span data-ttu-id="dfaea-128">完成以下步骤来预配新设备。</span><span class="sxs-lookup"><span data-stu-id="dfaea-128">Complete the following steps to provision a new device.</span></span>

1. <span data-ttu-id="dfaea-129">登录到 Teams 管理中心。</span><span class="sxs-lookup"><span data-stu-id="dfaea-129">Sign in to the Teams admin center.</span></span>
2. <span data-ttu-id="dfaea-130">展开 **"设备"。**</span><span class="sxs-lookup"><span data-stu-id="dfaea-130">Expand **Devices**.</span></span>
3. <span data-ttu-id="dfaea-131">从 **"操作"选项卡中选择** "预配 **新设备** "。</span><span class="sxs-lookup"><span data-stu-id="dfaea-131">Select **Provision new device** from the **Actions** tab.</span></span>

<span data-ttu-id="dfaea-132">在 **"预配新设备** "窗口中，可以手动添加 MAC 地址或上传文件。</span><span class="sxs-lookup"><span data-stu-id="dfaea-132">In the **Provision new devices** window, you can either add the MAC address manually or upload a file.</span></span>

### <a name="manually-add-a-device-mac-address"></a><span data-ttu-id="dfaea-133">手动添加设备 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="dfaea-133">Manually add a device MAC address</span></span>

1. <span data-ttu-id="dfaea-134">在"**正在等待激活"选项卡中**，选择"**添加 MAC ID"。**</span><span class="sxs-lookup"><span data-stu-id="dfaea-134">From the **Awaiting Activation** tab, select **Add MAC ID**.</span></span>

   ![手动添加设备 mac 地址](../media/remote-provision-6.png)

1. <span data-ttu-id="dfaea-136">输入 MAC ID。</span><span class="sxs-lookup"><span data-stu-id="dfaea-136">Enter the MAC ID.</span></span>
1. <span data-ttu-id="dfaea-137">输入一个位置，帮助技术人员确定安装设备的位置。</span><span class="sxs-lookup"><span data-stu-id="dfaea-137">Enter a location, which helps technicians identify where to install the devices.</span></span>
1. <span data-ttu-id="dfaea-138">完成后 **，选择"** 应用"。</span><span class="sxs-lookup"><span data-stu-id="dfaea-138">Select **Apply** when finished.</span></span>

### <a name="upload-a-file-to-add-a-device-mac-address"></a><span data-ttu-id="dfaea-139">上传文件以添加设备 MAC 地址</span><span class="sxs-lookup"><span data-stu-id="dfaea-139">Upload a file to add a device MAC address</span></span>

1. <span data-ttu-id="dfaea-140">在"**正在等待激活"选项卡** 中，选择 **"上传 MAC ID"。**</span><span class="sxs-lookup"><span data-stu-id="dfaea-140">From the **Awaiting Activation** tab, select **Upload MAC IDs**.</span></span>
2. <span data-ttu-id="dfaea-141">下载文件模板。</span><span class="sxs-lookup"><span data-stu-id="dfaea-141">Download the file template.</span></span>
3. <span data-ttu-id="dfaea-142">输入 MAC ID 和位置，然后保存文件。</span><span class="sxs-lookup"><span data-stu-id="dfaea-142">Enter the MAC ID and location, and then save the file.</span></span>
4. <span data-ttu-id="dfaea-143">**选择文件**，然后选择"上传 **"。**</span><span class="sxs-lookup"><span data-stu-id="dfaea-143">**Select file**, and then select **Upload**.</span></span>

## <a name="generate-a-verification-code"></a><span data-ttu-id="dfaea-144">生成验证码</span><span class="sxs-lookup"><span data-stu-id="dfaea-144">Generate a verification code</span></span>

<span data-ttu-id="dfaea-145">需要设备的验证码。</span><span class="sxs-lookup"><span data-stu-id="dfaea-145">You need a verification code for the devices.</span></span> <span data-ttu-id="dfaea-146">验证码以批量或设备级别生成，有效期为 24 小时。</span><span class="sxs-lookup"><span data-stu-id="dfaea-146">The verification code is generated in bulk or at the device level and is valid for 24 hours.</span></span>

1. <span data-ttu-id="dfaea-147">在" **正在等待激活"** 选项卡中，选择现有的 MAC ID。</span><span class="sxs-lookup"><span data-stu-id="dfaea-147">From the **Awaiting Activation** tab, select an existing MAC ID.</span></span>
   <span data-ttu-id="dfaea-148">为 MAC 地址创建密码，显示在"验证 **码"** 列中。</span><span class="sxs-lookup"><span data-stu-id="dfaea-148">A password is created for the MAC address and is shown in the **Verification Code** column.</span></span>

2. <span data-ttu-id="dfaea-149">向现场技术人员提供 MAC ID 和验证码列表。</span><span class="sxs-lookup"><span data-stu-id="dfaea-149">Provide the list of MAC IDs and verification codes to the field technicians.</span></span> <span data-ttu-id="dfaea-150">可以直接在文件中导出详细信息，并与执行实际安装工作的技术人员共享该文件。</span><span class="sxs-lookup"><span data-stu-id="dfaea-150">You can export the detail directly in a file and share the file with the technician who is doing the actual installation work.</span></span>

## <a name="provision-the-device"></a><span data-ttu-id="dfaea-151">预配设备</span><span class="sxs-lookup"><span data-stu-id="dfaea-151">Provision the device</span></span>

<span data-ttu-id="dfaea-152">当设备接通电源并连接到网络时，技术人员将设置设备。</span><span class="sxs-lookup"><span data-stu-id="dfaea-152">When the device is powered on and connected to the network, the technician provisions the device.</span></span> <span data-ttu-id="dfaea-153">这些步骤在 Teams 设备上完成。</span><span class="sxs-lookup"><span data-stu-id="dfaea-153">These steps are completed on the Teams device.</span></span>

1. <span data-ttu-id="dfaea-154">技术人员从"设置 **"中选择"** 预配 **设备"。**</span><span class="sxs-lookup"><span data-stu-id="dfaea-154">The technician selects **Provision device** from the **Settings**.</span></span>  

   !["操作"选项卡中的"预配新设备"选项](../media/provision-device1.png)
  
2. <span data-ttu-id="dfaea-156">技术人员在提供的输入字段中输入特定于设备的验证码。</span><span class="sxs-lookup"><span data-stu-id="dfaea-156">The technician enters the device-specific verification code in the provided input field.</span></span>

   ![预配新设备验证](../media/provision-device-verification1.png)

   <span data-ttu-id="dfaea-158">成功预配设备后，租户名称会显示在登录页上。</span><span class="sxs-lookup"><span data-stu-id="dfaea-158">Once the device is provisioned successfully, the tenant name appears on the sign-in page.</span></span>

   ![登录页上的租户名称](../media/provision-code.png)

## <a name="sign-in-remotely"></a><span data-ttu-id="dfaea-160">远程登录</span><span class="sxs-lookup"><span data-stu-id="dfaea-160">Sign in remotely</span></span>

<span data-ttu-id="dfaea-161">预配的设备显示在"等待 **登录"选项卡** 中。通过选择单个设备启动远程登录过程。</span><span class="sxs-lookup"><span data-stu-id="dfaea-161">The provisioned device appears in the **Awaiting sign in** tab. Start the remote sign-in process by selecting the individual device.</span></span>

1. <span data-ttu-id="dfaea-162">从"等待登录 **"选项卡中选择设备** 。</span><span class="sxs-lookup"><span data-stu-id="dfaea-162">Select a device from the **Awaiting sign in** tab.</span></span>

   ![一个窗口，其中列出了已准备好登录的设备。](../media/remote-device1.png)

2. <span data-ttu-id="dfaea-164">按照"登录 **用户"中的说明操作**，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="dfaea-164">Follow the instructions in **Sign in a user**, and then select **Close**.</span></span>

   ![单个设备的"登录用户"窗口](../media/sign-in-user.png)

## <a name="related-article"></a><span data-ttu-id="dfaea-166">相关文章</span><span class="sxs-lookup"><span data-stu-id="dfaea-166">Related article</span></span>

- [<span data-ttu-id="dfaea-167">在 Teams 中管理设备</span><span class="sxs-lookup"><span data-stu-id="dfaea-167">Manage your devices in Teams</span></span>](device-management.md)
- [<span data-ttu-id="dfaea-168">远程更新 Teams 设备</span><span class="sxs-lookup"><span data-stu-id="dfaea-168">Update Teams devices remotely</span></span>](remote-update.md)
