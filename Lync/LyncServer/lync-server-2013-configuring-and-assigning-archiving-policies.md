---
title: Lync Server 2013：配置和分配存档策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and assigning Archiving policies
ms:assetid: acd18ea8-c7f1-4178-871a-cd3b75bdaa8b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205175(v=OCS.15)
ms:contentKeyID: 48185121
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7db876d03f7322fae5f3a55f88708fe4165a20ba
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-and-assigning-archiving-policies-in-lync-server-2013"></a><span data-ttu-id="4efac-102">在 Lync Server 2013 中配置和分配存档策略</span><span class="sxs-lookup"><span data-stu-id="4efac-102">Configuring and assigning Archiving policies in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4efac-103">_**上次修改的主题：** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="4efac-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="4efac-104">在 Lync Server 2013 中，可以使用策略为驻留在 Lync Server 2013 上的用户启用和禁用对内部通信和外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="4efac-104">In Lync Server 2013, you use policies to enable and disable archiving for internal communications and external communications for users who are homed on Lync Server 2013.</span></span> <span data-ttu-id="4efac-105">这包括以下存档策略：</span><span class="sxs-lookup"><span data-stu-id="4efac-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="4efac-106">部署 Lync Server 2013 时默认创建的全局策略。</span><span class="sxs-lookup"><span data-stu-id="4efac-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="4efac-107">您可以创建并用来指定如何针对特定站点或用户实施存档的可选站点级别和用户级别策略。</span><span class="sxs-lookup"><span data-stu-id="4efac-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="4efac-108">您最初在部署存档时设置存档策略，但您可以在部署后更改、添加和删除策略。</span><span class="sxs-lookup"><span data-stu-id="4efac-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="4efac-109">在 Lync Server 2013 控制面板中，可以使用 "**存档和监控**" 组的 "**存档策略**" 页来管理全局级别、站点级别和用户级别的策略。</span><span class="sxs-lookup"><span data-stu-id="4efac-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="4efac-110">若要控制存档的实现，您必须在存档配置中指定选项，例如，是否存档 IM 或会议、关键模式的用法和清除选项。</span><span class="sxs-lookup"><span data-stu-id="4efac-110">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="4efac-111">默认情况下，在全局存档配置或任意站点或池存档配置中未启用任何选项。</span><span class="sxs-lookup"><span data-stu-id="4efac-111">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="4efac-112">您应在存档配置中指定所有适当的选项，然后在存档策略中为内部或外部通信启用存档。</span><span class="sxs-lookup"><span data-stu-id="4efac-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="4efac-113">有关详细信息，请参阅 Operations 文档中的在<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中管理存档配置选项（针对组织、网站和池</A>）。</span><span class="sxs-lookup"><span data-stu-id="4efac-113">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="4efac-114">如果将 Lync Server 存储与 Exchange 2013 存储集成，则 Exchange 用户策略优先于 Lync Server 2013 存档策略，但仅适用于驻留在 Exchange 2013 的用户已将其邮箱置于就地保留状态的用户。</span><span class="sxs-lookup"><span data-stu-id="4efac-114">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies but only for those users who are homed on Exchange 2013 who have had their mailboxes put on In-Place Hold.</span></span>



</div>

<span data-ttu-id="4efac-115">有关如何实施策略（包括策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="4efac-115">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span> <span data-ttu-id="4efac-116">有关如何在部署后管理策略的详细信息，请参阅操作文档中的在[Lync Server 2013 中管理内部和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)。</span><span class="sxs-lookup"><span data-stu-id="4efac-116">For details about how to manage policies after deployment, see [Managing the Archiving of internal and external communications in Lync Server 2013](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md) in the Operations documentation.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="4efac-117">本部分内容</span><span class="sxs-lookup"><span data-stu-id="4efac-117">In This Section</span></span>

  - [<span data-ttu-id="4efac-118">在 Lync Server 2013 中配置用于存档的全局策略</span><span class="sxs-lookup"><span data-stu-id="4efac-118">Configuring the global policy for Archiving in Lync Server 2013</span></span>](lync-server-2013-configuring-the-global-policy-for-archiving.md)

  - [<span data-ttu-id="4efac-119">在 Lync Server 2013 中设置用于存档的网站策略</span><span class="sxs-lookup"><span data-stu-id="4efac-119">Setting up site policies for Archiving in Lync Server 2013</span></span>](lync-server-2013-setting-up-site-policies-for-archiving.md)

  - [<span data-ttu-id="4efac-120">为 Lync Server 2013 中的用户设置存档策略</span><span class="sxs-lookup"><span data-stu-id="4efac-120">Setting up Archiving policies for users in Lync Server 2013</span></span>](lync-server-2013-setting-up-archiving-policies-for-users.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

