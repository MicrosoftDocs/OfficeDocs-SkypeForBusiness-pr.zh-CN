---
title: Lync Server 2013：向即时消息添加自定义文本
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Adding custom text to instant messages
ms:assetid: cabcc3ec-9d35-42ac-a403-e21b7d538c2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398847(v=OCS.15)
ms:contentKeyID: 48185458
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0681df9803615fee04c20e52258120bd6616e57d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42038564"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="adding-custom-text-to-instant-messages-in-lync-server-2013"></a><span data-ttu-id="056ee-102">在 Lync Server 2013 中向即时消息添加自定义文本</span><span class="sxs-lookup"><span data-stu-id="056ee-102">Adding custom text to instant messages in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="056ee-103">_**上次修改的主题：** 2013-02-20_</span><span class="sxs-lookup"><span data-stu-id="056ee-103">_**Topic Last Modified:** 2013-02-20_</span></span>

<span data-ttu-id="056ee-104">通过使用 Set-csclientpolicy 或**Set-csclientpolicy** Lync Server 命令行管理**程序**cmdlet 和 IMWarning 参数，将免责声明或警告添加到每个 Lync 2013 即时消息（IM）对话的开头。</span><span class="sxs-lookup"><span data-stu-id="056ee-104">Add a disclaimer or warning to the beginning of every Lync 2013 instant messaging (IM) conversation by using the **New-CSClientPolicy** or **Set-CSClientPolicy** Lync Server Management Shell cmdlets with the IMWarning parameter.</span></span>

<span data-ttu-id="056ee-105">以下示例中的命令会在新的 IM 对话开始时，在“对话”窗口的顶部添加安全提醒：</span><span class="sxs-lookup"><span data-stu-id="056ee-105">The command in the following example adds a security reminder at the top of the Conversation window whenever a new IM conversation begins:</span></span>

    New-CsClientPolicy -Identity IMSecurityNotice -IMWarning 
    "Remember, security is everyone's responsibility. Keep it confidential."

<span data-ttu-id="056ee-106">使用 **Grant-CSClientPolicy** 将此新策略分配给用户。</span><span class="sxs-lookup"><span data-stu-id="056ee-106">Use **Grant-CSClientPolicy** to assign this new policy to users.</span></span> <span data-ttu-id="056ee-107">有关详细信息，请参阅 Lync Server 命令行管理程序文档中的**set-csclientpolicy**和**Grant set-csclientpolicy** 。</span><span class="sxs-lookup"><span data-stu-id="056ee-107">For details, see **New-CSClientPolicy** and **Grant-CSClientPolicy** in the Lync Server Management Shell documentation.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

