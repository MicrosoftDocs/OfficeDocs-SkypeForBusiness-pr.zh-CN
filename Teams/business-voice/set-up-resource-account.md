---
title: 设置Microsoft 365 商务语音资源帐户
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: 了解如何设置一个Microsoft 365 商务语音自动助理使用的资源帐户。
appliesto:
- Microsoft Teams
ms.openlocfilehash: df5001b6f757b407e96a473d302c79d837af957c
ms.sourcegitcommit: 38fa37d83704200911866cf017566fcb128ea2fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105164"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="95f41-103">步骤 4：设置 Business Voice 资源帐户</span><span class="sxs-lookup"><span data-stu-id="95f41-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="95f41-104">资源帐户不会分配给任何特定用户。</span><span class="sxs-lookup"><span data-stu-id="95f41-104">Resource accounts aren't assigned to any specific user.</span></span> <span data-ttu-id="95f41-105">相反，使用免费虚拟用户许可证的资源帐户由虚拟机中的设备和服务Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="95f41-105">Instead, resource accounts, which use a free virtual user license, are used by devices and services in Microsoft 365.</span></span> <span data-ttu-id="95f41-106">在Microsoft Teams，为资源帐户分配电话号码，然后与自动助理和呼叫队列相关联。</span><span class="sxs-lookup"><span data-stu-id="95f41-106">In Microsoft Teams, resource accounts are assigned phone numbers and are then associated with auto attendants and call queues.</span></span>

<span data-ttu-id="95f41-107">通过将资源帐户关联到自动助理和呼叫队列，可以添加一个或多个收费或免费电话号码。</span><span class="sxs-lookup"><span data-stu-id="95f41-107">By associating resource accounts to auto attendants and call queues, you can add one or more toll or toll-free phone numbers to them.</span></span> <span data-ttu-id="95f41-108">例如，可以将一个资源帐户与收费电话号码关联到本地呼叫者的自动助理。</span><span class="sxs-lookup"><span data-stu-id="95f41-108">For example, you could associate one resource account with a toll number to an auto attendant for local callers.</span></span> <span data-ttu-id="95f41-109">对于长距离呼叫，可以将另一个资源帐户与免费电话号码关联到同一个自动助理。</span><span class="sxs-lookup"><span data-stu-id="95f41-109">For long distance calls, you could associate another resource account with a toll-free number to the same auto attendant.</span></span>

<span data-ttu-id="95f41-110">本文中的部分介绍了如何设置资源帐户，然后为其分配电话号码。</span><span class="sxs-lookup"><span data-stu-id="95f41-110">The sections in this article show you how to set up a resource account and then assign a phone number to it.</span></span> <span data-ttu-id="95f41-111">稍后，你将将资源帐户与自动助理关联。</span><span class="sxs-lookup"><span data-stu-id="95f41-111">Later on, you'll associate the resource account with an auto attendant.</span></span>

<span data-ttu-id="95f41-112">以下视频演示如何在管理中心内完成Teams步骤。</span><span class="sxs-lookup"><span data-stu-id="95f41-112">The following video shows you how to complete these steps in the Teams admin center.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4OFYG]

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="95f41-113">获取虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="95f41-113">Obtain virtual user licenses</span></span>

<span data-ttu-id="95f41-114">资源帐户需要许可证才能使用自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="95f41-114">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="95f41-115">可以使用免费的虚拟Microsoft 365 电话系统 *- 虚拟用户* 许可证。</span><span class="sxs-lookup"><span data-stu-id="95f41-115">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

