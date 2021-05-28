---
title: 配置运算符连接
author: cazawideh
ms.author: czawideh
manager: serdars
ms.date: 04/12/2021
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-voice
- m365initiative-voice
ms.reviewer: crowe
search.appverid: MET150
f1.keywords:
- NOCSH
- ms.teamsadmincenter.directrouting.overview
description: 详细了解如何配置运算符连接。
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: e82c862810448552bb9d2dc2d721815b5db43f55
ms.sourcegitcommit: 17e34d2de3d10f1d04929a695e301127db7014bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52689884"
---
# <a name="configure-operator-connect"></a><span data-ttu-id="c9171-103">配置运算符连接</span><span class="sxs-lookup"><span data-stu-id="c9171-103">Configure Operator Connect</span></span>

>[!NOTE]
><span data-ttu-id="c9171-104">运算符连接目前仅在公共 **预览版中可用**。</span><span class="sxs-lookup"><span data-stu-id="c9171-104">Operator Connect is currently available only in **public preview**.</span></span> <span data-ttu-id="c9171-105">公共预览版允许测试即将推出的功能并提供反馈。</span><span class="sxs-lookup"><span data-stu-id="c9171-105">Public preview allows you to test upcoming features and provide feedback.</span></span> <span data-ttu-id="c9171-106">公共预览版中包含的功能可能不完整、可能发生更改，并且不受云Office 365 政府版支持。</span><span class="sxs-lookup"><span data-stu-id="c9171-106">Features included in public preview may not be complete, may undergo changes, and are not supported in Office 365 Government Clouds.</span></span>

<span data-ttu-id="c9171-107">本文介绍如何配置运算符连接。</span><span class="sxs-lookup"><span data-stu-id="c9171-107">This article describes how to configure Operator Connect.</span></span> <span data-ttu-id="c9171-108">在配置操作员连接，请务必阅读操作员计划连接，了解先决条件[](operator-connect-plan.md)和许可的信息。</span><span class="sxs-lookup"><span data-stu-id="c9171-108">Before configuring Operator Connect, be sure to read [Plan for Operator Connect](operator-connect-plan.md) for information about prerequisites and licensing.</span></span>

## <a name="enable-an-operator"></a><span data-ttu-id="c9171-109">启用操作员</span><span class="sxs-lookup"><span data-stu-id="c9171-109">Enable an operator</span></span>

<span data-ttu-id="c9171-110">可以在管理中心启用、编辑和删除Teams运算符。</span><span class="sxs-lookup"><span data-stu-id="c9171-110">You can enable, edit, and remove operators in the Teams Admin Center.</span></span> <span data-ttu-id="c9171-111">在左侧导航窗格中，转到"语音">**运算符"。**</span><span class="sxs-lookup"><span data-stu-id="c9171-111">In the left navigation pane, go to **Voice > Operators**.</span></span>

<span data-ttu-id="c9171-112">启用操作员：</span><span class="sxs-lookup"><span data-stu-id="c9171-112">To enable an operator:</span></span>

1. <span data-ttu-id="c9171-113">**选择运算符。**</span><span class="sxs-lookup"><span data-stu-id="c9171-113">**Choose an operator.**</span></span> <span data-ttu-id="c9171-114">在" **所有运算符** "选项卡中，按区域或服务筛选可用的运算符，以查找满足语音需求的合适运算符。</span><span class="sxs-lookup"><span data-stu-id="c9171-114">In the **All operators** tab, filter available operators by region or service to find the right operator for your voice needs.</span></span> <span data-ttu-id="c9171-115">然后选择要启用的运算符。</span><span class="sxs-lookup"><span data-stu-id="c9171-115">Then select the operator you want to enable.</span></span>  

