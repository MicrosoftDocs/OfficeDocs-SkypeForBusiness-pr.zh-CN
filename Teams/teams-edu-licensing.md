---
title: 面向教育版管理员的 Microsoft Teams 资源
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.topic: reference
ms.service: msteams
audience: admin
ms.reviewer: karsmith
description: Microsoft Teams 教育版许可演练。
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- Teams_ITAdmin_RemoteWorkers
appliesto:
- Microsoft Teams
ms.openlocfilehash: 83448f32ddfc96800a14b5a599ef9cb7af52bb9b
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51119231"
---
# <a name="assign-microsoft-teams-licenses-for-edu"></a><span data-ttu-id="9545f-103">为教育版分配 Microsoft Teams 许可证</span><span class="sxs-lookup"><span data-stu-id="9545f-103">Assign Microsoft Teams licenses for EDU</span></span>

<span data-ttu-id="9545f-104">Microsoft Teams 是一个数字中心，其中汇聚了对话、内容及应用。</span><span class="sxs-lookup"><span data-stu-id="9545f-104">Microsoft Teams is a digital hub that brings conversations, content, and apps together in one place.</span></span> <span data-ttu-id="9545f-105">由于它是基于 Office 365 构建的，因此学校可以从与他们熟悉的 Office 应用和服务的集成中受益。</span><span class="sxs-lookup"><span data-stu-id="9545f-105">Because it's built on Office 365, schools benefit from integration with their familiar Office apps and services.</span></span> <span data-ttu-id="9545f-106">你的机构可以使用 Microsoft Teams 创建协作式教室、连接专业学校社区并与学校教职员工进行沟通 - 一切皆可通过 Office 365 教育版中的单一体验来实现。</span><span class="sxs-lookup"><span data-stu-id="9545f-106">Your institution can use Microsoft Teams to create collaborative classrooms, connect in professional learning communities, and communicate with school staff all from a single experience in Office 365 for Education.</span></span>

<span data-ttu-id="9545f-107">首先，IT 管理员需要使用 Microsoft 365 管理中心[为你的学校启用 Microsoft Teams](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams)。</span><span class="sxs-lookup"><span data-stu-id="9545f-107">To get started, IT administrators need to use the Microsoft 365 Admin Center to [enable Microsoft Teams for your school](/microsoft-365/education/intune-edu-trial/enable-microsoft-teams).</span></span>
<span data-ttu-id="9545f-108">完成后，你必须为用户帐户分配许可证，以便你的教职员工和学生可以访问 Office 365 服务，例如 Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="9545f-108">Once complete, you must assign licenses to user accounts so your faculty, staff, and students can access Office 365 services, such as Microsoft Teams.</span></span>

<span data-ttu-id="9545f-109">可通过组成员身份单独或自动向用户帐户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9545f-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span> <span data-ttu-id="9545f-110">本文将向你介绍如何通过 Microsoft 365 管理中心将 Office 365 许可证分配给单个或一小组用户帐户。</span><span class="sxs-lookup"><span data-stu-id="9545f-110">This article will walk you through how to assign Office 365 licenses to an individual or a small set of user accounts via the Microsoft 365 admin center.</span></span> <span data-ttu-id="9545f-111">要通过组成员身份自动分配许可证，请参阅我们的以下支持文章之一：</span><span class="sxs-lookup"><span data-stu-id="9545f-111">To assign licenses automatically through group membership, see one of our supporting articles:</span></span>

- [<span data-ttu-id="9545f-112">Office 365 Powershell</span><span class="sxs-lookup"><span data-stu-id="9545f-112">Office 365 Powershell</span></span>](/office365/enterprise/powershell/assign-licenses-to-user-accounts-with-office-365-powershell)
- [<span data-ttu-id="9545f-113">Active Directory 中基于组的许可</span><span class="sxs-lookup"><span data-stu-id="9545f-113">Group-based Licensing in Active Directory</span></span>](/azure/active-directory/users-groups-roles/licensing-groups-assign)

<span data-ttu-id="9545f-114">可在“**许可证**”页面或“**活动用户**”页面上向用户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="9545f-114">You can assign licenses to users on either the **Licenses** page, or on the **Active Users** page.</span></span> <span data-ttu-id="9545f-115">使用哪种方法取决于是要向特定用户分配产品许可证还是向特定产品分配用户许可证。</span><span class="sxs-lookup"><span data-stu-id="9545f-115">Which method you use depends on whether you want to assign product licenses to specific users, or assign users licenses to specific products.</span></span>

> [!NOTE]
> <span data-ttu-id="9545f-116">如果未使用新的 Microsoft 365 管理中心，可通过选择“**试用新的管理中心**”切换按钮（位于主页顶部）将其打开。</span><span class="sxs-lookup"><span data-stu-id="9545f-116">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

