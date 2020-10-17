---
title: Lync Server 2013：托管 Exchange 用户管理
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hosted Exchange user management
ms:assetid: e8723af5-0604-4d7d-bad2-463a9832efb4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg399037(v=OCS.15)
ms:contentKeyID: 48185887
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e4a54c4a7a3833fdd31999d7613659f9a35f9732
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48504199"
---
# <a name="hosted-exchange-user-management-in-lync-server-2013"></a><span data-ttu-id="53d4a-102">Lync Server 2013 中的托管 Exchange 用户管理</span><span class="sxs-lookup"><span data-stu-id="53d4a-102">Hosted Exchange user management in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53d4a-103">_**上次修改的主题：** 2012-10-18_</span><span class="sxs-lookup"><span data-stu-id="53d4a-103">_**Topic Last Modified:** 2012-10-18_</span></span>

<span data-ttu-id="53d4a-104">若要为其邮箱位于托管 Exchange 服务上的 Lync Server 2013 用户提供语音邮件服务，必须为其用户帐户启用托管语音邮件。</span><span class="sxs-lookup"><span data-stu-id="53d4a-104">To provide voice mail services for Lync Server 2013 users whose mailboxes are located on a hosted Exchange service, you must enable their user accounts for hosted voice mail.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="53d4a-105">在可以对 Lync Server 2013 用户启用托管语音邮件之前，必须部署适用于相应用户帐户的托管语音邮件策略。</span><span class="sxs-lookup"><span data-stu-id="53d4a-105">Before a Lync Server 2013 user can be enabled for hosted voice mail, a hosted voice mail policy that applies to the corresponding user account must be deployed.</span></span> <span data-ttu-id="53d4a-106">该策略的作用域可以是 global、site 或每用户，只要适用于要启用的用户即可。</span><span class="sxs-lookup"><span data-stu-id="53d4a-106">The policy can be global, site, or per-user in scope, as long as it applies to the user whom you want to enable.</span></span> <span data-ttu-id="53d4a-107">有关详细信息，请参阅 <A href="lync-server-2013-hosted-voice-mail-policies.md">Lync Server 2013 中的托管语音邮件策略</A>。</span><span class="sxs-lookup"><span data-stu-id="53d4a-107">For details, see <A href="lync-server-2013-hosted-voice-mail-policies.md">Hosted voice mail policies in Lync Server 2013</A>.</span></span>



</div>

<div>

## <a name="the-msexchucvoicemailsettings-attribute"></a><span data-ttu-id="53d4a-108">msExchUCVoiceMailSettings 属性</span><span class="sxs-lookup"><span data-stu-id="53d4a-108">The msExchUCVoiceMailSettings Attribute</span></span>

<span data-ttu-id="53d4a-109">Lync Server 2013 引入了一个名为 **msExchUCVoiceMailSettings**的新用户属性，该属性是作为 Lync Server 2013 Active Directory 架构准备的一部分创建的。</span><span class="sxs-lookup"><span data-stu-id="53d4a-109">Lync Server 2013 introduces a new user attribute named **msExchUCVoiceMailSettings**, which is created as part of the Lync Server 2013 Active Directory schema preparation.</span></span> <span data-ttu-id="53d4a-110">此多值属性保存由 Lync Server 2013 和托管 Exchange 服务共享的语音邮件设置。</span><span class="sxs-lookup"><span data-stu-id="53d4a-110">This multivalued attribute holds voice mail settings that are shared by Lync Server 2013 and the hosted Exchange service.</span></span>

<span data-ttu-id="53d4a-111">在某些情况下，托管 Exchange 服务可能会在启用 Exchange UM 或在将邮箱传输到托管 Exchange Server 的过程中设置 msExchUCVoiceMailSettings 属性的值。</span><span class="sxs-lookup"><span data-stu-id="53d4a-111">The hosted Exchange service may in some cases set the value of the msExchUCVoiceMailSettings attribute in the process of enabling Exchange UM, or during the process of transferring mailboxes to a hosted Exchange Server.</span></span> <span data-ttu-id="53d4a-112">如果 Exchange 不设置此属性，则 Lync Server 2013 管理员必须通过运行 Set-CsUser cmdlet 来设置它，如本主题前面所述。</span><span class="sxs-lookup"><span data-stu-id="53d4a-112">If this attribute is not set by Exchange, the Lync Server 2013 administrator must set it by running the Set-CsUser cmdlet, as described earlier in this topic.</span></span>

