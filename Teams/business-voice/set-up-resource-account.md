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
ms.openlocfilehash: 76e91a650e9e72c21a39d292e32fe5ff8ecbf80b
ms.sourcegitcommit: 49cdcf344c63c805bcb6365804c6f5d1393e926a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2021
ms.locfileid: "52130326"
---
# <a name="step-4-set-up-a-business-voice-resource-account"></a><span data-ttu-id="59993-103">步骤 4：设置 Business Voice 资源帐户</span><span class="sxs-lookup"><span data-stu-id="59993-103">Step 4: Set up a Business Voice resource account</span></span>

<span data-ttu-id="59993-104">在Microsoft Teams，每个自动助理或呼叫队列都需要一个资源帐户。</span><span class="sxs-lookup"><span data-stu-id="59993-104">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="59993-105">还可以为资源帐户分配服务电话号码。</span><span class="sxs-lookup"><span data-stu-id="59993-105">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="59993-106">这是将电话号码分配给自动助理和呼叫队列，允许来自外部呼叫Teams呼叫者进入自动助理或呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="59993-106">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

## <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="59993-107">获取虚拟用户许可证</span><span class="sxs-lookup"><span data-stu-id="59993-107">Obtain virtual user licenses</span></span>

<span data-ttu-id="59993-108">资源帐户需要许可证才能使用自动助理和呼叫队列。</span><span class="sxs-lookup"><span data-stu-id="59993-108">Resource accounts require a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="59993-109">可以使用免费的虚拟Microsoft 365 电话系统 *- 虚拟用户* 许可证。</span><span class="sxs-lookup"><span data-stu-id="59993-109">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span>

1. <span data-ttu-id="59993-110">登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="59993-110">Sign in to the Microsoft 365 admin center.</span></span>
2. <span data-ttu-id="59993-111">转到 **计费**  >  **购买服务**  >  **附加内容**  >  **查看所有附加内容产品**</span><span class="sxs-lookup"><span data-stu-id="59993-111">Go to **Billing** > **Purchase services** > **Add-ons** > **See all Add-ons products**</span></span>
3. <span data-ttu-id="59993-112">滚动到末尾，找到 **"Microsoft 365 电话系统 – 虚拟用户"** 许可证。</span><span class="sxs-lookup"><span data-stu-id="59993-112">Scroll to the end to find the **Microsoft 365 Phone System – Virtual User** license.</span></span> <span data-ttu-id="59993-113">选择"**详细信息"，** 然后选择"**购买"。**</span><span class="sxs-lookup"><span data-stu-id="59993-113">Select **Details**, then **Buy**.</span></span>
4. <span data-ttu-id="59993-114">在许可证购买页上，选择想要的虚拟用户许可证数。</span><span class="sxs-lookup"><span data-stu-id="59993-114">On the license purchase page, select the number of virtual user licenses you want.</span></span> <span data-ttu-id="59993-115">需要为计划设置的每个自动助理和呼叫队列提供一个虚拟许可证。</span><span class="sxs-lookup"><span data-stu-id="59993-115">You need one virtual license for each auto attendant and call queue you plan to set up.</span></span> <span data-ttu-id="59993-116">我们建议选择至少五个许可证，以便将来可以轻松设置更多自动助理和呼叫队列，而无需立即购买更多许可证。</span><span class="sxs-lookup"><span data-stu-id="59993-116">We recommend selecting at least five licenses so you can easily set up more auto attendants and call queues in the future without having to purchase more licenses right away.</span></span>
5. <span data-ttu-id="59993-117">取消 **选中"自动分配给没有许可证的所有用户"。**</span><span class="sxs-lookup"><span data-stu-id="59993-117">Uncheck **Automatically assign to all of your users with no licenses**.</span></span>
6. <span data-ttu-id="59993-118">选择 **"现在签出"。**</span><span class="sxs-lookup"><span data-stu-id="59993-118">Select **Check out now**.</span></span>
7. <span data-ttu-id="59993-119">确认订单，选择"下一 **步**"，然后选择"**下订单"。**</span><span class="sxs-lookup"><span data-stu-id="59993-119">Confirm your order, select **Next**, and then **Place order**.</span></span>

> [!NOTE]
> <span data-ttu-id="59993-120">请记住，即使许可证的成本  **为零** ，仍必须购买许可证。</span><span class="sxs-lookup"><span data-stu-id="59993-120">Keep in mind you must still  **Buy** the license even though it has a cost of zero.</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="59993-121">创建资源帐户</span><span class="sxs-lookup"><span data-stu-id="59993-121">Create a resource account</span></span>

<span data-ttu-id="59993-122">收到"虚拟 *用户Microsoft 365 电话系统后*，可以创建资源帐户。</span><span class="sxs-lookup"><span data-stu-id="59993-122">After you've received your *Microsoft 365 Phone System - Virtual User* license, you can create your resource account.</span></span>

