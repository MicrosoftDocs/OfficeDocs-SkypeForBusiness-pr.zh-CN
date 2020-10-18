---
title: 迁移拨入访问号码
description: 迁移拨入访问号码。
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Migrate dial-in access numbers
ms:assetid: e0dfaed2-64c7-45cb-aaa9-d6117a26625d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721909(v=OCS.15)
ms:contentKeyID: 49733843
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e2c8bd34a30bc4b3f8999144cd84a1eee62e2ab1
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579318"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="b9dde-103">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="b9dde-103">Migrate dial-in access numbers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9dde-104">_**上次修改的主题：** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b9dde-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b9dde-105">若要将拨入访问号码从 Lync Server 2010 迁移到 Lync Server 2013，则需要运行 **CsApplicationEndpoint** cmdlet 以迁移 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="b9dde-105">Migrating dial-in access numbers from Lync Server 2010 to Lync Server 2013 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="b9dde-106">在 Lync Server 2010 和 Lync Server 2013 共存期间，您在 Lync Server 2013 中创建的拨入访问号码与您在 Lync Server 2010 中创建的拨入访问号码类似，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="b9dde-106">During the Lync Server 2010 and Lync Server 2013 coexistence period, dial-in access numbers that you created in Lync Server 2013 behave similarly to the dial-in access numbers that you create in Lync Server 2010, as described in this section.</span></span>

<span data-ttu-id="b9dde-107">在迁移之前或之后，在 Lync Server 2010 中创建的电话拨入访问号码已移动到 Lync server 2013，或者在迁移过程中或迁移后2013创建，具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="b9dde-107">Dial-in access numbers that you created in Lync Server 2010 but moved to Lync Server 2013 or that you created in Lync Server 2013 before, during or after migration have the following characteristics:</span></span>

  - <span data-ttu-id="b9dde-108">不会出现在 Office 通信服务器 2007 R2 会议邀请和 "拨入访问号码" 页上。</span><span class="sxs-lookup"><span data-stu-id="b9dde-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="b9dde-109">显示在 Lync Server 2010 会议邀请和 "拨入访问号码" 页上。</span><span class="sxs-lookup"><span data-stu-id="b9dde-109">Appear on Lync Server 2010 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="b9dde-110">显示在 Lync Server 2013 会议邀请和 "拨入访问号码" 页上。</span><span class="sxs-lookup"><span data-stu-id="b9dde-110">Appear on Lync Server 2013 meeting invitations and the dial-in access number page.</span></span>

  - <span data-ttu-id="b9dde-111">无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="b9dde-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

  - <span data-ttu-id="b9dde-112">可以在 Lync Server 2010 控制面板中和 Lync Server 2010 命令行管理程序中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="b9dde-112">Can be viewed and modified in the Lync Server 2010 Control Panel and in Lync Server 2010 Management Shell.</span></span>

  - <span data-ttu-id="b9dde-113">可以在 Lync Server 2013 控制面板中和 Lync Server 2013 命令行管理程序中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="b9dde-113">Can be viewed and modified in the Lync Server 2013 Control Panel and in Lync Server 2013 Management Shell.</span></span>

  - <span data-ttu-id="b9dde-114">可以通过使用 Set-CsDialinConferencingAccessNumber cmdlet 和 Priority 参数在区域内重新排序。</span><span class="sxs-lookup"><span data-stu-id="b9dde-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="b9dde-115">在停用 Lync Server 2010 池之前，您必须完成指向 Lync Server 2010 池的拨入访问号码的迁移。</span><span class="sxs-lookup"><span data-stu-id="b9dde-115">You must finish migrating dial-in access numbers that point to a Lync Server 2010 pool before you decommission the Lync Server 2010 pool.</span></span> <span data-ttu-id="b9dde-116">如果您未按以下过程所述完成拨入访问号码迁移，则对访问号码的传入呼叫将失败。</span><span class="sxs-lookup"><span data-stu-id="b9dde-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="b9dde-117">必须先执行此过程，然后才能解除 Lync Server 2010 池。</span><span class="sxs-lookup"><span data-stu-id="b9dde-117">You must perform this procedure prior to decommissioning the Lync Server 2010 pool.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="b9dde-118">我们建议您在网络使用率较低时移动拨入访问号码，以防出现短时间的服务中断。</span><span class="sxs-lookup"><span data-stu-id="b9dde-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span>



