---
title: Lync Server 2013：规划和部署视频
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning and deploying video
ms:assetid: dadfb7f3-dfd6-4847-b137-17dacafd7368
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205307(v=OCS.15)
ms:contentKeyID: 48185558
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2662a6397bc096969ca73baab096bc886de65ce3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755152"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="f8617-102">在 Lync Server 2013 中规划和部署视频</span><span class="sxs-lookup"><span data-stu-id="f8617-102">Planning and deploying video in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f8617-103">_**主题上次修改时间：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="f8617-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="f8617-104">Lync Server 2013 引入了以下新的视频功能：</span><span class="sxs-lookup"><span data-stu-id="f8617-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="f8617-105">**HD 视频**   用户可以在两方呼叫和多方会议中体验到完全高清（HD）（即，1920 x 1080）的分辨率。</span><span class="sxs-lookup"><span data-stu-id="f8617-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="f8617-106">\*\*\*\* 在包含两人以上的视频会议中，用户可以在会议中查看参与者的视频。   </span><span class="sxs-lookup"><span data-stu-id="f8617-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="f8617-107">如果会议具有超过五个参与者，则只有最活跃参与者的视频显示在顶部行中，并且其他参与者显示照片。</span><span class="sxs-lookup"><span data-stu-id="f8617-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="f8617-108">**H-p 视频**   现在，在 Lync 2013 客户端上编码视频的默认编码编解码器。</span><span class="sxs-lookup"><span data-stu-id="f8617-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="f8617-109">H-p 视频支持更大范围的分辨率和帧速率，并提高视频可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="f8617-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="f8617-110">Lync Server 2013 仍然支持 VC1 编解码器，用于与以前版本的 Lync 进行互操作。</span><span class="sxs-lookup"><span data-stu-id="f8617-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="f8617-111">有关新视频编解码器的详细信息和背景信息，请参阅 Jeff Schertz 的博客文章 "Lync 2013 中的视频互操作<A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>性"。</span><span class="sxs-lookup"><span data-stu-id="f8617-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="f8617-112">本部分介绍如何在 Lync Server 2013 中管理视频的带宽以及如何配置视频功能。</span><span class="sxs-lookup"><span data-stu-id="f8617-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="f8617-113">本节内容</span><span class="sxs-lookup"><span data-stu-id="f8617-113">In This Section</span></span>

  - [<span data-ttu-id="f8617-114">在 Lync Server 2013 中配置视频带宽</span><span class="sxs-lookup"><span data-stu-id="f8617-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="f8617-115">在 Lync Server 2013 中配置库视图</span><span class="sxs-lookup"><span data-stu-id="f8617-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="f8617-116">配置 Lync Server 2013 的视频示例方案</span><span class="sxs-lookup"><span data-stu-id="f8617-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="f8617-117">Lync Server 2013 中的视频会议的互操作性注意事项</span><span class="sxs-lookup"><span data-stu-id="f8617-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

