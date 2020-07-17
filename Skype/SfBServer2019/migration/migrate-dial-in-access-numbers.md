---
title: 迁移拨入访问号码
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: 将拨入访问号码迁移到 Skype for business Server 2019 需要运行 CsApplicationEndpoint cmdlet 来迁移 contact 对象。 在旧版安装和 Skype for business Server 2019 共存期间，您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧版安装中创建的拨入访问号码类似，如本节中所述。
ms.openlocfilehash: 0df71debe8a6d5c686d8bce17b837f32a4ca2bab
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/16/2020
ms.locfileid: "44752694"
---
# <a name="migrate-dial-in-access-numbers"></a><span data-ttu-id="f85ae-104">迁移拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="f85ae-104">Migrate dial-in access numbers</span></span>

<span data-ttu-id="f85ae-105">将拨入访问号码迁移到 Skype for business Server 2019 需要运行**CsApplicationEndpoint** cmdlet 来迁移 contact 对象。</span><span class="sxs-lookup"><span data-stu-id="f85ae-105">Migrating dial-in access numbers to Skype for Business Server 2019 requires running the **Move-CsApplicationEndpoint** cmdlet to migrate the contact objects.</span></span> <span data-ttu-id="f85ae-106">在旧版安装和 Skype for business Server 2019 共存期间，您在 Skype for Business Server 2019 中创建的拨入访问号码与您在旧版安装中创建的拨入访问号码类似，如本节中所述。</span><span class="sxs-lookup"><span data-stu-id="f85ae-106">During the legacy install and Skype for Business Server 2019 coexistence period, dial-in access numbers that you created in Skype for Business Server 2019 behave similarly to the dial-in access numbers that you create in the legacy install, as described in this section.</span></span> 

<span data-ttu-id="f85ae-107">您在旧版安装中创建但移动到 Skype for business Server 2019 的拨入访问号码，或者在迁移过程中、迁移过程中或迁移之后，您在 Skype for business Server 2019 中创建的号码具有以下特征：</span><span class="sxs-lookup"><span data-stu-id="f85ae-107">Dial-in access numbers that you created in the legacy install but moved to Skype for Business Server 2019, or that you created in Skype for Business Server 2019 before, during, or after migration, have the following characteristics:</span></span>

- <span data-ttu-id="f85ae-108">不会出现在 Office 通信服务器 2007 R2 会议邀请和 "拨入访问号码" 页上。</span><span class="sxs-lookup"><span data-stu-id="f85ae-108">Do not appear on Office Communications Server 2007 R2 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="f85ae-109">显示在旧版 "安装会议邀请" 和 "拨入访问号码" 页上。</span><span class="sxs-lookup"><span data-stu-id="f85ae-109">Appear on the legacy install meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="f85ae-110">出现在 Skype for Business Server 2019 会议邀请和 "拨入访问号码" 页上。</span><span class="sxs-lookup"><span data-stu-id="f85ae-110">Appear on Skype for Business Server 2019 meeting invitations and the dial-in access number page.</span></span>

- <span data-ttu-id="f85ae-111">无法在 Office 通信服务器 2007 R2 管理工具中查看或修改。</span><span class="sxs-lookup"><span data-stu-id="f85ae-111">Cannot be viewed or modified in the Office Communications Server 2007 R2 administrative tool.</span></span>

- <span data-ttu-id="f85ae-112">可以在旧版安装控制面板和旧版安装命令行管理程序中进行查看和修改。</span><span class="sxs-lookup"><span data-stu-id="f85ae-112">Can be viewed and modified in the legacy install Control Panel and in the legacy install Management Shell.</span></span>

- <span data-ttu-id="f85ae-113">可以在 Skype for Business Server 2019 控制面板和 Skype for Business Server 2019 命令行管理程序中查看和修改。</span><span class="sxs-lookup"><span data-stu-id="f85ae-113">Can be viewed and modified in the Skype for Business Server 2019 Control Panel and in Skype for Business Server 2019 Management Shell.</span></span>

- <span data-ttu-id="f85ae-114">可以通过使用 Set-csdialinconferencingaccessnumber cmdlet 和 Priority 参数在区域内重新排序。</span><span class="sxs-lookup"><span data-stu-id="f85ae-114">Can be re-sequenced within the region by using the Set-CsDialinConferencingAccessNumber cmdlet with the Priority parameter.</span></span>

<span data-ttu-id="f85ae-115">在停止旧版安装池之前，必须完成指向旧版安装池的拨入访问号码的迁移。</span><span class="sxs-lookup"><span data-stu-id="f85ae-115">You must finish migrating dial-in access numbers that point to the legacy install pool before you decommission the legacy install pool.</span></span> <span data-ttu-id="f85ae-116">如果您未按以下过程所述完成拨入访问号码迁移，则对访问号码的传入呼叫将失败。</span><span class="sxs-lookup"><span data-stu-id="f85ae-116">If you do not complete dial-in access number migration as described in the following procedure, incoming calls to the access numbers will fail.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f85ae-117">必须先执行此过程，然后才能解除旧版安装池。</span><span class="sxs-lookup"><span data-stu-id="f85ae-117">You must perform this procedure prior to decommissioning the legacy install pool.</span></span> 

