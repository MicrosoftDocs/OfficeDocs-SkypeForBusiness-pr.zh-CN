---
title: 迁移中介服务器
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 79fc35a7641b4acb42578ec4e75375e171ae905e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845220"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="a050a-102">迁移中介服务器</span><span class="sxs-lookup"><span data-stu-id="a050a-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a050a-103">_**主题上次修改时间:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="a050a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="a050a-104">当运行 "合并向导" 时, 中介服务器将合并到 Lync Server 2013 试点拓扑中。</span><span class="sxs-lookup"><span data-stu-id="a050a-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="a050a-105">但是, 你可以配置 Lync Server 2013 中介服务器, 因为 Office 通信服务器 2007 R2 池无法与 Lync server 2013 中介服务器通信, 因此在迁移所有用户后。</span><span class="sxs-lookup"><span data-stu-id="a050a-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="a050a-106">在并行迁移期间, Lync Server 2013 池与 Office 通信服务器 2007 R2 中介服务器通信。</span><span class="sxs-lookup"><span data-stu-id="a050a-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="a050a-107">当您配置 Lync Server 2013 中介服务器时, 您还必须升级或替换您的 Office 通信服务器 2007 R2 网关。</span><span class="sxs-lookup"><span data-stu-id="a050a-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="a050a-108">Office 通信服务器 2007 R2 网关不支持 Lync Server 2013 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="a050a-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="a050a-109">你需要部署已认证的适用于 Lync Server 2013 的网关, 并将其与 Lync Server 2013 中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="a050a-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="a050a-110">必须先执行此步骤, 然后才能完全停止 Office 通信服务器 2007 R2 部署。</span><span class="sxs-lookup"><span data-stu-id="a050a-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="a050a-111">本部分中的主题介绍了在完成 Lync Server 2013 中介服务器的迁移后需要执行的配置任务。</span><span class="sxs-lookup"><span data-stu-id="a050a-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="a050a-112">将 collocated 中介服务器转换为独立的中介服务器是一种可选任务。</span><span class="sxs-lookup"><span data-stu-id="a050a-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="a050a-113">配置中介服务器</span><span class="sxs-lookup"><span data-stu-id="a050a-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="a050a-114">将语音路由更改为使用新的 Lync Server 2013 中介服务器</span><span class="sxs-lookup"><span data-stu-id="a050a-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="a050a-115">将 collocated 中介服务器转换为独立的中介服务器 (可选)</span><span class="sxs-lookup"><span data-stu-id="a050a-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