2. <span data-ttu-id="c9171-116">**选择国家/地区。**</span><span class="sxs-lookup"><span data-stu-id="c9171-116">**Select countries.**</span></span> <span data-ttu-id="c9171-117">在 **"操作员设置**"下，选择要通过所选操作员启用的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="c9171-117">Under **Operator settings**, select the countries you want to enable with your selected operator.</span></span>

3. <span data-ttu-id="c9171-118">**提供联系信息 (可选) 。**</span><span class="sxs-lookup"><span data-stu-id="c9171-118">**Provide contact information (optional).**</span></span> <span data-ttu-id="c9171-119">如果希望操作员联系您，并提供有关接线员连接，请选中该框并提供联系信息。</span><span class="sxs-lookup"><span data-stu-id="c9171-119">If you want operators to contact you with additional information about Operator Connect, check the box and provide your contact information.</span></span>  

4. <span data-ttu-id="c9171-120">**接受数据传输通知。**</span><span class="sxs-lookup"><span data-stu-id="c9171-120">**Accept the data transfer notice.**</span></span>

5. <span data-ttu-id="c9171-121">**添加运算符。**</span><span class="sxs-lookup"><span data-stu-id="c9171-121">**Add your operator.**</span></span> <span data-ttu-id="c9171-122">选择 **"添加为我的运算符"** 以保存。</span><span class="sxs-lookup"><span data-stu-id="c9171-122">Select **Add as my operator** to save.</span></span>

## <a name="set-up-phone-numbers"></a><span data-ttu-id="c9171-123">设置电话号码</span><span class="sxs-lookup"><span data-stu-id="c9171-123">Set up phone numbers</span></span>

<span data-ttu-id="c9171-124">设置电话号码的方式取决于你是为新用户设置号码，还是从 Microsoft 呼叫计划或直接路由移动现有号码。</span><span class="sxs-lookup"><span data-stu-id="c9171-124">How you set up phone numbers depends on whether you're setting up numbers for new users, or moving existing numbers from either Microsoft Calling Plans or Direct Routing.</span></span>

