---
title: 'Lync Server 2013: 持久聊天服务器 cmdlet'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat Server cmdlets
ms:assetid: 5aa59edb-db57-406f-9fbd-54bf1a55d31b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204920(v=OCS.15)
ms:contentKeyID: 48184226
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8f71b1f87c236384bd8ec22485981222c05bf4f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825224"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-cmdlets-in-lync-server-2013"></a><span data-ttu-id="dbe82-102">Lync Server 2013 中的持久聊天服务器 cmdlet</span><span class="sxs-lookup"><span data-stu-id="dbe82-102">Persistent Chat Server cmdlets in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dbe82-103">_**主题上次修改时间:** 2012-06-27_</span><span class="sxs-lookup"><span data-stu-id="dbe82-103">_**Topic Last Modified:** 2012-06-27_</span></span>

<span data-ttu-id="dbe82-104">利用永久聊天 cmdlet, 你可以管理和配置 Microsoft Lync Server 2013 持久聊天服务 (以前称为群组聊天服务)。</span><span class="sxs-lookup"><span data-stu-id="dbe82-104">The Persistent Chat cmdlets enable you to manage and configure the Microsoft Lync Server 2013 Persistent Chat service (formerly known as the Group Chat service).</span></span> <span data-ttu-id="dbe82-105">持久聊天使用户能够参与联机即时消息会话。</span><span class="sxs-lookup"><span data-stu-id="dbe82-105">Persistent Chat enables users to participate in online instant messaging sessions.</span></span> <span data-ttu-id="dbe82-106">虽然这些会话可以实时进行, 但每个会话的内容都是持久的;这意味着任何人都可以随时恢复这些对话。</span><span class="sxs-lookup"><span data-stu-id="dbe82-106">Although these sessions can take place in real time, the content of each session is persistent; that means these conversations can be resumed by anyone at any time.</span></span>

<div>

## <a name="persistent-chat-cmdlets"></a><span data-ttu-id="dbe82-107">持久聊天 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="dbe82-107">Persistent Chat Cmdlets</span></span>

<span data-ttu-id="dbe82-108">利用持久聊天 cmdlet, 你可以管理和配置 Lync Server 持久聊天服务。</span><span class="sxs-lookup"><span data-stu-id="dbe82-108">The Persistent Chat cmdlets enable you to manage and configure the Lync Server Persistent Chat service.</span></span>

<span data-ttu-id="dbe82-109">**持久聊天 Cmdlet**</span><span class="sxs-lookup"><span data-stu-id="dbe82-109">**Persistent Chat Cmdlets**</span></span>

  - <span data-ttu-id="dbe82-110">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-110">[Get-CsAdPrincipal](https://technet.microsoft.com/en-us/library/JJ205326(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-111">[Set-CsPersistentChatActiveServer](https://technet.microsoft.com/en-us/library/JJ205065(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-112">[Get-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204670(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-113">[New-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204641(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-114">[Remove-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ205350(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-115">[Set-CsPersistentChatAddin](https://technet.microsoft.com/en-us/library/JJ204721(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-116">[Get-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204771(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-117">[New-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204803(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-118">[Remove-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204660(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-119">[Set-CsPersistentChatCategory](https://technet.microsoft.com/en-us/library/JJ204952(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-120">[Get-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204625(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-121">[New-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ205163(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-122">[Remove-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204767(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-123">[Set-CsPersistentChatComplianceConfiguration](https://technet.microsoft.com/en-us/library/JJ204949(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-124">[Get-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205140(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-125">[New-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205330(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-126">[Remove-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ204927(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-127">[Set-CsPersistentChatConfiguration](https://technet.microsoft.com/en-us/library/JJ205122(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-128">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-128">[Export-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ205378(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-129">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-129">[Import-CsPersistentChatData](https://technet.microsoft.com/en-us/library/JJ204709(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-130">[Get-CsPersistentChatEligiblePrincipal](https://technet.microsoft.com/en-us/library/JJ204891(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-131">[Get-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204764(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-132">[New-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204811(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-133">[Remove-CsPersistentChatEndpoint](https://technet.microsoft.com/en-us/library/JJ204626(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-134">[Remove-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204668(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-135">[Test-CsPersistentChatMessage](https://technet.microsoft.com/en-us/library/JJ204656(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-136">[Get-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204673(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-137">[Grant-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ204907(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-138">[New-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205396(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-139">[Remove-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205301(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-140">[Set-CsPersistentChatPolicy](https://technet.microsoft.com/en-us/library/JJ205192(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-141">[Clear-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204976(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-142">[Get-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205123(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-143">[New-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ205166(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-144">[Remove-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204639(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-145">[Set-CsPersistentChatRoom](https://technet.microsoft.com/en-us/library/JJ204801(v=OCS.15))</span></span>

<!-- end list -->

  - <span data-ttu-id="dbe82-146">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-146">[Get-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ204915(v=OCS.15))</span></span>

  - <span data-ttu-id="dbe82-147">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span><span class="sxs-lookup"><span data-stu-id="dbe82-147">[Set-CsPersistentChatState](https://technet.microsoft.com/en-us/library/JJ205109(v=OCS.15))</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

