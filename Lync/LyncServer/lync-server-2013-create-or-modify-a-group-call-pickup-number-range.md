---
title: Lync Server 2013：创建或修改组内呼叫应答号码范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ee394401999038c205826c99b3e6b2e35734087d
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48506129"
---
# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a><span data-ttu-id="3088e-102">在 Lync Server 2013 中创建或修改组内呼叫装货号码范围</span><span class="sxs-lookup"><span data-stu-id="3088e-102">Create or modify a Group Call Pickup number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3088e-103">_**上次修改的主题：** 2013-01-30_</span><span class="sxs-lookup"><span data-stu-id="3088e-103">_**Topic Last Modified:** 2013-01-30_</span></span>

<span data-ttu-id="3088e-104">使用以下过程可在呼叫寄存通道表中创建或修改呼叫应答组号码范围。</span><span class="sxs-lookup"><span data-stu-id="3088e-104">Use the following procedure to create or modify a call pickup group number range in the call park orbit table.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="3088e-105">必须使用 Lync Server 命令行管理程序在呼叫寄存通道表中创建、修改、删除和查看组内呼叫应答号码范围。</span><span class="sxs-lookup"><span data-stu-id="3088e-105">You must use Lync Server Management Shell to create, modify, remove, and view Group Call Pickup number ranges in the call park orbit table.</span></span> <span data-ttu-id="3088e-106">组内呼叫应答号码范围在 Lync Server 控制面板中不可用。</span><span class="sxs-lookup"><span data-stu-id="3088e-106">Group Call Pickup number ranges are not available in Lync Server Control Panel.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3088e-107">必须为呼叫应答组号码范围分配一种类型的 GroupPickup。</span><span class="sxs-lookup"><span data-stu-id="3088e-107">The call pickup group number range must be assigned a type of GroupPickup.</span></span> <span data-ttu-id="3088e-108">仅当用户分配的组编号为类型 GroupPickup 时，才会为其启用组呼叫应答。</span><span class="sxs-lookup"><span data-stu-id="3088e-108">Users are enabled for Group Call Pickup only if the group number that they are assigned is type GroupPickup.</span></span>



</div>

