---
title: 'Lync Server 2013: 配置用于 Office Web Apps 服务器的客户端'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 263f53b61aa609c4385af2a9646bf84da2dea3cd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837273"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="12f93-102">配置 Lync Server 2013 客户端以与 Office Web Apps 服务器配合使用</span><span class="sxs-lookup"><span data-stu-id="12f93-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="12f93-103">_**主题上次修改时间:** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="12f93-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="12f93-104">如果你希望用户体验 Office Web App 服务器的完整功能, 则应将这些用户升级到 Microsoft Lync 2013;只有 Lync 2013 的用户才能像滚动浏览 PowerPoint 幻灯片, 而不是在实际的 PowerPoint 演示文稿中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="12f93-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="12f93-105">(也就是说, 这些用户可以随时查看演示文稿中的任何幻灯片, 而无需任何方式干扰实际演示文稿。)未使用 Lync 2013 的用户仍可以加入联机会议和查看 PowerPoint 演示文稿;但是, 他们无法单独滚动浏览幻灯片, 也不能查看幻灯片切换效果或查看嵌入的视频。</span><span class="sxs-lookup"><span data-stu-id="12f93-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="12f93-106">请注意, Lync 2013 的用户将始终可以使用这些功能;即使 PowerPoint 演示者运行的是 Microsoft Lync 2010, 也是如此。</span><span class="sxs-lookup"><span data-stu-id="12f93-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="12f93-107">如果 PowerPoint 演示文稿由运行 Lync 2010 的用户托管, 则 Lync Server 2013 将与 Office Web Apps 服务器协调, 以确保 Lync 2013 用户将查看该演示文稿的 Office Web Apps 服务器版本。</span><span class="sxs-lookup"><span data-stu-id="12f93-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="12f93-108">对于运行 Lync 2013 以外的客户端的用户, Office Web Apps 服务器不提供 PowerPoint 服务。</span><span class="sxs-lookup"><span data-stu-id="12f93-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="12f93-109">相反, 这些用户连接到会议服务器服务并以与在 Microsoft Lync Server 2010 中相同的方式查看 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="12f93-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="12f93-110">这还意味着, 这些用户将只能访问 Lync Server 2010 提供的更有限的功能。</span><span class="sxs-lookup"><span data-stu-id="12f93-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="12f93-111">虽然 Office Web Apps 服务器 (而不是升级到 Lync 2013 的用户) 不需要任何客户端配置, 但建议会议参与者升级到 Internet Explorer 9。</span><span class="sxs-lookup"><span data-stu-id="12f93-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="12f93-112">尽管可以使用 Internet Explorer 8 访问会议, 但使用该 Web 浏览器有一些限制。</span><span class="sxs-lookup"><span data-stu-id="12f93-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="12f93-113">例如, Internet Explorer 8 的用户将无法将 PowerPoint 阶段的大小调整为自定义大小;而是仅限于使用三个预定义的阶段大小之一。</span><span class="sxs-lookup"><span data-stu-id="12f93-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="12f93-114">同样, Internet Explorer 8 用户将不能播放媒体文件。</span><span class="sxs-lookup"><span data-stu-id="12f93-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

