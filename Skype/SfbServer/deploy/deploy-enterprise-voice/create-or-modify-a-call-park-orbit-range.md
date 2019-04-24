---
title: 创建或修改呼叫寄存通道范围中的业务的 Skype
ms.reviewer: ''
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
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 创建或修改业务 Server 企业语音的呼叫寄存通道范围表 Skype 中。
ms.openlocfilehash: 23de2c42ff7b7e8bf3c020eaf3bb5050524b87d3
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212528"
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business"></a><span data-ttu-id="c8415-103">创建或修改呼叫寄存通道范围中的业务的 Skype</span><span class="sxs-lookup"><span data-stu-id="c8415-103">Create or modify a Call Park orbit range in Skype for Business</span></span>

<span data-ttu-id="c8415-104">创建或修改业务 Server 企业语音的呼叫寄存通道范围表 Skype 中。</span><span class="sxs-lookup"><span data-stu-id="c8415-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>

<span data-ttu-id="c8415-105">呼叫寄存使用的呼叫寄存轨道。</span><span class="sxs-lookup"><span data-stu-id="c8415-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="c8415-106">用户可寄存并取回呼叫之前，您必须配置呼叫寄存通道表。</span><span class="sxs-lookup"><span data-stu-id="c8415-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="c8415-107">您需要指定的范围的分机号 （轨道），您的组织将保留用于寄存呼叫，并定义这些区域路由通过指定的呼叫寄存池处理每个范围。</span><span class="sxs-lookup"><span data-stu-id="c8415-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="c8415-108">定义通道范围时，目标是具有足够的通道，以便不会在短时间内重用任何一个通道，但又不能有太多通道，以致于不得不限制用户或其他服务可使用的分机数量。</span><span class="sxs-lookup"><span data-stu-id="c8415-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="c8415-109">您可以为每个 Skype 部署呼叫寄存应用程序的业务服务器池创建多个呼叫寄存轨道范围。</span><span class="sxs-lookup"><span data-stu-id="c8415-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="c8415-110">每个呼叫寄存通道范围必须具有一个全局唯一的名称和一组唯一的扩展。</span><span class="sxs-lookup"><span data-stu-id="c8415-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c8415-p102">每个通道范围包含的通道数通常不超过 100。范围可以更大一点，只要每个范围的通道数小于最大值 10,000 且每个池的通道数小于 50,000。如果范围太小，很快就会重用通道。</span><span class="sxs-lookup"><span data-stu-id="c8415-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span>

<span data-ttu-id="c8415-114">请使用虚拟分机（未向其分配用户或电话的分机）块作为通道范围。</span><span class="sxs-lookup"><span data-stu-id="c8415-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span>

> [!NOTE]
> <span data-ttu-id="c8415-115">不支持将外线直拨分机 (DID) 号码分配为通道号码的呼叫寄存通道表。</span><span class="sxs-lookup"><span data-stu-id="c8415-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span>

<span data-ttu-id="c8415-116">使用下列过程之一可创建或修改呼叫寄存通道范围。</span><span class="sxs-lookup"><span data-stu-id="c8415-116">Use one of the following procedures to create or modify a call park orbit range.</span></span>

### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="c8415-117">若要使用的业务 Server Control Panel Skype 创建或修改寄存呼叫的号码范围</span><span class="sxs-lookup"><span data-stu-id="c8415-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="c8415-p103">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅**Delegate Setup Permissions**。</span><span class="sxs-lookup"><span data-stu-id="c8415-p103">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role. For details, see **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="c8415-120">打开一个浏览器窗口，然后输入管理 URL 以打开 Skype 业务 Server Control Panel。</span><span class="sxs-lookup"><span data-stu-id="c8415-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>

3. <span data-ttu-id="c8415-121">在左侧导航栏中，单击“语音功能”\*\*\*\*，然后单击“呼叫寄存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8415-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>

4. <span data-ttu-id="c8415-122">在“呼叫寄存”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="c8415-122">On the **Call Park** page, do one of the following:</span></span>

   - <span data-ttu-id="c8415-p104">若要创建新的通道范围，请单击“新建”\*\*\*\*。在“名称”\*\*\*\* 中，键入此号码范围的标识名称。</span><span class="sxs-lookup"><span data-stu-id="c8415-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>

     > [!NOTE]
     > <span data-ttu-id="c8415-125">在将通道范围提交到数据库后，将无法更改该名称。</span><span class="sxs-lookup"><span data-stu-id="c8415-125">After you commit the orbit range to the database, you cannot change this name.</span></span>

   - <span data-ttu-id="c8415-p105">若要修改现有通道范围，请在搜索字段中键入通道范围的全部或部分名称。在通道的结果列表中，单击所需的通道，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8415-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>

