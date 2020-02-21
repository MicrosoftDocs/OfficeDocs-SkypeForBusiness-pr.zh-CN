---
title: Lync Server 2013：在 Lync Server 中设置用于存档的用户策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up user policies for Archiving in Lync Server
ms:assetid: 22d6cc76-6b5c-4a8c-bb8a-7996450ec085
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204742(v=OCS.15)
ms:contentKeyID: 48183626
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8e032dd276ee41a711ded56d33a065d515b182ab
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42200375"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="setting-up-user-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="73d58-102">在 Lync Server 2013 中设置用户策略以进行存档</span><span class="sxs-lookup"><span data-stu-id="73d58-102">Setting up user policies for Archiving in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="73d58-103">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="73d58-103">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="73d58-104">如果为驻留在 Lync Server 2013 上的特定用户启用或禁用存档，则需要创建和配置一个或多个用户策略，然后将适当的策略应用于特定用户或用户组。</span><span class="sxs-lookup"><span data-stu-id="73d58-104">Enabling or disabling Archiving for specific users homed on Lync Server 2013 requires creating and configuring one or more user policies, and then applying the appropriate policy to specific users or user groups.</span></span> <span data-ttu-id="73d58-105">用户策略会覆盖网站和全局策略，但仅适用于驻留在 Lync Server 2013 上的用户。</span><span class="sxs-lookup"><span data-stu-id="73d58-105">User policies override site and global policies, but only for users homed on Lync Server 2013.</span></span>

<span data-ttu-id="73d58-106">用户始终驻留在 Lync Server 中。</span><span class="sxs-lookup"><span data-stu-id="73d58-106">Users are always homed in Lync Server.</span></span> <span data-ttu-id="73d58-107">如果启用了 Microsoft Exchange 集成，则邮箱位于 Microsoft Exchange Server 2013 中的用户不需要在 Lync Server 中管理其存档策略。</span><span class="sxs-lookup"><span data-stu-id="73d58-107">If Microsoft Exchange integration is enabled, users whose mailboxes are in Microsoft Exchange Server 2013 don’t need to have their Archiving policies in Lync Server managed.</span></span> <span data-ttu-id="73d58-108">将通过 Exchange 就地保留来管理这些具有存档的用户。</span><span class="sxs-lookup"><span data-stu-id="73d58-108">These users with Archiving will be managed by Exchange In-Place Hold.</span></span>

<span data-ttu-id="73d58-109">有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="73d58-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="73d58-110">如果为您的部署启用了 Microsoft Exchange 集成，则 Exchange 就地保留策略控制是否为托管在 Exchange 2013 上的用户启用存档。</span><span class="sxs-lookup"><span data-stu-id="73d58-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013.</span></span> <span data-ttu-id="73d58-111">为这些用户启用存档要求他们将其邮箱置于就地保留状态。</span><span class="sxs-lookup"><span data-stu-id="73d58-111">Archiving for these users requires that they have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="73d58-112">有关详细信息，请参阅部署文档中的<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="73d58-112">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="73d58-113">在启用存档之前，应在存档配置中指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="73d58-113">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="73d58-114">有关详细信息，请参阅部署文档中的在<A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A>。</span><span class="sxs-lookup"><span data-stu-id="73d58-114">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="73d58-115">本部分内容</span><span class="sxs-lookup"><span data-stu-id="73d58-115">In This Section</span></span>

  - [<span data-ttu-id="73d58-116">在 Lync Server 2013 中创建和配置用于存档的用户策略</span><span class="sxs-lookup"><span data-stu-id="73d58-116">Creating and configuring user policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md)

  - [<span data-ttu-id="73d58-117">在 Lync Server 2013 中将 Lync Server 存档策略应用于用户</span><span class="sxs-lookup"><span data-stu-id="73d58-117">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>](lync-server-2013-applying-a-lync-server-archiving-policy-to-a-user.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