## <a name="assign-licenses-to-users-on-the-licenses-page"></a><span data-ttu-id="9545f-117">在“许可证”页面上向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9545f-117">Assign licenses to users on the Licenses page</span></span>

> [!NOTE]
> <span data-ttu-id="9545f-118">你必须是全局管理员、账单管理员、许可证管理员或用户管理管理员。有关详细信息，请参阅[关于 Office 365 管理员角色](/microsoft-365/admin/add-users/about-admin-roles)。</span><span class="sxs-lookup"><span data-stu-id="9545f-118">You must be a Global admin, Billing admin, License admin, or User management admin. For more information, see [About Office 365 admin roles](/microsoft-365/admin/add-users/about-admin-roles).</span></span>

<span data-ttu-id="9545f-119">使用“**许可证**”页面分配许可证时，最多可向 20 名用户分配特定产品的许可证。</span><span class="sxs-lookup"><span data-stu-id="9545f-119">When you use the **Licenses** page to assign licenses, you assign licenses for a specific product for up to 20 users.</span></span> <span data-ttu-id="9545f-120">在“**许可证**”页面上，你会看到你已订阅的所有产品的列表，还有每个产品的许可证总数、已分配的许可证数以及可用的许可证数。</span><span class="sxs-lookup"><span data-stu-id="9545f-120">On the **Licenses** page, you see a list of all the products you have subscriptions for, together with the total number of licenses for each product, how many licenses are assigned, and how many are available.</span></span>

