---
title: Lync Server 2013：托管 Exchange 用户管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ead9762c67f3239f84cc1290b4ff2e9acc976318
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830063"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="4c947-102">Lync Server 2013 中的托管 Exchange 用户管理</span><span class="sxs-lookup"><span data-stu-id="4c947-102">Hosted Exchange user management in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c947-103">_**主题上次修改时间:** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="4c947-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="4c947-104">若要为 Lync Server 2013 用户提供其邮箱位于托管 Exchange 服务上的语音邮件服务, 必须为托管语音邮件启用其用户帐户。</span><span class="sxs-lookup"><span data-stu-id="4c947-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4c947-105">在 Lync Server 2013 用户可启用托管语音邮件之前, 必须部署适用于相应用户帐户的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="4c947-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="4c947-106">策略可以是全局、网站或每用户在范围内, 只要它适用于要启用的用户。</span><span class="sxs-lookup"><span data-stu-id="4c947-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="4c947-107">有关详细信息, 请参阅<A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。</span><span class="sxs-lookup"><span data-stu-id="4c947-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="4c947-108">MsExchUCVoiceMailSettings 属性</span><span class="sxs-lookup"><span data-stu-id="4c947-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="4c947-109">Lync Server 2013 引入了名为**msExchUCVoiceMailSettings**的新用户属性, 该属性是作为 Lync Server 2013 Active Directory 架构准备的一部分创建的。</span><span class="sxs-lookup"><span data-stu-id="4c947-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="4c947-110">此多值属性包含由 Lync Server 2013 和托管 Exchange 服务共享的语音邮件设置。</span><span class="sxs-lookup"><span data-stu-id="4c947-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="4c947-111">在某些情况下, 托管 Exchange 服务可能会在启用 Exchange UM 的过程中或在将邮箱传输到托管 Exchange 服务器的过程中设置 msExchUCVoiceMailSettings 属性的值。</span><span class="sxs-lookup"><span data-stu-id="4c947-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="4c947-112">如果此属性不是由 Exchange 设置的, 则 Lync Server 2013 管理员必须通过运行 Move-csuser cmdlet 来设置它, 如本主题中前面所述。</span><span class="sxs-lookup"><span data-stu-id="4c947-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="4c947-113">属性的键/值对及其作者如下表所示。</span><span class="sxs-lookup"><span data-stu-id="4c947-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="4c947-114">MsExchUCVoiceMailSettings 属性键/值对</span><span class="sxs-lookup"><span data-stu-id="4c947-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4c947-115">值</span><span class="sxs-lookup"><span data-stu-id="4c947-115">Value</span></span></th>
<th><span data-ttu-id="4c947-116">授权</span><span class="sxs-lookup"><span data-stu-id="4c947-116">Author</span></span></th>
<th><span data-ttu-id="4c947-117">含义</span><span class="sxs-lookup"><span data-stu-id="4c947-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c947-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="4c947-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="4c947-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="4c947-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="4c947-120">用户已为 Exchange Server 启用托管 UM 访问。</span><span class="sxs-lookup"><span data-stu-id="4c947-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="4c947-121">Exchange UM 路由应用程序将检查用户的托管语音邮件策略中是否有路由详细信息。</span><span class="sxs-lookup"><span data-stu-id="4c947-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c947-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="4c947-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="4c947-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="4c947-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="4c947-124">Exchange Server 的托管 UM 访问已禁用用户。</span><span class="sxs-lookup"><span data-stu-id="4c947-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c947-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="4c947-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="4c947-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="4c947-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="4c947-127">用户已为 Lync Server 2013 启用托管 UM 访问。</span><span class="sxs-lookup"><span data-stu-id="4c947-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="4c947-128">Lync Server 2013 ExUM 路由应用程序将检查用户的托管语音邮件策略中是否有路由详细信息。</span><span class="sxs-lookup"><span data-stu-id="4c947-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c947-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="4c947-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="4c947-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="4c947-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="4c947-131">Lync Server 2013 已禁用 "托管 UM 访问" 用户。</span><span class="sxs-lookup"><span data-stu-id="4c947-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="4c947-132">如果该属性已具有除 Lync Server 2013 键/值对之外的值 (CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1), 则会出现一个警告, 指示该属性可能由其他应用程序管理。</span><span class="sxs-lookup"><span data-stu-id="4c947-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="4c947-133">例如, 如果 key/value 对 ExchangeHostedVoiceMail = 0 或 ExchangeHostedVoiceMail = 1 已存在, 则会显示警告。</span><span class="sxs-lookup"><span data-stu-id="4c947-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="4c947-134">在这种情况下, 你可以通过编辑 Active Directory 来更改该值, 或者运行以下 cmdlet 以将该值设置为 null:</span><span class="sxs-lookup"><span data-stu-id="4c947-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="4c947-135">Move-csuser-身份识别用户-HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="4c947-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="4c947-136">为用户启用托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="4c947-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="4c947-137">若要使用户的语音邮件呼叫能够路由到托管 Exchange UM, 必须运行 Move-csuser cmdlet 以设置*HostedVoiceMail*参数的值。</span><span class="sxs-lookup"><span data-stu-id="4c947-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="4c947-138">此参数还会向 Lync Server 2013 发出信号, 以突出 "呼叫语音邮件" 指示器。</span><span class="sxs-lookup"><span data-stu-id="4c947-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="4c947-139">以下示例为托管语音邮件启用 Pilar Ackerman 的用户帐户:</span><span class="sxs-lookup"><span data-stu-id="4c947-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="4c947-140">该 cmdlet 验证托管的语音邮件策略 (全局、网站级别或每用户) 是否适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="4c947-140">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="4c947-141">如果未应用任何策略, 则 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="4c947-141">If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="4c947-142">以下示例将禁用托管语音邮件的 Pilar Ackerman 用户帐户:</span><span class="sxs-lookup"><span data-stu-id="4c947-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="4c947-143">该 cmdlet 验证任何托管语音邮件策略 (全局、网站级别或每用户) 是否适用于此用户。</span><span class="sxs-lookup"><span data-stu-id="4c947-143">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user.</span></span> <span data-ttu-id="4c947-144">如果应用了策略, 则 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="4c947-144">If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="4c947-145">有关使用 Move-csuser cmdlet 的详细信息, 请参阅 Lync Server Management Shell 文档。</span><span class="sxs-lookup"><span data-stu-id="4c947-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

