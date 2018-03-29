---
title: 在 Skype for Business 2015 中创建或修改呼叫寄存通道范围
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 2/7/2018
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 549ec118-eee5-4333-9416-80929ec057e0
description: 创建或修改业务服务器企业语音在 Skype 呼叫公园轨道幅度表。
ms.openlocfilehash: 3617fb739d56e395c31359c6cedae74e9fb63756
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2018
---
# <a name="create-or-modify-a-call-park-orbit-range-in-skype-for-business-2015"></a><span data-ttu-id="bd30a-103">在 Skype for Business 2015 中创建或修改呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="bd30a-103">Create or modify a Call Park orbit range in Skype for Business 2015</span></span>
 
<span data-ttu-id="bd30a-104">创建或修改业务服务器企业语音在 Skype 呼叫公园轨道幅度表。</span><span class="sxs-lookup"><span data-stu-id="bd30a-104">Create or modify a Call Park orbit range table in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="bd30a-105">调用公园用于停车调用使用轨道。</span><span class="sxs-lookup"><span data-stu-id="bd30a-105">Call Park uses orbits for parking calls.</span></span> <span data-ttu-id="bd30a-106">用户可以寄存和检索调用之前，您必须配置呼叫公园轨道表。</span><span class="sxs-lookup"><span data-stu-id="bd30a-106">Before users can park and retrieve calls, you must configure the Call Park orbit table.</span></span> <span data-ttu-id="bd30a-107">您需要指定分机号码 （轨道），您的组织将保留用于停车调用和定义这些区域传送范围通过指定哪个调用公园池处理每个范围。</span><span class="sxs-lookup"><span data-stu-id="bd30a-107">You need to specify the ranges of extension numbers (orbits) that your organization will reserve for parking calls and define the routing for those ranges by specifying which Call Park pool handles each range.</span></span> <span data-ttu-id="bd30a-108">定义通道范围时，目标是具有足够的通道，以便不会在短时间内重用任何一个通道，但又不能有太多通道，以致于不得不限制用户或其他服务可使用的分机数量。</span><span class="sxs-lookup"><span data-stu-id="bd30a-108">When you define orbit ranges, the goal is to have enough orbits so that any one orbit is not reused too quickly, but not so many orbits that you limit the number of extensions available for users or other services.</span></span> <span data-ttu-id="bd30a-109">您可以为每个 Skype 业务服务器池公园调用应用程序的部署位置创建多个调用公园轨道范围。</span><span class="sxs-lookup"><span data-stu-id="bd30a-109">You can create multiple Call Park orbit ranges for each Skype for Business Server pool where the Call Park application is deployed.</span></span> <span data-ttu-id="bd30a-110">每个调用公园轨道区域必须具有一个全局唯一名称和唯一的一组扩展。</span><span class="sxs-lookup"><span data-stu-id="bd30a-110">Each Call Park orbit range must have a globally unique name and a unique set of extensions.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="bd30a-p102">每个通道范围包含的通道数通常不超过 100。范围可以更大一点，只要每个范围的通道数小于最大值 10,000 且每个池的通道数小于 50,000。如果范围太小，很快就会重用通道。</span><span class="sxs-lookup"><span data-stu-id="bd30a-p102">An orbit range typically encompasses 100 or fewer orbits. Each range can be much larger, as long as it is smaller than the maximum of 10,000 orbits per range and you have fewer than 50,000 orbits per pool. If a range is too small, the orbits are reused more quickly.</span></span> 
  
<span data-ttu-id="bd30a-114">请使用虚拟分机（未向其分配用户或电话的分机）块作为通道范围。</span><span class="sxs-lookup"><span data-stu-id="bd30a-114">Use blocks of virtual extensions (extensions that have no user or phone assigned to them) for your orbit ranges.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="bd30a-115">不支持以调用公园轨道数分配直接向内拨号 (DID) 数字轨道表。</span><span class="sxs-lookup"><span data-stu-id="bd30a-115">Assigning Direct Inward Dialing (DID) numbers as orbit numbers in the Call Park orbit table is not supported.</span></span> 
  
<span data-ttu-id="bd30a-116">使用下列过程之一可创建或修改呼叫寄存通道范围。</span><span class="sxs-lookup"><span data-stu-id="bd30a-116">Use one of the following procedures to create or modify a call park orbit range.</span></span> 
  