<span data-ttu-id="53d4a-113">该属性的键/值对及其作者显示在下表中。</span><span class="sxs-lookup"><span data-stu-id="53d4a-113">The attribute’s key/value pairs and their authors are shown in the following table.</span></span>

### <a name="the-msexchucvoicemailsettings-attribute-keyvalue-pairs"></a><span data-ttu-id="53d4a-114">msExchUCVoiceMailSettings 属性键/值对</span><span class="sxs-lookup"><span data-stu-id="53d4a-114">The msExchUCVoiceMailSettings Attribute Key/Value Pairs</span></span>

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="53d4a-115">值</span><span class="sxs-lookup"><span data-stu-id="53d4a-115">Value</span></span></th>
<th><span data-ttu-id="53d4a-116">作者</span><span class="sxs-lookup"><span data-stu-id="53d4a-116">Author</span></span></th>
<th><span data-ttu-id="53d4a-117">含义</span><span class="sxs-lookup"><span data-stu-id="53d4a-117">Meaning</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="53d4a-118">ExchangeHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="53d4a-118">ExchangeHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="53d4a-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="53d4a-119">Exchange</span></span></p></td>
<td><p><span data-ttu-id="53d4a-120">Exchange Server 已为用户启用托管 UM 访问。</span><span class="sxs-lookup"><span data-stu-id="53d4a-120">User has been enabled for hosted UM access by Exchange Server.</span></span> <span data-ttu-id="53d4a-121">Exchange UM 路由应用程序将检查用户的托管语音邮件策略以了解路由详细信息。</span><span class="sxs-lookup"><span data-stu-id="53d4a-121">The Exchange UM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d4a-122">ExchangeHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="53d4a-122">ExchangeHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="53d4a-123">Exchange</span><span class="sxs-lookup"><span data-stu-id="53d4a-123">Exchange</span></span></p></td>
<td><p><span data-ttu-id="53d4a-124">Exchange Server 已为用户禁用托管 UM 访问。</span><span class="sxs-lookup"><span data-stu-id="53d4a-124">User has been disabled for hosted UM access by Exchange Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="53d4a-125">CsHostedVoiceMail = 1</span><span class="sxs-lookup"><span data-stu-id="53d4a-125">CsHostedVoiceMail=1</span></span></p></td>
<td><p><span data-ttu-id="53d4a-126">Lync Server</span><span class="sxs-lookup"><span data-stu-id="53d4a-126">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="53d4a-127">用户已为 Lync Server 2013 启用了托管 UM 访问。</span><span class="sxs-lookup"><span data-stu-id="53d4a-127">User has been enabled for hosted UM access by Lync Server 2013.</span></span> <span data-ttu-id="53d4a-128">Lync Server 2013 ExUM 路由应用程序将检查用户的托管语音邮件策略以了解路由详细信息。</span><span class="sxs-lookup"><span data-stu-id="53d4a-128">The Lync Server 2013 ExUM Routing application will check the user’s hosted voice mail policy for routing details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="53d4a-129">CsHostedVoiceMail = 0</span><span class="sxs-lookup"><span data-stu-id="53d4a-129">CsHostedVoiceMail=0</span></span></p></td>
<td><p><span data-ttu-id="53d4a-130">Lync Server</span><span class="sxs-lookup"><span data-stu-id="53d4a-130">Lync Server</span></span></p></td>
<td><p><span data-ttu-id="53d4a-131">已为 Lync Server 2013 禁用托管 UM 访问的用户。</span><span class="sxs-lookup"><span data-stu-id="53d4a-131">User has been disabled for hosted UM access by Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> <span data-ttu-id="53d4a-132">如果该属性已经有一个除 Lync Server 2013 键/值对之外的值 (CSHostedVoiceMail = 0 或 CSHostedVoiceMail = 1) ，则将显示一条警告，指示该属性可能由不同的应用程序管理。</span><span class="sxs-lookup"><span data-stu-id="53d4a-132">If the attribute already has values other than one of the Lync Server 2013 key/value pairs (CSHostedVoiceMail=0 or CSHostedVoiceMail=1), a warning will indicate that the attribute may be managed by a different application.</span></span> <span data-ttu-id="53d4a-133">例如，如果键/值对 ExchangeHostedVoiceMail=0 或 ExchangeHostedVoiceMail=1 已存在，则显示警告。</span><span class="sxs-lookup"><span data-stu-id="53d4a-133">For example, a warning is displayed if the key/value pair ExchangeHostedVoiceMail=0 or ExchangeHostedVoiceMail=1 is already present.</span></span> <span data-ttu-id="53d4a-134">在这种情况下，可以通过在 Active Directory 中编辑来更改值，或运行以下 cmdlet 将值设置为 null：</span><span class="sxs-lookup"><span data-stu-id="53d4a-134">In that case, you can change the value by editing it the Active Directory, or run the following cmdlet to set the value to null:</span></span><BR><span data-ttu-id="53d4a-135">Set-CsUser –identity user –HostedVoicemail $null</span><span class="sxs-lookup"><span data-stu-id="53d4a-135">Set-CsUser –identity user –HostedVoicemail $null</span></span>



