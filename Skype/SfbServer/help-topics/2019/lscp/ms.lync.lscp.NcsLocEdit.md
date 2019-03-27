---
title: 位置策略创建新的或编辑现有的
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
ROBOTS: NOINDEX, NOFOLLOW
description: 您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: d148b7b546b5c0e239c1fbccfdbcf27e0a3840fa
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/27/2019
ms.locfileid: "30886210"
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="9977f-103">位置策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="9977f-103">Location Policy: Create New or Edit Existing</span></span>

<span data-ttu-id="9977f-104">您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="9977f-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>

## <a name="ui-reference"></a><span data-ttu-id="9977f-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="9977f-105">UI Reference</span></span>

<span data-ttu-id="9977f-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="9977f-106">The following list describes the fields on the page.</span></span>

- <span data-ttu-id="9977f-107">**范围**标识您正在创建或修改的位置策略的范围： 全局、 站点或用户。</span><span class="sxs-lookup"><span data-stu-id="9977f-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>

- <span data-ttu-id="9977f-108">**名称**每个位置策略需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="9977f-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="9977f-109">全局和站点位置策略默认情况下，命名为和无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="9977f-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="9977f-110">用户位置策略，使用标识的用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="9977f-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>

    > [!NOTE]
    > <span data-ttu-id="9977f-111">保存位置策略后，将无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="9977f-111">After you save the location policy, the name cannot be changed.</span></span>

- <span data-ttu-id="9977f-112">**启用增强型的 9-1-1 (E9-1-1)** 选中此复选框以启用分配此位置策略的用户 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="9977f-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>

- <span data-ttu-id="9977f-113">**位置**指定是否提示用户输入位置信息：</span><span class="sxs-lookup"><span data-stu-id="9977f-113">**Location** Specify whether users are prompted for location information:</span></span>

  - <span data-ttu-id="9977f-114">**所需**如果用户要在新位置中将他们的客户端注册时被提示输入位置信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="9977f-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="9977f-115">用户可以消除提示符处，无需输入位置信息。</span><span class="sxs-lookup"><span data-stu-id="9977f-115">Users can dismiss the prompt without entering location information.</span></span>

  - <span data-ttu-id="9977f-116">**不需要**如果用户将不会提示您输入位置信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="9977f-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>

  - <span data-ttu-id="9977f-117">**免责声明**如果用户提示位置信息，但如果拒绝邀请无需输入信息提示符处，将看到免责声明的信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="9977f-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="9977f-118">在用户输入位置信息之前，用户可以完成紧急呼叫，但没有任何其他呼叫。</span><span class="sxs-lookup"><span data-stu-id="9977f-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>

- <span data-ttu-id="9977f-119">**E9-1-1 仅使用位置**如果位置信息仅用于紧急呼叫，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="9977f-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>

- <span data-ttu-id="9977f-120">**PSTN 用法**选择将用于确定的语音路由将用于紧急呼叫路由使用此配置文件的客户端的公用电话交换网 (pstn) 用法。</span><span class="sxs-lookup"><span data-stu-id="9977f-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="9977f-121">与此用法的路由应指向专用紧急呼叫或到最接近公共安全应答点 (PSAP) 的紧急呼叫路由的紧急位置标识号 (ELIN) 网关的 SIP 中继。</span><span class="sxs-lookup"><span data-stu-id="9977f-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="9977f-122">**内部**、**本地**或**长途**的选项。</span><span class="sxs-lookup"><span data-stu-id="9977f-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>

- <span data-ttu-id="9977f-123">**E9-1-1 拨打号码**指定要获得紧急服务时所拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="9977f-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>

