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
ms.openlocfilehash: 2547e6ca3aed10d112897aa1b24900a479c5c8ef
ms.sourcegitcommit: a7c823f61d9ab88424bad924113d780ce11e509f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2020
ms.locfileid: "44224205"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="ee2a6-103">如何在你的组织中使用来电显示</span><span class="sxs-lookup"><span data-stu-id="ee2a6-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="ee2a6-104">呼叫方 ID 可以通过使用名为 CallingLineIdentity 的策略控制电话系统用户的入站和出站呼叫。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-104">Caller ID can be controlled for both inbound and outbound calls for Phone System users by using a policy called CallingLineIdentity.</span></span>
  
<span data-ttu-id="ee2a6-105">无论 PSTN 连接如何，所有电话系统用户均可使用呼叫方 ID 功能：</span><span class="sxs-lookup"><span data-stu-id="ee2a6-105">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity:</span></span>
  
- <span data-ttu-id="ee2a6-106">在线 PSTN 连接</span><span class="sxs-lookup"><span data-stu-id="ee2a6-106">Online PSTN Connectivity</span></span>
    
- <span data-ttu-id="ee2a6-107">使用 Skype for Business Cloud Connector Edition 的内部部署 PSTN 连接（要求使用 Cloud Connector Edition 1.4.2 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee2a6-107">On-Premises PSTN Connectivity with Skype for Business Cloud Connector Edition (requires Cloud Connector Edition 1.4.2 and beyond)</span></span>
    
- <span data-ttu-id="ee2a6-108">使用 Skype for Business Server 的内部部署 PSTN 连接（要求使用 Skype for Business Server 2015 CU5 及更高版本）</span><span class="sxs-lookup"><span data-stu-id="ee2a6-108">On-Premises PSTN Connectivity with Skype for Business Server (requires Skype for Business Server 2015 CU5 and beyond)</span></span>
    
> [!NOTE]
> <span data-ttu-id="ee2a6-109">[!注释] 此策略在 Skype for Business 2015 Server 上不可用。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-109">This policy isn't available in Skype for Business 2015 Server.</span></span> 
  
## <a name="outbound-caller-id"></a><span data-ttu-id="ee2a6-110">出站来电显示</span><span class="sxs-lookup"><span data-stu-id="ee2a6-110">Outbound caller ID</span></span>

<span data-ttu-id="ee2a6-111">出站 PSTN 呼叫方 ID 有三个可用选项：</span><span class="sxs-lookup"><span data-stu-id="ee2a6-111">There are three options available for outbound PSTN caller ID:</span></span>
  
- <span data-ttu-id="ee2a6-112">分配给用户的电话号码（默认值）。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-112">The telephone number assigned to the user, which is the default.</span></span>
    
- <span data-ttu-id="ee2a6-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span><span class="sxs-lookup"><span data-stu-id="ee2a6-p101">A telephone number that is classified as a *service* and *toll-free* number in your Calling Plans in Office 365 telephone number inventory. It is usually assigned to an organizational auto attendant or call queue.</span></span>
    
- <span data-ttu-id="ee2a6-115">设置为匿名。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-115">Set to anonymous.</span></span>
    
<span data-ttu-id="ee2a6-116">但你不能为出站来电显示分配以下类型的电话号码：</span><span class="sxs-lookup"><span data-stu-id="ee2a6-116">However, you can't assign these types of phone numbers for the outbound caller ID:</span></span>
  
- <span data-ttu-id="ee2a6-117">在您的通话计划中分类为*用户*的任何电话号码，电话号码库存</span><span class="sxs-lookup"><span data-stu-id="ee2a6-117">Any phone numbers that are classified as a  *user*  in your Calling Plans telephone number inventory</span></span>
    
- <span data-ttu-id="ee2a6-118">Skype for Business Server 内部部署电话号码</span><span class="sxs-lookup"><span data-stu-id="ee2a6-118">A Skype for Business Server on-premises phone number</span></span>
    