![添加资源帐户用户界面的屏幕截图](../media/resource-account-add.png)

1. <span data-ttu-id="59993-124">在Teams管理中心，展开 **"组织范围的设置**"，然后单击"**资源帐户"。**</span><span class="sxs-lookup"><span data-stu-id="59993-124">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>
2. <span data-ttu-id="59993-125">选择“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="59993-125">Select **Add**.</span></span>
3. <span data-ttu-id="59993-126">在"**添加资源帐户"** 窗格中，填写 **"显示名称"，** 然后填写"**用户名"。**</span><span class="sxs-lookup"><span data-stu-id="59993-126">In the **Add resource account** pane, fill out **Display name**, and then **Username**.</span></span> <span data-ttu-id="59993-127">选择描述性显示名称例如"主行自动助理"来描述资源帐户的用途。</span><span class="sxs-lookup"><span data-stu-id="59993-127">Choose a descriptive display name such as "Main line auto attendant" to describe the purpose of the resource account.</span></span>
4. <span data-ttu-id="59993-128">在 **"资源帐户类型"中**，选择 **"自动助理"。**</span><span class="sxs-lookup"><span data-stu-id="59993-128">In **Resource account type**, select **Auto attendant**.</span></span>
5. <span data-ttu-id="59993-129">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="59993-129">Select **Save**.</span></span>

![资源帐户列表的屏幕截图](../media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="59993-131">分配许可证</span><span class="sxs-lookup"><span data-stu-id="59993-131">Assign a license</span></span>

<span data-ttu-id="59993-132">创建资源帐户后，需要分配一个 Microsoft 365 电话系统 *-* 虚拟用户 *许可证或电话系统* 许可证。</span><span class="sxs-lookup"><span data-stu-id="59993-132">After you've created your resource account, you need to assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![在管理中心内分配许可证Microsoft 365屏幕截图](../media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="59993-134">在Microsoft 365中心，转到"用户  >  **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="59993-134">In the Microsoft 365 admin center, go to **Users** > **Active users**.</span></span>
2. <span data-ttu-id="59993-135">选择资源帐户。</span><span class="sxs-lookup"><span data-stu-id="59993-135">Select your resource account.</span></span>
1. <span data-ttu-id="59993-136">在"**许可证和应用"选项卡上的**"许可证 **"下**，选择 **"Microsoft 365 电话系统 - 虚拟用户"。**</span><span class="sxs-lookup"><span data-stu-id="59993-136">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>
1. <span data-ttu-id="59993-137">选择 **"保存更改"，** 然后选择"**关闭"。**</span><span class="sxs-lookup"><span data-stu-id="59993-137">Select **Save changes** and then **Close**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="59993-138">分配服务编号</span><span class="sxs-lookup"><span data-stu-id="59993-138">Assign a service number</span></span>

![分配服务编号用户界面的屏幕截图](../media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="59993-140">在Teams管理中心，转到 **"组织范围的** 设置"，然后转到"**资源帐户"。**</span><span class="sxs-lookup"><span data-stu-id="59993-140">In the Teams admin center, go to **Org-wide settings** and then **Resource accounts**.</span></span> 
1. <span data-ttu-id="59993-141">选择刚刚创建的资源帐户，然后单击"**分配/取消分配"。**</span><span class="sxs-lookup"><span data-stu-id="59993-141">Select the resource account you just created, and then click **Assign/unassign**.</span></span>
1. <span data-ttu-id="59993-142">在 **"电话类型**"下拉列表中，选择"联机 **"。**</span><span class="sxs-lookup"><span data-stu-id="59993-142">In the **Phone number type** dropdown, choose **Online**.</span></span>
1. <span data-ttu-id="59993-143">在 **"分配的电话号码"** 框中，搜索想要使用的号码，然后单击"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="59993-143">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span> <span data-ttu-id="59993-144">请务必包括国家/地区代码 (例如 **，+1** 250 555 0012) </span><span class="sxs-lookup"><span data-stu-id="59993-144">Be sure to include the country code (for example, **+1** 250 555 0012)</span></span>
1. <span data-ttu-id="59993-145">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="59993-145">Click **Save**.</span></span>
    > [!NOTE]
    > <span data-ttu-id="59993-146">无需在"分配对象"下选择自动助理，因为已选中要添加号码的自动助理。</span><span class="sxs-lookup"><span data-stu-id="59993-146">You don't need to select an auto attendant under **Assign to** because the auto attendant you want to add the number to is already selected.</span></span>

> [!div class="nextstepaction"]
> [<span data-ttu-id="59993-147">下一步：向用户分配电话号码</span><span class="sxs-lookup"><span data-stu-id="59993-147">Next step: Assign phone numbers to your users</span></span>](set-up-assign-numbers.md)
