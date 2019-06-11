---
title: Lync Server 2013：设置边缘服务器
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up Edge Servers
ms:assetid: 09a22919-e36f-4122-8f0d-8d041198912d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398147(v=OCS.15)
ms:contentKeyID: 48183354
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 89c3de2695ef4e9dca538e8e0c6287a19c1a5035
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845926"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-edge-servers-in-lync-server-2013"></a><span data-ttu-id="51c75-102">在 Lync Server 2013 中设置边缘服务器</span><span class="sxs-lookup"><span data-stu-id="51c75-102">Setting up Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51c75-103">_**主题上次修改时间:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="51c75-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="51c75-104">设置边缘服务器所需的主要任务与安装单个边缘服务器或负载平衡的边缘服务器池相同, 只是硬件负载平衡的边缘服务器池需要部署负载平衡器和其他步骤在多台边缘服务器上复制设置。</span><span class="sxs-lookup"><span data-stu-id="51c75-104">The primary tasks required to set up Edge Servers are the same for installing a single Edge Server or a load-balanced pool of Edge Servers, except that a pool of hardware load balanced Edge Servers requires deployment of the load balancers and additional steps for replicating the set up on multiple Edge Servers.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="51c75-105">本节内容</span><span class="sxs-lookup"><span data-stu-id="51c75-105">In This Section</span></span>

  - [<span data-ttu-id="51c75-106">在 Lync Server 2013 中设置边缘服务器的网络接口</span><span class="sxs-lookup"><span data-stu-id="51c75-106">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>](lync-server-2013-set-up-network-interfaces-for-edge-servers.md)

  - [<span data-ttu-id="51c75-107">在 Lync Server 2013 边缘服务器上安装必备软件</span><span class="sxs-lookup"><span data-stu-id="51c75-107">Install prerequisite software on Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-prerequisite-software-on-edge-servers.md)

  - [<span data-ttu-id="51c75-108">导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装</span><span class="sxs-lookup"><span data-stu-id="51c75-108">Export your Lync Server 2013 topology and copy it to external media for edge installation</span></span>](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)

  - [<span data-ttu-id="51c75-109">安装适用于 Lync Server 2013 的边缘服务器</span><span class="sxs-lookup"><span data-stu-id="51c75-109">Install Edge Servers for Lync Server 2013</span></span>](lync-server-2013-install-edge-servers.md)

  - [<span data-ttu-id="51c75-110">为 Lync Server 2013 设置边缘证书</span><span class="sxs-lookup"><span data-stu-id="51c75-110">Set up Edge certificates for Lync Server 2013</span></span>](lync-server-2013-set-up-edge-certificates.md)

  - [<span data-ttu-id="51c75-111">在 Lync Server 2013 中启动边缘服务器</span><span class="sxs-lookup"><span data-stu-id="51c75-111">Start Edge Servers in Lync Server 2013</span></span>](lync-server-2013-start-edge-servers.md)

  - [<span data-ttu-id="51c75-112">为 Lync Server 2013 设置反向代理服务器</span><span class="sxs-lookup"><span data-stu-id="51c75-112">Setting up reverse proxy servers for Lync Server 2013</span></span>](lync-server-2013-setting-up-reverse-proxy-servers.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

