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
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Phone System
description: 了解部署步骤以获取正确的固件、根据需要进行更新、分配许可证并配置 Skype for Business online 电话的设置。
ms.openlocfilehash: 4237e1cb32204a3d87d639710a2829c1111cc354
ms.sourcegitcommit: cbb4738e119cf366c3aad9aad7f7b369bcd86c19
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2018
ms.locfileid: "23780059"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="b24d5-103">部署 Skype for Business Online 电话</span><span class="sxs-lookup"><span data-stu-id="b24d5-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="b24d5-104">本部署指南将帮助你部署 Skype for Business Online IP 电话。</span><span class="sxs-lookup"><span data-stu-id="b24d5-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="b24d5-p101">在所有类型的企业中，拥有电话号码让用户能够拨打和接听语音呼叫，这也是开展业务的重要要求。拥有电话号码的用户将能够跨各种 Skype for Business 设备进行语音通话，包括 IP 电话、PC 和移动设备。如需了解有关 Skype for Business IP 电话的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p101">In all types of businesses, having a phone number allows users to make and get voice calls and it is an important requirement to do business. Users that have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by seeing, [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="b24d5-108">部署 IP 电话的步骤</span><span class="sxs-lookup"><span data-stu-id="b24d5-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="b24d5-109">第 1 步 - 下载制造商的管理员指南和电话手册</span><span class="sxs-lookup"><span data-stu-id="b24d5-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="b24d5-110">开始之前，最好先下载电话制造商的管理指南和电话用户手册。</span><span class="sxs-lookup"><span data-stu-id="b24d5-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="b24d5-111">有关 Polycom 电话，请参阅 [Polycom 部署指南] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-111">For Polycom phones, see the http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="b24d5-112">对于 Yealink 电话，请参阅 [Yealink Skype for Business HD SIP 电话解决方案](http://www.yealink.com/products_top_2.html)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-112">For Yealink phones, see [Yealink Skype for Business® HD IP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="b24d5-113">对于 AudioCodes 电话，请参阅 [Audiocodes 配置管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="b24d5-114">第 2 步 - 确保购买或迁移支持 Skype for Business 的 IP 电话和固件</span><span class="sxs-lookup"><span data-stu-id="b24d5-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="b24d5-p102">支持 Skype for Business Online 的电话和固件也兼容 Skype for Business Server，但事实并非总是如此。要确保购买或配置了受支持的电话和固件，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)指南。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) guide.</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="b24d5-117">第 3 步 - 检查是否安装了正确的固件并根据需要更新固件</span><span class="sxs-lookup"><span data-stu-id="b24d5-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="b24d5-p103">检查电话的固件版本。对于：</span><span class="sxs-lookup"><span data-stu-id="b24d5-p103">To check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="b24d5-120">**Polycom VVX 电话**，请转到**设置** > **状态** > **平台** > **应用程序** > **主要**。</span><span class="sxs-lookup"><span data-stu-id="b24d5-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="b24d5-121">**Yealink 电话** ，请转到电话主屏幕上的" **状态** "。</span><span class="sxs-lookup"><span data-stu-id="b24d5-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="b24d5-122">**AudioCodes 电话**，请转到开始菜单的**菜单** > **设备状态** > **固件版本**。</span><span class="sxs-lookup"><span data-stu-id="b24d5-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b24d5-p104">如需远程访问电话详细信息，请参考制造商管理指南。请通过上面的链接获取用户指南和电话手册。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p104">For remote access to phone details refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="b24d5-125">**Lync Phone Edition (LPE) 电话**，请转到开始屏幕的**菜单** > **系统信息**。</span><span class="sxs-lookup"><span data-stu-id="b24d5-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="b24d5-126">第 4 步 - 设备更新注意事项</span><span class="sxs-lookup"><span data-stu-id="b24d5-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="b24d5-p105">5.5.1.X 之前的 Polycom 固件具有一个特定于制造商的设备锁机制，该机制已被替换为 Skype for Business 策略"电话锁"。将电话从使用"设备锁"确保安全性的 5.4.X.X 升级到使用"电话锁"的 5.5.1.X 不会继承"设备锁"的 PIN 代码，这会导致电话不安全。对于已经激活"设备锁"的用户，需要启用以下 Polycom 设备配置文件参数，以便为用户提供对升级时间的控制 (lync.deviceUpdate.popUpSK.enabled=1)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p105">Polycom firmware prior to 5.5.1.X had a manufacturer specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock". Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock", which can leave the phone unsecured. For users who have activated "Device-Lock", you need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="b24d5-p106">固件更新由 Skype for Business 服务管理。每个通过 Skype for Business 认证的电话固件都上传到 Skype for Business 更新服务器，并且默认情况下在所有电话上启用设备更新。根据电话的非活动时间和轮训间隔，电话将自动下载并安装最新认证的内部版本。你可以通过使用 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet 并将 _EnableDeviceUpdate_ 参数设置为 `false` 来禁用设备更新设置。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![部署电话。](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="b24d5-p107">新固件可用且能够进行下载和安装时，电话会通知用户。Polycom 电话会通知用户并让用户选择" **更新** "或" **推迟更新** "。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update**, or **Postpone**.</span></span>
  
![部署电话。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="b24d5-138">对于 Polycom 电话，可以通过选择" **软件更新**"来更新电话上的固件。</span><span class="sxs-lookup"><span data-stu-id="b24d5-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![部署电话。](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="b24d5-p108">还可以选择使用合作伙伴配置系统来管理固件更新。有关包含高级电话自定义的合作伙伴配置系统管理，请参考制造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="b24d5-142">[!警告] 确保拥有单个设备更新授权（带内设备更新或第三方配置服务器），以避免更新循环。</span><span class="sxs-lookup"><span data-stu-id="b24d5-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="b24d5-143">步骤 5 - 配置和基础结构电话设置</span><span class="sxs-lookup"><span data-stu-id="b24d5-143">Step 5 - Configure and infrastructure phone settings</span></span>

<span data-ttu-id="b24d5-p109">你可以使用 Skype for Business 带内管理 Windows PowerShell cmdlet 来设置最常用的电话选项和策略。有关这些参数和设置的详细信息，请参阅 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="b24d5-146">有关网络基础结构规划，请参阅 [Skype Operations Framework](https://www.skypeoperationsframework.com/)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/) andDeploy, Migrate, and Roll Out.</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="b24d5-147">第 6 步 - 为用户登录做准备</span><span class="sxs-lookup"><span data-stu-id="b24d5-147">Step 6 - Preparing for users to sign-in</span></span>

<span data-ttu-id="b24d5-p110">要使用户能够成功登录 Skype for Business Online 电话并进行通话，需要确保为用户分配正确的许可证。至少需要分配 电话系统许可证和通话套餐。有关其他信息，请参阅 [Skype for Business 和 Microsoft Teams 附加许可](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)和[分配 Skype for Business 和 Microsoft Teams 许可证](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p110">To enable users to successfully sign-on to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum you will need to assign a Skype for Business Cloud PBX license and a PSTN Calling plan. For additional information you can see [Skype for Business add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and[Assign Skype for Business licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) .</span></span>
  
<span data-ttu-id="b24d5-151">有关通话套餐的详细信息，请参阅[什么是 Office 365 的通话套餐？](/microsoftteams/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="b24d5-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="b24d5-152">Online 用户可以使用的 **登录选项** 包括：</span><span class="sxs-lookup"><span data-stu-id="b24d5-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="b24d5-153">使用 **Polycom VVX 5XX/6XX** 电话的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="b24d5-153">For those users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![部署电话。](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="b24d5-155">使用 **Yealink T48G/T46G** 电话的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="b24d5-155">For those users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Yealink 电话登录。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="b24d5-157">有关制造商支持的登录选项的详细信息，请参阅[获取适用于 Skype for Business Online 的电话](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-157">For details on sign-in options supported by manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="b24d5-p111">**用户 ID** 通过电话键盘或屏幕键盘（如有），用户可以使用其组织的用户名和密码登录电话。例如，他们应使用类似 *amosm@contoso.com*  的 UPN 格式作为其用户名。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like *amosm@contoso.com*  for their user name.</span></span>
    
     ![部署电话。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="b24d5-161">[!注释] Skype for Business Online 不支持对 LPE 和合作伙伴 IP 电话进行 PIN 身份验证。</span><span class="sxs-lookup"><span data-stu-id="b24d5-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="b24d5-p112">**使用 PC** 如果用户 PC 上安装并启用了 Better Together over Ethernet (BToE) 软件，用户可以使用其 Windows Skype for Business 应用上的身份验证窗口登录其电话。有关其他信息，请参阅[第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log into their phone using the authentication window on their Windows Skype for Business App. See[Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="b24d5-p113">[!注释] 用户需要使用其组织的用户名和密码登录电话。例如，他们应使用类似  *amosm@contoso.com*  的 UPN 格式作为其用户名。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  *amosm@contoso.com*  for their user name.</span></span>
  
     ![部署电话。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="b24d5-p114">**使用 Web 登录**：这是 Online 用户使用标准 Web 浏览器进行身份验证的新方式。当用户使用浏览器登录时，会收到一套需要遵循的说明。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p114">**Using a** Web Sign-in: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign-in.</span></span>
    
  - <span data-ttu-id="b24d5-169">使用 **Polycom VVX 5XX/6XX** 电话的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="b24d5-169">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![部署电话。](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="b24d5-171">使用 **Yealink T48G/T46G** 电话的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="b24d5-171">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Yealink 电话登录。](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="b24d5-p115">生成的代码将于 15 分钟后过期。代码过期后，用户必须单击" **重试**"或" **确定**"，以便根据电话生成新代码。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code depending on the phone.</span></span>
    
  - <span data-ttu-id="b24d5-175">使用 **Polycom VVX 5XX/6XX** 电话的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="b24d5-175">For users with **Polycom VVX 5XX/6XX** phones, they will see:</span></span>
    
     ![PIN 代码已过期。](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="b24d5-177">使用 **Yealink T48G/T46G** 电话的用户将看到：</span><span class="sxs-lookup"><span data-stu-id="b24d5-177">For users with **Yealink T48G/T46G** phones, they will see:</span></span>
    
     ![Yealink 电话登录。](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="b24d5-179">使用浏览器，导航到电话上显示的地址，输入 Skype for Business 用户名。</span><span class="sxs-lookup"><span data-stu-id="b24d5-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![部署电话。](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="b24d5-181">输入电话上显示的代码。</span><span class="sxs-lookup"><span data-stu-id="b24d5-181">Enter the code shown on the phone.</span></span>
    
     ![部署电话。](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="b24d5-183">使用 ble="false" class="locked monad startTag">**Yealink T48G/T46G**  电话的用户将看到：\*\* \*\*</span><span class="sxs-lookup"><span data-stu-id="b24d5-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**", and click **Continue**.</span></span>
    
     ![部署电话。](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="b24d5-185">单击用户的凭据或单击" **使用其他帐户**"：</span><span class="sxs-lookup"><span data-stu-id="b24d5-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![部署电话。](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="b24d5-187">部署电话。</span><span class="sxs-lookup"><span data-stu-id="b24d5-187">Once below page is displayed, it is safe to close the browser.</span></span>
    
     ![部署电话。](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="b24d5-189">[!注释] 适用于 Skype for Business Online 的 LPE 电话仅支持通过 USB 数据连线登录。</span><span class="sxs-lookup"><span data-stu-id="b24d5-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="b24d5-190">**支持的部署** 下表显示了当前支持的部署模式所支持的身份验证类型，包括 Exchange 集成、使用多因素身份验证 (MFA) 的新式验证以及 Skype for Business Online 和本地部署。</span><span class="sxs-lookup"><span data-stu-id="b24d5-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="b24d5-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="b24d5-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="b24d5-192">**Exchange**</span><span class="sxs-lookup"><span data-stu-id="b24d5-192">**Exchange**</span></span> <br/> |<span data-ttu-id="b24d5-193">**电话登录方法**</span><span class="sxs-lookup"><span data-stu-id="b24d5-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="b24d5-194">**Skype For Business 访问**</span><span class="sxs-lookup"><span data-stu-id="b24d5-194">**Skype For Business Access**</span></span> <br/> |<span data-ttu-id="b24d5-195">**禁用新式验证和 MFA 的 Exchange 访问**</span><span class="sxs-lookup"><span data-stu-id="b24d5-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="b24d5-196">**启用新式验证和 MFA 的 Exchange 访问**</span><span class="sxs-lookup"><span data-stu-id="b24d5-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="b24d5-197">Online</span><span class="sxs-lookup"><span data-stu-id="b24d5-197">Online</span></span>  <br/> |<span data-ttu-id="b24d5-198">Online</span><span class="sxs-lookup"><span data-stu-id="b24d5-198">Online</span></span>  <br/> |<span data-ttu-id="b24d5-199">Web 登录</span><span class="sxs-lookup"><span data-stu-id="b24d5-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="b24d5-200">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-200">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-201">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-201">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-202">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-202">Yes</span></span>  <br/> |
|<span data-ttu-id="b24d5-203">Online</span><span class="sxs-lookup"><span data-stu-id="b24d5-203">Online</span></span>  <br/> |<span data-ttu-id="b24d5-204">Online</span><span class="sxs-lookup"><span data-stu-id="b24d5-204">Online</span></span>  <br/> |<span data-ttu-id="b24d5-205">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="b24d5-205">Username/Password</span></span>  <br/> |<span data-ttu-id="b24d5-206">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-206">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-207">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-207">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-208">否</span><span class="sxs-lookup"><span data-stu-id="b24d5-208">No</span></span>  <br/> |
|<span data-ttu-id="b24d5-209">Online</span><span class="sxs-lookup"><span data-stu-id="b24d5-209">Online</span></span>  <br/> |<span data-ttu-id="b24d5-210">本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-210">On-premises</span></span>  <br/> |<span data-ttu-id="b24d5-211">Web 登录</span><span class="sxs-lookup"><span data-stu-id="b24d5-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="b24d5-212">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-212">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-213">否</span><span class="sxs-lookup"><span data-stu-id="b24d5-213">No</span></span>  <br/> |<span data-ttu-id="b24d5-214">否</span><span class="sxs-lookup"><span data-stu-id="b24d5-214">No</span></span>  <br/> |
|<span data-ttu-id="b24d5-215">Online</span><span class="sxs-lookup"><span data-stu-id="b24d5-215">Online</span></span>  <br/> |<span data-ttu-id="b24d5-216">本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-216">On-Premises</span></span>  <br/> |<span data-ttu-id="b24d5-217">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="b24d5-217">Username/Password</span></span>  <br/> |<span data-ttu-id="b24d5-218">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-218">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-219">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-219">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-220">否</span><span class="sxs-lookup"><span data-stu-id="b24d5-220">No</span></span>  <br/> |
|<span data-ttu-id="b24d5-221">本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-221">On-premises</span></span>  <br/> |<span data-ttu-id="b24d5-222">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="b24d5-223">PIN 身份验证</span><span class="sxs-lookup"><span data-stu-id="b24d5-223">Pin Authentication</span></span>  <br/> |<span data-ttu-id="b24d5-224">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-224">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-225">否</span><span class="sxs-lookup"><span data-stu-id="b24d5-225">No</span></span>  <br/> |<span data-ttu-id="b24d5-226">否</span><span class="sxs-lookup"><span data-stu-id="b24d5-226">No</span></span>  <br/> |
|<span data-ttu-id="b24d5-227">本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-227">On-premises</span></span>  <br/> |<span data-ttu-id="b24d5-228">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="b24d5-229">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="b24d5-229">Username/Password</span></span>  <br/> |<span data-ttu-id="b24d5-230">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-230">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-231">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-231">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-232">不适用</span><span class="sxs-lookup"><span data-stu-id="b24d5-232">N/A</span></span>  <br/> |
|<span data-ttu-id="b24d5-233">本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-233">On-premises</span></span>  <br/> |<span data-ttu-id="b24d5-234">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="b24d5-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="b24d5-235">通过 PC 登录 (BTOE)</span><span class="sxs-lookup"><span data-stu-id="b24d5-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="b24d5-236">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-236">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-237">是</span><span class="sxs-lookup"><span data-stu-id="b24d5-237">Yes</span></span>  <br/> |<span data-ttu-id="b24d5-238">不适用</span><span class="sxs-lookup"><span data-stu-id="b24d5-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="b24d5-p116">**电话功能** 功能集可能有所变化稍微基于 IP 电话合作伙伴。完整功能设置并为每个电话制造商的功能的详细信息，请参阅[获取  Skype for Business Online 电话](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p116">**Phone features** The feature-set may slightly vary based on the IP phone partner. For complete feature set, see[Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md) for more information on the features for each phone manufacturer.</span></span>
    
- <span data-ttu-id="b24d5-p117">**电话锁** 是 Skype for Business 认证电话新引入的功能，用于确保电话的安全。启用后，用户在成功登录时会被要求创建一个 PIN。创建后，如果超过定义的空闲超时时间，电话将锁定。用户可以手动锁定其电话，或使用电话配对使其电话锁与其 PC 锁同步。如果多次输错电话锁 PIN，电话会将此用户注销或要求输入管理员的代码才能解锁电话，但不同电话合作伙伴在这方面的要求有所差异。用户的 PIN 应为 6-15 位数字。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successfully authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require a administrator's code to unlock the phone, but this will vary from depending on the phone Partner. The user's PIN should be between 6-15 digits.</span></span>
    
    <span data-ttu-id="b24d5-p118">可以为组织禁用电话锁（默认情况下处于启用状态）、更改空闲超时时间并选择用户在处于锁定状态或不使用带内设置时是否可以进行电话通话。有关这些设置的详细信息，请参阅 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p118">You can disable Phone-Lock for your organization that is enabled by default, change the idle-timeout and choose if users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="b24d5-248">第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="b24d5-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="b24d5-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="b24d5-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="b24d5-p119">BToE 是适用于合作伙伴 IP 电话的电话配对机制，用于将用户的电话与其 Windows Skype for Business 应用进行配对。利用 BToE，用户可以：</span><span class="sxs-lookup"><span data-stu-id="b24d5-p119">BToE is a phone paining mechanism for Partner IP phones that pairs user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="b24d5-252">使用其 Skype for Business 桌面应用（使用 PC）登录其 IP 电话</span><span class="sxs-lookup"><span data-stu-id="b24d5-252">Sign-into their IP phone using their Skype for Business desktop app (using a PC).</span></span>
    
- <span data-ttu-id="b24d5-253">使电话锁与 PC 锁同步</span><span class="sxs-lookup"><span data-stu-id="b24d5-253">Synchronize phone-lock with PC lock.</span></span>
    
- <span data-ttu-id="b24d5-254">单击进行呼叫</span><span class="sxs-lookup"><span data-stu-id="b24d5-254">Click to call.</span></span>
    
<span data-ttu-id="b24d5-p120">BToE 可以配置为采用两种模式运行： *自动*  （默认）和 *手动*  。也可以为使用 Skype for Business 带内设置的用户启用（默认）/禁用此功能。采用 *手动*  模式运行时，用户还必须执行其他步骤，以便将其电话与其 Windows 应用配对。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p120">BToE can be configured to operate in 2 modes;  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="b24d5-258">**为用户部署 BToE**</span><span class="sxs-lookup"><span data-stu-id="b24d5-258">\*\*\*\* To deploy BToE to users</span></span>
  
1. <span data-ttu-id="b24d5-259">使用 PC 端口将 PC 与电话相连。</span><span class="sxs-lookup"><span data-stu-id="b24d5-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![部署电话。](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="b24d5-p121">从制造商网站（链接如下所示）下载并安装最新的 BToE 软件。要获取更好的用户体验，可以使用 System Center Configuration Manager (SCCM) 等管理员分发解决方案来分发并安装 BToE 软件。有关使用 SCCM 的帮助，请参阅[ System Center Configuration Manager 中的软件包和程序](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="b24d5-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
  - [<span data-ttu-id="b24d5-264">Polycom BToE 软件下载网站</span><span class="sxs-lookup"><span data-stu-id="b24d5-264">Polycom BToE Software Download site:</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
  - [<span data-ttu-id="b24d5-265">Yealink BToE 软件下载</span><span class="sxs-lookup"><span data-stu-id="b24d5-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
  - [<span data-ttu-id="b24d5-266">AudioCodes BToE 软件下载</span><span class="sxs-lookup"><span data-stu-id="b24d5-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="b24d5-267">默认情况下，BToE 的服务器设置设为**已启用**和**自动模式** 。</span><span class="sxs-lookup"><span data-stu-id="b24d5-267">The server setting for BToE is set to Enabled and Auto mode by default, to change those settings, seeSet-CsIPPhonePolicy.</span></span> <span data-ttu-id="b24d5-268">若要更改这些设置，请参阅[设置 CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="b24d5-268">To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="b24d5-269">Mac 和 VDI 平台目前不支持 BToE。</span><span class="sxs-lookup"><span data-stu-id="b24d5-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="b24d5-270">相关主题</span><span class="sxs-lookup"><span data-stu-id="b24d5-270">Related topics</span></span>
[<span data-ttu-id="b24d5-271">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="b24d5-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="b24d5-272">Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="b24d5-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="b24d5-273">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="b24d5-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
