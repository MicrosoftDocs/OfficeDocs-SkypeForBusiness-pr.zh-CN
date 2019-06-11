---
title: 使用 Exchange Server 集成时设置存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Setting up policies for Archiving when using Exchange Server integration
ms:assetid: 8b9b2bad-a4b3-42e1-85a7-04022e9442ad
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205063(v=OCS.15)
ms:contentKeyID: 48184742
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 78e5f5bf1bcfa9b11a96722df1f6ff7535912bb1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845892"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="setting-up-policies-for-archiving-in-lync-server-2013-when-using-exchange-server-integration"></a><span data-ttu-id="26d24-102">使用 Exchange Server 集成时, 在 Lync Server 2013 中设置存档策略</span><span class="sxs-lookup"><span data-stu-id="26d24-102">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="26d24-103">_**主题上次修改时间:** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="26d24-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="26d24-104">如果托管在 Exchange 2013 上的用户已将其邮箱置于原地保留, 则 Exchange 就地保留策略控制这些用户的存档。</span><span class="sxs-lookup"><span data-stu-id="26d24-104">If users homed on Exchange 2013 have their mailboxes put on In-Place Hold, Exchange In-Place Hold policies control archiving for those users.</span></span> <span data-ttu-id="26d24-105">如果你针对你的部署使用 Microsoft Exchange 集成, Exchange 2013 策略将覆盖托管在 Exchange 2013 上的用户的 Lync Server 存档策略。</span><span class="sxs-lookup"><span data-stu-id="26d24-105">If you use Microsoft Exchange integration for your deployment, Exchange 2013 policies override Lync Server Archiving policies for users who are homed on Exchange 2013.</span></span> <span data-ttu-id="26d24-106">有关配置 Exchange 存档策略的信息, 请参阅 Exchange 2013 文档。</span><span class="sxs-lookup"><span data-stu-id="26d24-106">For information about configuring Exchange Archiving policies, see the Exchange 2013 documentation.</span></span> <span data-ttu-id="26d24-107">有关为驻留在 Lync Server 2013 上的用户设置用户策略的详细信息, 请参阅部署文档中的在[Lync Server 2013 中设置用于存档的用户策略](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)。</span><span class="sxs-lookup"><span data-stu-id="26d24-107">For details about setting up user policies for users homed on Lync Server 2013, see [Setting up user policies for Archiving in Lync Server 2013](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span> <span data-ttu-id="26d24-108">有关策略如何工作的详细信息, 请参阅规划文档、部署文档或操作文档中的在[Lync Server 2013 中的存档的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="26d24-108">For details about how policies work, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="26d24-109">如果在同一林中部署 Exchange 2013 和 Lync Server 2013, Exchange 2013 就地保留策略控制存档。</span><span class="sxs-lookup"><span data-stu-id="26d24-109">If you deploy Exchange 2013 and Lync Server 2013 in the same forest, your Exchange 2013 In-Place Hold policies control archiving.</span></span> <span data-ttu-id="26d24-110">如果在单独的目录林中部署 Exchange 2013 和 Lync Server 2013, 请参阅在<A href="lync-server-2013-deployment-checklist-for-archiving.md">Lync server 2013 中的存档部署清单中的</A>"部署 Lync 服务器和 Microsoft Exchange 其他林中"。</span><span class="sxs-lookup"><span data-stu-id="26d24-110">If you deploy Exchange 2013 and Lync Server 2013 in separate forests, see “Deploying Lync Server and Microsoft Exchange in Different Forests” in <A href="lync-server-2013-deployment-checklist-for-archiving.md">Deployment checklist for Archiving in Lync Server 2013</A>.</span></span>



</div>

</div>

<span> </span>

</div>

</div>

</div>

