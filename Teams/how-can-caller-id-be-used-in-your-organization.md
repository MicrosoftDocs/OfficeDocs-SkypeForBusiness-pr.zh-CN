---
title: 如何在你的组织中使用来电显示
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: jens, roykuntz
ms.topic: article
ms.assetid: 5a0bd8ba-3334-46ee-becf-1025597737f6
ms.tgt.pltfrm: cloud
search.appverid: MET150
ms.collection:
- M365-voice
ms.service: msteams
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
description: 可以使用名为 CallingLineIdentity 的策略控制 电话系统 用户的入站和出站呼叫的来电显示。
ms.openlocfilehash: 2a104679be84dfdaa4574353ccc79142d8a82284
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308341"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="52932-103">如何在你的组织中使用来电显示</span><span class="sxs-lookup"><span data-stu-id="52932-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="52932-104">调用方 ID 由两个面向用户的可识别信息片段组成：</span><span class="sxs-lookup"><span data-stu-id="52932-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="52932-105">电话号码 (称为 CLID 或呼叫线路 ID) 。</span><span class="sxs-lookup"><span data-stu-id="52932-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="52932-106">这是 PSTN 公用 (号码) 表示为呼叫者的标识。</span><span class="sxs-lookup"><span data-stu-id="52932-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="52932-107">呼叫方名称 (称为 CNAM) 。</span><span class="sxs-lookup"><span data-stu-id="52932-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="52932-108">无论 PSTN 连接选项如何，电话系统呼叫者 ID 功能都可用：</span><span class="sxs-lookup"><span data-stu-id="52932-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="52932-109">Microsoft 通话套餐</span><span class="sxs-lookup"><span data-stu-id="52932-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="52932-110">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="52932-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="52932-111">可以使用名为 CallingLineIdentity 的策略控制入站和出站呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="52932-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="52932-112">有关详细信息，请参阅 [有关呼叫线路 ID 和呼叫方名称的更多信息](more-about-calling-line-id-and-calling-party-name.md)。</span><span class="sxs-lookup"><span data-stu-id="52932-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="52932-113">出站 PSTN 呼叫者 ID</span><span class="sxs-lookup"><span data-stu-id="52932-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="52932-114">对于出站 PSTN 呼叫者 ID，可以使用以下选项。</span><span class="sxs-lookup"><span data-stu-id="52932-114">For the outbound PSTN caller ID, the following options are available.</span></span> 

> [!NOTE]
> <span data-ttu-id="52932-115">下面指示的一些选项以预览版提供。</span><span class="sxs-lookup"><span data-stu-id="52932-115">Some options, indicated below, are in preview release.</span></span>
  
