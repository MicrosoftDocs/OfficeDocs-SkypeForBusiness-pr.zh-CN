---
title: 新建或编辑现有位置策略
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 3/24/2015
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.lscp.NcsLocEdit
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d9b30b3b-570b-49a6-b2b4-46b0cf490153
description: 您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。
ms.openlocfilehash: cc2d5119e4bb21badf96dcf24099844ffffd0639
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="location-policy-create-new-or-edit-existing"></a><span data-ttu-id="82a59-103">位置策略：创建新的或编辑现有的</span><span class="sxs-lookup"><span data-stu-id="82a59-103">Location Policy: Create New or Edit Existing</span></span>
 
<span data-ttu-id="82a59-104">您可以配置位置策略以确定是否启用增强型 9-1-1 (E9-1-1) 和如何使用它，以及如何将位置信息用于用户和联系人。</span><span class="sxs-lookup"><span data-stu-id="82a59-104">You can configure Location policies to determine whether Enhanced 9-1-1 (E9-1-1) is enabled and how it is used, as well as how location information is used for users and contacts.</span></span>
  
## <a name="ui-reference"></a><span data-ttu-id="82a59-105">用户界面参考</span><span class="sxs-lookup"><span data-stu-id="82a59-105">UI Reference</span></span>

<span data-ttu-id="82a59-106">下表介绍了该页上的各个字段。</span><span class="sxs-lookup"><span data-stu-id="82a59-106">The following list describes the fields on the page.</span></span>
  
- <span data-ttu-id="82a59-107">**作用域**标识要创建或修改的位置策略的作用域： 全局站点或用户。</span><span class="sxs-lookup"><span data-stu-id="82a59-107">**Scope** Identifies the scope of the location policy that you are creating or modifying: global, site, or user.</span></span>
    
- <span data-ttu-id="82a59-108">**名称**每个位置策略需要一个名称。</span><span class="sxs-lookup"><span data-stu-id="82a59-108">**Name** Each location policy requires a name.</span></span> <span data-ttu-id="82a59-109">默认情况下，称为全局和站点位置策略，名称不能更改。</span><span class="sxs-lookup"><span data-stu-id="82a59-109">Global and site location policies are named by default, and the name cannot be changed.</span></span> <span data-ttu-id="82a59-110">对于用户位置的策略，使用标识的用户组的描述性名称。</span><span class="sxs-lookup"><span data-stu-id="82a59-110">For user location policies, use a descriptive name that identifies the user or group of users.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="82a59-111">保存位置策略后，将无法更改此名称。</span><span class="sxs-lookup"><span data-stu-id="82a59-111">After you save the location policy, the name cannot be changed.</span></span> 
  
- <span data-ttu-id="82a59-112">**启用增强的 9-1-1 (E9-1-1)**选中此复选框可以为用户分配此位置策略启用 E9-1-1。</span><span class="sxs-lookup"><span data-stu-id="82a59-112">**Enable Enhanced 9-1-1 (E9-1-1)** Select this check box to enable E9-1-1 for users who are assigned this location policy.</span></span>
    
- <span data-ttu-id="82a59-113">**位置**指定是否提示用户输入位置信息：</span><span class="sxs-lookup"><span data-stu-id="82a59-113">**Location** Specify whether users are prompted for location information:</span></span>
    
  - <span data-ttu-id="82a59-114">**所需**如果用户将会提示您输入位置信息在其客户端注册的新位置时，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="82a59-114">**Required** Select this option if users are to be prompted for location information when their client registers at a new location.</span></span> <span data-ttu-id="82a59-115">用户可以消除不输入位置信息的提示。</span><span class="sxs-lookup"><span data-stu-id="82a59-115">Users can dismiss the prompt without entering location information.</span></span>
    
  - <span data-ttu-id="82a59-116">**不需要**如果用户将不会提示您输入位置信息，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="82a59-116">**Not required** Select this option if users are not to be prompted for location information.</span></span>
    
  - <span data-ttu-id="82a59-117">**免责声明**如果以提示您输入位置信息，但用户将看到免责声明的信息，如果他们拒绝不输入该信息的提示，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="82a59-117">**Disclaimer** Select this option if users are to be prompted for location information, but will see a disclaimer message if they decline the prompt without entering the information.</span></span> <span data-ttu-id="82a59-118">用户可以完成紧急调用，但没有其他电话，直到他们输入的位置信息。</span><span class="sxs-lookup"><span data-stu-id="82a59-118">Users can complete an emergency call but no other calls until they enter the location information.</span></span>
    
