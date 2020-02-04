---
title: 位置策略创建新的或编辑现有的
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: 1ae4d2b5223599dd595dcbcceae60396a4af4869
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/03/2020
ms.locfileid: "41691047"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="3b5aa-103">位置策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="3b5aa-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="3b5aa-104">您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="3b5aa-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="3b5aa-105">UI Reference</span></span>

<span data-ttu-id="3b5aa-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="3b5aa-107">**范围**标识要创建或修改的位置策略的范围：全局、网站或用户。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="3b5aa-108">**名称**每个位置策略都需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="3b5aa-109">全局和网站位置策略默认命名，不能更改名称。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="3b5aa-110">对于用户位置策略，请使用标识用户或用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="3b5aa-111">保存位置策略后，将无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="3b5aa-112">**启用增强的9-1-1 （E9** -1）选中此复选框可为分配了此位置策略的用户启用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="3b5aa-113">**位置**指定是否提示用户输入位置信息：</span><span class="sxs-lookup"><span data-stu-id="3b5aa-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="3b5aa-114">**必需**如果用户在其客户注册到新位置时，系统会提示用户输入位置信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="3b5aa-115">用户可以在不输入位置信息的情况下关闭提示。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="3b5aa-116">**不需要**如果不提示用户输入位置信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="3b5aa-117">**免责声明**如果提示用户输入位置信息，请选择此选项，但如果用户在不输入信息的情况下拒绝提示，则会看到声明消息。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="3b5aa-118">用户可以完成紧急呼叫，但不能拨打任何其他电话，直到他们输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="3b5aa-119">**仅对 E9 使用位置-1-** 1如果 "位置信息" 仅用于紧急呼叫，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="3b5aa-120">**PSTN 使用**选择公共交换电话网络（PSTN）使用，用于确定将使用此配置文件的客户端路由紧急呼叫的语音路线。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="3b5aa-121">与此使用关联的路由应指向专用于紧急呼叫的 SIP 中继，或者指向紧急位置标识号码（ELIN）网关，该网关将紧急呼叫路由到最近的公共安全应答点（PSAP）。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="3b5aa-122">选项包括 "**内部**"、"**本地**" 或 "**长途**"。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="3b5aa-123">**E9-1-1 个拨号号码**指定为达到紧急服务而拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="3b5aa-124">**E9-1-1）拨号掩码**指定用户拨号的号码，然后将该号码转换为 "紧急电话拨号码"。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="3b5aa-125">例如，在此字段中输入一个212的值，以便用户可以拨打212以联系紧急服务。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="3b5aa-126">这允许拨打备用紧急号码，并且仍然可以呼叫紧急服务（例如，如果某个国家或地区的某人使用不同的紧急号码，请尝试拨打该国家或地区的号码而不是电话号码当前所在的国家或地区）。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="3b5aa-127">可以通过使用分号分隔值来定义多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="3b5aa-128">例如，212;414。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-128">For example, 212;414.</span></span> <span data-ttu-id="3b5aa-129">字符串的最大长度为100个字符。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="3b5aa-130">每个字符都必须为 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="3b5aa-131">确保拨号掩码与呼叫寄存号码范围中的号码不同，因为呼叫寄存路由将优先于紧急拨号字符串转换。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="3b5aa-132">若要查看呼叫公园的号码范围，请单击左侧导航栏中的 "**语音功能**"，然后单击 "**呼叫寄存**"。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="3b5aa-133">**通知 URI**指定发出紧急呼叫时要通知的一个或多个 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="3b5aa-134">例如，键入公司安全 office 的 SIP URI，以便在发生紧急呼叫时使用即时消息通知安全人员。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="3b5aa-135">如果呼叫者的位置可用，则该位置将包含在通知中。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="3b5aa-136">你可以将多个 SIP Uri 指定为以逗号分隔的列表。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="3b5aa-137">例如，"sip： security@litwareinc .com"、"sip： kmyer@litwareinc .com"。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="3b5aa-138">字符串的长度必须介于1到256个字符之间，并且必须以前缀 "sip：" 开头。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="3b5aa-139">您还可以指定通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="3b5aa-140">**会议 URI**为要 conferenced 的第三方指定 "紧急电话" 的 SIP URI （本例中为 "电话号码"）。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="3b5aa-141">例如，键入公司安全办公室的电话号码，以便他们在进行紧急呼叫时收到呼叫。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="3b5aa-142">**会议模式**的设置确定第三方是否可以参与呼叫或仅接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="3b5aa-143">该字符串的长度必须介于1到256个字符之间，并且必须以前缀 sip：开头。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="3b5aa-144">**会议模式**如果为**会议 URI**指定了值，请将此字段设置为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="3b5aa-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="3b5aa-145">**单向**指定第三方只能侦听呼叫方与 PSAP 运算符之间的调用。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="3b5aa-146">**双向**指定第三方可以参与呼叫方和 PSAP 操作员之间的通话。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="3b5aa-147">有关企业语音紧急服务功能和功能的详细信息，请参阅规划文档中的[E9 概述 1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="3b5aa-148">有关使用位置策略的详细信息，请参阅操作文档中的[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="3b5aa-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


