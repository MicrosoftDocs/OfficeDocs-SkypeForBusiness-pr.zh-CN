---
title: 共存注意事项
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Coexistence considerations
ms:assetid: 9d1a3c0f-492a-4e37-bc2f-63509e328785
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205131(v=OCS.15)
ms:contentKeyID: 48184990
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c0e06e5620b3b9ce81826bf623a42ec8d89c5d3d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="coexistence-considerations"></a><span data-ttu-id="8f8eb-102">共存注意事项</span><span class="sxs-lookup"><span data-stu-id="8f8eb-102">Coexistence considerations</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8f8eb-103">_**主题上次修改时间:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="8f8eb-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="8f8eb-104">迁移后, 仅存在 Lync Server 2013、持久聊天服务器池, 并且您可以停止使用旧部署。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-104">After migration, only a Lync Server 2013, Persistent Chat Server pool will exist, and you can decommission your legacy deployment.</span></span>

<span data-ttu-id="8f8eb-105">在迁移完成之前以及完全取消当前组聊天服务器部署的配置之前, 你可能会遇到以下任何部署:</span><span class="sxs-lookup"><span data-stu-id="8f8eb-105">Before migration completes and before you have decommissioned your current Group Chat Server deployment completely, you may have any of the following deployments:</span></span>

  - <span data-ttu-id="8f8eb-106">Lync Server 2013 持久聊天服务器池, 它必须托管在 Lync Server 2013 池。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-106">Lync Server 2013, Persistent Chat Server pool, which must be homed on a Lync Server 2013 pool.</span></span>

  - <span data-ttu-id="8f8eb-107">Lync Server 2010、群组聊天池, 它必须驻留在 Lync Server 2010 池中。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-107">Lync Server 2010, Group Chat pool, which must be homed on a Lync Server 2010 pool.</span></span>

  - <span data-ttu-id="8f8eb-108">Office 通信服务器 2007 R2 群组聊天池, 它必须驻留在 Office 通信服务器 2007 R2 池中。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-108">Office Communications Server 2007 R2 Group Chat pool, which must be homed on an Office Communications Server 2007 R2 pool.</span></span>

<span data-ttu-id="8f8eb-109">这些部署可以并排存在。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-109">These deployments can exist side by side.</span></span> <span data-ttu-id="8f8eb-110">但是, 一个部署中的类别、会议室和外接程序不与附带的部署中的相同。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-110">However the categories, rooms, and add-ins in one deployment do not interact with those in the accompanying deployment.</span></span>

<span data-ttu-id="8f8eb-111">使用手动配置时, 旧客户端 (组聊天客户端) 可以一次连接到 Office 通信服务器 2007 R2、Lync Server 2010、群组聊天或 Lync Server 2013 的一个池。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-111">Using manual configuration, a legacy client (Group Chat client) can connect to one pool at a time for Office Communications Server 2007 R2, Lync Server 2010, Group Chat, or Lync Server 2013.</span></span>

<span data-ttu-id="8f8eb-112">Lync 2013 (客户端) 只能与 Lync Server 2013、持久聊天服务器池 (而不是旧版组聊天服务器池) 交互。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-112">The Lync 2013 (client) can interact only with the Lync Server 2013, Persistent Chat Server pool, not with legacy Group Chat Server pools.</span></span> <span data-ttu-id="8f8eb-113">若要在 Lync 2013 (客户端) 中使用持久聊天, 用户必须托管在 Lync 2013 并由策略启用。</span><span class="sxs-lookup"><span data-stu-id="8f8eb-113">To use Persistent Chat in a Lync 2013 (client), the user must be homed on Lync 2013 and enabled by policy.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