- <span data-ttu-id="c9171-125">如果需要获取新用户的电话号码，请参阅[获取新用户Teams号码](#acquire-numbers-for-new-teams-users)。</span><span class="sxs-lookup"><span data-stu-id="c9171-125">If you need to acquire phone numbers for new users, see [Acquire numbers for new Teams users](#acquire-numbers-for-new-teams-users).</span></span>

- <span data-ttu-id="c9171-126">如果要将现有号码从"呼叫计划"移动到"接线员连接，请参阅将号码从"呼叫套餐"移动到"接线[员连接"。](#move-numbers-from-calling-plans-to-operator-connect)</span><span class="sxs-lookup"><span data-stu-id="c9171-126">If you want to move existing numbers from Calling Plans to Operator Connect, see [Move numbers from Calling Plans to Operator Connect](#move-numbers-from-calling-plans-to-operator-connect).</span></span>

- <span data-ttu-id="c9171-127">如果要将现有号码从"直接路由"移动到"操作员连接，请参阅将数字从"直接路由"移动到["连接"。](#move-numbers-from-direct-routing-to-operator-connect)</span><span class="sxs-lookup"><span data-stu-id="c9171-127">If you want to move existing numbers from Direct Routing to Operator Connect, see [Move numbers from Direct Routing to Operator Connect](#move-numbers-from-direct-routing-to-operator-connect).</span></span>

>[!IMPORTANT]
><span data-ttu-id="c9171-128">**紧急地址：** 与从操作员获取的号码关联的紧急地址直接与操作员管理。</span><span class="sxs-lookup"><span data-stu-id="c9171-128">**Emergency addresses:** Emergency addresses associated with a number acquired from the operator are managed directly with the operator.</span></span> <span data-ttu-id="c9171-129">请联系接线员进行任何更改。</span><span class="sxs-lookup"><span data-stu-id="c9171-129">Please contact the operator to make any changes.</span></span>

### <a name="acquire-numbers-for-new-teams-users"></a><span data-ttu-id="c9171-130">获取新用户Teams号码</span><span class="sxs-lookup"><span data-stu-id="c9171-130">Acquire numbers for new Teams users</span></span>

<span data-ttu-id="c9171-131">若要获取新用户Teams号码，请执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="c9171-131">To acquire numbers for new Teams users, follow these steps:</span></span>

1. <span data-ttu-id="c9171-132">**分配电话系统许可证。**</span><span class="sxs-lookup"><span data-stu-id="c9171-132">**Assign a Phone System license.**</span></span> <span data-ttu-id="c9171-133">可以从管理中心电话系统 PowerShell 为用户Microsoft 365许可证。</span><span class="sxs-lookup"><span data-stu-id="c9171-133">You can assign a Phone System license to your users from the Microsoft 365 admin center or using PowerShell.</span></span> <span data-ttu-id="c9171-134">有关详细信息，请参阅[将Teams许可证分配给用户](teams-add-on-licensing/assign-teams-add-on-licenses.md)。</span><span class="sxs-lookup"><span data-stu-id="c9171-134">For more information, see [Assign Teams add-on licenses to users](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span>

2. <span data-ttu-id="c9171-135">**确保你已进入 TeamsOnly 模式。**</span><span class="sxs-lookup"><span data-stu-id="c9171-135">**Make sure you're in TeamsOnly mode.**</span></span> <span data-ttu-id="c9171-136">若要检查，请在Teams中心，转到"组织范围的设置"，> Teams **升级"。**</span><span class="sxs-lookup"><span data-stu-id="c9171-136">To check, in the Teams admin center, go to **Org-wide settings > Teams upgrade**.</span></span> <span data-ttu-id="c9171-137">共存模式应设置为仅Teams模式。</span><span class="sxs-lookup"><span data-stu-id="c9171-137">The coexistence mode should be set to Teams only.</span></span>

3. <span data-ttu-id="c9171-138">**创建和验证紧急地址。**</span><span class="sxs-lookup"><span data-stu-id="c9171-138">**Create and validate emergency addresses.**</span></span> <span data-ttu-id="c9171-139">在Teams管理中心，转到"位置 **">"紧急地址**"以设置紧急地址。</span><span class="sxs-lookup"><span data-stu-id="c9171-139">In the Teams admin center, go to **Locations > Emergency addresses** to set up emergency addresses.</span></span> <span data-ttu-id="c9171-140">有关详细信息，请参阅为组织添加、更改或删除 [紧急位置](add-change-remove-emergency-location-organization.md)。</span><span class="sxs-lookup"><span data-stu-id="c9171-140">To learn more, see [Add, change, or remove an emergency location for your organization](add-change-remove-emergency-location-organization.md).</span></span>

4. <span data-ttu-id="c9171-141">**获取数字。**</span><span class="sxs-lookup"><span data-stu-id="c9171-141">**Acquire numbers.**</span></span> <span data-ttu-id="c9171-142">转到接线员的网站以订购和获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="c9171-142">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="c9171-143">有关运算符网站的列表，请参阅 [运算符](#operators)。</span><span class="sxs-lookup"><span data-stu-id="c9171-143">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="c9171-144">需要提供租户 ID。</span><span class="sxs-lookup"><span data-stu-id="c9171-144">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="c9171-145">如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9171-145">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

5. <span data-ttu-id="c9171-146">**分配数字。**</span><span class="sxs-lookup"><span data-stu-id="c9171-146">**Assign numbers.**</span></span> <span data-ttu-id="c9171-147">操作员完成订单后，将测试编号上传到租户。</span><span class="sxs-lookup"><span data-stu-id="c9171-147">Once your operator completes the order, they'll upload test numbers to your tenant.</span></span> <span data-ttu-id="c9171-148">可以通过在"语音"Teams管理中心查看号码和> 电话 **提供商**。</span><span class="sxs-lookup"><span data-stu-id="c9171-148">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="c9171-149">使用管理中心或 PowerShell Teams向用户分配号码。</span><span class="sxs-lookup"><span data-stu-id="c9171-149">Assign numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="c9171-150">有关详细信息，请参阅 [分配数字](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="c9171-150">For more information, see [Assign numbers](#assign-numbers).</span></span>
 

### <a name="move-numbers-from-calling-plans-to-operator-connect"></a><span data-ttu-id="c9171-151">将号码从通话套餐移动到接线员连接</span><span class="sxs-lookup"><span data-stu-id="c9171-151">Move numbers from Calling Plans to Operator Connect</span></span>

1. <span data-ttu-id="c9171-152">联系接线员将号码移植到接线员连接。</span><span class="sxs-lookup"><span data-stu-id="c9171-152">Contact your operator to port your numbers to Operator Connect.</span></span> <span data-ttu-id="c9171-153">请参阅 [运算符](#operators) 以查找操作员的网站。</span><span class="sxs-lookup"><span data-stu-id="c9171-153">See [Operators](#operators) to find your operator's website.</span></span>

2. <span data-ttu-id="c9171-154">运营商完成移植订单后，可以取消分配用户的"呼叫计划"电话号码，并删除"呼叫计划许可证"。</span><span class="sxs-lookup"><span data-stu-id="c9171-154">After your operator completes the porting order, you can unassign your users' Calling Plan phone numbers, and remove the Calling Plan License.</span></span> <span data-ttu-id="c9171-155">然后，操作员可以将数字上传到租户。</span><span class="sxs-lookup"><span data-stu-id="c9171-155">Then, your operator can upload the numbers to your tenant.</span></span>

3. <span data-ttu-id="c9171-156">使用 连接管理中心或 PowerShell 为Teams分配操作员编号。</span><span class="sxs-lookup"><span data-stu-id="c9171-156">Assign Operator Connect numbers to users by using the Teams admin center or by using PowerShell.</span></span> <span data-ttu-id="c9171-157">有关详细信息，请参阅 [分配数字](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="c9171-157">For more information, see [Assign numbers](#assign-numbers).</span></span>

 
### <a name="move-numbers-from-direct-routing-to-operator-connect"></a><span data-ttu-id="c9171-158">将数字从"直接路由"移动到"操作员连接</span><span class="sxs-lookup"><span data-stu-id="c9171-158">Move numbers from Direct Routing to Operator Connect</span></span>

1. <span data-ttu-id="c9171-159">删除用户的现有电话号码，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c9171-159">Remove the existing telephone number from the user as follows:</span></span>  

   <span data-ttu-id="c9171-160">通过运行以下 PowerShell 命令获取现有的 On-prem 行 URI：</span><span class="sxs-lookup"><span data-stu-id="c9171-160">Get the existing On-prem Line URI by running the following PowerShell command:</span></span>

   ```
   Get-CsOnlineUser -Identity <user> | select OnPremLineURI 
   ```

   <span data-ttu-id="c9171-161">通过运行以下 PowerShell 命令删除 On-prem Line URI：</span><span class="sxs-lookup"><span data-stu-id="c9171-161">Remove the On-prem Line URI by running the following PowerShell command:</span></span>  

   ```
   Set-CsUser -identity <user> - OnPremLineURI $null 
   ```

2. <span data-ttu-id="c9171-162">删除与用户关联的任何 PSTNUsage，否则呼叫将路由到 PSTN 使用中指定的网关。</span><span class="sxs-lookup"><span data-stu-id="c9171-162">Remove any PSTNUsage associated with your users, otherwise calls will be routed to the gateway specified in the PSTN Usage.</span></span> <span data-ttu-id="c9171-163">若要了解如何删除 PSTN 使用情况，请参阅[Set-CsOnlinePstnUsage。](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps)</span><span class="sxs-lookup"><span data-stu-id="c9171-163">To learn how to remove PSTN usage, see [Set-CsOnlinePstnUsage](/powershell/module/skype/set-csonlinepstnusage?view=skype-ps).</span></span>

3. <span data-ttu-id="c9171-164">转到接线员的网站以订购和获取电话号码。</span><span class="sxs-lookup"><span data-stu-id="c9171-164">Go to your operator's website to order and acquire phone numbers.</span></span> <span data-ttu-id="c9171-165">有关运算符网站的列表，请参阅 [运算符](#operators)。</span><span class="sxs-lookup"><span data-stu-id="c9171-165">For a list of operator websites, see [Operators](#operators).</span></span> <span data-ttu-id="c9171-166">需要提供租户 ID。</span><span class="sxs-lookup"><span data-stu-id="c9171-166">You'll need to provide your tenant ID.</span></span> <span data-ttu-id="c9171-167">如果不知道租户 ID，请参阅查找租户Microsoft 365 [ID](/onedrive/find-your-office-365-tenant-id)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="c9171-167">If you don't know your tenant ID, see [Find your Microsoft 365 tenant ID](/onedrive/find-your-office-365-tenant-id) for more information.</span></span>

4. <span data-ttu-id="c9171-168">操作员完成订单后，将测试编号上传到租户。</span><span class="sxs-lookup"><span data-stu-id="c9171-168">Once your operator completes the order, they'll upload test numbers to your tenant.</span></span> <span data-ttu-id="c9171-169">可以通过在"语音"Teams管理中心查看号码和> 电话 **提供商**。</span><span class="sxs-lookup"><span data-stu-id="c9171-169">You can view the numbers and the provider in the Teams admin center by going to **Voice > Phone numbers**.</span></span> <span data-ttu-id="c9171-170">使用 连接管理中心或 PowerShell 为Teams分配操作员编号。</span><span class="sxs-lookup"><span data-stu-id="c9171-170">Assign Operator Connect numbers to users by using the Teams admin center or by using  PowerShell.</span></span> <span data-ttu-id="c9171-171">有关详细信息，请参阅 [分配数字](#assign-numbers)。</span><span class="sxs-lookup"><span data-stu-id="c9171-171">For more information, see [Assign numbers](#assign-numbers).</span></span>

   

### <a name="assign-numbers"></a><span data-ttu-id="c9171-172">分配数字</span><span class="sxs-lookup"><span data-stu-id="c9171-172">Assign numbers</span></span>

<span data-ttu-id="c9171-173">无论是添加新用户Teams还是将现有用户移动到接线员连接，分配号码的步骤如下：</span><span class="sxs-lookup"><span data-stu-id="c9171-173">Whether you're adding new Teams users or moving existing users to Operator Connect, the steps for assigning numbers are as follows:</span></span>

<span data-ttu-id="c9171-174">若要使用管理中心Teams号码，请转到电话 **号码**。</span><span class="sxs-lookup"><span data-stu-id="c9171-174">To assign numbers by using the Teams admin center, go to **Phone numbers**.</span></span> <span data-ttu-id="c9171-175">步骤与为呼叫计划分配号码相同。</span><span class="sxs-lookup"><span data-stu-id="c9171-175">The steps are the same as assigning numbers for Calling Plans.</span></span> <span data-ttu-id="c9171-176">有关详细信息，请参阅 [向用户分配电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c9171-176">For more information, see [Assign a phone number to a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>

<span data-ttu-id="c9171-177">若要使用 PowerShell 分配数字，请使用 Set-CsOnlineVoiceUser cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="c9171-177">To assign numbers by using PowerShell, use the Set-CsOnlineVoiceUser cmdlet as follows:</span></span>

```
Set-CsOnlineVoiceUser -Identity <user>  -TelephoneNumber <phone number> 
```

<span data-ttu-id="c9171-178">例如：</span><span class="sxs-lookup"><span data-stu-id="c9171-178">For example:</span></span>

```
Set-CsOnlineVoiceUser -Identity john@contoso.com -TelephoneNumber +14255550101
```

<span data-ttu-id="c9171-179">若要详细了解如何向用户分配电话号码，请参阅为用户分配、更改 [或删除电话号码](assign-change-or-remove-a-phone-number-for-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c9171-179">For more information about how to assign phone numbers to your users, see [Assign, change, or remove a phone number for a user](assign-change-or-remove-a-phone-number-for-a-user.md).</span></span>



## <a name="manage-your-operators"></a><span data-ttu-id="c9171-180">管理操作员</span><span class="sxs-lookup"><span data-stu-id="c9171-180">Manage your operators</span></span>

<span data-ttu-id="c9171-181">在"我的运算符"选项卡中，可以查看运算符及其状态，并更改所选内容：</span><span class="sxs-lookup"><span data-stu-id="c9171-181">From the My operators tab, you can view your operators and their status and make the following changes to your selections:</span></span>  

- <span data-ttu-id="c9171-182">按国家/地区管理运营商服务</span><span class="sxs-lookup"><span data-stu-id="c9171-182">Manage operator services by country</span></span>
- <span data-ttu-id="c9171-183">暂停操作员</span><span class="sxs-lookup"><span data-stu-id="c9171-183">Suspend an operator</span></span>
- <span data-ttu-id="c9171-184">删除运算符</span><span class="sxs-lookup"><span data-stu-id="c9171-184">Remove an operator</span></span>

> [!NOTE]
> <span data-ttu-id="c9171-185">在从组织或国家/地区中删除接线员之前，必须删除分配给组织或国家/地区用户的所有电话号码，并联系接线员释放号码。</span><span class="sxs-lookup"><span data-stu-id="c9171-185">Before removing an operator from your organization or from a country, you must remove all phone numbers assigned to users in the organization or country and contact the operator to release the numbers.</span></span>

## <a name="operators"></a><span data-ttu-id="c9171-186">运算符</span><span class="sxs-lookup"><span data-stu-id="c9171-186">Operators</span></span>

<span data-ttu-id="c9171-187">您可以通过访问此处链接的网站，从以下运营商获取电话号码：</span><span class="sxs-lookup"><span data-stu-id="c9171-187">You can acquire phone numbers from the following operators by going to the websites linked here:</span></span>


|<span data-ttu-id="c9171-188">接线员</span><span class="sxs-lookup"><span data-stu-id="c9171-188">Operator</span></span>  |<span data-ttu-id="c9171-189">运营商网站</span><span class="sxs-lookup"><span data-stu-id="c9171-189">Operator website</span></span>  |
|---------|---------|
|`BT`     |     https://www.globalservices.bt.com/en/aboutus/operator-connect        |
|`Deutsche Telekom`     |   https://cloud.telekom.de/de/blog/cloud-software/microsoft-teams-operator-connect      |
|`Intrado`     | https://insight.intrado.com/operator-connect       |
|`NTT`     |  https://www.hello.global.ntt/operator-connect       |
|`NuWave`     |   https://ipilot.io/microsoft-operator-connect/   |
|`Orange Business Services`     | https://www.orange-business.com/en/blogs/operator-connect-orange-and-microsoft-streamline-calling-for-teams-users        |
|`Pure IP`    | https://info.pure-ip.com/operator-connect        |
|`Rogers`    | https://www.rogers.com/business/products-and-solutions/microsoft-365-business-voice        |
|`TATA Communications`     |  https://www.tatacommunications.com/solutions/unified-communications/unified-communications-as-a-service/microsoft-teams-solutions/       |
|`Telenor`     | https://www.telenor.no/bedrift/telefoni/teams/operator-connect        |
|`Verizon`     |  https://www.verizon.com/business/resources/lp/operator-connect       |