<span data-ttu-id="3088e-109">呼叫应答组号码范围必须符合以下规则：</span><span class="sxs-lookup"><span data-stu-id="3088e-109">The call pickup group number ranges must comply with the following rules:</span></span>

  - <span data-ttu-id="3088e-110">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="3088e-110">The beginning number of the range must be less than or equal to the ending number of the range.</span></span>

  - <span data-ttu-id="3088e-111">该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</span><span class="sxs-lookup"><span data-stu-id="3088e-111">The value of the beginning number of the range must be the same length as the ending number of the range.</span></span>

  - <span data-ttu-id="3088e-p103">号码范围必须是唯一的。该范围不能与其他任何范围重叠。</span><span class="sxs-lookup"><span data-stu-id="3088e-p103">The number range must be unique. This range cannot overlap with any other range.</span></span>

  - <span data-ttu-id="3088e-114">如果数字范围以字符 \* 或开头，则 \# 该范围必须大于100。</span><span class="sxs-lookup"><span data-stu-id="3088e-114">If the number range begins with the character \* or \#, the range must be greater than 100.</span></span>

  - <span data-ttu-id="3088e-115">有效值：必须与正则表达式字符串 (的值相匹配 \[ \\ \* | \# \] ？ \[1-9 \] \\ d {0,7}) | (\[ 1-9 \] \\ d {0,8}) 。</span><span class="sxs-lookup"><span data-stu-id="3088e-115">Valid values: Must match the regular expression string (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}).</span></span> <span data-ttu-id="3088e-116">这意味着值必须是以字符 \* 或 \# 数字1到9开头的字符串， (第一个字符不能为零) 。</span><span class="sxs-lookup"><span data-stu-id="3088e-116">This means the value must be a string beginning with either the character \* or \# or a number 1 through 9 (the first character cannot be a zero).</span></span> <span data-ttu-id="3088e-117">如果第一个字符是 \* 或 \# ，则以下字符必须是数字1到 9 (不能为零) 。</span><span class="sxs-lookup"><span data-stu-id="3088e-117">If the first character is \* or \#, the following character must be a number 1 through 9 (it cannot be a zero).</span></span> <span data-ttu-id="3088e-118">后续字符可以是0到9之间的任何数字，最多可以有七个其他字符 (例如，" \# 6000"、" \* 92000"、" \* 95551212" 和 "915551212" ) 。</span><span class="sxs-lookup"><span data-stu-id="3088e-118">Subsequent characters can be any number 0 through 9 up to seven additional characters (for example, "\#6000", "\*92000", "\*95551212", and "915551212").</span></span> <span data-ttu-id="3088e-119">如果第一个字符不是 \* 或 \# ，则第一个字符必须是从1到9的数字， (不能为零) ，后跟八个字符，每个数字0到 9 (例如，"915551212"、"41212"、"300" ) 。</span><span class="sxs-lookup"><span data-stu-id="3088e-119">If the first character is not \* or \#, the first character must be a number 1 through 9 (it cannot be zero), followed by up to eight characters, each a number 0 through 9 (for example, "915551212", "41212", "300").</span></span>

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a><span data-ttu-id="3088e-120">创建或修改呼叫装货组范围</span><span class="sxs-lookup"><span data-stu-id="3088e-120">To create or modify a call pickup group range</span></span>

1.  <span data-ttu-id="3088e-121">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="3088e-121">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3088e-122">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3088e-122">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3088e-123">使用 **CsCallParkOrbit** 创建一个新的呼叫应答组号码范围。</span><span class="sxs-lookup"><span data-stu-id="3088e-123">Use **New-CsCallParkOrbit** to create a new range of call pickup group numbers.</span></span> <span data-ttu-id="3088e-124">使用 **CsCallParkOrbit** 可修改现有的呼叫装货号码范围。</span><span class="sxs-lookup"><span data-stu-id="3088e-124">Use **Set-CsCallParkOrbit** to modify an existing range of call pickup numbers.</span></span>
    
    <span data-ttu-id="3088e-125">在命令行中运行：</span><span class="sxs-lookup"><span data-stu-id="3088e-125">At the command line, run:</span></span>
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    <span data-ttu-id="3088e-126">例如：</span><span class="sxs-lookup"><span data-stu-id="3088e-126">For example:</span></span>
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    <span data-ttu-id="3088e-127">下面的示例演示如何将号码范围从呼叫寄存轨道式更改为呼叫应答组。</span><span class="sxs-lookup"><span data-stu-id="3088e-127">The following example shows how to change a range of numbers from call park orbits to call pickup groups.</span></span>
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="3088e-128">仅当最初指定了不正确的类型且组范围尚未使用时，才能使用此 cmdlet 更改分配给号码范围的类型。</span><span class="sxs-lookup"><span data-stu-id="3088e-128">Use this cmdlet to change the type assigned to number ranges only if you initially specified the incorrect type and the group range is not yet in use.</span></span> <span data-ttu-id="3088e-129">如果将号码范围从 CallPark 更改为 GroupPickup，反之亦然，而号码范围已在使用中，则呼叫寄存或 Group Call Pickup 将停止对该号码范围的工作。</span><span class="sxs-lookup"><span data-stu-id="3088e-129">If you change the number range from CallPark to GroupPickup or vice versa and the number range is already in use, either Call Park or Group Call Pickup will stop working for that number range.</span></span> <span data-ttu-id="3088e-130">例如，如果将号码范围从 CallPark 更改为 GroupPick，则呼叫寄存应用程序无法再将该范围的轨道式用于寄存呼叫。</span><span class="sxs-lookup"><span data-stu-id="3088e-130">For example, if you change a number range from CallPark to GroupPick, the Call Park application can no longer use that range of orbits to park calls.</span></span>

    
    </div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3088e-131">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3088e-131">See Also</span></span>


[<span data-ttu-id="3088e-132">在 Lync Server 2013 中删除呼叫寄存通道范围</span><span class="sxs-lookup"><span data-stu-id="3088e-132">Delete a Call Park orbit range in Lync Server 2013</span></span>](lync-server-2013-delete-a-call-park-orbit-range.md)  


[<span data-ttu-id="3088e-133">新 CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="3088e-133">New-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[<span data-ttu-id="3088e-134">CsCallParkOrbit</span><span class="sxs-lookup"><span data-stu-id="3088e-134">Set-CsCallParkOrbit</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

