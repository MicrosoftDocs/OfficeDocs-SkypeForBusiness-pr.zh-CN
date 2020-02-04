---
title: Lync Server 2013：新的语音邮件功能
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New voice mail feature
ms:assetid: 84d13238-67ef-42cc-801a-2d8147ba3b7f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688117(v=OCS.15)
ms:contentKeyID: 49733715
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 27dbea942488181eb69695f78713c9e126c32aab
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755846"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-voice-mail-feature-in-lync-server-2013"></a><span data-ttu-id="75ec7-102">Lync Server 2013 中新的语音邮件功能</span><span class="sxs-lookup"><span data-stu-id="75ec7-102">New voice mail feature in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="75ec7-103">_**主题上次修改时间：** 2012-10-05_</span><span class="sxs-lookup"><span data-stu-id="75ec7-103">_**Topic Last Modified:** 2012-10-05_</span></span>

<span data-ttu-id="75ec7-104">Lync Server 2013 引入了语音邮件转义，它是管理语音邮件的增强功能。</span><span class="sxs-lookup"><span data-stu-id="75ec7-104">Lync Server 2013 introduces Voice mail Escape, an enhancement for managing voice mail.</span></span> <span data-ttu-id="75ec7-105">此新功能可以检测何时已将呼叫路由到语音邮件，并阻止呼叫立即路由到用户的移动电话语音邮件，而无需让用户有机会接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="75ec7-105">This new feature can detect when a call has been routed to voice mail, and prevent the call from being immediately routed to the user’s mobile phone voice mail without giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="75ec7-106">当用户允许同时拨打其移动电话，并且其移动电话已关闭、电池电量不足或超出范围时，会出现此情况。</span><span class="sxs-lookup"><span data-stu-id="75ec7-106">This scenario occurs when the user enables simultaneous ringing to their mobile phone, and their mobile phone is turned off, out of battery, or out of range.</span></span> <span data-ttu-id="75ec7-107">语音邮件 Escape 检测到呼叫已由用户的移动电话语音邮件立即应答，并断开与移动电话语音邮件的通话。</span><span class="sxs-lookup"><span data-stu-id="75ec7-107">Voicemail Escape detects that the call was immediately answered by the user’s mobile phone voice mail, and disconnects the call to the mobile phone voice mail.</span></span> <span data-ttu-id="75ec7-108">通话继续在用户的其他终结点上响铃，让用户有机会接听呼叫。</span><span class="sxs-lookup"><span data-stu-id="75ec7-108">The call continues to ring on the user’s other endpoints giving the user the opportunity to answer the call.</span></span> <span data-ttu-id="75ec7-109">如果用户不接听呼叫，则呼叫将路由到公司语音邮件。</span><span class="sxs-lookup"><span data-stu-id="75ec7-109">If the user does not answer the call, then the call is routed to the corporate voice mail.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="75ec7-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="75ec7-110">See Also</span></span>


[<span data-ttu-id="75ec7-111">在 Lync Server 2013 中配置语音邮件转义</span><span class="sxs-lookup"><span data-stu-id="75ec7-111">Configuring voice mail escape in Lync Server 2013</span></span>](lync-server-2013-configuring-voice-mail-escape.md)  


[<span data-ttu-id="75ec7-112">Lync Server 2013 中新的企业语音功能</span><span class="sxs-lookup"><span data-stu-id="75ec7-112">New Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-new-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

