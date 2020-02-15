---
title: Lync Server 2013：管理呼叫允许控制
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing call admission control
ms:assetid: b0bd4783-6f47-408d-b010-2e30f9bc1770
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721851(v=OCS.15)
ms:contentKeyID: 49733784
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ccb92b69c16f6dd45eedb584f0f63294dcbea4c0
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42037130"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-call-admission-control-in-lync-server-2013"></a><span data-ttu-id="dc234-102">在 Lync Server 2013 中管理呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="dc234-102">Managing call admission control in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dc234-103">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="dc234-103">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="dc234-104">呼叫允许控制 (CAC) 根据可用网络带宽确定是否允许建立实时通信会话（如语音呼叫或视频呼叫）。</span><span class="sxs-lookup"><span data-stu-id="dc234-104">Call admission control (CAC) determines, based on available network bandwidth, whether to allow real-time communications sessions such as voice or video calls to be established.</span></span> <span data-ttu-id="dc234-105">使用以下过程可管理 Lync Server 2013 环境的不同 CAC 功能。</span><span class="sxs-lookup"><span data-stu-id="dc234-105">Use the following procedures to manage different CAC features for your Lync Server 2013 environment.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dc234-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="dc234-106">In This Section</span></span>

  - [<span data-ttu-id="dc234-107">在 Lync Server 2013 中启用呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="dc234-107">Enabling call admission control in Lync Server 2013</span></span>](lync-server-2013-enabling-call-admission-control.md)

  - [<span data-ttu-id="dc234-108">在 Lync Server 2013 中管理网络带宽策略配置文件</span><span class="sxs-lookup"><span data-stu-id="dc234-108">Managing network bandwidth policy profiles in Lync Server 2013</span></span>](lync-server-2013-managing-network-bandwidth-policy-profiles.md)

  - [<span data-ttu-id="dc234-109">Lync Server 2013 中的网络区域</span><span class="sxs-lookup"><span data-stu-id="dc234-109">Network regions in Lync Server 2013</span></span>](lync-server-2013-network-regions.md)

  - [<span data-ttu-id="dc234-110">Lync Server 2013 中的网络区域路由</span><span class="sxs-lookup"><span data-stu-id="dc234-110">Network region routes in Lync Server 2013</span></span>](lync-server-2013-network-region-routes.md)

  - [<span data-ttu-id="dc234-111">Lync Server 2013 中对网站的呼叫允许控制</span><span class="sxs-lookup"><span data-stu-id="dc234-111">Call admission control for sites in Lync Server 2013</span></span>](lync-server-2013-call-admission-control-for-sites.md)

  - [<span data-ttu-id="dc234-112">在 Lync Server 2013 中启用和禁用媒体旁路</span><span class="sxs-lookup"><span data-stu-id="dc234-112">Enabling and disabling media bypass in Lync Server 2013</span></span>](lync-server-2013-enabling-and-disabling-media-bypass.md)

  - [<span data-ttu-id="dc234-113">在 Lync Server 2013 中链接网络区域</span><span class="sxs-lookup"><span data-stu-id="dc234-113">Linking network regions in Lync Server 2013</span></span>](lync-server-2013-linking-network-regions.md)

  - [<span data-ttu-id="dc234-114">在 Lync Server 2013 中管理网络子网</span><span class="sxs-lookup"><span data-stu-id="dc234-114">Managing network subnets in Lync Server 2013</span></span>](lync-server-2013-managing-network-subnets.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="dc234-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc234-115">See Also</span></span>


[<span data-ttu-id="dc234-116">Lync Server 2013 中的呼叫允许控制概述</span><span class="sxs-lookup"><span data-stu-id="dc234-116">Overview of call admission control in Lync Server 2013</span></span>](lync-server-2013-overview-of-call-admission-control.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

