---
title: Lync Server 2013：为用户设置存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up Archiving policies for users
ms:assetid: 1bbb45df-0590-4c66-9d65-d25526f57790
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204722(v=OCS.15)
ms:contentKeyID: 48183549
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f58d7b149c55d8daac9cb47f5e3ab0e1b4ea0596
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48509729"
---
# <a name="setting-up-archiving-policies-for-users-in-lync-server-2013"></a><span data-ttu-id="dd962-102">为 Lync Server 2013 中的用户设置存档策略</span><span class="sxs-lookup"><span data-stu-id="dd962-102">Setting up Archiving policies for users in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="dd962-103">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="dd962-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="dd962-104">通过为用户创建和配置存档策略、然后将该策略应用于特定用户或用户组，可为特定用户启用或禁用存档。</span><span class="sxs-lookup"><span data-stu-id="dd962-104">You can enable or disable Archiving for specific users by creating and configuring an Archiving policy for users, and then applying the policy to specific users or user groups.</span></span> <span data-ttu-id="dd962-105">用户策略会覆盖任何全局策略或站点策略。</span><span class="sxs-lookup"><span data-stu-id="dd962-105">User policies override any global policy or site policies.</span></span> <span data-ttu-id="dd962-106">仅当您不使用 Microsoft Exchange 集成时，或者，如果您使用 Microsoft Exchange 集成，但某些用户不驻留在 Exchange 2013 上，并且其邮箱置于 In-Place 保留状态，则存档策略仅适用。</span><span class="sxs-lookup"><span data-stu-id="dd962-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="dd962-107">有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅 [在 Lync Server 2013](lync-server-2013-how-archiving-works.md) 规划文档、部署文档或操作文档中存档的工作原理。</span><span class="sxs-lookup"><span data-stu-id="dd962-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="dd962-108">如果为部署启用了 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。</span><span class="sxs-lookup"><span data-stu-id="dd962-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="dd962-109">有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。</span><span class="sxs-lookup"><span data-stu-id="dd962-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="dd962-110">在存档策略中启用内部或外部通信的存档之前，应在存档配置中指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="dd962-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="dd962-111">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A> 。</span><span class="sxs-lookup"><span data-stu-id="dd962-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="dd962-112">本部分内容</span><span class="sxs-lookup"><span data-stu-id="dd962-112">In This Section</span></span>

  - [<span data-ttu-id="dd962-113">在 Lync Server 2013 中设置用户策略以进行存档</span><span class="sxs-lookup"><span data-stu-id="dd962-113">Setting up user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="dd962-114">在使用 Exchange Server 集成时，在 Lync Server 2013 中设置存档策略</span><span class="sxs-lookup"><span data-stu-id="dd962-114">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

