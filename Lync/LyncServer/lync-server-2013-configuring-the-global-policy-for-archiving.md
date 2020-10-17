---
title: Lync Server 2013：配置全局策略以进行存档
description: Lync Server 2013：配置用于存档的全局策略。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring the global policy for Archiving
ms:assetid: 58341d6b-c3ff-4dd9-b1c7-0048f33861ca
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204906(v=OCS.15)
ms:contentKeyID: 48184192
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8f8125f458c4269626e0b1c929f2acb1a8de0b9
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48556858"
---
# <a name="configuring-the-global-policy-for-archiving-in-lync-server-2013"></a><span data-ttu-id="2b84f-103">在 Lync Server 2013 中配置用于存档的全局策略</span><span class="sxs-lookup"><span data-stu-id="2b84f-103">Configuring the global policy for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2b84f-104">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="2b84f-104">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="2b84f-105">当您部署前端服务器时，Lync Server 将创建一个用于存档的全局策略。</span><span class="sxs-lookup"><span data-stu-id="2b84f-105">When you deploy your Front End Servers, Lync Server creates a global policy for Archiving.</span></span> <span data-ttu-id="2b84f-106">默认情况下，将在全局策略中禁用存档。</span><span class="sxs-lookup"><span data-stu-id="2b84f-106">By default, Archiving is disabled in the global policy.</span></span> <span data-ttu-id="2b84f-107">全局策略控制是否为您的整个部署启用存档以进行内部和外部通信，除非您设置站点策略或用户策略（这将覆盖全局策略），或者您对部分或所有用户使用 Microsoft Exchange 集成。</span><span class="sxs-lookup"><span data-stu-id="2b84f-107">The global policy controls whether archiving is enabled for internal and external communications for your entire deployment, unless you set up site or user policies, which override the global policy, or if you use Microsoft Exchange integration for some or all of your users.</span></span> <span data-ttu-id="2b84f-108">如果使用 Microsoft Exchange 集成，则全局策略不会应用于托管在 Exchange 2013 上并将邮箱置于 In-Place 保留状态的任何用户。</span><span class="sxs-lookup"><span data-stu-id="2b84f-108">If you use Microsoft Exchange integration, the global policy does not apply to any users who are homed on Exchange 2013 and have the mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="2b84f-109">有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅 [在 Lync Server 2013](lync-server-2013-how-archiving-works.md) 规划文档、部署文档或操作文档中存档的工作原理。</span><span class="sxs-lookup"><span data-stu-id="2b84f-109">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="2b84f-110">如果为部署启用了 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。</span><span class="sxs-lookup"><span data-stu-id="2b84f-110">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="2b84f-111">有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。</span><span class="sxs-lookup"><span data-stu-id="2b84f-111">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="2b84f-112">在启用存档之前，应在存档配置中指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="2b84f-112">You should specify all appropriate options in the Archiving configurations before enabling Archiving.</span></span> <span data-ttu-id="2b84f-113">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A> 。</span><span class="sxs-lookup"><span data-stu-id="2b84f-113">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-configure-the-global-policy-for-archiving-when-using-lync-server-archiving-databases"></a><span data-ttu-id="2b84f-114">配置使用 Lync Server 存档数据库时用于存档的全局策略</span><span class="sxs-lookup"><span data-stu-id="2b84f-114">To configure the global policy for archiving when using Lync Server Archiving databases</span></span>

1.  <span data-ttu-id="2b84f-115">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="2b84f-115">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="2b84f-116">打开浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。</span><span class="sxs-lookup"><span data-stu-id="2b84f-116">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span> <span data-ttu-id="2b84f-117">有关可用于启动 Lync Server 2013 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。</span><span class="sxs-lookup"><span data-stu-id="2b84f-117">For details about the different methods you can use to start Lync Server 2013 Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="2b84f-118">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="2b84f-118">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>

4.  <span data-ttu-id="2b84f-119">在“存档策略”\*\*\*\* 页上，单击“全局”\*\*\*\*，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b84f-119">On the **Archiving Policy** page, click **Global**, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="2b84f-120">在“编辑存档策略 - 全局”\*\*\*\* 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="2b84f-120">In **Edit Archiving Policy - Global**, do the following:</span></span>
    
      - <span data-ttu-id="2b84f-121">在“名称”\*\*\*\* 中，如果不想使用全局策略的默认名称 Global，可以为其指定新名称。</span><span class="sxs-lookup"><span data-stu-id="2b84f-121">In **Name**, if you do not want to use the default name of Global, specify a new name for the global policy.</span></span>
    
      - <span data-ttu-id="2b84f-122">在“说明”\*\*\*\* 中，提供有关该策略内容的信息（例如，*divisionName* 的全局策略）</span><span class="sxs-lookup"><span data-stu-id="2b84f-122">In **Description**, provide information about what the policy is (for example, Global policy for *divisionName*).</span></span>
    
      - <span data-ttu-id="2b84f-123">要控制未通过特定站点策略或用户策略控制的所有站点和用户的内部通信存档，请选中或清除“存档内部通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="2b84f-123">To control archiving of internal communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="2b84f-124">要控制未通过特定站点策略或用户策略控制的所有站点和用户的外部通信存档，请选中或清除“存档外部通信”\*\*\*\* 复选框。</span><span class="sxs-lookup"><span data-stu-id="2b84f-124">To control archiving of external communications for all sites and users not specifically controlled through a site policy or user policy, select or clear the **Archive external communications** check box.</span></span>

6.  <span data-ttu-id="2b84f-125">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="2b84f-125">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

