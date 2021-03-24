---
title: 在 Skype for Business 中创建或修改组内呼叫接听号码范围
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: Create or modify a Group Call Pickup number range in Skype for Business Server 企业语音.
ms.openlocfilehash: e71915519014b1fa4cfffa3172327e9949ed73a2
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51100418"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="864d9-103">在 Skype for Business 中创建或修改组内呼叫接听号码范围</span><span class="sxs-lookup"><span data-stu-id="864d9-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="864d9-104">Create or modify a Group Call Pickup number range in Skype for Business Server 企业语音.</span><span class="sxs-lookup"><span data-stu-id="864d9-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="864d9-105">组内呼叫接听基于呼叫管理应用程序。</span><span class="sxs-lookup"><span data-stu-id="864d9-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="864d9-106">部署组内呼叫分拣时，必须使用指定为呼叫接听组号码的电话号码范围来配置呼叫安排通道表。</span><span class="sxs-lookup"><span data-stu-id="864d9-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="864d9-107">这些组号码是用户为接听为其他用户响铃的呼叫而拨打的号码。</span><span class="sxs-lookup"><span data-stu-id="864d9-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="864d9-108">与呼叫管理通道号码一样，呼叫接听组号码需要是未为其分配用户或电话的虚拟分机。</span><span class="sxs-lookup"><span data-stu-id="864d9-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="864d9-109">每个部署组内呼叫接听的前端池都可以有一个或多个呼叫接听组号码范围。</span><span class="sxs-lookup"><span data-stu-id="864d9-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="864d9-110">组号码范围在部署中必须全局唯一，并且必须分配为 **GroupPickup** 类型。</span><span class="sxs-lookup"><span data-stu-id="864d9-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="864d9-111">使用以下过程可创建或修改呼叫管理通道表中的呼叫接听组号码范围。</span><span class="sxs-lookup"><span data-stu-id="864d9-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="864d9-112">必须使用 Skype for Business Server 命令行管理程序在呼叫等待通道表中创建、修改、删除和查看组内呼叫接听号码范围。</span><span class="sxs-lookup"><span data-stu-id="864d9-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="864d9-113">组内呼叫接听号码范围在 Skype for Business Server 控制面板中不可用。</span><span class="sxs-lookup"><span data-stu-id="864d9-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="864d9-114">呼叫接听组号码范围必须符合以下规则：</span><span class="sxs-lookup"><span data-stu-id="864d9-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="864d9-115">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="864d9-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="864d9-116">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="864d9-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="864d9-p104">号码范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="864d9-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="864d9-119">如果号码范围以字符或 #开头，则范围 \* 必须大于 100。</span><span class="sxs-lookup"><span data-stu-id="864d9-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="864d9-120">有效值：必须与正则表达式字符串匹配 ([ \\ \*|#]？[1-9]\d {0,7}) | ([1-9]\d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="864d9-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="864d9-121">这意味着该值必须是以字符或 # 或数字 1 到 9 开头的字符串 (第一个字符不能为 \* 零) 。</span><span class="sxs-lookup"><span data-stu-id="864d9-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="864d9-122">如果第一个字符是 或 #，则下一个字符必须是 1 到 \* 9 (不能是零) 。</span><span class="sxs-lookup"><span data-stu-id="864d9-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="864d9-123">后续字符可以是 0 到 9 之间的任意数字 (例如 \* ，"#6000"、"92000"、"95551212"和 \* "915551212") 。</span><span class="sxs-lookup"><span data-stu-id="864d9-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="864d9-124">如果第一个字符不是 或 #，则第一个字符必须是 1 到 9 个数字 (不能为零) ，后跟最多八个字符，每个字符从 0 到 \* 9 (例如，"915551212"、"41212"、"300") 。</span><span class="sxs-lookup"><span data-stu-id="864d9-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="864d9-125">创建或修改呼叫接听组范围</span><span class="sxs-lookup"><span data-stu-id="864d9-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="864d9-126">以 RTCUniversalServerAdmins 组的成员或委派安装权限中所述的必要用户权限登录到安装了 Skype for Business Server 命令行管理程序 **的计算机**。</span><span class="sxs-lookup"><span data-stu-id="864d9-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="864d9-127">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="864d9-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="864d9-128">使用 **New-CsCallParkOrbit** 创建呼叫接听组号码的新范围。</span><span class="sxs-lookup"><span data-stu-id="864d9-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="864d9-129">使用 **Set-CsCallParkOrbit** 修改呼叫接听号码的现有范围。</span><span class="sxs-lookup"><span data-stu-id="864d9-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="864d9-130">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="864d9-130">At the command line, run:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="864d9-131">例如：</span><span class="sxs-lookup"><span data-stu-id="864d9-131">For example:</span></span>

   ```powershell
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="864d9-132">以下示例演示如何将号码范围从呼叫呼叫轨道更改为呼叫接听组。</span><span class="sxs-lookup"><span data-stu-id="864d9-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```powershell
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="864d9-133">只有在最初指定的类型不正确且组范围尚未使用时，使用此 cmdlet 才能更改分配给号码范围的类型。</span><span class="sxs-lookup"><span data-stu-id="864d9-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="864d9-134">如果将号码范围从 CallPark 更改为 GroupPickup，反之亦然，并且该号码范围已在使用中，则呼叫等待或组内呼叫接听将停止处理该号码范围。</span><span class="sxs-lookup"><span data-stu-id="864d9-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="864d9-135">例如，如果将一个号码范围从 CallPark 更改为 GroupPick，则呼叫等待应用程序不能再使用该通道范围来呼叫。</span><span class="sxs-lookup"><span data-stu-id="864d9-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="864d9-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="864d9-136">See also</span></span>

[<span data-ttu-id="864d9-137">New-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="864d9-137">New-CsCallParkOrbit</span></span>](/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="864d9-138">Set-CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="864d9-138">Set-CsCallParkOrbit</span></span>](/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="864d9-139">删除呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="864d9-139">Delete a Call Park Orbit Range</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-delete-a-call-park-orbit-range)