- <span data-ttu-id="82a59-119">**使用位置 E9-1-1 只**如果位置信息只用于紧急呼叫，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="82a59-119">**Use location for E9-1-1 only** Select this check box if location information is to be used only for emergency calls.</span></span>
    
- <span data-ttu-id="82a59-120">**PSTN 使用情况**选择将用于确定哪些语音路由用于路由的紧急电话，来自客户端使用此配置文件的公共交换的电话网络 (PSTN) 使用。</span><span class="sxs-lookup"><span data-stu-id="82a59-120">**PSTN usage** Select the public switched telephone network (PSTN) usage that will be used to determine which voice route will be used for routing emergency calls from clients that use this profile.</span></span> <span data-ttu-id="82a59-121">这种用法与相关联的路由应指向 SIP 中继专用于紧急电话或路由紧急呼叫到接近公共安全应答点 (PSAP) 紧急位置识别号 (ELIN) 网关。</span><span class="sxs-lookup"><span data-stu-id="82a59-121">The route associated with this usage should point to a SIP trunk dedicated to emergency calls or to an Emergency Location Identification Number (ELIN) gateway that routes emergency calls to the nearest Public Safety Answering Point (PSAP).</span></span> <span data-ttu-id="82a59-122">选项是**内部**、**本地**或**远距离的位置**。</span><span class="sxs-lookup"><span data-stu-id="82a59-122">Options are **Internal**, **Local**, or **Long distance**.</span></span>
    
- <span data-ttu-id="82a59-123">**E9-1-1 拨号码**指定拨号连接紧急服务的数量。</span><span class="sxs-lookup"><span data-stu-id="82a59-123">**E9-1-1 dial number** Specify the number that is dialed to reach emergency services.</span></span>
    