</div>

</div>

<div>

## <a name="enabling-users-for-hosted-voice-mail"></a><span data-ttu-id="53d4a-136">为用户启用托管语音邮件</span><span class="sxs-lookup"><span data-stu-id="53d4a-136">Enabling Users for Hosted Voice Mail</span></span>

<span data-ttu-id="53d4a-137">要使用户的语音邮件呼叫可以路由到托管 Exchange UM，必须运行 Set-CsUser cmdlet 来设置 *HostedVoiceMail* 参数的值。</span><span class="sxs-lookup"><span data-stu-id="53d4a-137">To enable a user’s voice mail calls to be routed to hosted Exchange UM, you must run the Set-CsUser cmdlet to set the value of the *HostedVoiceMail* parameter.</span></span> <span data-ttu-id="53d4a-138">此参数还会向 Lync Server 2013 发出信号，以使 "呼叫语音邮件" 指示器亮起来。</span><span class="sxs-lookup"><span data-stu-id="53d4a-138">This parameter also signals Lync Server 2013 to light up the “call voice mail” indicator.</span></span>

  - <span data-ttu-id="53d4a-139">以下示例为 Pilar Ackerman 的用户帐户启用托管语音邮件：</span><span class="sxs-lookup"><span data-stu-id="53d4a-139">The following example enables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $True
    
    <span data-ttu-id="53d4a-p108">该 cmdlet 验证是否有适用于该用户的托管语音邮件策略（全局、站点级别或每用户）。如果没有适用的策略，该 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="53d4a-p108">The cmdlet verifies that a hosted voice mail policy (global, site-level or per-user) applies to this user. If no policy applies, the cmdlet fails.</span></span>

  - <span data-ttu-id="53d4a-142">以下示例为 Pilar Ackerman 的用户帐户禁用托管语音邮件：</span><span class="sxs-lookup"><span data-stu-id="53d4a-142">The following example disables Pilar Ackerman’s user account for hosted voice mail:</span></span>
    
        Set-CsUser -Identity "Pilar Ackerman" -HostedVoiceMail $False
    
    <span data-ttu-id="53d4a-p109">该 cmdlet 验证是否没有适用于该用户的托管语音邮件策略（全局、站点级别或每用户）。如果有适用的策略，该 cmdlet 将失败。</span><span class="sxs-lookup"><span data-stu-id="53d4a-p109">The cmdlet verifies that no hosted voice mail policy (global, site-level or per-user) applies to this user. If a policy does apply, the cmdlet fails.</span></span>

<span data-ttu-id="53d4a-145">有关使用 Set-CsUser cmdlet 的详细信息，请参阅 Lync Server 命令行管理程序文档。</span><span class="sxs-lookup"><span data-stu-id="53d4a-145">For details about using the Set-CsUser cmdlet, see the Lync Server Management Shell documentation.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

