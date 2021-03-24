---
title: 位置策略 创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/24/2015
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: 可以配置位置策略以确定增强型 9-1-1 (E9-1-1) 是否已启用，如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: 587d239551111c028026aef463c853a1ac93714f
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51099708"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="7c81e-103">位置策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="7c81e-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="7c81e-104">可以配置位置策略以确定增强型 9-1-1 (E9-1-1) 是否已启用，如何使用它，以及如何将位置信息用于用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="7c81e-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="7c81e-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="7c81e-105">UI Reference</span></span>

<span data-ttu-id="7c81e-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="7c81e-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="7c81e-107">**范围** 标识要创建或修改的位置策略的范围：全局、站点或用户。</span><span class="sxs-lookup"><span data-stu-id="7c81e-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="7c81e-108">**名称** 每个位置策略都需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="7c81e-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="7c81e-109">默认情况下会命名全局和站点位置策略，并且无法更改名称。</span><span class="sxs-lookup"><span data-stu-id="7c81e-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="7c81e-110">对于用户位置策略，请使用用于标识用户或用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="7c81e-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="7c81e-111">保存位置策略后，名称将无法更改。</span><span class="sxs-lookup"><span data-stu-id="7c81e-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="7c81e-112">**启用增强型 9-1-1 (E9-1-1)** 选中此复选框，为分配了此位置策略的用户启用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="7c81e-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="7c81e-113">**位置** 指定是否提示用户提供位置信息：</span><span class="sxs-lookup"><span data-stu-id="7c81e-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="7c81e-114">**必需** 如果用户的客户端在新位置注册时提示用户提供位置信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7c81e-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="7c81e-115">用户无需输入位置信息即可消除提示。</span><span class="sxs-lookup"><span data-stu-id="7c81e-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="7c81e-116">**不是必需的** 如果未提示用户输入位置信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7c81e-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="7c81e-117">**免责声明** 如果系统提示用户输入位置信息，但如果用户拒绝提示而不输入信息，则会看到免责声明消息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="7c81e-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="7c81e-118">在用户输入位置信息之前，用户可以完成紧急呼叫，但不能完成其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="7c81e-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="7c81e-119">**仅对 E9-1-1 使用位置** 如果位置信息仅用于紧急呼叫，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="7c81e-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="7c81e-120">**PSTN 用法** 选择公用电话交换网 (PSTN) 用法，该用法将用于确定哪些语音路由将用于路由来自使用此配置文件的客户端的紧急呼叫。</span><span class="sxs-lookup"><span data-stu-id="7c81e-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="7c81e-121">与此用法关联的路由应指向专用于紧急呼叫的 SIP 中继或紧急位置标识号 (ELIN) 网关，该网关将紧急呼叫路由到最近的公共安全应答点 (PSAP) 。</span><span class="sxs-lookup"><span data-stu-id="7c81e-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="7c81e-122">选项有 **Internal、Local** 或 **Long distance。** </span><span class="sxs-lookup"><span data-stu-id="7c81e-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="7c81e-123">**E9-1-1 拨号号码** 指定为获得紧急服务而拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="7c81e-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="7c81e-124">**E9-1-1 拨号掩码** 指定用户拨打的号码，然后转换为紧急拨号号码。</span><span class="sxs-lookup"><span data-stu-id="7c81e-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="7c81e-125">例如，在此字段中输入值 212，以便用户可以拨打 212 来访问紧急服务。</span><span class="sxs-lookup"><span data-stu-id="7c81e-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="7c81e-126">这样，可以拨打备用紧急号码，并且仍可将呼叫联系紧急服务 (例如，来自具有不同紧急号码的某个国家/地区或地区的用户尝试拨打该国家/地区的号码，而不是当前位于) 中的某个国家/地区的号码。</span><span class="sxs-lookup"><span data-stu-id="7c81e-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="7c81e-127">您可以通过使用分号分隔值来定义多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="7c81e-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="7c81e-128">例如，212;414。</span><span class="sxs-lookup"><span data-stu-id="7c81e-128">For example, 212;414.</span></span> <span data-ttu-id="7c81e-129">字符串的最大长度为 100 个字符。</span><span class="sxs-lookup"><span data-stu-id="7c81e-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="7c81e-130">每个字符都必须为 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="7c81e-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="7c81e-131">确保拨号掩码与呼叫号码范围中的号码不同，因为呼叫呼叫停止路由优先于紧急拨号字符串转换。</span><span class="sxs-lookup"><span data-stu-id="7c81e-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="7c81e-132">To see the Call Park number ranges， click **Voice Features** in the left navigation bar， and then click **Call Park**.</span><span class="sxs-lookup"><span data-stu-id="7c81e-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="7c81e-133">**通知 URI** 指定进行紧急呼叫时要通知的一个或多个 SIP URI。</span><span class="sxs-lookup"><span data-stu-id="7c81e-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="7c81e-134">例如，键入公司安全办公室的 SIP URI，以在发出紧急呼叫时通过即时消息通知安全人员。</span><span class="sxs-lookup"><span data-stu-id="7c81e-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="7c81e-135">如果呼叫者的位置可用，该位置将包含在通知中。</span><span class="sxs-lookup"><span data-stu-id="7c81e-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="7c81e-136">可以将多个 SIP URI 指定为逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="7c81e-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="7c81e-137">例如，"sip:security@litwareinc.com"、"sip:kmyer@litwareinc.com"。</span><span class="sxs-lookup"><span data-stu-id="7c81e-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="7c81e-138">字符串长度必须为 1 到 256 个字符，并且必须以前缀"sip："开头。</span><span class="sxs-lookup"><span data-stu-id="7c81e-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="7c81e-139">您还可以指定通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="7c81e-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="7c81e-140">**会议 URI** 指定 SIP URI (电话号码，在这种情况下，) 第三方参加紧急呼叫会议。</span><span class="sxs-lookup"><span data-stu-id="7c81e-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="7c81e-141">例如，键入公司安全办公室的电话号码，以便他们在拨打紧急呼叫时收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="7c81e-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="7c81e-142">会议 **模式设置** 确定第三方是可以参与还是只收听呼叫。</span><span class="sxs-lookup"><span data-stu-id="7c81e-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="7c81e-143">该字符串的长度必须为 1 到 256 个字符，并且必须以前缀 sip: 开头。</span><span class="sxs-lookup"><span data-stu-id="7c81e-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="7c81e-144">**会议模式** 如果为 Conference **URI 指定了** 值，将此字段设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="7c81e-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="7c81e-145">**单向** 指定第三方只能侦听呼叫者与 PSAP 接线员之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7c81e-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="7c81e-146">**双向** 指定第三方可以参与呼叫者与 PSAP 接线员之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="7c81e-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="7c81e-147">有关紧急企业语音功能的详细信息，请参阅规划文档中的[Overview of E9-1-1。](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1)</span><span class="sxs-lookup"><span data-stu-id="7c81e-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](/previous-versions/office/lync-server-2013/lync-server-2013-overview-of-e9-1-1) in the Planning documentation.</span></span> <span data-ttu-id="7c81e-148">有关使用位置策略的详细信息，请参阅操作文档中的[Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information)。</span><span class="sxs-lookup"><span data-stu-id="7c81e-148">For details about working with location policies, see [Configuring Location Policy](/previous-versions/office/lync-server-2013/lync-server-2013-viewing-location-policy-information) in the Operations documentation.</span></span>