- <span data-ttu-id="82a59-124">**E9-1-1 拨掩码**指定用户拨，然后转换成紧急拨数字的一个数字。</span><span class="sxs-lookup"><span data-stu-id="82a59-124">**E9-1-1 dial mask** Specify a number that a user dials, which is then translated into the emergency dial number.</span></span> <span data-ttu-id="82a59-125">例如，在此字段中输入值为 212，以便用户可以拨 212 到达紧急服务。</span><span class="sxs-lookup"><span data-stu-id="82a59-125">For example, enter a value of 212 in this field so that a user can dial 212 to reach emergency services.</span></span> <span data-ttu-id="82a59-126">这样就可以替代紧急号码拨打并且仍然有到达紧急服务的调用 (例如，如果有人从某个国家或地区具有不同的紧急号码试图拨打的国家或地区的数字而不是为数量国家或地区，他们目前在）。</span><span class="sxs-lookup"><span data-stu-id="82a59-126">This allows for alternate emergency numbers to be dialed and still have the call reach emergency services (for example, if someone from a country or region with a different emergency number attempts to dial that country or region's number rather than the number for the country or region they are currently in).</span></span> <span data-ttu-id="82a59-127">可以通过使用分号分隔值来定义多个紧急拨号掩码。</span><span class="sxs-lookup"><span data-stu-id="82a59-127">You can define multiple emergency dial masks by separating the values with semicolons.</span></span> <span data-ttu-id="82a59-128">例如，212;414。</span><span class="sxs-lookup"><span data-stu-id="82a59-128">For example, 212;414.</span></span> <span data-ttu-id="82a59-129">字符串的最大长度为 100 个字符。</span><span class="sxs-lookup"><span data-stu-id="82a59-129">The maximum length of the string is 100 characters.</span></span> <span data-ttu-id="82a59-130">每个字符都必须为 0 到 9 的数字。</span><span class="sxs-lookup"><span data-stu-id="82a59-130">Each character must be a digit 0 through 9.</span></span>
    
    > [!IMPORTANT]
    > <span data-ttu-id="82a59-131">确保拨号掩码与呼叫寄存号码范围中的号码不同，因为呼叫寄存路由将优先于紧急拨号字符串转换。</span><span class="sxs-lookup"><span data-stu-id="82a59-131">Make sure that the dial mask is not the same as a number in a call park number range, because call park routing takes precedence over emergency dial string conversion.</span></span> <span data-ttu-id="82a59-132">若要查看呼叫公园数字范围，在左侧的导航栏中，单击**语音功能**，再单击**呼叫公园**。</span><span class="sxs-lookup"><span data-stu-id="82a59-132">To see the Call Park number ranges, click **Voice Features** in the left navigation bar, and then click **Call Park**.</span></span> 
  
- <span data-ttu-id="82a59-133">**通知的 URI**指定进行紧急调用时要通知的一个或多个 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="82a59-133">**Notification URI** Specify one or more SIP URIs to be notified when an emergency call is made.</span></span> <span data-ttu-id="82a59-134">例如，键入公司安全办公室 SIP URI 进行紧急呼叫时通知安全人员使用即时消息。</span><span class="sxs-lookup"><span data-stu-id="82a59-134">For example, type the company security office's SIP URI to notify security staff with an instant message whenever an emergency call is made.</span></span> <span data-ttu-id="82a59-135">如果可用的呼叫者的位置，该位置将包括通知中。</span><span class="sxs-lookup"><span data-stu-id="82a59-135">If the caller's location is available, the location is included in the notification.</span></span> <span data-ttu-id="82a59-136">您可以以逗号分隔的列表形式指定多个 SIP Uri。</span><span class="sxs-lookup"><span data-stu-id="82a59-136">You can specify multiple SIP URIs as a comma-separated list.</span></span> <span data-ttu-id="82a59-137">例如，"sip:security@litwareinc.com"、"sip:kmyer@litwareinc.com"。</span><span class="sxs-lookup"><span data-stu-id="82a59-137">For example, "sip:security@litwareinc.com","sip:kmyer@litwareinc.com".</span></span> <span data-ttu-id="82a59-138">该字符串必须介于 1 到 256 个字符的长度，并必须以前缀开头"sip:"。</span><span class="sxs-lookup"><span data-stu-id="82a59-138">The string must be from 1 to 256 characters in length and must begin with the prefix "sip:".</span></span> <span data-ttu-id="82a59-139">您还可以指定通讯组列表。</span><span class="sxs-lookup"><span data-stu-id="82a59-139">You can also specify distribution lists.</span></span>
    
- <span data-ttu-id="82a59-140">**会议的 URI**第三方为 conferenced 中紧急调用指定 SIP URI （在此情况下，电话号码）。</span><span class="sxs-lookup"><span data-stu-id="82a59-140">**Conference URI** Specify the SIP URI (telephone number, in this case) for a third party to be conferenced in to emergency calls.</span></span> <span data-ttu-id="82a59-141">例如，键入公司安全办公室的电话号码，以便他们进行紧急调用时接收调用。</span><span class="sxs-lookup"><span data-stu-id="82a59-141">For example, type the company security office's phone number so that they receive a call when an emergency call is made.</span></span> <span data-ttu-id="82a59-142">**会议模式**的设置决定是否第三方可以参与或只是听电话。</span><span class="sxs-lookup"><span data-stu-id="82a59-142">The setting for **Conference mode** determines whether the third party can participate or just listen in to the call.</span></span> <span data-ttu-id="82a59-143">该字符串必须介于 1 到 256 个字符的长度，并必须以前缀 sip:。</span><span class="sxs-lookup"><span data-stu-id="82a59-143">The string must be from 1 to 256 characters in length and must begin with the prefix sip:.</span></span>
    
- <span data-ttu-id="82a59-144">**会议模式**如果**会议**uri 中指定一个值，则将此字段设置为以下值之一：</span><span class="sxs-lookup"><span data-stu-id="82a59-144">**Conference mode** If you specified a value for **Conference URI**, set this field to one of the following values:</span></span>
    
  - <span data-ttu-id="82a59-145">**单向**指定第三方可以只侦听调用方和 PSAP 运算符之间的调用。</span><span class="sxs-lookup"><span data-stu-id="82a59-145">**One-way** Specifies that the third party can only listen in to the call between the caller and the PSAP operator.</span></span>
    
  - <span data-ttu-id="82a59-146">**双向**指定第三方可以参与方和 PSAP 运算符之间的调用。</span><span class="sxs-lookup"><span data-stu-id="82a59-146">**Two-way** Specifies that the third party can participate in the call between the caller and the PSAP operator.</span></span>
    
<span data-ttu-id="82a59-147">企业语音紧急服务的特性和功能的详细信息，请参阅规划文档中[概述的 E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="82a59-147">For details about Enterprise Voice emergency service features and capabilities, see [Overview of E9-1-1](http://technet.microsoft.com/library/c01e6774-bc9f-4c5b-a60b-478b7317b2b7.aspx) in the Planning documentation.</span></span> <span data-ttu-id="82a59-148">有关使用位置策略的详细信息，请参阅操作文档中的[配置位置策略](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx)。</span><span class="sxs-lookup"><span data-stu-id="82a59-148">For details about working with location policies, see [Configuring Location Policy](http://technet.microsoft.com/library/14e41bcb-ea0a-49c2-99b3-1f61fc34416d.aspx) in the Operations documentation.</span></span>
  

