---
title: 共存注意事项
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b31b8f3e534fc7b060f194f84310050a0386d8c
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180995"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="fcc3d-102">共存注意事项</span><span class="sxs-lookup"><span data-stu-id="fcc3d-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="fcc3d-103">_**上次修改的主题：** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="fcc3d-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="fcc3d-104">迁移后，只有 Lync Server 2013、持久聊天服务器池存在，并且您可以停止使用旧版部署。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="fcc3d-105">在迁移完成之前和完全取消当前组聊天服务器部署之前，可能会有以下任一部署：</span><span class="sxs-lookup"><span data-stu-id="fcc3d-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="fcc3d-106">Lync Server 2013、持久聊天服务器池（必须驻留在 Lync Server 2013 池上）。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="fcc3d-107">Lync Server 2010，组聊天池，它必须驻留在 Lync Server 2010 池上。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="fcc3d-108">Office 通信服务器 2007 R2 组聊天池，它必须驻留在 Office 通信服务器 2007 R2 池上。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="fcc3d-p101">这些部署可并行存在。但是一个部署中的类别、聊天室和外接程序不会与伴随部署中的交互。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-p101">These deployments can exist side by side. However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="fcc3d-111">使用手动配置，旧版客户端（组聊天客户端）可以一次连接到一个池，以获取 Office 通信服务器 2007 R2、Lync Server 2010、组聊天或 Lync Server 2013。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="fcc3d-112">Lync 2013 （客户端）只能与 Lync Server 2013、持久聊天服务器池进行交互，而不能与旧版组聊天服务器池交互。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="fcc3d-113">若要在 Lync 2013 （客户端）中使用持久聊天，用户必须驻留在 Lync 2013 上并由策略启用。</span><span class="sxs-lookup"><span data-stu-id="fcc3d-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

