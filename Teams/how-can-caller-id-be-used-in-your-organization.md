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
ms.openlocfilehash: 43d3d6633ca46485aa111a7d97b9bd37b0547818
ms.sourcegitcommit: 02e243d6c58eab463a00ed45dadd80112087006e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/02/2021
ms.locfileid: "52723543"
---
# <a name="how-can-caller-id-be-used-in-your-organization"></a><span data-ttu-id="c6493-103">如何在你的组织中使用来电显示</span><span class="sxs-lookup"><span data-stu-id="c6493-103">How can caller ID be used in your organization</span></span>

<span data-ttu-id="c6493-104">调用方 ID 由两个面向用户的可识别信息片段组成：</span><span class="sxs-lookup"><span data-stu-id="c6493-104">Caller ID consists of two user-facing identifiable pieces of information:</span></span>

- <span data-ttu-id="c6493-105">电话号码 (称为 CLID 或呼叫线路 ID) 。</span><span class="sxs-lookup"><span data-stu-id="c6493-105">A phone number (typically referred to as CLID or calling line ID).</span></span> <span data-ttu-id="c6493-106">这是 PSTN 公用 (号码) 表示为呼叫者的标识。</span><span class="sxs-lookup"><span data-stu-id="c6493-106">This is the Public Switched Telephone Number (PSTN) presented as the identification of the caller.</span></span>

- <span data-ttu-id="c6493-107">呼叫方名称 (称为 CNAM) 。</span><span class="sxs-lookup"><span data-stu-id="c6493-107">A Calling party name (typically referred to as CNAM).</span></span> 
  
<span data-ttu-id="c6493-108">无论 PSTN 连接选项如何，电话系统呼叫者 ID 功能都可用：</span><span class="sxs-lookup"><span data-stu-id="c6493-108">The caller ID functionality is available to all Phone System users regardless of PSTN connectivity option:</span></span>

- <span data-ttu-id="c6493-109">Microsoft 通话套餐</span><span class="sxs-lookup"><span data-stu-id="c6493-109">Microsoft Calling Plans</span></span> 

- <span data-ttu-id="c6493-110">电话系统直接路由</span><span class="sxs-lookup"><span data-stu-id="c6493-110">Phone System Direct Routing</span></span> 
  
<span data-ttu-id="c6493-111">可以使用名为 CallingLineIdentity 的策略控制入站和出站呼叫的来电显示。</span><span class="sxs-lookup"><span data-stu-id="c6493-111">You can control Caller ID for both inbound and outbound calls by using a policy called CallingLineIdentity.</span></span> <span data-ttu-id="c6493-112">有关详细信息，请参阅 [有关呼叫线路 ID 和呼叫方名称的更多信息](more-about-calling-line-id-and-calling-party-name.md)。</span><span class="sxs-lookup"><span data-stu-id="c6493-112">For more information, see [More about Calling Line ID and Calling Party Name](more-about-calling-line-id-and-calling-party-name.md).</span></span>

  
## <a name="outbound-pstn-caller-id"></a><span data-ttu-id="c6493-113">出站 PSTN 呼叫者 ID</span><span class="sxs-lookup"><span data-stu-id="c6493-113">Outbound PSTN caller ID</span></span>

<span data-ttu-id="c6493-114">对于出站 PSTN 呼叫者 ID，可以使用以下选项。</span><span class="sxs-lookup"><span data-stu-id="c6493-114">For the outbound PSTN caller ID, the following options are available.</span></span> 
  
- <span data-ttu-id="c6493-115">分配给用户的电话号码，这是默认设置。</span><span class="sxs-lookup"><span data-stu-id="c6493-115">The telephone number assigned to the user, which is the default.</span></span>

- <span data-ttu-id="c6493-116">匿名，通过删除用户的 PSTN 号码的表示形式提供。</span><span class="sxs-lookup"><span data-stu-id="c6493-116">Anonymous, which is available by removing the presentation of the user’s PSTN number.</span></span> 

