---
title: 创建或修改 Skype for Business 中的组呼叫分拣号码范围
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
description: 创建或修改业务 Server 企业语音中 Skype 的组呼叫分拣号码范围。
ms.openlocfilehash: d73b3e72aa7cd5f733406c861d8a3357fe28fe45
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883951"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-skype-for-business"></a><span data-ttu-id="f401d-103">创建或修改 Skype for Business 中的组呼叫分拣号码范围</span><span class="sxs-lookup"><span data-stu-id="f401d-103">Create or modify a Group Call Pickup number range in Skype for Business</span></span>

<span data-ttu-id="f401d-104">创建或修改业务 Server 企业语音中 Skype 的组呼叫分拣号码范围。</span><span class="sxs-lookup"><span data-stu-id="f401d-104">Create or modify a Group Call Pickup number range in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="f401d-105">组呼叫分拣基于呼叫寄存应用程序。</span><span class="sxs-lookup"><span data-stu-id="f401d-105">Group Call Pickup is based on the Call Park application.</span></span> <span data-ttu-id="f401d-106">当您部署组呼叫分拣时，必须使用范围指定为呼叫分拣组电话号码的电话号码的配置呼叫寄存通道表。</span><span class="sxs-lookup"><span data-stu-id="f401d-106">When you deploy Group Call Pickup, you must configure the call park orbit table with ranges of phone numbers that are designated as call pickup group numbers.</span></span> <span data-ttu-id="f401d-107">这些组号码是用户拨打以应答为另一个用户响铃的呼叫的号码。</span><span class="sxs-lookup"><span data-stu-id="f401d-107">These group numbers are the numbers that users dial to pick up calls that are ringing for another user.</span></span>

<span data-ttu-id="f401d-108">与呼叫寄存轨道号码类似，呼叫应答组号码需要是没有为其分配用户或电话的虚拟分机号。</span><span class="sxs-lookup"><span data-stu-id="f401d-108">Like call park orbit numbers, call pickup group numbers need to be virtual extensions that have no user or phone assigned to them.</span></span> <span data-ttu-id="f401d-109">在部署组呼叫分拣每个前端池可以有一个或多个呼叫分拣组号码范围。</span><span class="sxs-lookup"><span data-stu-id="f401d-109">Each Front End pool where you deploy Group Call Pickup can have one or more ranges of call pickup group numbers.</span></span> <span data-ttu-id="f401d-110">组号码范围在部署中必须是全局唯一的，并且必须作为 **GroupPickup** 类型分配。</span><span class="sxs-lookup"><span data-stu-id="f401d-110">The group number ranges must be globally unique in your deployment, and must be assigned as the **GroupPickup** type.</span></span>

<span data-ttu-id="f401d-111">使用下面的过程在呼叫寄存轨道表中创建或修改呼叫应答组号码范围。</span><span class="sxs-lookup"><span data-stu-id="f401d-111">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

> [!NOTE]
> <span data-ttu-id="f401d-112">您必须使用 Skype 的业务 Server 命令行管理程序创建、 修改、 删除和查看呼叫寄存通道表中的组呼叫分拣号码范围。</span><span class="sxs-lookup"><span data-stu-id="f401d-112">You must use Skype for Business Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="f401d-113">组呼叫分拣号码范围中的业务 Server Control Panel Skype 不可。</span><span class="sxs-lookup"><span data-stu-id="f401d-113">Group Call Pickup number ranges are not available in Skype for Business Server Control Panel.</span></span>

<span data-ttu-id="f401d-114">呼叫应答组号码范围必须符合以下规则：</span><span class="sxs-lookup"><span data-stu-id="f401d-114">The call pickup group number ranges must comply with the following rules:</span></span>

- <span data-ttu-id="f401d-115">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="f401d-115">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

- <span data-ttu-id="f401d-116">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="f401d-116">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

- <span data-ttu-id="f401d-p104">号码范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="f401d-p104">The number range must be unique. This range cannot overlap with any other range.</span></span>

- <span data-ttu-id="f401d-119">如果号码范围以字符开头\*或 #，该范围必须大于 100。</span><span class="sxs-lookup"><span data-stu-id="f401d-119">If the number range begins with the character \* or #, the range must be greater than 100.</span></span>

- <span data-ttu-id="f401d-120">有效值： 必须匹配的正则表达式的字符串 ([\\* | #] ? [1-9] \d{0,7}) |([1-9] \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="f401d-120">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="f401d-121">这意味着的值必须是字符开头的字符串\*或 # 或数字 1 至 9 （的第一个字符不能为零）。</span><span class="sxs-lookup"><span data-stu-id="f401d-121">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="f401d-122">如果第一个字符是\*或 #，以下字符必须是数字 1 至 9 （不能为零）。</span><span class="sxs-lookup"><span data-stu-id="f401d-122">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="f401d-123">后续字符可以是任何数字 0 到 9 最多七个其他字符 (例如，"#6000"、"\*92000"，"\*95551212" 和"915551212")。</span><span class="sxs-lookup"><span data-stu-id="f401d-123">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="f401d-124">如果第一个字符不是\*或 #、 第一个字符必须是数字 1 至 9 （不能为零），最多八个字符后, 跟每个数字 0 到 9 （例如，"915551212"、"41212"、"300"）。</span><span class="sxs-lookup"><span data-stu-id="f401d-124">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

### <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="f401d-125">创建或修改呼叫应答组范围</span><span class="sxs-lookup"><span data-stu-id="f401d-125">To create or modify a call pickup group range</span></span>

1. <span data-ttu-id="f401d-126">登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="f401d-126">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="f401d-127">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="f401d-127">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="f401d-128">使用**New-cscallparkorbit**创建新的呼叫分拣组号码范围。</span><span class="sxs-lookup"><span data-stu-id="f401d-128">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="f401d-129">**设置 CsCallParkOrbit**用于修改现有的呼叫分拣号码范围。</span><span class="sxs-lookup"><span data-stu-id="f401d-129">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>

    <span data-ttu-id="f401d-130">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="f401d-130">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
   ```

    <span data-ttu-id="f401d-131">例如：</span><span class="sxs-lookup"><span data-stu-id="f401d-131">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
   ```

    <span data-ttu-id="f401d-132">下面的示例演示如何将号码范围从呼叫寄存轨道更改为呼叫应答组。</span><span class="sxs-lookup"><span data-stu-id="f401d-132">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
   ```

    > [!IMPORTANT]
    > <span data-ttu-id="f401d-133">仅在你最初指定了错误的类型并且组范围尚未使用时，才能使用此 cmdlet 更改分配到号码范围的类型。</span><span class="sxs-lookup"><span data-stu-id="f401d-133">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="f401d-134">如果你将号码范围从 CallPark 更改为 GroupPickup 或相反，并且号码范围已在使用中，则呼叫寄存或组内呼叫应答将不再对该号码范围起作用。</span><span class="sxs-lookup"><span data-stu-id="f401d-134">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="f401d-135">例如，如果您更改从 CallPark 为 GroupPick 号码范围，则呼叫寄存应用程序不再使用呼叫寄存轨道的范围。</span><span class="sxs-lookup"><span data-stu-id="f401d-135">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

## <a name="see-also"></a><span data-ttu-id="f401d-136">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f401d-136">See also</span></span>

[<span data-ttu-id="f401d-137">新 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f401d-137">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="f401d-138">设置 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="f401d-138">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="f401d-139">删除呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="f401d-139">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)