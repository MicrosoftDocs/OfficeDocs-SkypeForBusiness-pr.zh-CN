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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 了解获取正确的固件、 如果需要对其进行更新、 分配许可证和配置的业务联机电话设置 Skype 的部署步骤
ms.openlocfilehash: 26748f79d62b2f4b40a249dcf1af1736bae2d06f
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25374569"
---
# <a name="deploying-skype-for-business-online-phones"></a><span data-ttu-id="bd639-103">部署 Skype for Business Online 电话</span><span class="sxs-lookup"><span data-stu-id="bd639-103">Deploying Skype for Business Online phones</span></span>

<span data-ttu-id="bd639-104">本部署指南将帮助你部署 Skype for Business Online IP 电话。</span><span class="sxs-lookup"><span data-stu-id="bd639-104">This is deployment guide will help you deploy Skype for Business Online IP phones.</span></span>
  
<span data-ttu-id="bd639-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="bd639-p101">In all types of businesses, having a phone number allows users to make and get voice calls, and it is an important requirement to do business. Users who have phone numbers will be able to make voice calls across all Skype for Business devices including IP phones, PCs, and mobile devices. You can learn more about Skype for Business IP phones by reading [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
## <a name="deployment-steps-for-ip-phones"></a><span data-ttu-id="bd639-108">部署 IP 电话的步骤</span><span class="sxs-lookup"><span data-stu-id="bd639-108">Deployment steps for IP phones</span></span>

### <a name="step-1---download-the-manufacturers-administrator-guides-and-phone-manuals"></a><span data-ttu-id="bd639-109">第 1 步 - 下载制造商的管理员指南和电话手册</span><span class="sxs-lookup"><span data-stu-id="bd639-109">Step 1 - Download the manufacturer's administrator guides and phone manuals</span></span>

<span data-ttu-id="bd639-110">开始之前，最好先下载电话制造商的管理指南和电话用户手册。</span><span class="sxs-lookup"><span data-stu-id="bd639-110">Before you get started, it's a good idea to download the phone manufacturer's administration guides and phone user manuals.</span></span>
  