- <span data-ttu-id="c6493-117">替代电话号码，可以是：</span><span class="sxs-lookup"><span data-stu-id="c6493-117">A substitute phone number, which can be:</span></span>

  - <span data-ttu-id="c6493-118">在"呼叫计划"电话号码清单中分类为服务和免费电话号码的电话号码。</span><span class="sxs-lookup"><span data-stu-id="c6493-118">A telephone number that is classified as a service and toll-free number in your Calling Plans telephone number inventory.</span></span> <span data-ttu-id="c6493-119">它通常分配给一个Teams 自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="c6493-119">It is usually assigned to a Teams Auto Attendant or Call Queue.</span></span>

  - <span data-ttu-id="c6493-120">本地电话号码，通过直接路由分配给呼叫队列或呼叫Teams 自动助理资源帐户。</span><span class="sxs-lookup"><span data-stu-id="c6493-120">An on-premises telephone number through Direct Routing that is assigned to a resource account used by a Teams Auto Attendant or Call Queue.</span></span> 

- <span data-ttu-id="c6493-121">在出站 PSTN 呼叫上设置的呼叫方名称或 CNAM。</span><span class="sxs-lookup"><span data-stu-id="c6493-121">The Calling Party Name or CNAM set on the outbound PSTN call.</span></span>  
    
