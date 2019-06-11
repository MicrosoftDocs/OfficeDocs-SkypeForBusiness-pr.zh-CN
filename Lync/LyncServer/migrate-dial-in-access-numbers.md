---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f4f0f286450aeaaf747d4642bf8791695d16b603
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845218"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="d84e7-102">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="d84e7-102">Migrate dial-in access numbers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d84e7-103">_**主题上次修改时间:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="d84e7-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="d84e7-104">将 Lync Server 2010 中的拨入访问号码迁移到 Lync Server 2013 需要运行**CsApplicationEndpoint** cmdlet 以迁移联系人对象。</span><span class="sxs-lookup"><span data-stu-id="d84e7-104">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="d84e7-105">在 Lync Server 2010 和 Lync Server 2013 共存期内, 在 Lync Server 2013 中创建的拨入访问号码与您在 Lync Server 2010 中创建的拨入访问号码类似, 如本部分所述。</span><span class="sxs-lookup"><span data-stu-id="d84e7-105">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="d84e7-106">您在 Lync Server 2010 中创建的拨入接入号码, 但迁移到 Lync Server 2013 或在迁移期间或之后在 Lync Server 2013 中创建的号码具有以下特征:</span><span class="sxs-lookup"><span data-stu-id="d84e7-106">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="d84e7-107">不会出现在 Office 通信服务器 2007 R2 邀请和 "拨入访问号码" 页面上。</span><span class="sxs-lookup"><span data-stu-id="d84e7-107">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="d84e7-108">显示在 Lync Server 2010 的 "会议邀请" 和 "拨入访问号码" 页面上。</span><span class="sxs-lookup"><span data-stu-id="d84e7-108">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="d84e7-109">显示在 Lync Server 2013 的 "会议邀请" 和 "拨入访问号码" 页面上。</span><span class="sxs-lookup"><span data-stu-id="d84e7-109">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="d84e7-110">无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="d84e7-110">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="d84e7-111">可在 Lync Server 2010 控制面板和 Lync Server 2010 管理外壳程序中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="d84e7-111">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="d84e7-112">可在 Lync Server 2013 控制面板和 Lync Server 2013 管理外壳程序中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="d84e7-112">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="d84e7-113">可通过将 CsDialinConferencingAccessNumber cmdlet 与 Priority 参数一起使用来在区域内重新排序。</span><span class="sxs-lookup"><span data-stu-id="d84e7-113">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="d84e7-114">在解除 Lync Server 2010 池之前, 必须完成指向 Lync Server 2010 池的迁移拨入访问号码的迁移。</span><span class="sxs-lookup"><span data-stu-id="d84e7-114">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="d84e7-115">如果您没有完成拨入访问号码迁移, 如以下过程中所述, 对接入号码的拨入调用将失败。</span><span class="sxs-lookup"><span data-stu-id="d84e7-115">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d84e7-116">必须先执行此过程, 然后才能解除 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="d84e7-116">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="d84e7-117">我们建议你在网络使用率较低时移动拨入访问号码, 以防出现短时间的服务中断。</span><span class="sxs-lookup"><span data-stu-id="d84e7-117">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="d84e7-118">**标识和移动拨入访问号码**</span><span class="sxs-lookup"><span data-stu-id="d84e7-118">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="d84e7-119">启动 Lync Server 命令行管理程序: 依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**", 然后单击 " **Lync server Management shell**"。</span><span class="sxs-lookup"><span data-stu-id="d84e7-119">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="d84e7-120">要将每个拨入访问号码从命令行运行到 Lync Server 2013 上托管的池, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d84e7-120">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="d84e7-121">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="d84e7-121">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="d84e7-122">在左侧导航栏中，单击“**会议**”。</span><span class="sxs-lookup"><span data-stu-id="d84e7-122">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="d84e7-123">单击 "**拨入访问号码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d84e7-123">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="d84e7-124">验证你要从中迁移的 Lync Server 2010 池不会保留拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="d84e7-124">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="d84e7-125">当所有拨入访问号码都指向 Lync Server 2013 池时, 您就可以停止 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="d84e7-125">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="d84e7-126">**使用 Lync Server "控制面板" 验证拨入访问号码迁移**</span><span class="sxs-lookup"><span data-stu-id="d84e7-126">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="d84e7-127">从分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="d84e7-127">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="d84e7-128">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="d84e7-128">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="d84e7-129">在左侧导航栏中，单击“**会议**”。</span><span class="sxs-lookup"><span data-stu-id="d84e7-129">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="d84e7-130">单击 "**拨入访问号码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="d84e7-130">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="d84e7-131">验证所有拨入访问号码是否已迁移到 Lync Server 2013 上托管的池。</span><span class="sxs-lookup"><span data-stu-id="d84e7-131">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="d84e7-132">**使用 Lync Server 命令行管理程序验证拨入访问号码迁移**</span><span class="sxs-lookup"><span data-stu-id="d84e7-132">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="d84e7-133">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="d84e7-133">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="d84e7-134">要从命令行中返回已迁移的所有拨入式会议访问号码, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="d84e7-134">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="d84e7-135">验证所有拨入访问号码是否已迁移到 Lync Server 2013 上托管的池。</span><span class="sxs-lookup"><span data-stu-id="d84e7-135">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