<span data-ttu-id="ee2a6-119">要设置出站来电显示，请参见[为用户设置来电显示](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-119">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="ee2a6-120">终端用户对出站呼叫程序 ID 的控制</span><span class="sxs-lookup"><span data-stu-id="ee2a6-120">End user control of outbound caller ID</span></span>

<span data-ttu-id="ee2a6-p102">EnableUserOverride 属性允许单个或多个用户将其来电显示设置更改为**匿名**。这仅适用于使用 LineURI 或替代的 CallingIDSubstitute 参数配置了 CallingLineIdentity 策略。EnableUserOverride 的默认值为 False。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-p102">The EnableUserOverride attribute enables single or multiple users to change their caller ID setting to **Anonymous**. This only applies when a CallingLineIdentity policy is configured with a CallingIDSubstitute parameter of either LineURI or Substitute. The default value of EnableUserOverride is False.</span></span>
  
<span data-ttu-id="ee2a6-124">最终用户可以使用 Skype for Business 桌面客户端中的 "**设置**" 选项卡将其来电显示设置为**匿名**，选择 "**调用最终用户**（如果由管理员启用）"，然后选择 **"隐藏所有呼叫的电话号码和配置文件信息**"。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-124">Your end users can set their caller ID to **Anonymous** by using the **Settings** tab in the Skype for Business desktop client, select **Calls an End User** (if enabled by admin), and then select **Hide my phone number and profile information for all calls**.</span></span> <span data-ttu-id="ee2a6-125">在团队中，用户可以在右上角转到其个人资料图片，选择 "**设置**  >  **呼叫**"，然后在 "**来电**显示" 下，选择 "**隐藏所有呼叫的电话号码和配置文件信息**"。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-125">In Teams, users can go to their profile picture in the upper-right corner, select **Settings** > **Calls**,  and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>
  
||||
|:-----|:-----|:-----|
|<span data-ttu-id="ee2a6-126">**Windows**</span><span class="sxs-lookup"><span data-stu-id="ee2a6-126">**Windows**</span></span> <br/> |<span data-ttu-id="ee2a6-127">**版本**</span><span class="sxs-lookup"><span data-stu-id="ee2a6-127">**Version**</span></span> <br/> |<span data-ttu-id="ee2a6-128">**支持**</span><span class="sxs-lookup"><span data-stu-id="ee2a6-128">**Supported**</span></span> <br/> |
|<span data-ttu-id="ee2a6-129">即点即用</span><span class="sxs-lookup"><span data-stu-id="ee2a6-129">Click-to-Run</span></span>  <br/> |<span data-ttu-id="ee2a6-130">2016 年 12 月 6 日发布的当前频道 - 版本 1611（内部版本 7571.2072）</span><span class="sxs-lookup"><span data-stu-id="ee2a6-130">Current Channel released on December 6, 2016 - version 1611 (Build 7571.2072)</span></span>  <br/> |<span data-ttu-id="ee2a6-131">是</span><span class="sxs-lookup"><span data-stu-id="ee2a6-131">Yes</span></span>  <br/> |
|<span data-ttu-id="ee2a6-132">即点即用</span><span class="sxs-lookup"><span data-stu-id="ee2a6-132">Click-to-Run</span></span>  <br/> |<span data-ttu-id="ee2a6-133">2017 年 2 月 22 日发布的延期频道的首次发布 - 版本 1701（内部版本 7766.2060）</span><span class="sxs-lookup"><span data-stu-id="ee2a6-133">First Release for Deferred Channel released on February 22, 2017 - Version 1701 (Build 7766.2060)</span></span>  <br/> |<span data-ttu-id="ee2a6-134">是</span><span class="sxs-lookup"><span data-stu-id="ee2a6-134">Yes</span></span>  <br/> |
|<span data-ttu-id="ee2a6-135">即点即用</span><span class="sxs-lookup"><span data-stu-id="ee2a6-135">Click-to-Run</span></span>  <br/> |<span data-ttu-id="ee2a6-136">延迟通道于 2017 年 6 月 13 日发布 - 版本 1701 (Build 7766.2092)</span><span class="sxs-lookup"><span data-stu-id="ee2a6-136">Deferred Channel released on June 13, 2017 - Version 1701 (Build 7766.2092)</span></span>  <br/> |<span data-ttu-id="ee2a6-137">是</span><span class="sxs-lookup"><span data-stu-id="ee2a6-137">Yes</span></span>  <br/> |
|<span data-ttu-id="ee2a6-138">MSI</span><span class="sxs-lookup"><span data-stu-id="ee2a6-138">MSI</span></span>  <br/> |<span data-ttu-id="ee2a6-139">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ee2a6-139">Skype for Business</span></span>  <br/> |<span data-ttu-id="ee2a6-140">否</span><span class="sxs-lookup"><span data-stu-id="ee2a6-140">No</span></span>  <br/> |
|<span data-ttu-id="ee2a6-141">Mac</span><span class="sxs-lookup"><span data-stu-id="ee2a6-141">Mac</span></span>  <br/> |<span data-ttu-id="ee2a6-142">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="ee2a6-142">Skype for Business</span></span>  <br/> |<span data-ttu-id="ee2a6-143">否</span><span class="sxs-lookup"><span data-stu-id="ee2a6-143">No</span></span>  <br/> |
   
## <a name="inbound-caller-id"></a><span data-ttu-id="ee2a6-144">入站呼叫者 ID</span><span class="sxs-lookup"><span data-stu-id="ee2a6-144">Inbound caller ID</span></span>

<span data-ttu-id="ee2a6-145">如果数字与 Azure AD 中的用户关联，则电话系统将显示为外部电话号码调用的 ID。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-145">Phone System will show called ID for an external phone number if the number is associated with a user in Azure AD.</span></span> <span data-ttu-id="ee2a6-146">如果电话号码不在 Azure AD 中，则将显示通讯提供的显示名称（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-146">If the phone number is not in Azure AD, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="ee2a6-147">BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-147">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="ee2a6-148">你可以设置此属性，但你的最终用户无法在 "用户设置" 页面上使用该属性。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-148">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="ee2a6-149">当前仅在使用在线 PSTN 连接时可用。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-149">And it is currently available only with Online PSTN connectivity.</span></span>
  
<span data-ttu-id="ee2a6-150">要设置出站来电显示，请参见[为用户设置来电显示](/microsoftteams/set-the-caller-id-for-a-user)。</span><span class="sxs-lookup"><span data-stu-id="ee2a6-150">To set the outbound caller ID, see [Set the Caller ID for a user](/microsoftteams/set-the-caller-id-for-a-user).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="ee2a6-151">相关主题</span><span class="sxs-lookup"><span data-stu-id="ee2a6-151">Related topics</span></span>
[<span data-ttu-id="ee2a6-152">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="ee2a6-152">Transferring phone numbers common questions</span></span>](/microsoftteams/transferring-phone-numbers-common-questions)

[<span data-ttu-id="ee2a6-153">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="ee2a6-153">Different kinds of phone numbers used for Calling Plans</span></span>](/microsoftteams/different-kinds-of-phone-numbers-used-for-calling-plans)

[<span data-ttu-id="ee2a6-154">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="ee2a6-154">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="ee2a6-155">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="ee2a6-155">Emergency calling terms and conditions</span></span>](/microsoftteams/emergency-calling-terms-and-conditions)

<span data-ttu-id="ee2a6-156">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="ee2a6-156">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
 
