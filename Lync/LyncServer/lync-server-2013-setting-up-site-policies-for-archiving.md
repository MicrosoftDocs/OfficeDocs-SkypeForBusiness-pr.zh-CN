---
title: Lync Server 2013：设置用于存档的网站策略
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Setting up site policies for Archiving
ms:assetid: dc2ea206-8b9c-44dd-a479-efb217593c89
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205325(v=OCS.15)
ms:contentKeyID: 48185613
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 33e5ac47b0bd8c7668fa929fbc5f712ad8d396af
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48521789"
---
# <a name="setting-up-site-policies-for-archiving-in-lync-server-2013"></a><span data-ttu-id="8d600-102">在 Lync Server 2013 中设置用于存档的网站策略</span><span class="sxs-lookup"><span data-stu-id="8d600-102">Setting up site policies for Archiving in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="8d600-103">_**上次修改的主题：** 2012-10-09_</span><span class="sxs-lookup"><span data-stu-id="8d600-103">_**Topic Last Modified:** 2012-10-09_</span></span>

<span data-ttu-id="8d600-104">您可以通过为每个网站创建和配置存档策略来启用或禁用对特定网站的存档。</span><span class="sxs-lookup"><span data-stu-id="8d600-104">You can enable or disable Archiving for specific sites by creating and configuring an Archiving policy for each of those sites.</span></span> <span data-ttu-id="8d600-105">站点策略会覆盖全局策略，但用户策略会覆盖站点策略。</span><span class="sxs-lookup"><span data-stu-id="8d600-105">A site policy overrides the global policy, but user policies override site policies.</span></span> <span data-ttu-id="8d600-106">仅当您不使用 Microsoft Exchange 集成时，或者，如果您使用 Microsoft Exchange 集成，但某些用户不驻留在 Exchange 2013 上，并且其邮箱置于 In-Place 保留状态，则存档策略仅适用。</span><span class="sxs-lookup"><span data-stu-id="8d600-106">Archiving policies only apply if you do not use Microsoft Exchange integration or, if you do use Microsoft Exchange integration, but have some users who are not homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span>

<span data-ttu-id="8d600-107">有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅 [在 Lync Server 2013](lync-server-2013-how-archiving-works.md) 规划文档、部署文档或操作文档中存档的工作原理。</span><span class="sxs-lookup"><span data-stu-id="8d600-107">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="8d600-108">如果为部署启用了 Microsoft Exchange 集成，Exchange In-Place 保留策略将控制是否为驻留在 Exchange 2013 上的用户启用存档，并将其邮箱置于 In-Place 保留状态。</span><span class="sxs-lookup"><span data-stu-id="8d600-108">If you enable Microsoft Exchange integration for your deployment, Exchange In-Place Hold policies control whether archiving is enabled for the users who are homed on Exchange 2013 and have their mailboxes put on In-Place Hold.</span></span> <span data-ttu-id="8d600-109">有关详细信息，请参阅部署文档中的 <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">使用 Exchange Server 集成时，请参阅在 Lync Server 2013 中设置存档策略</A> 。</span><span class="sxs-lookup"><span data-stu-id="8d600-109">For details, see <A href="lync-server-2013-setting-up-policies-for-archiving-when-using-exchange-server-integration.md">Setting up policies for Archiving in Lync Server 2013 when using Exchange Server integration</A> in the Deployment documentation.</span></span><BR><span data-ttu-id="8d600-110">在存档策略中启用内部或外部通信的存档之前，应在存档配置中指定所有适当选项。</span><span class="sxs-lookup"><span data-stu-id="8d600-110">You should specify all appropriate options in the Archiving configurations before enabling Archiving of internal or external communications in the Archiving policies.</span></span> <span data-ttu-id="8d600-111">有关详细信息，请参阅部署文档中的在 <A href="lync-server-2013-configuring-archiving-options.md">Lync Server 2013 中配置存档选项</A> 。</span><span class="sxs-lookup"><span data-stu-id="8d600-111">For details, see <A href="lync-server-2013-configuring-archiving-options.md">Configuring Archiving options in Lync Server 2013</A> in the Deployment documentation.</span></span>



</div>

<div>

## <a name="to-create-an-archiving-policy-for-a-site"></a><span data-ttu-id="8d600-112">为网站创建存档策略</span><span class="sxs-lookup"><span data-stu-id="8d600-112">To create an archiving policy for a site</span></span>

1.  <span data-ttu-id="8d600-113">使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="8d600-113">From a user account that is assigned to the CsArchivingAdministrator or CsAdministrator role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="8d600-114">打开浏览器窗口，然后输入管理员 URL 以打开 Lync Server 2013 控制面板。</span><span class="sxs-lookup"><span data-stu-id="8d600-114">Open a browser window, and then enter the Admin URL to open the Lync Server 2013 Control Panel.</span></span>

3.  <span data-ttu-id="8d600-115">在左侧导航栏中，单击 **“监控和存档”**，然后单击 **“存档策略”**。</span><span class="sxs-lookup"><span data-stu-id="8d600-115">In the left navigation bar, click **Monitoring and Archiving**, and then click **Archiving Policy**.</span></span>
    
    <span data-ttu-id="8d600-116">有关存档策略的工作原理（包括全局、站点和用户策略的层次结构）的详细信息，请参阅 [在 Lync Server 2013](lync-server-2013-how-archiving-works.md) 规划文档、部署文档或操作文档中存档的工作原理。</span><span class="sxs-lookup"><span data-stu-id="8d600-116">For details about how Archiving policies work, including the hierarchy for global, site, and user policies, see [How Archiving works in Lync Server 2013](lync-server-2013-how-archiving-works.md) Planning documentation, Deployment documentation, or Operations documentation.</span></span>

4.  <span data-ttu-id="8d600-117">单击“新建”\*\*\*\*，然后单击“站点策略”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8d600-117">Click **New**, and then click **Site policy**.</span></span>

5.  <span data-ttu-id="8d600-118">在 " **选择站点**" 中，单击要应用该策略的站点。</span><span class="sxs-lookup"><span data-stu-id="8d600-118">In **Select a site**, click the site to which the policy is to be applied.</span></span>

6.  <span data-ttu-id="8d600-119">在 **“新建存档策略”** 中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="8d600-119">In **New Archiving Policy**, do the following:</span></span>
    
      - <span data-ttu-id="8d600-120">在 " **名称**" 中，指定网站策略的名称。</span><span class="sxs-lookup"><span data-stu-id="8d600-120">In **Name**, specify the name for the site policy.</span></span>
    
      - <span data-ttu-id="8d600-121">在 " **说明**" 中，提供有关网站策略 (的信息，例如，Redmond) 的网站策略。</span><span class="sxs-lookup"><span data-stu-id="8d600-121">In **Description**, provide information about what the site policy is (for example, site policy for Redmond).</span></span>
    
      - <span data-ttu-id="8d600-122">若要控制指定站点的内部通信的存档，请选中或清除 " **存档内部通信** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="8d600-122">To control archiving of internal communications for the specified site, select or clear the **Archive internal communications** check box.</span></span>
    
      - <span data-ttu-id="8d600-123">若要控制指定站点的外部通信存档，请选中或清除 " **存档外部通信** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="8d600-123">To control archiving of external communications for the specified site, select or clear the **Archive external communications** check box.</span></span>

7.  <span data-ttu-id="8d600-124">单击“提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="8d600-124">Click **Commit**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

