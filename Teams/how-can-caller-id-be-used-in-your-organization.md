---
title: 如何在你的组织中使用来电显示
author: CarolynRowe
ms.author: crowe
manager: serdars
ms.reviewer: mikedav, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Calling Plans
- ms.teamsadmincenter.voice.callerid.overview
description: 呼叫方 ID 可以通过使用名为 CallingLineIdentity 的策略控制电话系统用户的入站和出站呼叫。
ms.openlocfilehash: 5c20f439d156997c89ca54c2a3bf39e9c3a42ae4
ms.sourcegitcommit: ded1e92348b6c18aa31f7f67e68ced3db525977d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "46506195"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="424f2-103">如何在你的组织中使用来电显示</span><span class="sxs-lookup"><span data-stu-id="424f2-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="424f2-104">呼叫方 ID 可以通过使用名为 CallingLineIdentity 的策略控制电话系统用户的入站和出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="424f2-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="424f2-105">无论 PSTN 连接如何，所有电话系统用户均可使用呼叫方 ID 功能：</span><span class="sxs-lookup"><span data-stu-id="424f2-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>

- <span data-ttu-id="424f2-106">Microsoft 通话计划</span><span class="sxs-lookup"><span data-stu-id="424f2-106">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="424f2-107">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="424f2-107">Phone System Direct Routing</span></span> 
  
- <span data-ttu-id="424f2-108">在线 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="424f2-108">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="424f2-109">使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="424f2-109">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="424f2-110">使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="424f2-110">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="424f2-111">[!注释] 此策略在 Skype for Business 2015 Server 上不可用。</span><span class="sxs-lookup"><span data-stu-id="424f2-111">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="424f2-112">出站来电显示</span><span class="sxs-lookup"><span data-stu-id="424f2-112">Outbound caller ID</span></span>

<span data-ttu-id="424f2-113">出站 PSTN 呼叫方 ID 有三个可用选项：</span><span class="sxs-lookup"><span data-stu-id="424f2-113">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="424f2-114">分配给用户的电话号码（默认值）。</span><span class="sxs-lookup"><span data-stu-id="424f2-114">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="424f2-115">您的通话计划电话号码库存中归类为*服务*和免费号码的*电话号码。*</span><span class="sxs-lookup"><span data-stu-id="424f2-115">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="424f2-116">它通常分配给组织的自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="424f2-116">It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="424f2-117">设置为匿名。</span><span class="sxs-lookup"><span data-stu-id="424f2-117">Set to anonymous.</span></span>
    
