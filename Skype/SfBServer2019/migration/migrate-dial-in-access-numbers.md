---
title: 迁移拨入访问号码
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 迁移拨入访问号码到业务服务器 2019年的 Skype 需要运行 Move-csapplicationendpoint cmdlet 迁移的联系对象。 在旧的安装和 Skype 业务服务器 2019年共存期间，在 Skype for Business Server 2019 中创建的拨入访问号码行为类似旧安装中创建的拨入访问号码中所述部分。
ms.openlocfilehash: 697ffb05e54722576f15dce2b4e7f0721b255aa2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/04/2018
ms.locfileid: "25370726"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="c58f0-104">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="c58f0-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="c58f0-105">迁移拨入访问号码到业务服务器 2019年的 Skype 需要运行**Move-csapplicationendpoint** cmdlet 迁移的联系对象。</span><span class="sxs-lookup"><span data-stu-id="c58f0-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="c58f0-106">在旧的安装和 Skype 业务服务器 2019年共存期间，在 Skype for Business Server 2019 中创建的拨入访问号码行为类似旧安装中创建的拨入访问号码中所述部分。</span><span class="sxs-lookup"><span data-stu-id="c58f0-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="c58f0-107">您在旧中创建的拨入访问号码安装，但移动到 Skype 业务服务器 2019，或您在 Skype for Business Server 2019 之前，创建期间或迁移后，具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="c58f0-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="c58f0-108">不显示在 Office Communications Server 2007 R2 会议邀请和拨入访问号码页。</span><span class="sxs-lookup"><span data-stu-id="c58f0-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c58f0-109">显示在旧安装会议邀请和拨入访问号码页。</span><span class="sxs-lookup"><span data-stu-id="c58f0-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c58f0-110">业务服务器 2019年会议邀请和拨入访问号码页上显示在 Skype 上。</span><span class="sxs-lookup"><span data-stu-id="c58f0-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="c58f0-111">无法查看或修改 Office Communications Server 2007 R2 管理工具中。</span><span class="sxs-lookup"><span data-stu-id="c58f0-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="c58f0-112">可以查看和修改旧安装控制面板和旧安装命令行管理程序中。</span><span class="sxs-lookup"><span data-stu-id="c58f0-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="c58f0-113">可以查看和修改业务 Server 2019 控制面板的 Skype 和 Skype 的业务服务器 2019年命令行管理程序中。</span><span class="sxs-lookup"><span data-stu-id="c58f0-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="c58f0-114">可以在区域内重新排序使用带有 Priority 参数的 Set-csdialinconferencingaccessnumber cmdlet。</span><span class="sxs-lookup"><span data-stu-id="c58f0-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="c58f0-115">您必须完成迁移拨入访问号码指向旧的安装池之前停用旧安装池。</span><span class="sxs-lookup"><span data-stu-id="c58f0-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="c58f0-116">如果您未完成电话拨入访问号码迁移以下过程中所述，将失败传入呼叫的访问号码。</span><span class="sxs-lookup"><span data-stu-id="c58f0-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c58f0-117">您必须执行此过程之前在停用旧安装池。</span><span class="sxs-lookup"><span data-stu-id="c58f0-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="c58f0-118">我们建议您没有的服务中断期间较短的情况下，网络使用率较低时, 移动拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="c58f0-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="c58f0-119">确认和移动电话拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="c58f0-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="c58f0-120">为业务 Server 命令行管理程序启动 Skype： 单击**开始**，单击**所有程序**，都单击**Microsoft Skype 的业务服务器 2019年**，，然后都单击**Skype 的业务 Server Management Shell**。</span><span class="sxs-lookup"><span data-stu-id="c58f0-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="c58f0-121">若要将每个拨入访问号码移动到的业务服务器 2019 Skype 上承载的池，从命令行运行：</span><span class="sxs-lookup"><span data-stu-id="c58f0-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="c58f0-122">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c58f0-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="c58f0-123">在左侧导航栏中，单击“**会议**”。</span><span class="sxs-lookup"><span data-stu-id="c58f0-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="c58f0-124">单击**电话拨入访问号码**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c58f0-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="c58f0-125">确认要从中迁移的旧安装池没有保留任何拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="c58f0-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c58f0-126">当所有拨入访问号码都指向业务服务器 2019年池 Skype 时，然后可以停用旧安装池。</span><span class="sxs-lookup"><span data-stu-id="c58f0-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="c58f0-127">确认用于业务 Server Control Panel Skype 拨入访问号码迁移</span><span class="sxs-lookup"><span data-stu-id="c58f0-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="c58f0-128">使用分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="c58f0-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="c58f0-129">打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c58f0-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c58f0-130">在左侧导航栏中，单击“**会议**”。</span><span class="sxs-lookup"><span data-stu-id="c58f0-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="c58f0-131">单击**电话拨入访问号码**选项卡。</span><span class="sxs-lookup"><span data-stu-id="c58f0-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="c58f0-132">确认所有拨入访问号码均已都迁移到的业务服务器 2019 Skype 上承载的池。</span><span class="sxs-lookup"><span data-stu-id="c58f0-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="c58f0-133">确认电话拨入访问号码迁移 Skype 用于业务 Server 命令行管理程序</span><span class="sxs-lookup"><span data-stu-id="c58f0-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="c58f0-134">打开 Skype 业务 Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="c58f0-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="c58f0-135">若要返回所有的电话拨入式会议访问号码迁移，从命令行运行：</span><span class="sxs-lookup"><span data-stu-id="c58f0-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="c58f0-136">确认所有拨入访问号码均已都迁移到的业务服务器 2019 Skype 上承载的池。</span><span class="sxs-lookup"><span data-stu-id="c58f0-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


