---
title: 迁移中介服务器
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate Mediation Server
ms:assetid: b0b77121-2c8f-413e-b276-dbf1038361d3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205173(v=OCS.15)
ms:contentKeyID: 48185117
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 80c6dbc55e41324ad9c3e7d83bb593d8b8e93c64
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44756953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="migrate-mediation-server"></a><span data-ttu-id="e03db-102">迁移中介服务器</span><span class="sxs-lookup"><span data-stu-id="e03db-102">Migrate Mediation Server</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e03db-103">_**上次修改的主题：** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="e03db-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="e03db-104">运行合并向导时，中介服务器将合并到 Lync Server 2013 试点拓扑中。</span><span class="sxs-lookup"><span data-stu-id="e03db-104">Your Mediation Server is merged into your Lync Server 2013 pilot topology when you run the Merge wizard.</span></span> <span data-ttu-id="e03db-105">但是，在迁移所有用户后，可以配置 Lync Server 2013 中介服务器，因为 Office 通信服务器 2007 R2 池无法与 Lync Server 2013 中介服务器通信。</span><span class="sxs-lookup"><span data-stu-id="e03db-105">You configure the Lync Server 2013 Mediation Server, however, after all users are migrated because an Office Communications Server 2007 R2 pool cannot communicate with a Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="e03db-106">在并行迁移过程中，Lync Server 2013 池与 Office 通信服务器 2007 R2 中介服务器通信。</span><span class="sxs-lookup"><span data-stu-id="e03db-106">During the side-by-side migration, the Lync Server 2013 pool communicates with the Office Communications Server 2007 R2 Mediation Server.</span></span>

<span data-ttu-id="e03db-107">配置 Lync Server 2013 中介服务器时，还必须升级或替换 Office 通信服务器 2007 R2 网关。</span><span class="sxs-lookup"><span data-stu-id="e03db-107">When you configure your Lync Server 2013 Mediation Server, you must also upgrade or replace your Office Communications Server 2007 R2 gateways.</span></span> <span data-ttu-id="e03db-108">Office 通信服务器 2007 R2 网关不支持 Lync Server 2013 中介服务器。</span><span class="sxs-lookup"><span data-stu-id="e03db-108">Office Communications Server 2007 R2 gateways do not support Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="e03db-109">您需要部署认证为 Lync Server 2013 的网关，并将其与 Lync Server 2013 中介服务器相关联。</span><span class="sxs-lookup"><span data-stu-id="e03db-109">You need to deploy gateways that are certified for Lync Server 2013 and associate them with the Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="e03db-110">必须先执行此步骤，然后才能完全停止 Office 通信服务器 2007 R2 部署。</span><span class="sxs-lookup"><span data-stu-id="e03db-110">This step is required before you can completely decommission your Office Communications Server 2007 R2 deployment.</span></span>

<span data-ttu-id="e03db-111">本节中的主题介绍在完成 Lync Server 2013 中介服务器的迁移后需要执行的配置任务。</span><span class="sxs-lookup"><span data-stu-id="e03db-111">The topics in this section describe configuration tasks that you need to perform after you have completed your migration of Lync Server 2013 Mediation Server.</span></span> <span data-ttu-id="e03db-112">将并置的中介服务器转换为独立中介服务器是可选任务。</span><span class="sxs-lookup"><span data-stu-id="e03db-112">Transitioning the collocated Mediation Server to a stand-alone Mediation Server is an optional task.</span></span>

  - [<span data-ttu-id="e03db-113">配置中介服务器</span><span class="sxs-lookup"><span data-stu-id="e03db-113">Configure Mediation Server</span></span>](configure-mediation-server.md)

  - [<span data-ttu-id="e03db-114">将语音路由更改为使用新的 Lync Server 2013 中介服务器</span><span class="sxs-lookup"><span data-stu-id="e03db-114">Change voice routes to use the new Lync Server 2013 Mediation Server</span></span>](change-voice-routes-to-use-the-new-lync-server-2013-mediation-server.md)

  - [<span data-ttu-id="e03db-115">将并置中介服务器转换为独立的中介服务器（可选）</span><span class="sxs-lookup"><span data-stu-id="e03db-115">Transition a collocated Mediation Server to a stand-alone Mediation Server (optional)</span></span>](transition-a-collocated-mediation-server-to-a-stand-alone-mediation-server-optional.md)

</div>

<span> </span>

</div>

</div>

</div>

