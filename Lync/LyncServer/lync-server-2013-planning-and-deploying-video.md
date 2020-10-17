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
ms.openlocfilehash: bf5eca9118c9f4706aa209dc1e2db1b3dbbed358
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48519809"
---
# <a name="planning-and-deploying-video-in-lync-server-2013"></a><span data-ttu-id="c3d88-102">在 Lync Server 2013 中规划和部署视频</span><span class="sxs-lookup"><span data-stu-id="c3d88-102">Planning and deploying video in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3d88-103">_**上次修改的主题：** 2012-10-02_</span><span class="sxs-lookup"><span data-stu-id="c3d88-103">_**Topic Last Modified:** 2012-10-02_</span></span>

<span data-ttu-id="c3d88-104">Lync Server 2013 引入了以下新的视频功能：</span><span class="sxs-lookup"><span data-stu-id="c3d88-104">Lync Server 2013 introduces the following new video features:</span></span>

  - <span data-ttu-id="c3d88-105">**HD 视频**    在两方呼叫和多方会议中，用户可以体验到完整高清晰度 (HD)  (即 1920 x 1080) 的分辨率。</span><span class="sxs-lookup"><span data-stu-id="c3d88-105">**HD video**   Users can experience resolutions up to full high definition (HD) (that is, 1920 x 1080) in two-party calls and multiparty conferences.</span></span>

  - <span data-ttu-id="c3d88-106">**库视图**    在包含两人以上的视频会议中，用户可以在会议中看到参与者的视频。</span><span class="sxs-lookup"><span data-stu-id="c3d88-106">**Gallery View**   In video conferences that have more than two people, users can see videos of participants in the conference.</span></span> <span data-ttu-id="c3d88-107">如果会议具有五个以上的参与者，则最活跃参与者的视频将显示在顶部行中，并显示其他参与者的照片。</span><span class="sxs-lookup"><span data-stu-id="c3d88-107">If the conference has more than five participants, video of only the most active participants appears in the top row, and a photo appears for the other participants.</span></span>

  - <span data-ttu-id="c3d88-108">**H-p 视频**    目前，在 Lync 2013 客户端上对视频进行编码的默认视频编解码器是默认编码解码器。</span><span class="sxs-lookup"><span data-stu-id="c3d88-108">**H.264 video**   The H.264 video codec is now the default for encoding video on Lync 2013 clients.</span></span> <span data-ttu-id="c3d88-109">H.264 视频支持范围更广的分辨率和帧速率，并改进了视频可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="c3d88-109">H.264 video supports a greater range of resolutions and frame rates, and improves video scalability.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c3d88-110">Lync Server 2013 仍支持 VC1 编解码器，以实现与 Lync 早期版本的互操作性。</span><span class="sxs-lookup"><span data-stu-id="c3d88-110">Lync Server 2013 still supports the VC1 codec for interoperability with previous versions of Lync.</span></span> <span data-ttu-id="c3d88-111">有关新视频编解码器的详细信息和背景信息，请参阅李明 Schertz 博客文章 "Lync 2013 中的视频互操作性"，网址为 <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A> 。</span><span class="sxs-lookup"><span data-stu-id="c3d88-111">For details and background information about the new video codec, see Jeff Schertz's Blog article, "Video Interoperability in Lync 2013," at <A class=uri href="http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/">http://blog.schertz.name/2012/07/video-interoperability-in-lync-2013/</A>.</span></span>

    
    </div>

<span data-ttu-id="c3d88-112">本节介绍如何在 Lync Server 2013 中管理视频的带宽以及如何配置视频功能。</span><span class="sxs-lookup"><span data-stu-id="c3d88-112">This section describes how to manage bandwidth for video in Lync Server 2013 and how to configure video features.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3d88-113">本部分内容</span><span class="sxs-lookup"><span data-stu-id="c3d88-113">In This Section</span></span>

  - [<span data-ttu-id="c3d88-114">在 Lync Server 2013 中配置视频带宽</span><span class="sxs-lookup"><span data-stu-id="c3d88-114">Configuring video bandwidth in Lync Server 2013</span></span>](lync-server-2013-configuring-video-bandwidth.md)

  - [<span data-ttu-id="c3d88-115">在 Lync Server 2013 中配置库视图</span><span class="sxs-lookup"><span data-stu-id="c3d88-115">Configuring Gallery View in Lync Server 2013</span></span>](lync-server-2013-configuring-gallery-view.md)

  - [<span data-ttu-id="c3d88-116">为 Lync Server 2013 配置视频示例方案</span><span class="sxs-lookup"><span data-stu-id="c3d88-116">Configuring video example scenarios for Lync Server 2013</span></span>](lync-server-2013-configuring-video-example-scenarios.md)

  - [<span data-ttu-id="c3d88-117">Lync Server 2013 中视频会议的互操作性注意事项</span><span class="sxs-lookup"><span data-stu-id="c3d88-117">Interoperability considerations for video conferencing in Lync Server 2013</span></span>](lync-server-2013-interoperability-considerations-for-video-conferencing.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