5. <span data-ttu-id="c8415-128">在第一个“号码范围”\*\*\*\* 字段中，键入此呼叫寄存通道的分机范围中的起始号码，在第二个“号码范围”\*\*\*\* 字段中，键入该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="c8415-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="c8415-129">注意：</span><span class="sxs-lookup"><span data-stu-id="c8415-129">Be aware:</span></span>

   - <span data-ttu-id="c8415-130">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="c8415-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

   - <span data-ttu-id="c8415-131">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="c8415-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

   - <span data-ttu-id="c8415-p107">通道范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="c8415-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>

   - <span data-ttu-id="c8415-134">如果通道范围以字符开头\*或 #，该范围必须大于 100。</span><span class="sxs-lookup"><span data-stu-id="c8415-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>

   - <span data-ttu-id="c8415-135">有效值： 必须匹配的正则表达式的字符串 ([\\* | #] ? [1-9] \d{0,7}) |([1-9] \d{0,8})。</span><span class="sxs-lookup"><span data-stu-id="c8415-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="c8415-136">这意味着的值必须是字符开头的字符串\*或 # 或数字 1 至 9 （的第一个字符不能为零）。</span><span class="sxs-lookup"><span data-stu-id="c8415-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="c8415-137">如果第一个字符是\*或 #，以下字符必须是数字 1 至 9 （不能为零）。</span><span class="sxs-lookup"><span data-stu-id="c8415-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="c8415-138">后续字符可以是任何数字 0 到 9 最多七个其他字符 (例如，"#6000"、"\*92000"，"\*95551212" 和"915551212")。</span><span class="sxs-lookup"><span data-stu-id="c8415-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="c8415-139">如果第一个字符不是\*或 #、 第一个字符必须是数字 1 至 9 （不能为零），最多八个字符后, 跟每个数字 0 到 9 （例如，"915551212"、"41212"、"300"）。</span><span class="sxs-lookup"><span data-stu-id="c8415-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

   - <span data-ttu-id="c8415-p109">每个池不应包含 50,000 个以上的通道。每个通道范围包含的通道数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。</span><span class="sxs-lookup"><span data-stu-id="c8415-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>

6. <span data-ttu-id="c8415-143">在**目标服务器的 FQDN**中，单击的完全限定的域名 (FQDN) 或服务 ID 承载呼叫寄存应用程序的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="c8415-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="c8415-144">寄存在由通道范围中的起始号码和结束号码指定的范围内的号码的所有呼叫都将路由到此服务器或池。</span><span class="sxs-lookup"><span data-stu-id="c8415-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>

7. <span data-ttu-id="c8415-145">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="c8415-145">Click **Commit**.</span></span>

### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="c8415-146">使用 Skype 的业务 Server 命令行管理程序创建或修改寄存呼叫的号码范围</span><span class="sxs-lookup"><span data-stu-id="c8415-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="c8415-147">登录到计算机的业务 Server Management Shell 的 Skype 或使用**Delegate Setup Permissions**中所述的必要用户权限的 RTCUniversalServerAdmins 组成员身份的安装。</span><span class="sxs-lookup"><span data-stu-id="c8415-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>

2. <span data-ttu-id="c8415-148">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c8415-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>

3. <span data-ttu-id="c8415-149">使用  **New-CsCallParkOrbit** 可创建通道号码的新范围。</span><span class="sxs-lookup"><span data-stu-id="c8415-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="c8415-150">使用  **Set-CsCallParkOrbit** 可修改通道号码的现有范围。</span><span class="sxs-lookup"><span data-stu-id="c8415-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>

    <span data-ttu-id="c8415-151">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="c8415-151">At the command line, run:</span></span>

   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="c8415-152">例如：</span><span class="sxs-lookup"><span data-stu-id="c8415-152">For example:</span></span>

   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="c8415-153">以下示例说明如何修改现有通道范围中的号码。</span><span class="sxs-lookup"><span data-stu-id="c8415-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>

   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="c8415-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8415-154">See also</span></span>

[<span data-ttu-id="c8415-155">新 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="c8415-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="c8415-156">设置 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="c8415-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)

[<span data-ttu-id="c8415-157">删除呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="c8415-157">Delete a Call Park Orbit Range</span></span>](https://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)