### <a name="to-use-skype-for-business-server-control-panel-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="bd30a-117">若要使用 Skype 业务服务器的控制面板来创建或修改用于停车调用一个数字范围</span><span class="sxs-lookup"><span data-stu-id="bd30a-117">To use Skype for Business Server Control Panel to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="bd30a-118">作为 RTCUniversalServerAdmins 组的成员身份或 CsVoiceAdministrator、 CsServerAdministrator 或 CsAdministrator 角色的成员登录到该计算机。</span><span class="sxs-lookup"><span data-stu-id="bd30a-118">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="bd30a-119">有关详细信息，请参阅**代理安装程序权限**。</span><span class="sxs-lookup"><span data-stu-id="bd30a-119">For details, see **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bd30a-120">打开浏览器窗口，然后输入管理员 URL 打开 Skype 业务服务器控件面板。</span><span class="sxs-lookup"><span data-stu-id="bd30a-120">Open a browser window, and then enter the Admin URL to open the Skype for Business Server Control Panel.</span></span>  
    
3. <span data-ttu-id="bd30a-121">在左侧导航栏中，单击“语音功能”****，然后单击“呼叫寄存”****。</span><span class="sxs-lookup"><span data-stu-id="bd30a-121">In the left navigation bar, click **Voice Features** and then click **Call Park**.</span></span>
    
4. <span data-ttu-id="bd30a-122">在“呼叫寄存”****页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="bd30a-122">On the **Call Park** page, do one of the following:</span></span>
    
  - <span data-ttu-id="bd30a-p104">若要创建新的通道范围，请单击“新建”****。在“名称”****中，键入此号码范围的标识名称。</span><span class="sxs-lookup"><span data-stu-id="bd30a-p104">To create a new orbit range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bd30a-125">在将通道范围提交到数据库后，将无法更改该名称。</span><span class="sxs-lookup"><span data-stu-id="bd30a-125">After you commit the orbit range to the database, you cannot change this name.</span></span> 
  
  - <span data-ttu-id="bd30a-p105">若要修改现有通道范围，请在搜索字段中键入通道范围的全部或部分名称。在通道的结果列表中，单击所需的通道，再单击“编辑”****，然后单击“显示详细信息”****。</span><span class="sxs-lookup"><span data-stu-id="bd30a-p105">To modify an existing orbit range, type all or part of the name of the orbit range in the search field. In the resulting list of orbits, click the orbit you want, click **Edit**, and then click **Show details**.</span></span>
    