> [!NOTE]
> <span data-ttu-id="95f41-116">如果已注册 Business Voice 试用期，应只需执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="95f41-116">You should only need to perform the following steps if you've signed up for a Business Voice trial period.</span></span> <span data-ttu-id="95f41-117">如果你购买了 Business Voice 许可证，则虚拟许可证应该已应用到你的帐户。</span><span class="sxs-lookup"><span data-stu-id="95f41-117">If you purchased Business Voice licenses, virtual licenses should already be applied to your account.</span></span> 
>
> <span data-ttu-id="95f41-118">若要查看是否已有虚拟许可证，Microsoft 365具有全局管理员权限的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="95f41-118">To see if you already have virtual licenses, log into Microsoft 365 using an account with Global admin permissions.</span></span> <span data-ttu-id="95f41-119">然后转到"你的>[计费"。](https://admin.microsoft.com/Adminportal/Home#/subscriptions)</span><span class="sxs-lookup"><span data-stu-id="95f41-119">Then go to Billing > [Your products](https://admin.microsoft.com/Adminportal/Home#/subscriptions).</span></span> <span data-ttu-id="95f41-120">如果有虚拟许可证，它们将显示为"Microsoft 365 电话系统 **- 虚拟用户"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-120">If you have virtual licenses, they'll appear as **Microsoft 365 Phone System - Virtual User**.</span></span>

1. <span data-ttu-id="95f41-121">打开Microsoft 365 管理中心帐户，使用全局管理员用户登录 (该帐户通常是用于注册帐户的帐户Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="95f41-121">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="95f41-122">在左侧导航窗格中，转到"<a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**计费**  >  **购买服务**</a>  >  **加载项**  >  **""查看所有附加内容产品"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-122">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/catalog" target="_blank">**Billing** > **Purchase services**</a> > **Add-ons** > **See all Add-ons products**.</span></span>
3. <span data-ttu-id="95f41-123">滚动到末尾，找到 **"Microsoft 365 电话系统 – 虚拟用户"** 许可证。</span><span class="sxs-lookup"><span data-stu-id="95f41-123">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="95f41-124">选择"**详细信息"，** 然后选择"**购买"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-124">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="95f41-125">在许可证购买页上，选择想要的虚拟用户许可证数。</span><span class="sxs-lookup"><span data-stu-id="95f41-125">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="95f41-126">需要为计划设置的每个自动助理和呼叫队列提供一个虚拟许可证。</span><span class="sxs-lookup"><span data-stu-id="95f41-126">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="95f41-127">我们建议选择至少五个许可证，以便将来可以轻松设置更多自动助理和呼叫队列，而无需立即购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="95f41-127">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="95f41-128">取消 **选中"自动分配给没有许可证的所有用户"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-128">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="95f41-129">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-129">Select **Check out now**.</span></span>
7. <span data-ttu-id="95f41-130">确认订单，选择"下一 **步**"，然后选择"**下订单"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-130">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="95f41-131">请记住，即使许可证的成本  **为零** ，仍必须购买许可证。</span><span class="sxs-lookup"><span data-stu-id="95f41-131">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="95f41-132">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="95f41-132">Create a resource account</span></span>

<span data-ttu-id="95f41-133">收到"虚拟 *用户Microsoft 365 电话系统后*，可以创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="95f41-133">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![添加资源帐户用户界面的屏幕截图](../media/resource-account-add.png)

1. <span data-ttu-id="95f41-135">打开 Microsoft Teams 管理中心，使用全局管理员用户登录 (该帐户通常是用于注册 Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="95f41-135">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
2. <span data-ttu-id="95f41-136">在左侧导航窗格中，转到"<a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**组织范围的设置""**  >  **资源帐户"。**</a></span><span class="sxs-lookup"><span data-stu-id="95f41-136">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
3. <span data-ttu-id="95f41-137">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="95f41-137">Select **Add**.</span></span>
4. <span data-ttu-id="95f41-138">在"**添加资源帐户"** 窗格中，填写 **"显示名称"，** 然后填写"**用户名"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-138">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="95f41-139">选择描述性显示名称例如"主行自动助理"来描述资源帐户的用途。</span><span class="sxs-lookup"><span data-stu-id="95f41-139">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
5. <span data-ttu-id="95f41-140">在 **"资源帐户类型"中**，选择 **"自动助理"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-140">In **Resource account type**, select **Auto attendant**.</span></span>
6. <span data-ttu-id="95f41-141">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="95f41-141">Select **Save**.</span></span>

![资源帐户列表的屏幕截图](../media/resource-accounts-auto-attendant-only-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="95f41-143">分配许可证</span><span class="sxs-lookup"><span data-stu-id="95f41-143">Assign a license</span></span>

<span data-ttu-id="95f41-144">创建资源帐户后，需要分配一个 Microsoft 365 电话系统 *-* 虚拟用户 *许可证或电话系统* 许可证。</span><span class="sxs-lookup"><span data-stu-id="95f41-144">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

!["许可证分配"用户界面的屏幕截图Microsoft 365 管理中心](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="95f41-146">打开Microsoft 365 管理中心帐户，使用全局管理员用户登录 (该帐户通常是用于注册帐户的帐户Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="95f41-146">Open the Microsoft 365 admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="95f41-147">在左侧导航窗格中，转到"用户 <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">  >  **""活动用户"。**</a></span><span class="sxs-lookup"><span data-stu-id="95f41-147">In the left navigation pane, go to <a href="https://admin.microsoft.com/Adminportal/Home#/users" target="_blank">**Users** > **Active users**</a>.</span></span>
1. <span data-ttu-id="95f41-148">选择资源帐户。</span><span class="sxs-lookup"><span data-stu-id="95f41-148">Select your resource account.</span></span>
1. <span data-ttu-id="95f41-149">在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-149">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="95f41-150">选择 **"保存更改"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-150">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="95f41-151">分配服务编号</span><span class="sxs-lookup"><span data-stu-id="95f41-151">Assign a service number</span></span>

![分配服务编号用户界面的屏幕截图](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="95f41-153">打开 Microsoft Teams 管理中心，使用全局管理员用户登录 (该帐户通常是用于注册 Microsoft 365) 。</span><span class="sxs-lookup"><span data-stu-id="95f41-153">Open the Microsoft Teams admin center and log in with a user that is a Global admin (this is usually the account you used to sign up for Microsoft 365).</span></span>
1. <span data-ttu-id="95f41-154">在左侧导航窗格中，转到"<a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**组织范围的设置""**  >  **资源帐户"。**</a></span><span class="sxs-lookup"><span data-stu-id="95f41-154">In the left navigation pane, go to <a href="https://admin.teams.microsoft.com/company-wide-settings/resource-accounts" target="_blank">**Org-wide settings** > **Resource accounts**</a>.</span></span>
1. <span data-ttu-id="95f41-155">选择刚刚创建的资源帐户，然后单击"**分配/取消分配"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-155">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="95f41-156">在 **"电话类型**"下拉列表中，选择"联机 **"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-156">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="95f41-157">在 **"分配的电话号码"** 框中，搜索想要使用的号码，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="95f41-157">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="95f41-158">请务必包括国家/地区代码 (例如 **，+1** 250 555 0012) </span><span class="sxs-lookup"><span data-stu-id="95f41-158">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="95f41-159">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="95f41-159">Click **Save**.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="95f41-160">下一步：向用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="95f41-160">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