<span data-ttu-id="424f2-118">但你不能为出站来电显示分配以下类型的电话号码：</span><span class="sxs-lookup"><span data-stu-id="424f2-118">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="424f2-119">在您的通话计划中分类为*用户*的任何电话号码，电话号码库存</span><span class="sxs-lookup"><span data-stu-id="424f2-119">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="424f2-120">Skype for Business Server 内部部署电话号码</span><span class="sxs-lookup"><span data-stu-id="424f2-120">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="424f2-121">要设置出站来电显示，请参见[为用户设置来电显示](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="424f2-121">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="424f2-122">终端用户对出站呼叫程序 ID 的控制</span><span class="sxs-lookup"><span data-stu-id="424f2-122">End user control of outbound caller ID</span></span>

<span data-ttu-id="424f2-123">EnableUserOverride 属性允许单个或多个用户将其来电显示设置更改为**匿名**。</span><span class="sxs-lookup"><span data-stu-id="424f2-123">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**.</span></span> <span data-ttu-id="424f2-124">仅当 CallingLineIdentity 策略配置了 CallingIDSubstitute 参数 LineURI 或 Substitute 时适用。</span><span class="sxs-lookup"><span data-stu-id="424f2-124">This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute.</span></span> <span data-ttu-id="424f2-125">EnableUserOverride 的默认值是 False。</span><span class="sxs-lookup"><span data-stu-id="424f2-125">The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="424f2-126">最终用户可以使用 Skype for Business 桌面客户端中的 "**设置**" 选项卡将其来电显示设置为**匿名**，选择 "**调用最终用户**（如果由管理员启用）"，然后选择 **"隐藏所有呼叫的电话号码和配置文件信息**"。</span><span class="sxs-lookup"><span data-stu-id="424f2-126">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="424f2-127">在团队中，用户可以在右上角转到其个人资料图片，选择 "**设置**  >  **呼叫**"，然后在 "**来电**显示" 下，选择 "**隐藏所有呼叫的电话号码和配置文件信息**"。</span><span class="sxs-lookup"><span data-stu-id="424f2-127">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="424f2-128">**Windows**</span><span class="sxs-lookup"><span data-stu-id="424f2-128">**Windows**</span></span> <br/> |<span data-ttu-id="424f2-129">**版本**</span><span class="sxs-lookup"><span data-stu-id="424f2-129">**Version**</span></span> <br/> |<span data-ttu-id="424f2-130">**支持**</span><span class="sxs-lookup"><span data-stu-id="424f2-130">**Supported**</span></span> <br/> |
|<span data-ttu-id="424f2-131">即点即用</span><span class="sxs-lookup"><span data-stu-id="424f2-131">Click-to-Run</span></span>  <br/> |<span data-ttu-id="424f2-132">2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）</span><span class="sxs-lookup"><span data-stu-id="424f2-132">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="424f2-133">是</span><span class="sxs-lookup"><span data-stu-id="424f2-133">Yes</span></span>  <br/> |
|<span data-ttu-id="424f2-134">即点即用</span><span class="sxs-lookup"><span data-stu-id="424f2-134">Click-to-Run</span></span>  <br/> |<span data-ttu-id="424f2-135">2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）</span><span class="sxs-lookup"><span data-stu-id="424f2-135">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="424f2-136">是</span><span class="sxs-lookup"><span data-stu-id="424f2-136">Yes</span></span>  <br/> |
|<span data-ttu-id="424f2-137">即点即用</span><span class="sxs-lookup"><span data-stu-id="424f2-137">Click-to-Run</span></span>  <br/> |<span data-ttu-id="424f2-138">延迟通道于 2017 年 6 月 13 日发布 - 版本 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="424f2-138">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="424f2-139">是</span><span class="sxs-lookup"><span data-stu-id="424f2-139">Yes</span></span>  <br/> |
|<span data-ttu-id="424f2-140">MSI</span><span class="sxs-lookup"><span data-stu-id="424f2-140">MSI</span></span>  <br/> |<span data-ttu-id="424f2-141">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="424f2-141">Skype for Business</span></span>  <br/> |<span data-ttu-id="424f2-142">否</span><span class="sxs-lookup"><span data-stu-id="424f2-142">No</span></span>  <br/> |
|<span data-ttu-id="424f2-143">Mac</span><span class="sxs-lookup"><span data-stu-id="424f2-143">Mac</span></span>  <br/> |<span data-ttu-id="424f2-144">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="424f2-144">Skype for Business</span></span>  <br/> |<span data-ttu-id="424f2-145">否</span><span class="sxs-lookup"><span data-stu-id="424f2-145">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="424f2-146">入站呼叫者 ID</span><span class="sxs-lookup"><span data-stu-id="424f2-146">Inbound caller ID</span></span>

<span data-ttu-id="424f2-147">如果数字与 Azure AD 中的用户关联，则电话系统将显示为外部电话号码调用的 ID。</span><span class="sxs-lookup"><span data-stu-id="424f2-147">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="424f2-148">如果电话号码不在 Azure AD 中，则将显示通讯提供的显示名称（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="424f2-148">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="424f2-149">BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。</span><span class="sxs-lookup"><span data-stu-id="424f2-149">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="424f2-150">你可以设置此属性，但你的最终用户无法在 "用户设置" 页面上使用该属性。</span><span class="sxs-lookup"><span data-stu-id="424f2-150">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="424f2-151">当前仅在使用在线 PSTN 连接时可用。</span><span class="sxs-lookup"><span data-stu-id="424f2-151">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="424f2-152">要设置出站来电显示，请参见[为用户设置来电显示](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="424f2-152">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="424f2-153">相关主题</span><span class="sxs-lookup"><span data-stu-id="424f2-153">Related topics</span></span>
[<span data-ttu-id="424f2-154">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="424f2-154">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="424f2-155">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="424f2-155">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="424f2-156">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="424f2-156">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="424f2-157">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="424f2-157">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="424f2-158">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="424f2-158">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