- <span data-ttu-id="bd639-111">有关 Polycom 电话，请参阅 [Polycom 部署指南] ((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html)。</span><span class="sxs-lookup"><span data-stu-id="bd639-111">For Polycom phones, see the [Polycom Deployment Guide]((http://www.polycom.com/voice-conferencing-solutions/desktop-ip-phones.html).</span></span>
    
- <span data-ttu-id="bd639-112">Yealink 电话，请参阅[Yealink Skype 业务 HD SIP 电话解决方案](http://www.yealink.com/products_top_2.html)。</span><span class="sxs-lookup"><span data-stu-id="bd639-112">For Yealink phones, see [Yealink Skype for Business HD SIP Phones Solution](http://www.yealink.com/products_top_2.html).</span></span>
    
- <span data-ttu-id="bd639-113">对于 AudioCodes 电话，请参阅 [Audiocodes 配置管理指南](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions)。</span><span class="sxs-lookup"><span data-stu-id="bd639-113">For AudioCodes phones, see the [Audiocodes Provisioning Management Guide](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/ip-phones-room-solutions).</span></span>
    
### <a name="step-2---make-sure-youre-purchasing-or-migrating-a-skype-for-business-supported-ip-phone-and-firmware"></a><span data-ttu-id="bd639-114">第 2 步 - 确保购买或迁移支持 Skype for Business 的 IP 电话和固件</span><span class="sxs-lookup"><span data-stu-id="bd639-114">Step 2 - Make sure you're purchasing or migrating a Skype for Business Supported IP phone and firmware</span></span>

<span data-ttu-id="bd639-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="bd639-p102">A Skype for Business Online supported phone and firmware is compatible for Skype for Business Server as well, but the opposite isn't always true. To make sure you are buying or provisioning a supported phone and firmware, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
  
### <a name="step-3---checking-that-the-right-firmware-is-installed-and-update-the-firmware-if-required"></a><span data-ttu-id="bd639-117">第 3 步 - 检查是否安装了正确的固件并根据需要更新固件。</span><span class="sxs-lookup"><span data-stu-id="bd639-117">Step 3 - Checking that the right firmware is installed and update the firmware if required</span></span>

<span data-ttu-id="bd639-p103">Check the firmware version on your phones. For:</span><span class="sxs-lookup"><span data-stu-id="bd639-p103">Check the firmware version on your phones. For:</span></span>
  
- <span data-ttu-id="bd639-120">**Polycom VVX 电话**，请转到**设置** > **状态** > **平台** > **应用程序** > **主要**。</span><span class="sxs-lookup"><span data-stu-id="bd639-120">**Polycom VVX phones**, go to **Settings** > **Status** > **Platform** > **Application** > **Main**.</span></span>
    
- <span data-ttu-id="bd639-121">**Yealink 电话** ，请转到电话主屏幕上的" **状态** "。</span><span class="sxs-lookup"><span data-stu-id="bd639-121">**Yealink phones**, go to **Status** on the main phone screen.</span></span>
    
- <span data-ttu-id="bd639-122">**AudioCodes 电话**，请转到开始菜单的**菜单** > **设备状态** > **固件版本**。</span><span class="sxs-lookup"><span data-stu-id="bd639-122">**AudioCodes phones**, go to **Menu** > **Device Status** > **Firmware version** from the start screen.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd639-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span><span class="sxs-lookup"><span data-stu-id="bd639-p104">For remote access to phone details, refer to manufacturer administration guides. See the links above for the user guides and phone manuals.</span></span> 
  
- <span data-ttu-id="bd639-125">**Lync Phone Edition (LPE) 电话**，请转到开始屏幕的**菜单** > **系统信息**。</span><span class="sxs-lookup"><span data-stu-id="bd639-125">**Lync Phone Edition (LPE) phones**, go to **Menu** > **System Information** from the start screen.</span></span>
    
### <a name="step-4---device-update-considerations"></a><span data-ttu-id="bd639-126">第 4 步 - 设备更新注意事项</span><span class="sxs-lookup"><span data-stu-id="bd639-126">Step 4 - Device Update Considerations</span></span>

> [!NOTE]
> <span data-ttu-id="bd639-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span><span class="sxs-lookup"><span data-stu-id="bd639-p105">Polycom firmware prior to 5.5.1.X had a manufacturer-specific device-lock mechanism that is replaced with a Skype for Business implementation "Phone-Lock." Upgrading a phone from 5.4.X.X that was secured with "Device-Lock" to 5.5.1.X with "Phone-Lock" won't inherit the PIN code from "Device-Lock," which can leave the phone unsecured. Users who have activated "Device-Lock" need to enable the following Polycom Device Profile parameter to give users control of time of upgrade (lync.deviceUpdate.popUpSK.enabled=1).</span></span> 
  
<span data-ttu-id="bd639-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span><span class="sxs-lookup"><span data-stu-id="bd639-p106">Firmware updates are managed by the Skype for Business Service. Every Skype for Business certified phone's firmware is uploaded to the Skype for Business Update server, and device update is enabled on all phones by default. Depending on the inactivity time on the phone and polling intervals, phones will automatically download and install the latest certified builds. You can disable the device update settings by using the [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) cmdlet and setting the _EnableDeviceUpdate_ parameter to `false`.</span></span>
  
![部署电话。](../../images/be727622-1924-439f-96ca-89230739db9e.png)
  
<span data-ttu-id="bd639-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span><span class="sxs-lookup"><span data-stu-id="bd639-p107">When a new firmware is available and ready for download and install, the phone will notify the user. Polycom phones will notify the user and provide them with an option to **Update** or **Postpone**.</span></span>
  
![部署电话。](../../images/50956fa0-da0c-4085-9bb5-4a2e99aecebb.png)
  
<span data-ttu-id="bd639-138">对于 Polycom 电话，可以通过选择" **软件更新**"来更新电话上的固件。</span><span class="sxs-lookup"><span data-stu-id="bd639-138">For a Polycom phone, you can update the firmware on the phone by selecting **SwUpdate**.</span></span>
  
![部署电话。](../../images/376c1998-6ce6-44b6-a84d-ae7d96b1c307.png)
  
<span data-ttu-id="bd639-p108">还可以选择使用合作伙伴配置系统来管理固件更新。有关包含高级电话自定义的合作伙伴配置系统管理，请参考制造商管理指南。</span><span class="sxs-lookup"><span data-stu-id="bd639-p108">You can also choose to manage firmware updates using a partner provisioning system. For partner provisioning system management including advanced phone customization, refer to manufacturer administration guides.</span></span>
  
> [!CAUTION]
> <span data-ttu-id="bd639-142">[!警告] 确保拥有单个设备更新授权（带内设备更新或第三方配置服务器），以避免更新循环。</span><span class="sxs-lookup"><span data-stu-id="bd639-142">Make sure to have a single device update authority (In-band device update or a third-party provisioning server) to avoid update loops.</span></span> 
  
### <a name="step-5---configuration-and-infrastructure-phone-settings"></a><span data-ttu-id="bd639-143">步骤 5-配置和基础结构电话设置</span><span class="sxs-lookup"><span data-stu-id="bd639-143">Step 5 - Configuration and infrastructure phone settings</span></span>

<span data-ttu-id="bd639-p109">你可以使用 Skype for Business 带内管理 Windows PowerShell cmdlet 来设置最常用的电话选项和策略。有关这些参数和设置的详细信息，请参阅 [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx)。</span><span class="sxs-lookup"><span data-stu-id="bd639-p109">You can set up the most commonly used phone options and policies using Skype for Business In-band management Windows PowerShell cmdlets. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for details of those parameters and settings.</span></span>
  
<span data-ttu-id="bd639-146">有关网络基础结构规划，请参阅[Skype Operations Framework](https://www.skypeoperationsframework.com/)。</span><span class="sxs-lookup"><span data-stu-id="bd639-146">For network infrastructure planning, see [Skype Operations Framework](https://www.skypeoperationsframework.com/).</span></span>
  
### <a name="step-6---preparing-for-users-to-sign-in"></a><span data-ttu-id="bd639-147">步骤 6-准备用户登录</span><span class="sxs-lookup"><span data-stu-id="bd639-147">Step 6 - Preparing for users to sign in</span></span>

<span data-ttu-id="bd639-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="bd639-p110">To enable users to successfully sign in to a Skype for Business Online phone and make calls, you need to make sure users are assigned the correct licenses. At a minimum, you will need to assign a Phone System license and a Calling Plan. For additional information, you can see [Skype for Business and Microsoft Teams add-on licensing](../../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md) and [Assign Skype for Business and Microsoft Teams licenses](../../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>
  
<span data-ttu-id="bd639-151">有关通话套餐的详细信息，请参阅[什么是 Office 365 的通话套餐？](/microsoftteams/what-are-calling-plans-in-office-365)</span><span class="sxs-lookup"><span data-stu-id="bd639-151">You can find out more about Calling Plans by reading [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365)</span></span>
  
- <span data-ttu-id="bd639-152">Online 用户可以使用的 **登录选项** 包括：</span><span class="sxs-lookup"><span data-stu-id="bd639-152">**Sign-in options** that are available for Online users are:</span></span>
    
  - <span data-ttu-id="bd639-153">与**Polycom VVX 5XX/6XX**电话的用户会看到：</span><span class="sxs-lookup"><span data-stu-id="bd639-153">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![部署电话。](../../images/8a1ffb33-8a63-4242-bb76-d5fafb6a6472.png)
  
  - <span data-ttu-id="bd639-155">与**Yealink T48G/T46G**电话的用户会看到：</span><span class="sxs-lookup"><span data-stu-id="bd639-155">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 电话登录。](../../images/2a2892ae-850d-4781-8be0-4ffb8af068c9.png)
  
    <span data-ttu-id="bd639-157">有关支持的制造商的登录选项的详细信息，请参阅[业务 online Skype 的入门电话](getting-phones-for-skype-for-business-online.md)。</span><span class="sxs-lookup"><span data-stu-id="bd639-157">For details on sign-in options supported by the manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="bd639-p111">**用户 ID** 通过电话键盘或屏幕键盘（如有），用户可以使用其组织的用户名和密码登录电话。例如，他们应使用类似 <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。</span><span class="sxs-lookup"><span data-stu-id="bd639-p111">**User ID** Using the phone's keypad or on-screen keyboard (if available), users can use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like <em>amosm@contoso.com</em>  for their user name.</span></span>
    
     ![部署电话。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
    > [!NOTE]
    > <span data-ttu-id="bd639-161">[!注释] Skype for Business Online 不支持对 LPE 和合作伙伴 IP 电话进行 PIN 身份验证。</span><span class="sxs-lookup"><span data-stu-id="bd639-161">PIN authentication isn't supported for Skype for Business Online for LPE and Partner IP phones.</span></span> 
  
- <span data-ttu-id="bd639-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span><span class="sxs-lookup"><span data-stu-id="bd639-p112">**Using a PC** When Better Together over Ethernet (BToE) software is installed on user's PC and enabled, users can log in to their phones using the authentication window on their Windows Skype for Business App. See [Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)](deploying-skype-for-business-online-phones.md#BK_BTOE) for other information.</span></span>
    
  > [!NOTE]
  > <span data-ttu-id="bd639-p113">[!注释] 用户需要使用其组织的用户名和密码登录电话。例如，他们应使用类似  <em>amosm@contoso.com</em>  的 UPN 格式作为其用户名。</span><span class="sxs-lookup"><span data-stu-id="bd639-p113">Users are required to use their organization's user name and password to sign in to the phone. For example, they should use the UPN format like  <em>amosm@contoso.com</em>  for their user name.</span></span>
  
     ![部署电话。](../../images/f67fa8f4-66a5-451d-bdf2-a12daac15cb5.png)
  
- <span data-ttu-id="bd639-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span><span class="sxs-lookup"><span data-stu-id="bd639-p114">**Using a Web Sign-in**: This is a new way for Online users to authenticate using a standard web browser. Users will be provided with a set of instructions to follow when they use a browser to sign in.</span></span>
    
  - <span data-ttu-id="bd639-169">与**Polycom VVX 5XX/6XX**电话的用户会看到：</span><span class="sxs-lookup"><span data-stu-id="bd639-169">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![部署电话。](../../images/ba0df923-a6e5-4a9b-b40b-b03ca188e814.png)
  
  - <span data-ttu-id="bd639-171">与**Yealink T48G/T46G**电话的用户会看到：</span><span class="sxs-lookup"><span data-stu-id="bd639-171">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 电话登录。](../../images/86551cc3-533a-4694-9683-bad907c9ad5a.png)
  
    <span data-ttu-id="bd639-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span><span class="sxs-lookup"><span data-stu-id="bd639-p115">The code that is generated will expire in 15 minutes. When it expires, the user will have to click **Retry** or **OK** to generate a new code, depending on the phone.</span></span>
    
  - <span data-ttu-id="bd639-175">与**Polycom VVX 5XX/6XX**电话的用户会看到：</span><span class="sxs-lookup"><span data-stu-id="bd639-175">Users with **Polycom VVX 5XX/6XX** phones will see:</span></span>
    
     ![PIN 代码已过期。](../../images/b5d27037-aa26-4054-be95-d5a6c293d08c.png)
  
  - <span data-ttu-id="bd639-177">与**Yealink T48G/T46G**电话的用户会看到：</span><span class="sxs-lookup"><span data-stu-id="bd639-177">Users with **Yealink T48G/T46G** phones will see:</span></span>
    
     ![Yealink 电话登录。](../../images/3a4462ac-0c59-409e-a3bb-1451cdcc8676.png)
  
    <span data-ttu-id="bd639-179">使用浏览器，导航到电话上显示的地址，输入 Skype for Business 用户名。</span><span class="sxs-lookup"><span data-stu-id="bd639-179">Using a browser, navigate to the address displayed on the phone and enter your Skype for Business username.</span></span>
    
     ![部署电话。](../../images/7c540b85-dc37-4ce7-a077-9e3454a0efd0.png)
  
    <span data-ttu-id="bd639-181">输入电话上显示的代码。</span><span class="sxs-lookup"><span data-stu-id="bd639-181">Enter the code shown on the phone.</span></span>
    
     ![部署电话。](../../images/d6b88016-35d2-41d1-a0da-81fef34521d4.png)
  
    <span data-ttu-id="bd639-183">验证网站是否显示"[电话制造商名称] **Skype 业务 Certified 电话**，"并单击**继续**。</span><span class="sxs-lookup"><span data-stu-id="bd639-183">Verify that the site shows "[Phone Manufacturer name] **Skype for Business Certified Phone**," and click **Continue**.</span></span>
    
     ![部署电话。](../../images/a8252b37-4ff5-4ece-9e2a-3e05bf928299.png)
  
    <span data-ttu-id="bd639-185">单击用户的凭据或单击" **使用其他帐户**"：</span><span class="sxs-lookup"><span data-stu-id="bd639-185">Click the user's credentials or click **Use another account**:</span></span>
    
     ![部署电话。](../../images/8415028b-7924-4747-b639-052d9b0b961e.png)
  
    <span data-ttu-id="bd639-187">将显示以下页，时，安全地关闭浏览器。</span><span class="sxs-lookup"><span data-stu-id="bd639-187">When the following page is displayed, it is safe to close the browser.</span></span>
    
     ![部署电话。](../../images/1a873201-52fc-4a63-b7b5-e82bbd031fd2.png)
  
    > [!NOTE]
    > <span data-ttu-id="bd639-189">[!注释] 适用于 Skype for Business Online 的 LPE 电话仅支持通过 USB 数据连线登录。</span><span class="sxs-lookup"><span data-stu-id="bd639-189">LPE phones for Skype for Business Online support sign-in through USB tethering only.</span></span> 
  
- <span data-ttu-id="bd639-190">**支持的部署** 下表显示了当前支持的部署模式所支持的身份验证类型，包括 Exchange 集成、使用多因素身份验证 (MFA) 的新式验证以及 Skype for Business Online 和本地部署。</span><span class="sxs-lookup"><span data-stu-id="bd639-190">**Supported deployments** The table below shows the supported authentication types for the currently supported deployment models including Exchange Integration, Modern authentication with Multi-factor Authentication (MFA), and Skype for Business Online and on-premises.</span></span>
    
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bd639-191">**Skype for Business**</span><span class="sxs-lookup"><span data-stu-id="bd639-191">**Skype for Business**</span></span> <br/> |<span data-ttu-id="bd639-192">**交换**</span><span class="sxs-lookup"><span data-stu-id="bd639-192">**Exchange**</span></span> <br/> |<span data-ttu-id="bd639-193">**电话登录方法**</span><span class="sxs-lookup"><span data-stu-id="bd639-193">**Phone Sign-In method**</span></span> <br/> |<span data-ttu-id="bd639-194">**Skype 商业访问**</span><span class="sxs-lookup"><span data-stu-id="bd639-194">**Skype for Business access**</span></span> <br/> |<span data-ttu-id="bd639-195">**禁用新式验证和 MFA 的 Exchange 访问**</span><span class="sxs-lookup"><span data-stu-id="bd639-195">**Exchange Access with Modern Auth and MFA disabled**</span></span> <br/> |<span data-ttu-id="bd639-196">**启用新式验证和 MFA 的 Exchange 访问**</span><span class="sxs-lookup"><span data-stu-id="bd639-196">**Exchange Access with Modern Auth and MFA enabled**</span></span> <br/> |
|<span data-ttu-id="bd639-197">Online</span><span class="sxs-lookup"><span data-stu-id="bd639-197">Online</span></span>  <br/> |<span data-ttu-id="bd639-198">Online</span><span class="sxs-lookup"><span data-stu-id="bd639-198">Online</span></span>  <br/> |<span data-ttu-id="bd639-199">Web 登录</span><span class="sxs-lookup"><span data-stu-id="bd639-199">Web Sign-in</span></span>  <br/> |<span data-ttu-id="bd639-200">是</span><span class="sxs-lookup"><span data-stu-id="bd639-200">Yes</span></span>  <br/> |<span data-ttu-id="bd639-201">是</span><span class="sxs-lookup"><span data-stu-id="bd639-201">Yes</span></span>  <br/> |<span data-ttu-id="bd639-202">是</span><span class="sxs-lookup"><span data-stu-id="bd639-202">Yes</span></span>  <br/> |
|<span data-ttu-id="bd639-203">Online</span><span class="sxs-lookup"><span data-stu-id="bd639-203">Online</span></span>  <br/> |<span data-ttu-id="bd639-204">Online</span><span class="sxs-lookup"><span data-stu-id="bd639-204">Online</span></span>  <br/> |<span data-ttu-id="bd639-205">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="bd639-205">Username/Password</span></span>  <br/> |<span data-ttu-id="bd639-206">是</span><span class="sxs-lookup"><span data-stu-id="bd639-206">Yes</span></span>  <br/> |<span data-ttu-id="bd639-207">是</span><span class="sxs-lookup"><span data-stu-id="bd639-207">Yes</span></span>  <br/> |<span data-ttu-id="bd639-208">否</span><span class="sxs-lookup"><span data-stu-id="bd639-208">No</span></span>  <br/> |
|<span data-ttu-id="bd639-209">Online</span><span class="sxs-lookup"><span data-stu-id="bd639-209">Online</span></span>  <br/> |<span data-ttu-id="bd639-210">本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-210">On-premises</span></span>  <br/> |<span data-ttu-id="bd639-211">Web 登录</span><span class="sxs-lookup"><span data-stu-id="bd639-211">Web Sign-in</span></span>  <br/> |<span data-ttu-id="bd639-212">是</span><span class="sxs-lookup"><span data-stu-id="bd639-212">Yes</span></span>  <br/> |<span data-ttu-id="bd639-213">否</span><span class="sxs-lookup"><span data-stu-id="bd639-213">No</span></span>  <br/> |<span data-ttu-id="bd639-214">否</span><span class="sxs-lookup"><span data-stu-id="bd639-214">No</span></span>  <br/> |
|<span data-ttu-id="bd639-215">Online</span><span class="sxs-lookup"><span data-stu-id="bd639-215">Online</span></span>  <br/> |<span data-ttu-id="bd639-216">本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-216">On-Premises</span></span>  <br/> |<span data-ttu-id="bd639-217">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="bd639-217">Username/Password</span></span>  <br/> |<span data-ttu-id="bd639-218">是</span><span class="sxs-lookup"><span data-stu-id="bd639-218">Yes</span></span>  <br/> |<span data-ttu-id="bd639-219">是</span><span class="sxs-lookup"><span data-stu-id="bd639-219">Yes</span></span>  <br/> |<span data-ttu-id="bd639-220">否</span><span class="sxs-lookup"><span data-stu-id="bd639-220">No</span></span>  <br/> |
|<span data-ttu-id="bd639-221">本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-221">On-premises</span></span>  <br/> |<span data-ttu-id="bd639-222">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-222">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="bd639-223">PIN 身份验证</span><span class="sxs-lookup"><span data-stu-id="bd639-223">PIN Authentication</span></span>  <br/> |<span data-ttu-id="bd639-224">是</span><span class="sxs-lookup"><span data-stu-id="bd639-224">Yes</span></span>  <br/> |<span data-ttu-id="bd639-225">否</span><span class="sxs-lookup"><span data-stu-id="bd639-225">No</span></span>  <br/> |<span data-ttu-id="bd639-226">否</span><span class="sxs-lookup"><span data-stu-id="bd639-226">No</span></span>  <br/> |
|<span data-ttu-id="bd639-227">本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-227">On-premises</span></span>  <br/> |<span data-ttu-id="bd639-228">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-228">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="bd639-229">用户名/密码</span><span class="sxs-lookup"><span data-stu-id="bd639-229">Username/Password</span></span>  <br/> |<span data-ttu-id="bd639-230">是</span><span class="sxs-lookup"><span data-stu-id="bd639-230">Yes</span></span>  <br/> |<span data-ttu-id="bd639-231">是</span><span class="sxs-lookup"><span data-stu-id="bd639-231">Yes</span></span>  <br/> |<span data-ttu-id="bd639-232">不适用</span><span class="sxs-lookup"><span data-stu-id="bd639-232">N/A</span></span>  <br/> |
|<span data-ttu-id="bd639-233">本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-233">On-premises</span></span>  <br/> |<span data-ttu-id="bd639-234">Online/本地部署</span><span class="sxs-lookup"><span data-stu-id="bd639-234">Online/On-Premises</span></span>  <br/> |<span data-ttu-id="bd639-235">通过 PC 登录 (BTOE)</span><span class="sxs-lookup"><span data-stu-id="bd639-235">Sign-in via PC (BTOE)</span></span>  <br/> |<span data-ttu-id="bd639-236">是</span><span class="sxs-lookup"><span data-stu-id="bd639-236">Yes</span></span>  <br/> |<span data-ttu-id="bd639-237">是</span><span class="sxs-lookup"><span data-stu-id="bd639-237">Yes</span></span>  <br/> |<span data-ttu-id="bd639-238">不适用</span><span class="sxs-lookup"><span data-stu-id="bd639-238">N/A</span></span>  <br/> |
   
- <span data-ttu-id="bd639-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="bd639-p116">**Phone features** The feature set may vary slightly based on the IP phone partner. For the complete feature set and for more information on the features for each phone manufacturer, see [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online.md).</span></span>
    
- <span data-ttu-id="bd639-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span><span class="sxs-lookup"><span data-stu-id="bd639-p117">**Phone-Lock** is a recently introduced feature in Skype for Business certified phones that is used to secure a phone. If enabled, users will be asked to create a PIN upon successful authentication. Once created, phones will lock when the idle-timeout that you define expires, a user manually locks their phone, or they sync their phone-lock with their PC lock using Phone Pairing. If the phone-lock PIN is entered wrong several times, the phone will either sign the user out or require an administrator's code to unlock the phone, but this will vary depending on the phone partner. The user's PIN should be between 6 and 15 digits.</span></span>
    
    <span data-ttu-id="bd639-p118">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span><span class="sxs-lookup"><span data-stu-id="bd639-p118">You can disable Phone-Lock for your organization (which is enabled by default), change the idle-timeout, and choose whether users can make phone calls while they are locked or not using inband-settings. See [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx) for more details on those settings.</span></span>
    
## <a name="step-7-optional---if-you-have-device-pairing-and-better-together-over-ethernet-btoe"></a><span data-ttu-id="bd639-248">第 7 步（可选）- 如果拥有设备配对和 Better Together over Ethernet (BToE)</span><span class="sxs-lookup"><span data-stu-id="bd639-248">Step 7 (optional) - If you have device pairing and Better Together over Ethernet (BToE)</span></span>
<span data-ttu-id="bd639-249"><a name="BK_BTOE"> </a></span><span class="sxs-lookup"><span data-stu-id="bd639-249"><a name="BK_BTOE"> </a></span></span>

<span data-ttu-id="bd639-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span><span class="sxs-lookup"><span data-stu-id="bd639-p119">BToE is a phone paining mechanism for Partner IP phones that pairs a user's phone with their Windows Skype for Business app. BToE enables users to:</span></span>
  
- <span data-ttu-id="bd639-252">登录到其 IP 电话使用其 Skype 业务桌面应用程序 （使用 PC）</span><span class="sxs-lookup"><span data-stu-id="bd639-252">Sign in to their IP phone using their Skype for Business desktop app (using a PC)</span></span>
    
- <span data-ttu-id="bd639-253">与 PC 锁定同步电话锁定</span><span class="sxs-lookup"><span data-stu-id="bd639-253">Synchronize Phone-Lock with PC lock</span></span>
    
- <span data-ttu-id="bd639-254">单击进行呼叫</span><span class="sxs-lookup"><span data-stu-id="bd639-254">Click to call</span></span>
    
<span data-ttu-id="bd639-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span><span class="sxs-lookup"><span data-stu-id="bd639-p120">BToE can be configured to operate in two modes:  *Auto*  (default) and *Manual*  . It can also be enabled (default)/disabled for users using Skype for Business in-band settings. When operating in *Manual*  mode, users will have to take an additional step to pair their phone with their Windows app.</span></span>
  
 <span data-ttu-id="bd639-258">**要向用户部署 BToE**</span><span class="sxs-lookup"><span data-stu-id="bd639-258">**To deploy BToE to users**</span></span>
  
1. <span data-ttu-id="bd639-259">使用 PC 端口将 PC 与电话相连。</span><span class="sxs-lookup"><span data-stu-id="bd639-259">Connect their PC to their phone using the PC port.</span></span>
    
     ![部署电话。](../../images/e21d76c7-867c-4fe6-95c6-fc40c608ed0c.png)
  
2. <span data-ttu-id="bd639-p121">从制造商网站（链接如下所示）下载并安装最新的 BToE 软件。要获取更好的用户体验，可以使用 System Center Configuration Manager (SCCM) 等管理员分发解决方案来分发并安装 BToE 软件。有关使用 SCCM 的帮助，请参阅[ System Center Configuration Manager 中的软件包和程序](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs)。</span><span class="sxs-lookup"><span data-stu-id="bd639-p121">Download and install the latest BToE software from the manufacturer website from the links below. For a better user experience, you can distribute and install the BToE software using an admin distribution solution such as System Center Configuration Manager (SCCM). For help using SCCM, See [Packages and programs in System Center Configuration Manager](https://docs.microsoft.com/en-us/sccm/apps/deploy-use/packages-and-programs).</span></span>
    
   - [<span data-ttu-id="bd639-264">Polycom BToE 软件下载站点</span><span class="sxs-lookup"><span data-stu-id="bd639-264">Polycom BToE Software Download site</span></span>](http://www.polycom.com/voice-conferencing-solutions/microsoft-phones.html)
    
   - [<span data-ttu-id="bd639-265">Yealink BToE 软件下载</span><span class="sxs-lookup"><span data-stu-id="bd639-265">Yealink BToE Software Download</span></span>](http://www.yealink.com/products_list_10.html)
    
   - [<span data-ttu-id="bd639-266">AudioCodes BToE 软件下载</span><span class="sxs-lookup"><span data-stu-id="bd639-266">AudioCodes BToE Software Downloads</span></span>](https://www.audiocodes.com/solutions-products/solutions/skype-for-business-microsoft-teams/skype-for-business-online)
    
3. <span data-ttu-id="bd639-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span><span class="sxs-lookup"><span data-stu-id="bd639-p122">The server setting for BToE is set to **Enabled** and **Auto mode** by default. To change those settings, see [Set-CsIPPhonePolicy](https://technet.microsoft.com/en-us/library/mt629497.aspx).</span></span>
    
> [!NOTE]
> <span data-ttu-id="bd639-269">[!注释] Mac 和 VDI 平台目前不支持 BToE。</span><span class="sxs-lookup"><span data-stu-id="bd639-269">BToE isn't currently supported on Mac and VDI platforms.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="bd639-270">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd639-270">Related topics</span></span>
[<span data-ttu-id="bd639-271">获取 Skype for Business 和 Microsoft Teams 的服务电话号码</span><span class="sxs-lookup"><span data-stu-id="bd639-271">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](../../what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="bd639-272">Office 365 中的电话系统的功能</span><span class="sxs-lookup"><span data-stu-id="bd639-272">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="bd639-273">音频会议和通话套餐的国家/地区可用性</span><span class="sxs-lookup"><span data-stu-id="bd639-273">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
