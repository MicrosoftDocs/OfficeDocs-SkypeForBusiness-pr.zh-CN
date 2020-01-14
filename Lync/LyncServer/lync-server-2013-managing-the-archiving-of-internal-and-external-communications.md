---
title: 管理内部和外部通信的存档
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Managing the Archiving of internal and external communications
ms:assetid: 6c2cf941-3204-4f1a-a7e0-416c828056d9
ms:mtpsurl: https://technet.microsoft.com/library/JJ204977(v=OCS.15)
ms:contentKeyID: 48184417
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 891318ba677891916af678b74365026d20d69016
ms.sourcegitcommit: 0119af282f53f49c4ab6e01c3319d01bc6fdad2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2020
ms.locfileid: "41111516"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-the-archiving-of-internal-and-external-communications-in-lync-server-2013"></a><span data-ttu-id="31fdd-102">在 Lync Server 2013 中管理内部和外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="31fdd-102">Managing the Archiving of internal and external communications in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="31fdd-103">_**主题上次修改时间：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="31fdd-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="31fdd-104">在 Lync Server 2013 中，如果你不使用 Microsoft Exchange 集成，或者你的用户未托管在 Exchange 2013 上，并且你的邮箱放在 Exchange 上，则可以使用存档策略来启用和禁用对内部通信和外部通信的存档就地保留。</span><span class="sxs-lookup"><span data-stu-id="31fdd-104">In Lync Server 2013, you use Archiving policies to enable and disable archiving for internal communications and external communications if you do not use Microsoft Exchange integration or you have users who are not homed on Exchange 2013 with their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="31fdd-105">这包括以下存档策略：</span><span class="sxs-lookup"><span data-stu-id="31fdd-105">This includes the following Archiving policies:</span></span>

  - <span data-ttu-id="31fdd-106">部署 Lync Server 2013 时默认创建的全局策略。</span><span class="sxs-lookup"><span data-stu-id="31fdd-106">A global policy that is created by default when you deploy Lync Server 2013.</span></span>

  - <span data-ttu-id="31fdd-107">可创建和使用的可选网站级和用户级策略，用于指定如何为特定网站或用户实现存档。</span><span class="sxs-lookup"><span data-stu-id="31fdd-107">Optional site-level and user-level policies that you can create and use to specify how archiving is implemented for specific sites or users.</span></span>

<span data-ttu-id="31fdd-108">你在部署存档时最初设置存档策略，但你可以在部署后更改、添加和删除策略。</span><span class="sxs-lookup"><span data-stu-id="31fdd-108">You initially set up Archiving policies when you deploy Archiving, but you can change, add, and delete policies after deployment.</span></span> <span data-ttu-id="31fdd-109">在 Lync Server 2013 控制面板中，你可以使用 "**存档和监视**" 组的 "**存档策略**" 页面管理全局级别、网站级别和用户级别的策略。</span><span class="sxs-lookup"><span data-stu-id="31fdd-109">In Lync Server 2013 Control Panel, you can use the **Archiving Policy** page of the **Archiving and Monitoring** group to manage policies at the global level, site level, and user level.</span></span> <span data-ttu-id="31fdd-110">如果你将 Lync Server 存储与 Exchange 2013 存储集成，Exchange 用户策略将优先于 Lync Server 2013 存档策略。</span><span class="sxs-lookup"><span data-stu-id="31fdd-110">If you integrate your Lync Server storage with Exchange 2013 storage, the Exchange user policies take precedence over the Lync Server 2013 archiving policies.</span></span>

<span data-ttu-id="31fdd-111">有关如何实施策略的详细信息（包括策略的层次结构），请参阅规划文档、部署文档或操作文档中的在[Lync Server 2013 中的存档的工作原理](lync-server-2013-how-archiving-works.md)。</span><span class="sxs-lookup"><span data-stu-id="31fdd-111">For details about how policies are implemented, including the hierarchy of policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]
> <span data-ttu-id="31fdd-112">若要控制存档的实现，必须指定存档配置中的选项，例如，是存档 IM 还是会议、使用关键模式和清除选项。</span><span class="sxs-lookup"><span data-stu-id="31fdd-112">To control the implementation of Archiving, you must specify options in Archiving configurations, such as whether to archive IM or conferencing, the use of critical mode, and purging options.</span></span> <span data-ttu-id="31fdd-113">默认情况下，全局存档配置或任何网站或池存档配置中均未启用任何选项。</span><span class="sxs-lookup"><span data-stu-id="31fdd-113">By default no options are enabled in the global Archiving configuration or any site or pool Archiving configuration.</span></span> <span data-ttu-id="31fdd-114">应在存档配置中指定所有适当的选项，然后才能在存档策略中启用内部或外部通信的存档。</span><span class="sxs-lookup"><span data-stu-id="31fdd-114">You should specify all appropriate options in the Archiving configurations before enabling Archiving for internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="31fdd-115">有关详细信息，请参阅在<A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Lync Server 2013 中为你的组织、网站和池在操作文档中管理存档配置选项</A>。</span><span class="sxs-lookup"><span data-stu-id="31fdd-115">For details, see <A href="lync-server-2013-managing-archiving-configuration-options-for-your-organization-sites-and-pools.md">Managing Archiving configuration options in Lync Server 2013 for your organization, sites, and pools</A> in the Operations documentation.</span></span><BR><span data-ttu-id="31fdd-116">如果为你的部署启用 Microsoft Exchange 集成，Exchange 策略将控制是否为托管于 Exchange 2013 的用户启用存档，并将其邮箱置于原地保留。</span><span class="sxs-lookup"><span data-stu-id="31fdd-116">If you enable Microsoft Exchange integration for your deployment, Exchange policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="31fdd-117">有关详细信息，请参阅在部署文档中<A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时在 Lync Server 2013 中设置存档策略</A>。</span><span class="sxs-lookup"><span data-stu-id="31fdd-117">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="31fdd-118">本节内容</span><span class="sxs-lookup"><span data-stu-id="31fdd-118">In This Section</span></span>

  - [<span data-ttu-id="31fdd-119">在 Lync Server 2013 中创建存档策略，以启用或禁用特定网站或用户的内部或外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="31fdd-119">Creating an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for specific sites or users</span></span>](lync-server-2013-create-archiving-policy-sites-users.md)

  - [<span data-ttu-id="31fdd-120">在 Lync Server 2013 中更改存档策略以启用或禁用组织、网站或用户的内部或外部通信的存档</span><span class="sxs-lookup"><span data-stu-id="31fdd-120">Changing an Archiving policy in Lync Server 2013 to enable or disable Archiving of internal or external communications for your organization, sites, or users</span></span>](lync-server-2013-change-archiving-policy-org-sites-users.md)

  - [<span data-ttu-id="31fdd-121">将存档策略应用于 Lync Server 2013 中的用户</span><span class="sxs-lookup"><span data-stu-id="31fdd-121">Applying an Archiving policy to users in Lync Server 2013</span></span>](lync-server-2013-applying-an-archiving-policy-to-users.md)

  - [<span data-ttu-id="31fdd-122">使用 Exchange Server 集成时，在 Lync Server 2013 中设置存档策略</span><span class="sxs-lookup"><span data-stu-id="31fdd-122">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</span></span>](lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md)

  - [<span data-ttu-id="31fdd-123">在 Lync Server 2013 中删除存档策略</span><span class="sxs-lookup"><span data-stu-id="31fdd-123">Deleting an Archiving policy in Lync Server 2013</span></span>](lync-server-2013-deleting-an-archiving-policy.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

