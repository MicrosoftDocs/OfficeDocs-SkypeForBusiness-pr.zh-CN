---
title: 'Lync Server 2013: 修改默认 URL 筛选器'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Modify the default URL filter
ms:assetid: 80a472b3-054e-45a6-80fc-9ee2bda28ee6
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg182544(v=OCS.15)
ms:contentKeyID: 48184653
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c95916729afc7d37dc195aeaa1a7ff214e28ca03
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826813"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="modify-the-default-url-filter-in-lync-server-2013"></a><span data-ttu-id="08e5c-102">在 Lync Server 2013 中修改默认 URL 筛选器</span><span class="sxs-lookup"><span data-stu-id="08e5c-102">Modify the default URL filter in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08e5c-103">_**主题上次修改时间:** 2012-06-26_</span><span class="sxs-lookup"><span data-stu-id="08e5c-103">_**Topic Last Modified:** 2012-06-26_</span></span>

<span data-ttu-id="08e5c-104">通过使用即时消息 (IM) 筛选器, Lync Server 2013 提供全局 URL 筛选器, 用于阻止在整个 Lync Server 2013 部署中的用户之间的 IM 对话中包含的特定 Url。</span><span class="sxs-lookup"><span data-stu-id="08e5c-104">By using the instant messaging (IM) filter, Lync Server 2013 provides a global URL filter that blocks specific URLs contained in IM conversations among users throughout your Lync Server 2013 deployment.</span></span> <span data-ttu-id="08e5c-105">通过使用 Lync Server "控制面板", 你可以执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="08e5c-105">By using Lync Server Control Panel, you can do the following:</span></span>

  - <span data-ttu-id="08e5c-106">在即时消息对话中阻止所有 Url 或 Url 的子集。</span><span class="sxs-lookup"><span data-stu-id="08e5c-106">Block all or a subset of URLs in instant message conversations.</span></span>

  - <span data-ttu-id="08e5c-107">允许所有 Url。</span><span class="sxs-lookup"><span data-stu-id="08e5c-107">Allow all URLs.</span></span> <span data-ttu-id="08e5c-108">作为一个选项, 你可以创建一个在包含 URL 的每个即时消息的开头插入的通知。</span><span class="sxs-lookup"><span data-stu-id="08e5c-108">As an option, you can create a notice that is inserted at the beginning of each instant message that contains a URL.</span></span>

  - <span data-ttu-id="08e5c-109">允许使用特定 Url, 并包含包含 URL 的每个即时消息的警告。</span><span class="sxs-lookup"><span data-stu-id="08e5c-109">Allow specific URLs and include a warning with each instant message that contains a URL.</span></span>

<span data-ttu-id="08e5c-110">此外, 你可以选择阻止包含特定文件类型的 Url, 或者通过允许服务器的本地 intranet 区域 (intranet Url) 内的 Url 通过服务器来阻止 Internet Url。</span><span class="sxs-lookup"><span data-stu-id="08e5c-110">In addition, you can choose to block URLs that contain specific file types, or block only Internet URLs by allowing URLs that are within the server’s local intranet zone — intranet URLs — to pass through the server.</span></span> <span data-ttu-id="08e5c-111">有关 URL 筛选的详细信息, 请参阅[在 Lync Server 2013 中为即时消息 (IM) 配置文件传输和 URL 筛选](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)。</span><span class="sxs-lookup"><span data-stu-id="08e5c-111">For details about URL filtering, see [Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md).</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="08e5c-112">另请参阅</span><span class="sxs-lookup"><span data-stu-id="08e5c-112">See Also</span></span>


[<span data-ttu-id="08e5c-113">在 Lync Server 2013 中为即时消息 (IM) 配置文件传输和 URL 筛选</span><span class="sxs-lookup"><span data-stu-id="08e5c-113">Configuring file transfer and URL filtering for instant messaging (IM) in Lync Server 2013</span></span>](lync-server-2013-configuring-file-transfer-and-url-filtering-for-instant-messaging-im.md)  
[<span data-ttu-id="08e5c-114">在 Lync Server 2013 中为特定网站创建新的文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="08e5c-114">Create a new file transfer filter in Lync Server 2013 for a specific site</span></span>](lync-server-2013-create-a-new-file-transfer-filter-for-a-specific-site.md)  
[<span data-ttu-id="08e5c-115">在 Lync Server 2013 中创建新的 URL 筛选器以处理即时消息对话中的超链接</span><span class="sxs-lookup"><span data-stu-id="08e5c-115">Create a new URL filter in Lync Server 2013 to handle hyperlinks in IM conversations</span></span>](lync-server-2013-create-a-new-url-filter-to-handle-hyperlinks-in-im-conversations.md)  
[<span data-ttu-id="08e5c-116">在 Lync Server 2013 中修改默认文件传输筛选器</span><span class="sxs-lookup"><span data-stu-id="08e5c-116">Modify the default file transfer filter in Lync Server 2013</span></span>](lync-server-2013-modify-the-default-file-transfer-filter.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