> [!NOTE]
> <span data-ttu-id="f85ae-118">我们建议您在网络使用率较低时移动拨入访问号码，以防出现短时间的服务中断。</span><span class="sxs-lookup"><span data-stu-id="f85ae-118">We recommend that you move dial-in access numbers when network usage is low, in case there is a short period of service outage.</span></span> 

## <a name="to-identify-and-move-dial-in-access-numbers"></a><span data-ttu-id="f85ae-119">标识和移动拨入访问号码</span><span class="sxs-lookup"><span data-stu-id="f85ae-119">To identify and move dial-in access numbers</span></span>

1. <span data-ttu-id="f85ae-120">启动 Skype for Business Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Skype for business server 2019**"，然后单击 " **Skype for business server Management Shell**"。</span><span class="sxs-lookup"><span data-stu-id="f85ae-120">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Skype for Business Server 2019**, and then click **Skype for Business Server Management Shell**.</span></span>

2. <span data-ttu-id="f85ae-121">若要将每个拨入访问号码移到托管在 Skype for Business Server 2019 上的池，请在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="f85ae-121">To move each dial-in access number to a pool hosted on Skype for Business Server 2019, from the command line run:</span></span> 

   ```PowerShell
   Move-CsApplicationEndpoint -Identity <SIP URI of the access number to be moved> -Target <FQDN of the pool to which the access number is moving>
   ```

3. <span data-ttu-id="f85ae-122">打开 "Skype for Business Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f85ae-122">Open Skype for Business Server Control Panel.</span></span>

4. <span data-ttu-id="f85ae-123">在左侧导航栏中，单击“会议”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f85ae-123">In the left navigation bar, click **Conferencing**.</span></span>

5. <span data-ttu-id="f85ae-124">单击 "**拨入访问号码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f85ae-124">Click the **Dial-in Access Number** tab.</span></span> 

6. <span data-ttu-id="f85ae-125">验证您要从中迁移的旧版安装池不会保留任何拨入访问号码。</span><span class="sxs-lookup"><span data-stu-id="f85ae-125">Verify that no dial-in access numbers remain for the legacy install pool from which you are migrating.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f85ae-126">当所有拨入访问号码都指向 Skype for Business Server 2019 池时，您就可以停止使用旧版安装池了。</span><span class="sxs-lookup"><span data-stu-id="f85ae-126">When all dial-in access numbers point to the Skype for Business Server 2019 pool, you can then decommission the legacy install pool.</span></span> 

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-control-panel"></a><span data-ttu-id="f85ae-127">使用 Skype for Business Server 控制面板验证拨入访问号码迁移</span><span class="sxs-lookup"><span data-stu-id="f85ae-127">Verify the dial-in access number migration using Skype for Business Server Control Panel</span></span>

1. <span data-ttu-id="f85ae-128">从分配给**CsUserAdministrator**角色或**CsAdministrator**角色的用户帐户中，登录到内部部署中的任何计算机。</span><span class="sxs-lookup"><span data-stu-id="f85ae-128">From a user account that is assigned to the **CsUserAdministrator** role or the **CsAdministrator** role, log on to any computer in your internal deployment.</span></span> 

2. <span data-ttu-id="f85ae-129">打开 "Skype for Business Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="f85ae-129">Open Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="f85ae-130">在左侧导航栏中，单击“会议”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f85ae-130">In the left navigation bar, click **Conferencing**.</span></span>

4. <span data-ttu-id="f85ae-131">单击 "**拨入访问号码**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f85ae-131">Click the **Dial-in Access Number** tab.</span></span> 

5. <span data-ttu-id="f85ae-132">验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。</span><span class="sxs-lookup"><span data-stu-id="f85ae-132">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>

## <a name="verify-the-dial-in-access-number-migration-using-skype-for-business-server-management-shell"></a><span data-ttu-id="f85ae-133">使用 Skype for Business Server 命令行管理程序验证拨入访问号码迁移</span><span class="sxs-lookup"><span data-stu-id="f85ae-133">Verify the dial-in access number migration using Skype for Business Server Management Shell</span></span>

1. <span data-ttu-id="f85ae-134">打开 Skype for Business Server 命令行管理程序。</span><span class="sxs-lookup"><span data-stu-id="f85ae-134">Open Skype for Business Server Management Shell.</span></span>

2. <span data-ttu-id="f85ae-135">若要从命令行运行，以返回已迁移的所有电话拨入式会议访问号码，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="f85ae-135">To return all the dial-in conferencing access numbers migrated, from the command line run:</span></span>

   ```PowerShell
   Get-CsDialInConferencingAccessNumber -Filter {Pool -eq "<FQDN of the pool to which the access number is moved>"}
   ```

3. <span data-ttu-id="f85ae-136">验证所有拨入访问号码是否已迁移到托管在 Skype for business Server 2019 上的池。</span><span class="sxs-lookup"><span data-stu-id="f85ae-136">Verify that all the dial-in access numbers are migrated to the pool hosted on Skype for Business Server 2019.</span></span>


