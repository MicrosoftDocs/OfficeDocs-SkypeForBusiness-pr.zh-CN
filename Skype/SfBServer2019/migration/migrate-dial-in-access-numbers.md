---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: 将拨入访问号码迁移到 Skype for business 服务器2019需要运行 CsApplicationEndpoint cmdlet 以迁移联系人对象。 在旧式安装和 Skype for business Server 2019 共存期间，您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧安装中创建的拨入访问号码类似，如下所述：顶部.
ms.openlocfilehash: 35c1e665f8affdbf84628f9a7d532405779648f0
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/08/2020
ms.locfileid: "40991137"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="e3502-104">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="e3502-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="e3502-105">将拨入访问号码迁移到 Skype for business 服务器2019需要运行**CsApplicationEndpoint** cmdlet 以迁移联系人对象。</span><span class="sxs-lookup"><span data-stu-id="e3502-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="e3502-106">在旧式安装和 Skype for business Server 2019 共存期间，您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧安装中创建的拨入访问号码类似，如下所述：顶部.</span><span class="sxs-lookup"><span data-stu-id="e3502-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="e3502-107">在旧安装中创建的拨入接入号码，但移动到 Skype for business Server 2019，或者在迁移期间或迁移后的 Skype for business Server 2019 中创建的号码具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="e3502-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="e3502-108">不会出现在 Office 通信服务器 2007 R2 邀请和 "拨入访问号码" 页面上。</span><span class="sxs-lookup"><span data-stu-id="e3502-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="e3502-109">显示在 "旧版安装会议邀请" 和 "拨入访问号码" 页面上。</span><span class="sxs-lookup"><span data-stu-id="e3502-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="e3502-110">显示在 Skype for Business Server 2019 会议邀请和 "拨入访问号码" 页面上。</span><span class="sxs-lookup"><span data-stu-id="e3502-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="e3502-111">无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="e3502-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="e3502-112">可在旧式安装控制面板和旧式安装命令行中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="e3502-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="e3502-113">可在 Skype for Business Server 2019 控制面板和 Skype for business Server 2019 管理外壳程序中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="e3502-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="e3502-114">可通过将 CsDialinConferencingAccessNumber cmdlet 与 Priority 参数一起使用来在区域内重新排序。</span><span class="sxs-lookup"><span data-stu-id="e3502-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="e3502-115">在停止旧版安装池之前，必须完成指向旧安装池的拨入访问号码的迁移。</span><span class="sxs-lookup"><span data-stu-id="e3502-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="e3502-116">如果您没有完成拨入访问号码迁移，如以下过程中所述，对接入号码的拨入调用将失败。</span><span class="sxs-lookup"><span data-stu-id="e3502-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e3502-117">必须先执行此过程，然后才能解除旧版安装池。</span><span class="sxs-lookup"><span data-stu-id="e3502-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="e3502-118">我们建议你在网络使用率较低时移动拨入访问号码，以防出现短时间的服务中断。</span><span class="sxs-lookup"><span data-stu-id="e3502-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="e3502-119">标识和移动拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="e3502-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="e3502-120">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft skype for business server 2019**"，然后单击 " **skype for business 服务器管理外壳**"。</span><span class="sxs-lookup"><span data-stu-id="e3502-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="e3502-121">若要将每个拨入访问号码移到托管在 Skype for Business Server 2019 上的池，请从命令行运行：</span><span class="sxs-lookup"><span data-stu-id="e3502-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="e3502-122">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="e3502-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="e3502-123">在左侧导航栏中，单击“**会议**”。</span><span class="sxs-lookup"><span data-stu-id="e3502-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="e3502-124">单击 "**拨入访问号码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e3502-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="e3502-125">验证你要从中迁移的旧版安装池不会保留拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="e3502-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3502-126">当所有拨入访问号码指向 Skype for business Server 2019 池时，您就可以停止使用旧安装池。</span><span class="sxs-lookup"><span data-stu-id="e3502-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="e3502-127">使用 Skype for Business Server "控制面板" 验证拨入访问号码迁移</span><span class="sxs-lookup"><span data-stu-id="e3502-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="e3502-128">从分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="e3502-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="e3502-129">打开 "Skype for Business 服务器" 控制面板。</span><span class="sxs-lookup"><span data-stu-id="e3502-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="e3502-130">在左侧导航栏中，单击“**会议**”。</span><span class="sxs-lookup"><span data-stu-id="e3502-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="e3502-131">单击 "**拨入访问号码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e3502-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="e3502-132">验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。</span><span class="sxs-lookup"><span data-stu-id="e3502-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="e3502-133">使用 Skype for Business Server 命令行管理程序验证拨入访问号码迁移</span><span class="sxs-lookup"><span data-stu-id="e3502-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="e3502-134">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="e3502-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="e3502-135">要从命令行中返回已迁移的所有拨入式会议访问号码，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="e3502-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="e3502-136">验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。</span><span class="sxs-lookup"><span data-stu-id="e3502-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


