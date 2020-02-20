---
title: Lync Server 2013：配置客户端以用于 Office Web Apps Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring clients for use with Office Web Apps Server
ms:assetid: e5eaead7-0b32-42fb-97eb-ca203af59a9d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205339(v=OCS.15)
ms:contentKeyID: 48185668
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 10ec5ddaca5a8409a18504cb73912d107c9a6455
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146965"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-clients-of-lync-server-2013-for-use-with-office-web-apps-server"></a><span data-ttu-id="74e5d-102">配置用于 Office Web Apps Server 的 Lync Server 2013 客户端</span><span class="sxs-lookup"><span data-stu-id="74e5d-102">Configuring clients of Lync Server 2013 for use with Office Web Apps Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="74e5d-103">_**上次修改的主题：** 2013-02-25_</span><span class="sxs-lookup"><span data-stu-id="74e5d-103">_**Topic Last Modified:** 2013-02-25_</span></span>

<span data-ttu-id="74e5d-104">如果您希望用户体验 Office Web App Server 的全部功能，则应将这些用户升级到 Microsoft Lync 2013;只有 Lync 2013 的用户才能通过独立于实际 PowerPoint 演示文稿的 PowerPoint 幻灯片进行滚动来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="74e5d-104">If you want users to experience the full capabilities of Office Web App Server then you should upgrade those users to Microsoft Lync 2013; only users of Lync 2013 will be able to do such things as scroll through PowerPoint slides independent of the actual PowerPoint presentation.</span></span> <span data-ttu-id="74e5d-105">（即，这些用户可以随时查看演示文稿中的任何幻灯片，而不会妨碍实际演示文稿的任何方式。）未使用 Lync 2013 的用户仍可以加入联机会议并查看 PowerPoint 演示文稿;但是，它们不能独立滚动幻灯片，也不能查看幻灯片切换或查看嵌入的视频。</span><span class="sxs-lookup"><span data-stu-id="74e5d-105">(That is, these users can look at any slide in the presentation at any time, without interfering in any way with the actual presentation.) Users who are not using Lync 2013 will still be able to join online conferences and view the PowerPoint presentation; however, they will not be able to independently scroll through the slides, nor will they be able to see slide transitions or view embedded videos.</span></span>

<span data-ttu-id="74e5d-106">请注意，Lync 2013 的用户将始终可以使用这些功能。即使 PowerPoint 演示者运行的是 Microsoft Lync 2010，也是如此。</span><span class="sxs-lookup"><span data-stu-id="74e5d-106">Note that these capabilities will always be available to users of Lync 2013; this is true even if the PowerPoint presenter is running Microsoft Lync 2010.</span></span> <span data-ttu-id="74e5d-107">如果 PowerPoint 演示文稿由运行 Lync 2010 的用户托管，则 Lync Server 2013 将与 Office Web Apps Server 进行协调，以确保 Lync 2013 用户将查看该演示文稿的 Office Web Apps Server 版本。</span><span class="sxs-lookup"><span data-stu-id="74e5d-107">If a PowerPoint presentation is being hosted by a user running Lync 2010, Lync Server 2013 will coordinate with Office Web Apps Server to make sure that Lync 2013 users will view the Office Web Apps Server version of that presentation.</span></span> <span data-ttu-id="74e5d-108">Office Web Apps Server 不会为运行 Lync 2013 之外的客户端的用户提供 PowerPoint 服务。</span><span class="sxs-lookup"><span data-stu-id="74e5d-108">Office Web Apps Server does not provide PowerPoint services for users running clients other than Lync 2013.</span></span> <span data-ttu-id="74e5d-109">相反，这些用户连接到会议服务器服务并以与在 Microsoft Lync Server 2010 中相同的方式查看 PowerPoint 演示文稿。</span><span class="sxs-lookup"><span data-stu-id="74e5d-109">Instead, those users connect to the Conferencing server service and view PowerPoint presentations the same way they did in Microsoft Lync Server 2010.</span></span> <span data-ttu-id="74e5d-110">这也意味着这些用户将只能访问 Lync Server 2010 提供的更有限的功能。</span><span class="sxs-lookup"><span data-stu-id="74e5d-110">This also means that these users will only have access to the more-limited capabilities offered by Lync Server 2010.</span></span>

<span data-ttu-id="74e5d-111">虽然 Office Web Apps Server （而不是将用户升级到 Lync 2013）不需要客户端配置，但建议会议参与者升级到 Internet Explorer 9。</span><span class="sxs-lookup"><span data-stu-id="74e5d-111">Although no client configuration is required for Office Web Apps Server (other than upgrading users to Lync 2013), it is recommended that conference attendees be upgrade to Internet Explorer 9.</span></span> <span data-ttu-id="74e5d-112">尽管可使用 Internet Explorer 8 访问会议，但对使用 Web 浏览器有一些限制。</span><span class="sxs-lookup"><span data-stu-id="74e5d-112">Although conferences can be accessed using Internet Explorer 8, there are some limitations to using that Web browser.</span></span> <span data-ttu-id="74e5d-113">例如，Internet Explorer 8 的用户无法将 PowerPoint 阶段的大小重新调整为自定义大小；而是将其限制为使用三个预定义阶段大小之一。</span><span class="sxs-lookup"><span data-stu-id="74e5d-113">For example, users of Internet Explorer 8 will not be able to resize the PowerPoint stage to a custom size; instead, they will be limited to using one of three predefined stage sizes.</span></span> <span data-ttu-id="74e5d-114">Internet Explorer 8 用户将很有可能无法播放媒体文件。</span><span class="sxs-lookup"><span data-stu-id="74e5d-114">Likewise, Internet Explorer 8 users will not be able to play media files.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

