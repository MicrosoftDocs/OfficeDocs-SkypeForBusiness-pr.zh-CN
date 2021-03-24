---
title: 部署 Skype for Business Online 电话
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: wasseemh
ms.topic: article
ms.assetid: faa17eb3-7483-4984-87f2-815d981b68ae
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Phone System
description: 了解部署步骤，获取正确的固件、根据需要更新固件、分配许可证以及配置 Skype for Business Online 电话的设置
ms.openlocfilehash: 4c683cd2b0259c0145632c8522f3b262c686c71d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51097098"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="62fc6-103">部署 Skype for Business Online 电话</span><span class="sxs-lookup"><span data-stu-id="62fc6-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="62fc6-104">本部署指南将帮助你部署 Skype for Business Online IP 电话。</span><span class="sxs-lookup"><span data-stu-id="62fc6-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="62fc6-105">在所有类型的业务中，拥有电话号码允许用户拨打和接听语音呼叫，这是一项重要的业务要求。</span><span class="sxs-lookup"><span data-stu-id="62fc6-105">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business.</span></span> <span data-ttu-id="62fc6-106">拥有电话号码的用户将能够跨所有 Skype for Business 设备（包括 IP 电话、电脑和移动设备）进行语音呼叫。</span><span class="sxs-lookup"><span data-stu-id="62fc6-106">Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices.</span></span> <span data-ttu-id="62fc6-107">你可以阅读获取 Skype for Business Online 的电话，了解有关 Skype for Business IP [电话的更多内容](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-107">You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="62fc6-108">部署 IP 电话的步骤</span><span class="sxs-lookup"><span data-stu-id="62fc6-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="62fc6-109">第 1 步 - 下载制造商的管理员指南和电话手册</span><span class="sxs-lookup"><span data-stu-id="62fc6-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="62fc6-110">开始之前，最好先下载电话制造商的管理指南和电话用户手册。</span><span class="sxs-lookup"><span data-stu-id="62fc6-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="62fc6-111">对于 Polycom 电话，请参阅 [Poly 文档库](https://documents.polycom.com/category/voice)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-111">For Polycom phones, see the [Poly Documentation Library](https://documents.polycom.com/category/voice).</span></span>
    
- <span data-ttu-id="62fc6-112">对于 Yealink 电话，请参阅 [Yealink Skype for Business HD SIP 电话解决方案](http://www.yealink.com/products_top_2.html)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="62fc6-113">对于 AudioCodes 电话，请参阅 [Audiocodes 配置管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="62fc6-114">第 2 步 - 确保购买或迁移支持 Skype for Business 的 IP 电话和固件</span><span class="sxs-lookup"><span data-stu-id="62fc6-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="62fc6-115">支持 Skype for Business Online 的电话和固件也兼容 Skype for Business Server，反之则不一定成立。</span><span class="sxs-lookup"><span data-stu-id="62fc6-115">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true.</span></span> <span data-ttu-id="62fc6-116">若要确保购买或预配受支持的电话和固件，请参阅 [获取 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-116">To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="62fc6-117">第 3 步 - 检查是否安装了正确的固件并根据需要更新固件。</span><span class="sxs-lookup"><span data-stu-id="62fc6-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="62fc6-118">检查手机上的固件版本。</span><span class="sxs-lookup"><span data-stu-id="62fc6-118">Check the firmware version on your phones.</span></span> <span data-ttu-id="62fc6-119">对于：</span><span class="sxs-lookup"><span data-stu-id="62fc6-119">For:</span></span>
  
- <span data-ttu-id="62fc6-120">**Polycom VVX 电话**，请转到 **设置** > **状态** > **平台** > **应用程序** > **主要**。</span><span class="sxs-lookup"><span data-stu-id="62fc6-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="62fc6-121">**Yealink 电话** ，请转到电话主屏幕上的" **状态** "。</span><span class="sxs-lookup"><span data-stu-id="62fc6-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="62fc6-122">**AudioCodes 电话**，请转到开始菜单的 **菜单** > **设备状态** > **固件版本**。</span><span class="sxs-lookup"><span data-stu-id="62fc6-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="62fc6-123">有关远程访问电话的详细信息，请参阅制造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="62fc6-123">For remote access to phone details, refer to manufacturer administration guides.</span></span> <span data-ttu-id="62fc6-124">请通过上面的链接获取用户指南和电话手册。</span><span class="sxs-lookup"><span data-stu-id="62fc6-124">See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="62fc6-125">**Lync Phone Edition (LPE) 电话**，请转到开始屏幕的 **菜单** > **系统信息**。</span><span class="sxs-lookup"><span data-stu-id="62fc6-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="62fc6-126">第 4 步 - 设备更新注意事项</span><span class="sxs-lookup"><span data-stu-id="62fc6-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="62fc6-127">5.5.1.X 之前的 Polycom 固件具有特定于制造商的设备锁定机制，该机制已替换为 Skype for Business 实现"Phone-Lock"。</span><span class="sxs-lookup"><span data-stu-id="62fc6-127">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock."</span></span> <span data-ttu-id="62fc6-128">将使用"Device-Lock"保护的手机从 5.4.X.X 升级到使用"Phone-Lock"保护的 5.5.1.X 不会从"Device-Lock"继承 PIN 码，因此手机可能不安全。</span><span class="sxs-lookup"><span data-stu-id="62fc6-128">Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured.</span></span> <span data-ttu-id="62fc6-129">已激活"Device-Lock"的用户需要启用以下 Polycom 设备配置文件参数，以便用户控制 (lync.deviceUpdate.popUpSK.enabled=1) 的升级时间。</span><span class="sxs-lookup"><span data-stu-id="62fc6-129">Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="62fc6-130">固件更新由 Skype for Business 服务管理。</span><span class="sxs-lookup"><span data-stu-id="62fc6-130">Firmware updates are managed by the Skype for Business Service.</span></span> <span data-ttu-id="62fc6-131">每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。</span><span class="sxs-lookup"><span data-stu-id="62fc6-131">Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default.</span></span> <span data-ttu-id="62fc6-132">根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。</span><span class="sxs-lookup"><span data-stu-id="62fc6-132">Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds.</span></span> <span data-ttu-id="62fc6-133">可以使用 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) cmdlet 将 _EnableDeviceUpdate_ 参数设置为 来禁用设备更新设置 `false` 。</span><span class="sxs-lookup"><span data-stu-id="62fc6-133">You can disable the device update settings by using the [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![显示部署手机的屏幕截图](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="62fc6-135">新固件可用且能够进行下载和安装时，电话会通知用户。</span><span class="sxs-lookup"><span data-stu-id="62fc6-135">When a new firmware is available and ready for download and install, the phone will notify the user.</span></span> <span data-ttu-id="62fc6-136">Polycom 电话将通知用户，并为用户提供"更新 **"或** "推迟 **"选项**。</span><span class="sxs-lookup"><span data-stu-id="62fc6-136">Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![显示"更新"和"推迟"选项的屏幕截图。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="62fc6-138">对于 Polycom 电话，可以通过选择" **软件更新**"来更新电话上的固件。</span><span class="sxs-lookup"><span data-stu-id="62fc6-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![显示 SwUpdate 选项的屏幕截图](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="62fc6-p108">还可以选择使用合作伙伴配置系统来管理固件更新。有关包含高级电话自定义的合作伙伴配置系统管理，请参考制造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="62fc6-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="62fc6-142">[!警告] 确保拥有单个设备更新授权（带内设备更新或第三方配置服务器），以避免更新循环。</span><span class="sxs-lookup"><span data-stu-id="62fc6-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="62fc6-143">步骤 5 - 配置和基础结构电话设置</span><span class="sxs-lookup"><span data-stu-id="62fc6-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="62fc6-p109">你可以使用 Skype for Business 带内管理 Windows PowerShell cmdlet 来设置最常用的电话选项和策略。有关这些参数和设置的详细信息，请参阅 [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="62fc6-146">有关网络基础结构规划，请参阅 [Skype Operations Framework](https://www.skypeoperationsframework.com/)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="62fc6-147">步骤 6 - 准备让用户登录</span><span class="sxs-lookup"><span data-stu-id="62fc6-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="62fc6-148">若要让用户成功登录到 Skype for Business Online 电话并拨打电话，你需要确保为用户分配正确的许可证。</span><span class="sxs-lookup"><span data-stu-id="62fc6-148">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses.</span></span> <span data-ttu-id="62fc6-149">至少需要分配电话系统许可证和呼叫计划。</span><span class="sxs-lookup"><span data-stu-id="62fc6-149">At a minimum, you will need to assign a Phone System license and a Calling Plan.</span></span> <span data-ttu-id="62fc6-150">有关其他信息，可参阅 [Skype for Business 和 Microsoft Teams 加载项授权](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) 和 [分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-150">For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="62fc6-151">你可以阅读电话系统和通话套餐，了解有关通话 [套餐的更多内容](/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="62fc6-151">You can find out more about Calling Plans by reading [Phone System and Calling Plans](/microsoftteams/calling-plan-landing-page)</span></span>
  
- <span data-ttu-id="62fc6-152">Online 用户可以使用的 **登录选项** 包括：</span><span class="sxs-lookup"><span data-stu-id="62fc6-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="62fc6-153">使用 **Polycom VVX 5XX/6XX 电话** 的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="62fc6-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![显示 Polycom 电话登录的屏幕截图](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="62fc6-155">使用 **Yealink T48G/T46G 电话** 的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="62fc6-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![显示 Yealink 手机登录的屏幕截图。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="62fc6-157">有关制造商支持的登录选项的详细信息，请参阅 [获取 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="62fc6-p111">**用户 ID** 通过电话键盘或屏幕键盘（如有），用户可以使用其组织的用户名和密码登录电话。例如，他们应使用类似 <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。</span><span class="sxs-lookup"><span data-stu-id="62fc6-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![显示登录屏幕的屏幕截图](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="62fc6-161">[!注释] Skype for Business Online 不支持对 LPE 和合作伙伴 IP 电话进行 PIN 身份验证。</span><span class="sxs-lookup"><span data-stu-id="62fc6-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="62fc6-162">**使用电脑** 在用户的电脑上安装并 (BToE) 软件后，用户可以使用 Windows Skype for Business 应用中的身份验证窗口登录到其手机。</span><span class="sxs-lookup"><span data-stu-id="62fc6-162">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App.</span></span> <span data-ttu-id="62fc6-163">请参阅 [步骤 7 (可选 ](deploying-skype-for-business-online-phones.md#BK_BTOE)) - 如果具有设备配对，请参阅 BToE (BToE) 更好的连接。</span><span class="sxs-lookup"><span data-stu-id="62fc6-163">See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="62fc6-p113">[!注释] 用户需要使用其组织的用户名和密码登录电话。例如，他们应使用类似  <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。</span><span class="sxs-lookup"><span data-stu-id="62fc6-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![显示登录屏幕的屏幕截图](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="62fc6-167">**使用 Web 登录**：这是联机用户使用标准 Web 浏览器进行身份验证的一种新方式。</span><span class="sxs-lookup"><span data-stu-id="62fc6-167">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser.</span></span> <span data-ttu-id="62fc6-168">当用户使用浏览器登录时，将为用户提供一组要遵循的说明。</span><span class="sxs-lookup"><span data-stu-id="62fc6-168">Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="62fc6-169">使用 **Polycom VVX 5XX/6XX 电话** 的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="62fc6-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![显示 Polycom 说明的屏幕截图](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="62fc6-171">使用 **Yealink T48G/T46G 电话** 的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="62fc6-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![显示 Yealink 说明的屏幕截图](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="62fc6-173">生成的代码将于 15 分钟后过期。</span><span class="sxs-lookup"><span data-stu-id="62fc6-173">The code that is generated will expire in 15 minutes.</span></span> <span data-ttu-id="62fc6-174">到期时，用户必须单击"重试"或"确定"以生成新代码，具体取决于手机。</span><span class="sxs-lookup"><span data-stu-id="62fc6-174">When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="62fc6-175">使用 **Polycom VVX 5XX/6XX 电话** 的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="62fc6-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![显示已过期 Polycom 代码的屏幕截图](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="62fc6-177">使用 **Yealink T48G/T46G 电话** 的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="62fc6-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![显示过期 Yealink 代码的屏幕截图](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="62fc6-179">使用浏览器，导航到电话上显示的地址，输入 Skype for Business 用户名。</span><span class="sxs-lookup"><span data-stu-id="62fc6-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![显示电子邮件验证的屏幕截图](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="62fc6-181">输入电话上显示的代码。</span><span class="sxs-lookup"><span data-stu-id="62fc6-181">Enter the code shown on the phone.</span></span>
    
     ![显示登录屏幕上的输入代码的屏幕截图](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="62fc6-183">验证站点是否显示"[电话制造商名称] **Skype for Business 认证电话**"，然后单击"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="62fc6-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![显示名称验证的屏幕截图](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="62fc6-185">单击用户的凭据或单击" **使用其他帐户**"：</span><span class="sxs-lookup"><span data-stu-id="62fc6-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![显示凭据选项的屏幕截图](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="62fc6-187">显示以下页面时，可以安全地关闭浏览器。</span><span class="sxs-lookup"><span data-stu-id="62fc6-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![显示确认消息的屏幕截图](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="62fc6-189">[!注释] 适用于 Skype for Business Online 的 LPE 电话仅支持通过 USB 数据连线登录。</span><span class="sxs-lookup"><span data-stu-id="62fc6-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="62fc6-190">**支持的部署** 下表显示了当前支持的部署模式所支持的身份验证类型，包括 Exchange 集成、使用多因素身份验证 (MFA) 的新式验证以及 Skype for Business Online 和本地部署。</span><span class="sxs-lookup"><span data-stu-id="62fc6-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="62fc6-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="62fc6-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="62fc6-192">**交换**</span><span class="sxs-lookup"><span data-stu-id="62fc6-192">**Exchange**</span></span> <br/> |<span data-ttu-id="62fc6-193">**电话登录方法**</span><span class="sxs-lookup"><span data-stu-id="62fc6-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="62fc6-194">**Skype for Business 访问**</span><span class="sxs-lookup"><span data-stu-id="62fc6-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="62fc6-195">**禁用新式验证和 MFA 的 Exchange 访问**</span><span class="sxs-lookup"><span data-stu-id="62fc6-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="62fc6-196">**启用新式验证和 MFA 的 Exchange 访问**</span><span class="sxs-lookup"><span data-stu-id="62fc6-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="62fc6-197">Online</span><span class="sxs-lookup"><span data-stu-id="62fc6-197">Online</span></span>  <br/> |<span data-ttu-id="62fc6-198">Online</span><span class="sxs-lookup"><span data-stu-id="62fc6-198">Online</span></span>  <br/> |<span data-ttu-id="62fc6-199">Web 登录</span><span class="sxs-lookup"><span data-stu-id="62fc6-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="62fc6-200">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-200">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-201">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-201">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-202">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-202">Yes</span></span>  <br/> |
|<span data-ttu-id="62fc6-203">Online</span><span class="sxs-lookup"><span data-stu-id="62fc6-203">Online</span></span>  <br/> |<span data-ttu-id="62fc6-204">Online</span><span class="sxs-lookup"><span data-stu-id="62fc6-204">Online</span></span>  <br/> |<span data-ttu-id="62fc6-205">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="62fc6-205">Username/Password</span></span>  <br/> |<span data-ttu-id="62fc6-206">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-206">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-207">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-207">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-208">否</span><span class="sxs-lookup"><span data-stu-id="62fc6-208">No</span></span>  <br/> |
|<span data-ttu-id="62fc6-209">Online</span><span class="sxs-lookup"><span data-stu-id="62fc6-209">Online</span></span>  <br/> |<span data-ttu-id="62fc6-210">本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-210">On-premises</span></span>  <br/> |<span data-ttu-id="62fc6-211">Web 登录</span><span class="sxs-lookup"><span data-stu-id="62fc6-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="62fc6-212">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-212">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-213">否</span><span class="sxs-lookup"><span data-stu-id="62fc6-213">No</span></span>  <br/> |<span data-ttu-id="62fc6-214">否</span><span class="sxs-lookup"><span data-stu-id="62fc6-214">No</span></span>  <br/> |
|<span data-ttu-id="62fc6-215">Online</span><span class="sxs-lookup"><span data-stu-id="62fc6-215">Online</span></span>  <br/> |<span data-ttu-id="62fc6-216">本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-216">On-Premises</span></span>  <br/> |<span data-ttu-id="62fc6-217">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="62fc6-217">Username/Password</span></span>  <br/> |<span data-ttu-id="62fc6-218">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-218">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-219">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-219">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-220">否</span><span class="sxs-lookup"><span data-stu-id="62fc6-220">No</span></span>  <br/> |
|<span data-ttu-id="62fc6-221">本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-221">On-premises</span></span>  <br/> |<span data-ttu-id="62fc6-222">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="62fc6-223">PIN 身份验证</span><span class="sxs-lookup"><span data-stu-id="62fc6-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="62fc6-224">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-224">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-225">否</span><span class="sxs-lookup"><span data-stu-id="62fc6-225">No</span></span>  <br/> |<span data-ttu-id="62fc6-226">否</span><span class="sxs-lookup"><span data-stu-id="62fc6-226">No</span></span>  <br/> |
|<span data-ttu-id="62fc6-227">本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-227">On-premises</span></span>  <br/> |<span data-ttu-id="62fc6-228">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="62fc6-229">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="62fc6-229">Username/Password</span></span>  <br/> |<span data-ttu-id="62fc6-230">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-230">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-231">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-231">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-232">不适用</span><span class="sxs-lookup"><span data-stu-id="62fc6-232">N/A</span></span>  <br/> |
|<span data-ttu-id="62fc6-233">本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-233">On-premises</span></span>  <br/> |<span data-ttu-id="62fc6-234">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="62fc6-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="62fc6-235">通过 PC 登录 (BTOE)</span><span class="sxs-lookup"><span data-stu-id="62fc6-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="62fc6-236">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-236">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-237">是</span><span class="sxs-lookup"><span data-stu-id="62fc6-237">Yes</span></span>  <br/> |<span data-ttu-id="62fc6-238">不适用</span><span class="sxs-lookup"><span data-stu-id="62fc6-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="62fc6-239">**电话功能** 根据 IP 电话合作伙伴，功能集可能会略有不同。</span><span class="sxs-lookup"><span data-stu-id="62fc6-239">**Phone features** The feature set may vary slightly based on the IP phone partner.</span></span> <span data-ttu-id="62fc6-240">有关完整功能集和各电话制造商的功能的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-240">For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="62fc6-241">**电话锁定** Skype for Business 认证电话新近引入的用于保护电话的功能。</span><span class="sxs-lookup"><span data-stu-id="62fc6-241">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone.</span></span> <span data-ttu-id="62fc6-242">如果启用，用户将被要求在身份验证成功后创建一个 PIN。</span><span class="sxs-lookup"><span data-stu-id="62fc6-242">If enabled, users will be asked to create a PIN upon successful authentication.</span></span> <span data-ttu-id="62fc6-243">一旦创建，当定义的空闲超时过期、 用户手动锁定其电话或使用电话配使其电话锁定与其 PC 锁定同步时，电话将锁定。</span><span class="sxs-lookup"><span data-stu-id="62fc6-243">Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing.</span></span> <span data-ttu-id="62fc6-244">如果多次输错电话锁定 PIN，电话会将此用户注销或要求输入管理员的代码才能解锁电话，但不同电话合作伙伴在这方面的要求有所差异。</span><span class="sxs-lookup"><span data-stu-id="62fc6-244">If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner.</span></span> <span data-ttu-id="62fc6-245">用户的 PIN 应为 6-15 位数字。</span><span class="sxs-lookup"><span data-stu-id="62fc6-245">The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="62fc6-246">你可以为Phone-Lock禁用 (默认启用的) ，更改空闲超时，并选择用户是否可以在锁定时进行电话呼叫或不使用带内设置。</span><span class="sxs-lookup"><span data-stu-id="62fc6-246">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings.</span></span> <span data-ttu-id="62fc6-247">有关[这些设置的更多详细信息，请参阅 Set-CsUCPhoneConfiguration。](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="62fc6-247">See [Set-CsUCPhoneConfiguration](/powershell/module/skype/set-csucphoneconfiguration?view=skype-ps) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="62fc6-248">第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="62fc6-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="62fc6-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="62fc6-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="62fc6-250">BToE 是合作伙伴 IP 电话的一种电话处理机制，用于将用户的手机与他们的 Windows Skype for Business 应用配对。</span><span class="sxs-lookup"><span data-stu-id="62fc6-250">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app.</span></span> <span data-ttu-id="62fc6-251">利用 BToE，用户可以：</span><span class="sxs-lookup"><span data-stu-id="62fc6-251">BToE enables users to:</span></span>
  
- <span data-ttu-id="62fc6-252">使用电脑设备通过 Skype for Business 桌面应用 (登录到其 IP) </span><span class="sxs-lookup"><span data-stu-id="62fc6-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="62fc6-253">将Phone-Lock电脑锁同步</span><span class="sxs-lookup"><span data-stu-id="62fc6-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="62fc6-254">单击以呼叫</span><span class="sxs-lookup"><span data-stu-id="62fc6-254">Click to call</span></span>
    
<span data-ttu-id="62fc6-255">BToE 可以配置为在两种模式下运行：自动 (默认) *手动*。</span><span class="sxs-lookup"><span data-stu-id="62fc6-255">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  .</span></span> <span data-ttu-id="62fc6-256">也可以为使用 Skype for Business 带内设置的用户启用（默认）/禁用此功能。</span><span class="sxs-lookup"><span data-stu-id="62fc6-256">It can also be enabled (default)/disabled for users using Skype for Business in-band settings.</span></span> <span data-ttu-id="62fc6-257">采用 *手动*  模式运行时，用户还必须执行其他步骤，以便将其电话与其 Windows 应用配对。</span><span class="sxs-lookup"><span data-stu-id="62fc6-257">When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="62fc6-258">**将 BToE 部署到用户**</span><span class="sxs-lookup"><span data-stu-id="62fc6-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="62fc6-259">使用 PC 端口将 PC 与电话相连。</span><span class="sxs-lookup"><span data-stu-id="62fc6-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![显示与电脑连接的屏幕截图](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="62fc6-261">从制造商网站（链接如下所示）下载并安装最新的 BToE 软件。</span><span class="sxs-lookup"><span data-stu-id="62fc6-261">Download and install the latest BToE software from the manufacturer website from the links below.</span></span> <span data-ttu-id="62fc6-262">为获得更好的用户体验，可以使用管理员分发解决方案（如 Microsoft 终结点配置管理器）分发和安装 BToE 软件。</span><span class="sxs-lookup"><span data-stu-id="62fc6-262">For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="62fc6-263">有关使用 Configuration Manager 的帮助，请参阅 Configuration [Manager 中的包和程序](/configmgr/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="62fc6-263">For help using Configuration Manager, See [Packages and programs in Configuration Manager](/configmgr/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="62fc6-264">Polycom BToE 软件下载站点</span><span class="sxs-lookup"><span data-stu-id="62fc6-264">Polycom BToE Software Download site</span></span>](https://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="62fc6-265">Yealink BToE 软件下载</span><span class="sxs-lookup"><span data-stu-id="62fc6-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="62fc6-266">AudioCodes BToE 软件下载</span><span class="sxs-lookup"><span data-stu-id="62fc6-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="62fc6-267">默认情况下，BToE 的服务器设置设置为 **"已启用\*\*\*\*"和"自动** 模式"。</span><span class="sxs-lookup"><span data-stu-id="62fc6-267">The server setting for BToE is set to **Enabled** and **Auto mode** by default.</span></span> <span data-ttu-id="62fc6-268">若要更改这些设置，请参阅[设置 CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy) 。</span><span class="sxs-lookup"><span data-stu-id="62fc6-268">To change those settings, see [Set-CsIPPhonePolicy](/powershell/module/skype/Set-CsIPPhonePolicy).</span></span>
    
> [!NOTE]
> <span data-ttu-id="62fc6-269">[!注释] Mac 和 VDI 平台目前不支持 BToE。</span><span class="sxs-lookup"><span data-stu-id="62fc6-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="62fc6-270">相关主题</span><span class="sxs-lookup"><span data-stu-id="62fc6-270">Related topics</span></span>
[<span data-ttu-id="62fc6-271">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="62fc6-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](/microsoftteams/getting-service-phone-numbers)

[<span data-ttu-id="62fc6-272">电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="62fc6-272">Here's what you get with Phone System</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="62fc6-273">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="62fc6-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