</div>

<span data-ttu-id="b9dde-119">**标识和移动拨入访问号码**</span><span class="sxs-lookup"><span data-stu-id="b9dde-119">**To identify and move dial-in access numbers**</span></span>

1.  <span data-ttu-id="b9dde-120">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9dde-120">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

2.  <span data-ttu-id="b9dde-121">若要将每个拨入访问号码移到驻留在 Lync Server 2013 上的池，请在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="b9dde-121">To move each dial-in access number to a pool hosted on Lync Server 2013, from the command line run:</span></span>
    
        Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>

3.  <span data-ttu-id="b9dde-122">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b9dde-122">Open Lync Server Control Panel.</span></span>

4.  <span data-ttu-id="b9dde-123">在左侧导航栏中，单击“会议”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9dde-123">In the left navigation bar, click **Conferencing**.</span></span>

5.  <span data-ttu-id="b9dde-124">单击 " **拨入访问号码** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9dde-124">Click the **Dial-in Access Number** tab.</span></span>

6.  <span data-ttu-id="b9dde-125">验证您要从中迁移的 Lync Server 2010 池没有保留的拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="b9dde-125">Verify that no dial-in access numbers remain for the Lync Server 2010 pool from which you are migrating.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="b9dde-126">当所有拨入访问号码指向 Lync Server 2013 池时，您就可以停止使用 Lync Server 2010 池了。</span><span class="sxs-lookup"><span data-stu-id="b9dde-126">When all dial-in access numbers point to the Lync Server 2013 pool, you can then decommission the Lync Server 2010 pool.</span></span>

    
    </div>

<span data-ttu-id="b9dde-127">**使用 Lync Server 控制面板验证拨入访问号码迁移**</span><span class="sxs-lookup"><span data-stu-id="b9dde-127">**Verify the dial-in access number migration using Lync Server Control Panel**</span></span>

1.  <span data-ttu-id="b9dde-128">从分配给 **CsUserAdministrator** 角色或 **CsAdministrator** 角色的用户帐户中，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="b9dde-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span>

2.  <span data-ttu-id="b9dde-129">打开“Lync Server 控制面板”。</span><span class="sxs-lookup"><span data-stu-id="b9dde-129">Open Lync Server Control Panel.</span></span>

3.  <span data-ttu-id="b9dde-130">在左侧导航栏中，单击“会议”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="b9dde-130">In the left navigation bar, click **Conferencing**.</span></span>

4.  <span data-ttu-id="b9dde-131">单击 " **拨入访问号码** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b9dde-131">Click the **Dial-in Access Number** tab.</span></span>

5.  <span data-ttu-id="b9dde-132">验证是否已将所有拨入访问号码迁移到在 Lync Server 2013 上托管的池。</span><span class="sxs-lookup"><span data-stu-id="b9dde-132">Verify all the dial-in access number are migrated to the pool hosted on Lync Server 2013.</span></span>

<span data-ttu-id="b9dde-133">**使用 Lync Server 命令行管理程序验证拨入访问号码迁移**</span><span class="sxs-lookup"><span data-stu-id="b9dde-133">**Verify the dial-in access number migration using Lync Server Management Shell**</span></span>

1.  <span data-ttu-id="b9dde-134">打开 Lync Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="b9dde-134">Open Lync Server Management Shell.</span></span>

2.  <span data-ttu-id="b9dde-135">若要从命令行运行，以返回已迁移的所有电话拨入式会议访问号码，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b9dde-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>
    
        Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}

3.  <span data-ttu-id="b9dde-136">验证是否已将所有拨入访问号码迁移到在 Lync Server 2013 上托管的池。</span><span class="sxs-lookup"><span data-stu-id="b9dde-136">Verify all the dial-in access numbers are migrated to the pool hosted on Lync Server 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