<span data-ttu-id="c6493-122">有关详细信息，请参阅 [为用户设置来电显示](./set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c6493-122">For more information, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
### <a name="end-user-control-of-outbound-caller-id"></a><span data-ttu-id="c6493-123">出站来电显示最终用户控制</span><span class="sxs-lookup"><span data-stu-id="c6493-123">End user control of outbound caller ID</span></span>

<span data-ttu-id="c6493-124">用户可以通过设置 EnableUserOverride **属性，** 将呼叫者 ID 设置更改为匿名。</span><span class="sxs-lookup"><span data-stu-id="c6493-124">Users can change their caller ID setting to **Anonymous** by setting the EnableUserOverride attribute.</span></span> 

<span data-ttu-id="c6493-125">如果出站呼叫者 ID 设置为 Anonymous，EnableUserOverride 将不起作用，并且调用方 ID 始终设置为 Anonymous。</span><span class="sxs-lookup"><span data-stu-id="c6493-125">If the outbound caller ID is set to Anonymous, the EnableUserOverride has no effect and the caller ID is always set to Anonymous.</span></span> <span data-ttu-id="c6493-126">EnableUserOverride 的默认值是 False。</span><span class="sxs-lookup"><span data-stu-id="c6493-126">The default value of EnableUserOverride is False.</span></span>

<span data-ttu-id="c6493-127">最终用户可以通过以下方法将其来电显示设置为匿名：设置 >呼叫"，然后在"呼叫者 **ID"** 下，选择"隐藏我的电话号码和所有呼叫 **的个人资料信息"。**</span><span class="sxs-lookup"><span data-stu-id="c6493-127">Your end users can set their caller ID to Anonymous by going to **Settings > Calls**, and then under **Caller ID**, select **Hide my phone number and profile information for all calls**.</span></span>

### <a name="notes"></a><span data-ttu-id="c6493-128">注释</span><span class="sxs-lookup"><span data-stu-id="c6493-128">Notes</span></span>

<span data-ttu-id="c6493-129">注意以下几项：</span><span class="sxs-lookup"><span data-stu-id="c6493-129">Keep the following in mind:</span></span>

- <span data-ttu-id="c6493-130">不能为出站来电显示分配以下类型的电话号码：</span><span class="sxs-lookup"><span data-stu-id="c6493-130">You can't assign the following types of phone numbers for the outbound caller ID:</span></span>

  - <span data-ttu-id="c6493-131">在"呼叫计划"电话号码清单中分类为用户的任何电话号码。</span><span class="sxs-lookup"><span data-stu-id="c6493-131">Any phone numbers that are classified as a user in your Calling Plans telephone number inventory.</span></span>

  - <span data-ttu-id="c6493-132">通过直接路由分配给用户的任何本地电话号码。</span><span class="sxs-lookup"><span data-stu-id="c6493-132">Any on-premises telephone number via Direct Routing that is assigned to a user.</span></span>

  - <span data-ttu-id="c6493-133">Skype for Business Server本地电话号码。</span><span class="sxs-lookup"><span data-stu-id="c6493-133">A Skype for Business Server on-premises telephone number.</span></span>

- <span data-ttu-id="c6493-134">使用资源帐户电话号码替换仅适用于Teams用户。</span><span class="sxs-lookup"><span data-stu-id="c6493-134">The use of resource account phone number substitution only works for Teams users.</span></span> <span data-ttu-id="c6493-135">服务电话号码的替换适用于 Skype for Business Online Teams用户。</span><span class="sxs-lookup"><span data-stu-id="c6493-135">The substitution of service phone number works for both Skype for Business Online and Teams users.</span></span>

- <span data-ttu-id="c6493-136">呼叫方名称仅在呼叫方 ID 替换为 LineUri、服务或资源帐户电话号码以及呼叫方是用户时Teams发送。</span><span class="sxs-lookup"><span data-stu-id="c6493-136">Calling Party Name is only sent on calls where the caller ID is substituted with LineUri, a service or resource account phone number and when the caller is a Teams user.</span></span>

- <span data-ttu-id="c6493-137">呼叫方名称最多可包含 200 个字符，但下游系统可能支持较少的字符。</span><span class="sxs-lookup"><span data-stu-id="c6493-137">Calling Party Name can have a maximum of 200 characters, but downstream systems might support fewer characters.</span></span>

- <span data-ttu-id="c6493-138">对于直接路由，电话号码替换和呼叫方名称在 FROM SIP 标头中发送。</span><span class="sxs-lookup"><span data-stu-id="c6493-138">For Direct Routing, the phone number substitution and the Calling Party Name is sent in the FROM SIP header.</span></span> <span data-ttu-id="c6493-139">如果相应的 OnlinePstnGateway 配置为 ForwardPai = True，则 P-ASSERTED-IDENTITY SIP 标头将包含真正的呼叫用户。</span><span class="sxs-lookup"><span data-stu-id="c6493-139">If the corresponding OnlinePstnGateway is configured with ForwardPai = True, the P-ASSERTED-IDENTITY SIP header will contain the real calling user.</span></span>

- <span data-ttu-id="c6493-140">除非替换设置为 Anonymous，否则 EnableUserOverride 优先于策略中的其他设置。</span><span class="sxs-lookup"><span data-stu-id="c6493-140">EnableUserOverride has precedence over other settings in the policy--unless substitution is set to Anonymous.</span></span> <span data-ttu-id="c6493-141">例如，假设策略实例具有使用资源帐户的替换项，并且 EnableUserOverride 由用户设置和启用。</span><span class="sxs-lookup"><span data-stu-id="c6493-141">For example, assume policy instance has substitution using a resource account and EnableUserOverride is set and enabled by the user.</span></span> <span data-ttu-id="c6493-142">在这种情况下，将阻止出站来电显示，使用匿名。</span><span class="sxs-lookup"><span data-stu-id="c6493-142">In this case, the outbound caller ID will be blocked and Anonymous will be used.</span></span> <span data-ttu-id="c6493-143">如果策略实例的替换设置为 Anonymous 且 EnableUserOverride 已设置，则出站调用方 ID 将始终为 Anonymous，而不考虑最终用户设置。</span><span class="sxs-lookup"><span data-stu-id="c6493-143">If a policy instance has substitution set to Anonymous and EnableUserOverride is set, then the outbound caller ID will always be Anonymous, regardless of the end user setting.</span></span>

   
## <a name="inbound-caller-id"></a><span data-ttu-id="c6493-144">入站来电显示</span><span class="sxs-lookup"><span data-stu-id="c6493-144">Inbound caller ID</span></span>

<span data-ttu-id="c6493-145">电话系统来电显示作为来电显示的外部电话号码。</span><span class="sxs-lookup"><span data-stu-id="c6493-145">Phone System will show the incoming external phone number as the caller ID.</span></span> <span data-ttu-id="c6493-146">如果号码与 Azure AD 中的用户或联系人或个人联系人相关联，Skype for Business客户端Teams基于该信息显示呼叫者 ID。</span><span class="sxs-lookup"><span data-stu-id="c6493-146">If the number is associated with a user or contact in Azure AD or a personal contact, the Skype for Business and Teams clients will show the caller ID based on that information.</span></span> <span data-ttu-id="c6493-147">如果电话号码不在 Azure AD 或个人联系人中，则会显示由显示名称提供的电话号码（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="c6493-147">If the phone number is not in Azure AD or a personal contact, the telco-provided display name will be shown if it is available.</span></span>

<span data-ttu-id="c6493-148">BlockIncomingCallerID 属性可以用于阻止 PSTN 来电的来电显示。</span><span class="sxs-lookup"><span data-stu-id="c6493-148">The BlockIncomingCallerID attribute allows for blocking the caller ID on incoming PSTN calls.</span></span> <span data-ttu-id="c6493-149">可以设置此属性，但它在用户设置页上对最终用户不可用。</span><span class="sxs-lookup"><span data-stu-id="c6493-149">You can set this attribute, but it isn't available to your end users on the user settings page.</span></span> <span data-ttu-id="c6493-150">启用此设置后，传入 PSTN 呼叫者将显示为来自匿名。</span><span class="sxs-lookup"><span data-stu-id="c6493-150">When this setting is enabled the incoming PSTN caller will be displayed as coming from Anonymous.</span></span>
  
<span data-ttu-id="c6493-151">若要阻止入站来电显示，请参阅 [为用户设置来电显示](./set-the-caller-id-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c6493-151">To block the inbound caller ID, see [Set the Caller ID for a user](./set-the-caller-id-for-a-user.md).</span></span>
  
## <a name="related-topics"></a><span data-ttu-id="c6493-152">相关主题</span><span class="sxs-lookup"><span data-stu-id="c6493-152">Related topics</span></span>
[<span data-ttu-id="c6493-153">关于转移电话号码的常见问题</span><span class="sxs-lookup"><span data-stu-id="c6493-153">Transferring phone numbers common questions</span></span>](./phone-number-calling-plans/port-order-overview.md)

[<span data-ttu-id="c6493-154">用于通话套餐的不同类型的电话号码</span><span class="sxs-lookup"><span data-stu-id="c6493-154">Different kinds of phone numbers used for Calling Plans</span></span>](./different-kinds-of-phone-numbers-used-for-calling-plans.md)

[<span data-ttu-id="c6493-155">管理你的组织的电话号码</span><span class="sxs-lookup"><span data-stu-id="c6493-155">Manage phone numbers for your organization</span></span>](/microsoftteams/manage-phone-numbers-for-your-organization)

[<span data-ttu-id="c6493-156">紧急呼叫条款和条件</span><span class="sxs-lookup"><span data-stu-id="c6493-156">Emergency calling terms and conditions</span></span>](./emergency-calling-terms-and-conditions.md)

<span data-ttu-id="c6493-157">[Skype for Business Online：紧急呼叫免责声明标签](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span><span class="sxs-lookup"><span data-stu-id="c6493-157">[Skype for Business Online: Emergency Calling disclaimer label](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/emergency-calling/emergency-calling-label-(en-us)-(v.1.0).zip?raw=true)</span></span>

  
