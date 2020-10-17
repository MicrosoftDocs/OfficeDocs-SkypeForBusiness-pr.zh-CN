---
title: Lync Server 2013：将 Lync Server 存档策略应用于用户
description: Lync Server 2013：将 Lync Server 存档策略应用于用户。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Applying a Lync Server Archiving policy to a user
ms:assetid: a23e4876-aa8d-4f49-a3bd-3696616e8290
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205143(v=OCS.15)
ms:contentKeyID: 48185024
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 69dcca5601185d65735b963673322a0630af6ebd
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48544988"
---
# <a name="applying-a-lync-server-archiving-policy-to-a-user-in-lync-server-2013"></a><span data-ttu-id="34a65-103">在 Lync Server 2013 中将 Lync Server 存档策略应用于用户</span><span class="sxs-lookup"><span data-stu-id="34a65-103">Applying a Lync Server Archiving policy to a user in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="34a65-104">_**上次修改的主题：** 2012-10-10_</span><span class="sxs-lookup"><span data-stu-id="34a65-104">_**Topic Last Modified:** 2012-10-10_</span></span>

<span data-ttu-id="34a65-105">创建 Lync Server 用户策略后，必须将其应用于驻留在 Lync Server 2013 上的特定用户或用户组，然后它才能生效。</span><span class="sxs-lookup"><span data-stu-id="34a65-105">After creating a Lync Server user policy, you must apply it to specific the users or user groups that are homed on Lync Server 2013 before it can take effect.</span></span> <span data-ttu-id="34a65-106">有关为特定用户创建用户策略的详细信息，请参阅部署文档中的在 [Lync Server 2013 中创建和配置用于存档的用户策略](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) 。</span><span class="sxs-lookup"><span data-stu-id="34a65-106">For details about creating user policies for specific users, see [Creating and configuring user policies for Archiving in Lync Server 2013](lync-server-2013-creating-and-configuring-user-policies-for-archiving-in-lync-server.md) in the Deployment documentation.</span></span>

<span data-ttu-id="34a65-107">有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的 [存档在 Lync Server 2013 中的工作原理](lync-server-2013-how-archiving-works.md) 。</span><span class="sxs-lookup"><span data-stu-id="34a65-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) in the Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="34a65-108">为了配置和使用存档，必须首先部署存档。</span><span class="sxs-lookup"><span data-stu-id="34a65-108">In order to configure and use archiving, you must first deploy archiving.</span></span> <span data-ttu-id="34a65-109">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-deploying-archiving.md">Lync Server 2013 中部署存档</A> 。</span><span class="sxs-lookup"><span data-stu-id="34a65-109">For details, see <A href="lync-server-2013-deploying-archiving.md">Deploying Archiving in Lync Server 2013</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="34a65-110">如果为您的部署启用了 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否为托管在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。</span><span class="sxs-lookup"><span data-stu-id="34a65-110">If you enabled Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="34a65-111">有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。</span><span class="sxs-lookup"><span data-stu-id="34a65-111">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="34a65-112">在启用存档之前，应在存档配置中指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="34a65-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="34a65-113">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A> 。</span><span class="sxs-lookup"><span data-stu-id="34a65-113">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-apply-a-lync-server-archiving-policy-to-a-user"></a><span data-ttu-id="34a65-114">将 Lync Server 存档策略应用于用户</span><span class="sxs-lookup"><span data-stu-id="34a65-114">To apply a Lync Server archiving policy to a user</span></span>

1.  <span data-ttu-id="34a65-115">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="34a65-115">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="34a65-116">打开浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。</span><span class="sxs-lookup"><span data-stu-id="34a65-116">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="34a65-117">有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="34a65-117">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="34a65-118">在左侧导航栏中，单击“用户”\*\*\*\*，然后搜索要配置的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="34a65-118">In the left navigation bar, click **Users**, and then search for the user account that you want to configure.</span></span>

4.  <span data-ttu-id="34a65-119">在列出搜索结果的表中，单击相应的用户帐户，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34a65-119">In the table that lists the search results, click the user account, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="34a65-120">在 " **编辑 Lync Server 用户** " 中的 " **存档策略**" 下，选择要应用的存档用户策略。</span><span class="sxs-lookup"><span data-stu-id="34a65-120">In **Edit Lync Server user** under **Archiving policy**, select the archiving user policy that you want to apply.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="34a65-121">" <STRONG> &lt; 自动 &gt; </STRONG>设置" 应用默认服务器安装设置。</span><span class="sxs-lookup"><span data-stu-id="34a65-121">The <STRONG>&lt;Automatic&gt;</STRONG> settings apply the default server installation settings.</span></span> <span data-ttu-id="34a65-122">服务器将自动应用这些设置。</span><span class="sxs-lookup"><span data-stu-id="34a65-122">These settings are applied automatically by the server.</span></span>

    
    </div>

6.  <span data-ttu-id="34a65-123">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="34a65-123">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