1. <span data-ttu-id="9545f-121">在管理中心，转到“**账单**” > “[许可证](https://go.microsoft.com/fwlink/p/?linkid=842264)”页面。</span><span class="sxs-lookup"><span data-stu-id="9545f-121">In the admin center, go to the **Billing** > [Licenses](https://go.microsoft.com/fwlink/p/?linkid=842264) page.</span></span>

   ![账单窗口和菜单选项的屏幕截图。](media/EDU-Lic-Billing-License.png)
2. <span data-ttu-id="9545f-123">选择要为其分配许可证的产品。</span><span class="sxs-lookup"><span data-stu-id="9545f-123">Select a product for which you want to assign licenses.</span></span> <span data-ttu-id="9545f-124">Microsoft Teams 是免费的 Office 365 A1 学生版 SKU 的一部分。</span><span class="sxs-lookup"><span data-stu-id="9545f-124">Microsoft Teams is part of the free Office 365 A1 for Students SKU.</span></span>

   ![“许可证”页面屏幕截图，其中包含可用于为其分配许可证的产品。](media/EDU-Lic-Licenses-Products.png)
3. <span data-ttu-id="9545f-126">选择“**分配许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9545f-126">Select **Assign licenses**.</span></span>

   ![页面的“用户”部分以及前面带有加号的“分配许可证”选项的屏幕截图。](media/EDU-Lic-Assign-Licenses.png)
4. <span data-ttu-id="9545f-128">在“**向用户分配许可证**”窗格中，开始键入名称，该名称应生成一个名称列表。</span><span class="sxs-lookup"><span data-stu-id="9545f-128">In the **Assign licenses to users** pane, begin typing a name, which should generate a list of names.</span></span> <span data-ttu-id="9545f-129">从结果中选择要查找的名称，以将其添加到列表中。</span><span class="sxs-lookup"><span data-stu-id="9545f-129">Choose the name you're looking for from the results to add it to the list.</span></span> <span data-ttu-id="9545f-130">一次最多可添加 20 名用户。</span><span class="sxs-lookup"><span data-stu-id="9545f-130">You can add up to 20 users at a time.</span></span>

   ![“向用户分配许可证”页面的屏幕截图，其中键入了部分名称，显示了该部分名称的搜索结果。](media/EDU-Lic-Assign-Licenses-Users.png)
5. <span data-ttu-id="9545f-132">选择“**打开或关闭应用和服务**”，向特定项目（例如 Microsoft Teams）分配访问权限或删除其访问权限。</span><span class="sxs-lookup"><span data-stu-id="9545f-132">Select **Turn apps and services on or off** to assign or remove access to specific items, such as Microsoft Teams.</span></span> <span data-ttu-id="9545f-133">请确保已选中 **Microsoft Teams** 和 **Office 网页版（教育版）**。</span><span class="sxs-lookup"><span data-stu-id="9545f-133">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>
6. <span data-ttu-id="9545f-134">完成后，选择“**分配**”，然后选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9545f-134">When you're finished, select **Assign**, then select **Close**.</span></span>

<span data-ttu-id="9545f-135">要更改应用和服务，用户需有权限：</span><span class="sxs-lookup"><span data-stu-id="9545f-135">To change the apps and services a user has access to:</span></span>

1. <span data-ttu-id="9545f-136">选择包含该用户的行。</span><span class="sxs-lookup"><span data-stu-id="9545f-136">Select the row that contains the user.</span></span>
1. <span data-ttu-id="9545f-137">在右侧窗格中，选择或取消选择要授予或取消访问权限的应用和服务。</span><span class="sxs-lookup"><span data-stu-id="9545f-137">In the right pane, select or deselect the apps and services that you want to give access to, or remove access from.</span></span>
1. <span data-ttu-id="9545f-138">完成后，选择“**保存**”，然后选择“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="9545f-138">When you're finished, select **Save**, then select **Close**.</span></span>

## <a name="assign-licenses-to-an-individual-or-multiple-users-on-the-active-users-page"></a><span data-ttu-id="9545f-139">在“活动用户”页面上向单个或多个用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="9545f-139">Assign licenses to an individual or multiple users on the Active users page</span></span>

1. <span data-ttu-id="9545f-140">在管理中心，转到“**用户**” > “[活动用户](https://go.microsoft.com/fwlink/p/?linkid=834822)”页面。</span><span class="sxs-lookup"><span data-stu-id="9545f-140">In the admin center, go to the **Users** > [Active users](https://go.microsoft.com/fwlink/p/?linkid=834822) page.</span></span>

   ![Microsoft O365 管理中心中“活动用户”菜单选项的屏幕截图。](media/EDU-Lic-Active-Users.png)
2. <span data-ttu-id="9545f-142">选中要向其分配许可证的用户姓名旁边的圆圈。</span><span class="sxs-lookup"><span data-stu-id="9545f-142">Select the circles next to the name(s) of the user(s) you want to assign license(s) to.</span></span>

   ![“活动用户”页面以及该页面上活动用户列表（其中一些用户被选中，因为其姓名旁边的圆圈被填充）的屏幕截图。](media/EDU-Lic-Active-Users-List.png)
3. <span data-ttu-id="9545f-144">在顶部，选择“**管理产品许可证**”。</span><span class="sxs-lookup"><span data-stu-id="9545f-144">At the top select **Manage product licenses**.</span></span>

   ![“管理产品许可证”选项卡以及一个以未经许可列出的用户的屏幕截图。](media/EDU-Lic-Manage-Product-Licenses.png)
4. <span data-ttu-id="9545f-146">在“**管理产品许可证**”窗格中，选择“**添加到现有产品许可证分配**” > “**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="9545f-146">In the **Manage product licenses** pane, select **Add to existing product license assignments** > **Next**.</span></span>

   ![“管理产品许可证”窗口的屏幕截图，其中选中了“添加到现有产品许可证分配”单选按钮。](media/EDU-Lic-Add-Existing-Product.png)
5. <span data-ttu-id="9545f-148">在“**添加到现有产品**”窗格中，将希望所选用户具备的许可证的开关切换到“**开**”位置。</span><span class="sxs-lookup"><span data-stu-id="9545f-148">In the **Add to existing products** pane, switch the toggle to the **On** position for the license that you want the selected users to have.</span></span> <span data-ttu-id="9545f-149">请确保已选中 **Microsoft Teams** 和 **Office 网页版（教育版）**。</span><span class="sxs-lookup"><span data-stu-id="9545f-149">Ensure **Microsoft Teams** and **Office for the web (Education)** are selected.</span></span>

   ![在“添加到现有产品”选项卡上选中 Microsoft Teams 和 Office 网页版（教育版）的屏幕截图。](media/EDU-Lic-Add-Existing-Products.png)

   <span data-ttu-id="9545f-151">默认情况下，与这些许可证关联的所有服务都将自动分配给该用户。</span><span class="sxs-lookup"><span data-stu-id="9545f-151">By default, all services associated with those license(s) are automatically assigned to the user(s).</span></span> <span data-ttu-id="9545f-152">可限制能提供给用户的具体服务。</span><span class="sxs-lookup"><span data-stu-id="9545f-152">You can limit which services are available to the users.</span></span> <span data-ttu-id="9545f-153">将不希望所选用户具备的服务的开关切换到“**关**”。</span><span class="sxs-lookup"><span data-stu-id="9545f-153">Switch the toggles to the **Off** position for the services that you don't want the users to have.</span></span>
6. <span data-ttu-id="9545f-154">在窗格底部，选择“添加”>“关闭”。</span><span class="sxs-lookup"><span data-stu-id="9545f-154">At the bottom of the pane, select Add > Close.</span></span>