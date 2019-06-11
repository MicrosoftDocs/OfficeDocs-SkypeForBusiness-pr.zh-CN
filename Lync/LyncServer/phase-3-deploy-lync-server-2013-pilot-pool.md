---
title: '第3阶段: 部署 Lync Server 2013 试验池'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: 'Phase 3: Deploy Lync Server 2013 pilot pool'
ms:assetid: f12b1517-fb56-4ded-8323-57aa9fc9ea48
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205367(v=OCS.15)
ms:contentKeyID: 48185778
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 345fe1a110a4521fddde239681891a1491a17cca
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845158"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-3-deploy-lync-server-2013-pilot-pool"></a><span data-ttu-id="ac819-102">第3阶段: 部署 Lync Server 2013 试验池</span><span class="sxs-lookup"><span data-stu-id="ac819-102">Phase 3: Deploy Lync Server 2013 pilot pool</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ac819-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="ac819-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="ac819-104">本部分介绍了部署 Lync Server 2013 的引导池所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="ac819-104">This section covers the steps required to deploy a pilot pool of Lync Server 2013.</span></span> <span data-ttu-id="ac819-105">Lync Server 2013 的部署需要使用拓扑生成器定义你的拓扑和要部署的组件, 为部署 Lync Server 2013 组件准备环境, 在第一前端发布拓扑设计服务器, 然后为部署的组件安装和配置 Lync Server 2013 软件。</span><span class="sxs-lookup"><span data-stu-id="ac819-105">The deployment of Lync Server 2013 requires using Topology Builder to define your topology and the components you want to deploy, preparing your environment for deployment of the Lync Server 2013 components, publishing your topology design on the first Front End Server, and then installing and configuring Lync Server 2013 software for the components for your deployment.</span></span> <span data-ttu-id="ac819-106">完成后, 您的 Lync Server 2013 试验池部署将与现有 Lync Server 2010 池共存。</span><span class="sxs-lookup"><span data-stu-id="ac819-106">When completed, your Lync Server 2013 pilot pool deployment will coexist with an existing Lync Server 2010 pool.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="ac819-107">本节内容</span><span class="sxs-lookup"><span data-stu-id="ac819-107">In This Section</span></span>

  - [<span data-ttu-id="ac819-108">为 Lync Server 准备 Active Directory</span><span class="sxs-lookup"><span data-stu-id="ac819-108">Prepare Active Directory for Lync Server</span></span>](prepare-active-directory-for-lync-server.md)

  - [<span data-ttu-id="ac819-109">从现有部署下载拓扑</span><span class="sxs-lookup"><span data-stu-id="ac819-109">Download topology from existing deployment</span></span>](download-topology-from-existing-deployment.md)

  - [<span data-ttu-id="ac819-110">部署 Lync Server 2013 试验池</span><span class="sxs-lookup"><span data-stu-id="ac819-110">Deploy Lync Server 2013 pilot pool</span></span>](deploy-lync-server-2013-pilot-pool.md)

  - [<span data-ttu-id="ac819-111">验证试点池与旧池的共存情况</span><span class="sxs-lookup"><span data-stu-id="ac819-111">Verify pilot pool coexistence with legacy pool</span></span>](verify-pilot-pool-coexistence-with-legacy-pool.md)

  - [<span data-ttu-id="ac819-112">将试点池连接到旧 Edge Server</span><span class="sxs-lookup"><span data-stu-id="ac819-112">Connect pilot pool to legacy Edge Servers</span></span>](connect-pilot-pool-to-legacy-edge-servers.md)

  - [<span data-ttu-id="ac819-113">配置 XMPP 网关访问策略和证书</span><span class="sxs-lookup"><span data-stu-id="ac819-113">Configure XMPP gateway access policies and certificates</span></span>](configure-xmpp-gateway-access-policies-and-certificates.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