- <span data-ttu-id="9977f-124">**E9-1-1 拨号掩码**指定用户拨打的号码，这可转换成紧急拨打号码。</span><span class="sxs-lookup"><span data-stu-id="9977f-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="9977f-125">例如，在此字段中输入的值为 212，以便用户可拨打 212 要获得紧急服务。</span><span class="sxs-lookup"><span data-stu-id="9977f-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="9977f-126">这样的备用紧急号码拨打和仍具有获得紧急服务呼叫 (例如，如果某人的国家或地区包含不同紧急号码尝试拨号国家或地区的号码而不是从的编号国家或地区他们当前正在）。</span><span class="sxs-lookup"><span data-stu-id="9977f-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="9977f-127">可以通过使用分号分隔值来定义多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="9977f-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="9977f-128">例如，212;414。</span><span class="sxs-lookup"><span data-stu-id="9977f-128">For example, 212;414.</span></span> <span data-ttu-id="9977f-129">字符串的最大长度为 100 个字符。</span><span class="sxs-lookup"><span data-stu-id="9977f-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="9977f-130">每个字符都必须为 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="9977f-130">Each character must be a digit 0 through 9.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="9977f-131">确保拨号掩码与呼叫寄存号码范围中的号码不同，因为呼叫寄存路由将优先于紧急拨号字符串转换。</span><span class="sxs-lookup"><span data-stu-id="9977f-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="9977f-132">若要查看的呼叫寄存号码范围，单击**语音功能**在左侧的导航栏中，，然后单击**呼叫寄存**。</span><span class="sxs-lookup"><span data-stu-id="9977f-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span>

- <span data-ttu-id="9977f-133">**通知 URI**指定在发出紧急呼叫时通知的一个或多个 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="9977f-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="9977f-134">例如，键入公司安全办公室的 SIP URI 进行紧急呼叫时通知安全人员使用即时消息。</span><span class="sxs-lookup"><span data-stu-id="9977f-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="9977f-135">可用的呼叫者的位置，如果位置包含在的通知。</span><span class="sxs-lookup"><span data-stu-id="9977f-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="9977f-136">您可以指定多个 SIP Uri 为以逗号分隔列表。</span><span class="sxs-lookup"><span data-stu-id="9977f-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="9977f-137">例如，"sip:security@litwareinc.com"、"sip:kmyer@litwareinc.com"。</span><span class="sxs-lookup"><span data-stu-id="9977f-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="9977f-138">字符串必须介于 1 到 256 个字符的长度，必须以前缀开头"sip:"。</span><span class="sxs-lookup"><span data-stu-id="9977f-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="9977f-139">您还可以指定通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="9977f-139">You can also specify distribution lists.</span></span>

- <span data-ttu-id="9977f-140">**会议 URI**指定要在会议中的紧急呼叫到第三方 SIP URI （在本例中电话号码）。</span><span class="sxs-lookup"><span data-stu-id="9977f-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="9977f-141">例如，键入公司安全办公室电话号码，以便他们进行紧急呼叫时接收呼叫。</span><span class="sxs-lookup"><span data-stu-id="9977f-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="9977f-142">**会议模式**的设置确定第三方可以参与，还是只接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="9977f-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="9977f-143">字符串必须介于 1 到 256 个字符的长度，必须以前缀 sip 开头:。</span><span class="sxs-lookup"><span data-stu-id="9977f-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>

- <span data-ttu-id="9977f-144">**会议模式**如果**会议**uri 指定一个值，将此字段设置为下列值之一：</span><span class="sxs-lookup"><span data-stu-id="9977f-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>

  - <span data-ttu-id="9977f-145">**单向**指定第三方可以只能接听呼叫者与 PSAP 接线员之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9977f-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>

  - <span data-ttu-id="9977f-146">**双向**指定第三方可以参与呼叫者与 PSAP 接线员之间的呼叫。</span><span class="sxs-lookup"><span data-stu-id="9977f-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>

<span data-ttu-id="9977f-147">有关企业语音紧急服务特性和功能的详细信息，请参阅规划文档中[概述的 E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="9977f-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](https://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="9977f-148">有关使用位置策略的详细信息，请参阅操作文档中的[Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="9977f-148">For details about working with location policies, see [Configuring Location Policy](https://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>