5. <span data-ttu-id="bd30a-128">在第一个“号码范围”****字段中，键入此呼叫寄存通道的分机范围中的起始号码，在第二个“号码范围”****字段中，键入该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="bd30a-128">In the first **Number range** field, type the beginning number of the range of extensions for this call park orbit, and in the second **Number range** field, type the ending number of the range.</span></span> <span data-ttu-id="bd30a-129">请注意：</span><span class="sxs-lookup"><span data-stu-id="bd30a-129">Be aware:</span></span>
    
   - <span data-ttu-id="bd30a-130">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="bd30a-130">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>
    
   - <span data-ttu-id="bd30a-131">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="bd30a-131">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>
    
   - <span data-ttu-id="bd30a-p107">通道范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="bd30a-p107">The orbit range must be unique. This range cannot overlap with any other range.</span></span>
    
   - <span data-ttu-id="bd30a-134">如果字符开头的轨道范围\*或 #，范围必须是大于 100。</span><span class="sxs-lookup"><span data-stu-id="bd30a-134">If the orbit range begins with the character \* or #, the range must be greater than 100.</span></span>
    
   - <span data-ttu-id="bd30a-135">有效值： 必须匹配的正则表达式字符串 ([\\* | #] ?[1-9]\d{0,7}) |([1-9] \d {0,8})。</span><span class="sxs-lookup"><span data-stu-id="bd30a-135">Valid values: Must match the regular expression string ([\\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}).</span></span> <span data-ttu-id="bd30a-136">这意味着该值必须是一个任意的字符开头的字符串\*# 或数字 1 到 9 （第一个字符不能为零）。</span><span class="sxs-lookup"><span data-stu-id="bd30a-136">This means the value must be a string beginning with either the character \* or # or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="bd30a-137">如果第一个字符是\*或 #，下面的字符必须是一个数字 1 到 9 （不能为零）。</span><span class="sxs-lookup"><span data-stu-id="bd30a-137">If the first character is \* or #, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="bd30a-138">后面的字符可以是任意数字 0 到 9，最多七个其他字符 (例如，"#6000"、"\*92000"、"\*95551212"，和"915551212")。</span><span class="sxs-lookup"><span data-stu-id="bd30a-138">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="bd30a-139">如果第一个字符不是\*#，第一个字符必须为最多八个字符后, 跟一个数字 1 到 9 （不能为零），或每个数字 0 到 9 （例如，"915551212"、"41212"、"300"）。</span><span class="sxs-lookup"><span data-stu-id="bd30a-139">If the first character is not \* or #, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>
    
   - <span data-ttu-id="bd30a-p109">每个池不应包含 50,000 个以上的通道。每个通道范围包含的通道数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。</span><span class="sxs-lookup"><span data-stu-id="bd30a-p109">You should not have more than a total of 50,000 orbits per pool. Each orbit range typically encompasses 100 or fewer orbits, but it can be much larger as long as it includes fewer than 10,000 orbits. For example, instead of specifying a starting number of "7000000" and an ending number of "8000000," consider specifying a starting number of "7000000" and an ending number of "7000100."</span></span>
    
6. <span data-ttu-id="bd30a-143">在**目标服务器的 FQDN**，请单击的完全合格的域名称 (FQDN) 或服务调用公园应用程序宿主的应用程序服务的 ID。</span><span class="sxs-lookup"><span data-stu-id="bd30a-143">In **FQDN of destination server**, click the fully qualified domain name (FQDN) or service ID of the Application service that hosts the Call Park application.</span></span> <span data-ttu-id="bd30a-144">寄存在由通道范围中的起始号码和结束号码指定的范围内的号码的所有呼叫都将路由到此服务器或池。</span><span class="sxs-lookup"><span data-stu-id="bd30a-144">All calls parked to numbers within the range specified by the start number and end number in the orbit range will be routed to this server or pool.</span></span>
    
7. <span data-ttu-id="bd30a-145">单击“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="bd30a-145">Click **Commit**.</span></span>
    
### <a name="to-use-skype-for-business-server-management-shell-to-create-or-modify-a-range-of-numbers-for-parking-calls"></a><span data-ttu-id="bd30a-146">若要使用 Skype 的业务服务器管理外壳程序创建或修改用于停车调用的编号范围</span><span class="sxs-lookup"><span data-stu-id="bd30a-146">To use Skype for Business Server Management Shell to create or modify a range of numbers for parking calls</span></span>

1. <span data-ttu-id="bd30a-147">登录到业务服务器管理外壳的 Skype 为成员的 RTCUniversalServerAdmins 组或**委托安装程序权限**中所述的必要的用户权限的安装位置的计算机上。</span><span class="sxs-lookup"><span data-stu-id="bd30a-147">Log on to the computer where Skype for Business Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in **Delegate Setup Permissions**.</span></span>
    
2. <span data-ttu-id="bd30a-148">启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。</span><span class="sxs-lookup"><span data-stu-id="bd30a-148">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="bd30a-149">使用**新建 CsCallParkOrbit**创建一个新轨道数字范围。</span><span class="sxs-lookup"><span data-stu-id="bd30a-149">Use **New-CsCallParkOrbit** to create a new range of orbit numbers.</span></span> <span data-ttu-id="bd30a-150">**一组 CsCallParkOrbit**用于修改现有轨道号的范围。</span><span class="sxs-lookup"><span data-stu-id="bd30a-150">Use **Set-CsCallParkOrbit** to modify an existing range of orbit numbers.</span></span>
    
    <span data-ttu-id="bd30a-151">在该命令行处，运行：</span><span class="sxs-lookup"><span data-stu-id="bd30a-151">At the command line, run:</span></span>
    
   ```
   New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
   ```

    <span data-ttu-id="bd30a-152">例如：</span><span class="sxs-lookup"><span data-stu-id="bd30a-152">For example:</span></span>
     
   ```
   New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
   ```

    <span data-ttu-id="bd30a-153">以下示例说明如何修改现有通道范围中的号码。</span><span class="sxs-lookup"><span data-stu-id="bd30a-153">The following example shows how to modify the numbers in an existing orbit range,</span></span>
    
   ```
   Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699
   ```

## <a name="see-also"></a><span data-ttu-id="bd30a-154">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bd30a-154">See also</span></span>

#### 

[<span data-ttu-id="bd30a-155">新 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="bd30a-155">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="bd30a-156">一组 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="bd30a-156">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/set-cscallparkorbit?view=skype-ps)
  
[<span data-ttu-id="bd30a-157">删除调用公园轨道范围</span><span class="sxs-lookup"><span data-stu-id="bd30a-157">Delete a Call Park Orbit Range</span></span>](http://technet.microsoft.com/library/85e9f916-062d-450d-ac0a-aeaefc0f7cdc.aspx)