- <span data-ttu-id="52932-116">分配给用户的电话号码，这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="52932-116">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="52932-117">匿名，通过删除用户的 PSTN 号码的表示形式提供。</span><span class="sxs-lookup"><span data-stu-id="52932-117">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="52932-118">替代电话号码，可以是：</span><span class="sxs-lookup"><span data-stu-id="52932-118">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="52932-119">在"呼叫计划"电话号码清单中分类为服务和免费电话号码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="52932-119">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="52932-120">它通常分配给一个Teams 自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="52932-120">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="52932-121">**预览版。**</span><span class="sxs-lookup"><span data-stu-id="52932-121">**Preview release.**</span></span> <span data-ttu-id="52932-122">本地电话号码，通过直接路由分配给呼叫队列或呼叫Teams 自动助理资源帐户。</span><span class="sxs-lookup"><span data-stu-id="52932-122">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="52932-123">**预览版。**</span><span class="sxs-lookup"><span data-stu-id="52932-123">**Preview release.**</span></span> <span data-ttu-id="52932-124">在出站 PSTN 呼叫上设置的呼叫方名称或 CNAM。</span><span class="sxs-lookup"><span data-stu-id="52932-124">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="52932-125">有关详细信息，请参阅 [为用户设置来电显示](./set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="52932-125">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="52932-126">出站来电显示最终用户控制</span><span class="sxs-lookup"><span data-stu-id="52932-126">End user control of outbound caller ID</span></span>

<span data-ttu-id="52932-127">用户可以通过设置 EnableUserOverride **属性，** 将呼叫者 ID 设置更改为匿名。</span><span class="sxs-lookup"><span data-stu-id="52932-127">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="52932-128">如果出站呼叫者 ID 设置为 Anonymous，EnableUserOverride 将不起作用，并且调用方 ID 始终设置为 Anonymous。</span><span class="sxs-lookup"><span data-stu-id="52932-128">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="52932-129">EnableUserOverride 的默认值是 False。</span><span class="sxs-lookup"><span data-stu-id="52932-129">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="52932-130">最终用户可以通过以下方法将其来电显示设置为匿名：设置 >呼叫"，然后在"呼叫者 **ID"** 下，选择"隐藏我的电话号码和所有呼叫 **的个人资料信息"。**</span><span class="sxs-lookup"><span data-stu-id="52932-130">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="52932-131">注释</span><span class="sxs-lookup"><span data-stu-id="52932-131">Notes</span></span>

<span data-ttu-id="52932-132">注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="52932-132">Keep the following in mind:</span></span>

- <span data-ttu-id="52932-133">不能为出站来电显示分配以下类型的电话号码：</span><span class="sxs-lookup"><span data-stu-id="52932-133">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="52932-134">在"呼叫计划"电话号码清单中分类为用户的任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="52932-134">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="52932-135">通过直接路由分配给用户的任何本地电话号码。</span><span class="sxs-lookup"><span data-stu-id="52932-135">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="52932-136">Skype for Business Server本地电话号码。</span><span class="sxs-lookup"><span data-stu-id="52932-136">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="52932-137">使用资源帐户电话号码替换仅适用于Teams用户。</span><span class="sxs-lookup"><span data-stu-id="52932-137">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="52932-138">服务电话号码的替换适用于 Skype for Business Online Teams用户。</span><span class="sxs-lookup"><span data-stu-id="52932-138">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="52932-139">呼叫方名称仅在呼叫方 ID 替换为 LineUri、服务或资源帐户电话号码以及呼叫方是用户时Teams发送。</span><span class="sxs-lookup"><span data-stu-id="52932-139">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="52932-140">呼叫方名称最多可包含 200 个字符，但下游系统可能支持较少的字符。</span><span class="sxs-lookup"><span data-stu-id="52932-140">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="52932-141">对于直接路由，电话号码替换和呼叫方名称在 FROM SIP 标头中发送。</span><span class="sxs-lookup"><span data-stu-id="52932-141">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="52932-142">如果相应的 OnlinePstnGateway 配置为 ForwardPai = True，则 P-ASSERTED-IDENTITY SIP 标头将包含真正的呼叫用户。</span><span class="sxs-lookup"><span data-stu-id="52932-142">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="52932-143">除非替换设置为 Anonymous，否则 EnableUserOverride 优先于策略中的其他设置。</span><span class="sxs-lookup"><span data-stu-id="52932-143">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="52932-144">例如，假设策略实例具有使用资源帐户的替换项，并且 EnableUserOverride 由用户设置和启用。</span><span class="sxs-lookup"><span data-stu-id="52932-144">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="52932-145">在这种情况下，将阻止出站来电显示，使用匿名。</span><span class="sxs-lookup"><span data-stu-id="52932-145">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="52932-146">如果策略实例的替换设置为 Anonymous 且 EnableUserOverride 已设置，则出站调用方 ID 将始终为 Anonymous，而不考虑最终用户设置。</span><span class="sxs-lookup"><span data-stu-id="52932-146">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="52932-147">入站来电显示</span><span class="sxs-lookup"><span data-stu-id="52932-147">Inbound caller ID</span></span>

<span data-ttu-id="52932-148">电话系统来电显示作为来电显示的外部电话号码。</span><span class="sxs-lookup"><span data-stu-id="52932-148">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="52932-149">如果号码与 Azure AD 中的用户或联系人或个人联系人相关联，Skype for Business客户端Teams基于该信息显示呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="52932-149">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="52932-150">如果电话号码不在 Azure AD 或个人联系人中，则会显示由显示名称提供的电话号码（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="52932-150">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="52932-151">BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。</span><span class="sxs-lookup"><span data-stu-id="52932-151">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="52932-152">可以设置此属性，但它在用户设置页上对最终用户不可用。</span><span class="sxs-lookup"><span data-stu-id="52932-152">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="52932-153">启用此设置后，传入 PSTN 呼叫者将显示为来自匿名。</span><span class="sxs-lookup"><span data-stu-id="52932-153">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="52932-154">若要阻止入站来电显示，请参阅 [为用户设置来电显示](./set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="52932-154">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="52932-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="52932-155">Related topics</span></span>
[<span data-ttu-id="52932-156">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="52932-156">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="52932-157">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="52932-157">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="52932-158">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="52932-158">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="52932-159">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="52932-159">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="52932-160">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="52932-160">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
