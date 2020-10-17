---
title: Lync Server 2013：创建或修改未分配号码范围
description: Lync Server 2013：创建或修改未分配号码范围。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify an unassigned number range
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412748(v=OCS.15)
ms:contentKeyID: 48185013
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2998616b931e94c9c38fc44d569b84b3af37709d
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48546948"
---
# <a name="create-or-modify-an-unassigned-number-range-in-lync-server-2013"></a><span data-ttu-id="3af07-103">在 Lync Server 2013 中创建或修改未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="3af07-103">Create or modify an unassigned number range in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3af07-104">_**上次修改的主题：** 2012-11-01_</span><span class="sxs-lookup"><span data-stu-id="3af07-104">_**Topic Last Modified:** 2012-11-01_</span></span>

<span data-ttu-id="3af07-105">使用以下过程之一为通知应用程序配置未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="3af07-105">Use one of the following procedures to configure unassigned number ranges for the Announcement application.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="3af07-106">在配置未分配号码表之前，必须已定义一个或多个通知，或已设置 Exchange 统一消息 (UM) 自动助理。</span><span class="sxs-lookup"><span data-stu-id="3af07-106">Before you configure the unassigned number table, you must have already defined one or more announcements or set up an Exchange Unified Messaging (UM) Auto Attendant.</span></span>



</div>

<div>

## <a name="to-use-lync-server-control-panel-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="3af07-107">使用 Lync Server 控制面板配置未分配的电话号码</span><span class="sxs-lookup"><span data-stu-id="3af07-107">To use Lync Server Control Panel to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="3af07-108">以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。</span><span class="sxs-lookup"><span data-stu-id="3af07-108">Log on to the computer as a member of the RTCUniversalServerAdmins group, or as a member of the CsVoiceAdministrator, CsServerAdministrator, or CsAdministrator role.</span></span> <span data-ttu-id="3af07-109">有关详细信息，请参阅 [Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="3af07-109">For details, see [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3af07-110">打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。</span><span class="sxs-lookup"><span data-stu-id="3af07-110">Open a browser window, and then enter the Admin URL to open the Lync Server Control Panel.</span></span> <span data-ttu-id="3af07-111">有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。</span><span class="sxs-lookup"><span data-stu-id="3af07-111">For details about the different methods you can use to start Lync Server Control Panel, see [Open Lync Server 2013 administrative tools](lync-server-2013-open-lync-server-administrative-tools.md).</span></span>

3.  <span data-ttu-id="3af07-112">在左侧导航栏中，单击“语音功能”\*\*\*\*，然后单击“未分配号码”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3af07-112">In the left navigation bar, click **Voice Features**, and then click **Unassigned Number**.</span></span>

4.  <span data-ttu-id="3af07-113">在“未分配号码”\*\*\*\* 页上，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3af07-113">On the **Unassigned Number** page, do one of the following:</span></span>
    
      - <span data-ttu-id="3af07-p103">若要创建新的号码范围，请单击“新建”\*\*\*\*。在“名称”\*\*\*\* 中，键入此号码范围的标识名称。</span><span class="sxs-lookup"><span data-stu-id="3af07-p103">To create a new number range, click **New**. In **Name**, type an identifying name for this range of numbers.</span></span>
        
        <div>
        

        > [!NOTE]  
        > <span data-ttu-id="3af07-116">新的未分配号码范围提交到数据库后，将无法更改该名称。</span><span class="sxs-lookup"><span data-stu-id="3af07-116">After you commit the new unassigned number range to the database, you cannot change this name.</span></span>

        
        </div>
    
      - <span data-ttu-id="3af07-p104">若要修改现有号码范围，请在搜索字段中键入号码范围的全部或部分名称。在号码范围的结果列表中，单击所需的名称，再单击“编辑”\*\*\*\*，然后单击“显示详细信息”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3af07-p104">To modify an existing number range, type all or part of the name of the number range in the search field. In the resulting list of number ranges, click the name you want, click **Edit**, and then click **Show details**.</span></span>

5.  <span data-ttu-id="3af07-119">在第一个“号码范围”\*\*\*\* 字段中，键入号码范围的起始号码，在第二个“号码范围”\*\*\*\* 字段中，键入该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="3af07-119">In the first **Number range** field, type the beginning number of the range, and in the second **Number range** field, type the ending number of the range.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <UL>
    > <LI>
    > <P><span data-ttu-id="3af07-120">该范围的起始号码必须小于或等于该范围的结束号码。</span><span class="sxs-lookup"><span data-stu-id="3af07-120">The beginning number of the range must be less than or equal to the ending number of the range.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="3af07-121">如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。</span><span class="sxs-lookup"><span data-stu-id="3af07-121">If the beginning number of the range or the ending number of the range includes an extension number, both the beginning number and the ending number of the range must include an extension, and the extension number must be the same for both the beginning number and the ending number.</span></span></P>
    > <LI>
    > <P><span data-ttu-id="3af07-122">该号码必须与正则表达式 (电话： ) ？ (\+) ？ [1-9] \d {0,17} (; ext = [1-9] \d {0,9}) ？。</span><span class="sxs-lookup"><span data-stu-id="3af07-122">The number must match the regular expression (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?.</span></span> <span data-ttu-id="3af07-123">这意味着此号码可能以字符串 tel:（如果没有指定此字符串，将自动为您添加）、加号 (+) 以及一个 1 到 9 之间的数字开头。</span><span class="sxs-lookup"><span data-stu-id="3af07-123">This means the number may begin with the string tel: (if you don’t specify that string, it will be automatically added for you), a plus sign (+), and a digit 1 through 9.</span></span> <span data-ttu-id="3af07-124">电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</span><span class="sxs-lookup"><span data-stu-id="3af07-124">The phone number can be up to 17 digits and may be followed by an extension in the format ;ext= followed by the extension number.</span></span></P></LI></UL>

    
    </div>

6.  <span data-ttu-id="3af07-125">在 **“通知服务”** 中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3af07-125">In **Announcement service**, do one of the following:</span></span>
    
      - <span data-ttu-id="3af07-126">单击 **“通知”**。</span><span class="sxs-lookup"><span data-stu-id="3af07-126">Click **Announcement**.</span></span>
    
      - <span data-ttu-id="3af07-127">单击 **“Exchange UM”**。</span><span class="sxs-lookup"><span data-stu-id="3af07-127">Click **Exchange UM**.</span></span>

7.  <span data-ttu-id="3af07-128">如果在上一步中单击了 **“通知”**，则执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3af07-128">If, in the previous step, you clicked **Announcement**, do the following:</span></span>
    
    1.  <span data-ttu-id="3af07-129">在 **“目标服务器的 FQDN”** 下，单击 **“选择”**，再单击运行通知应用程序的应用程序服务的服务 ID（该通知应用程序将处理到此未分配号码范围的传入呼叫），然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3af07-129">Under **FQDN of destination server**, click **Select**, click the service ID of the Application service that runs the Announcement application that will handle incoming calls to this range of unassigned numbers, and then click **OK**.</span></span>
    
    2.  <span data-ttu-id="3af07-130">在 **“通知”** 中，单击要为此未分配号码范围播放的通知。</span><span class="sxs-lookup"><span data-stu-id="3af07-130">In **Announcement**, click the announcement to be played for this range of unassigned numbers.</span></span>

8.  <span data-ttu-id="3af07-131">如果在上一步中单击了 **“Exchange UM”**，则在 **“自动助理电话号码”** 下，单击 **“选择”**，再单击将用于此未分配号码范围的电话号码，然后单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="3af07-131">If, in the previous step, you clicked **Exchange UM**, under **Auto Attendant phone number**, click **Select**, click the phone number to be used for this range of unassigned numbers, and then click **OK**.</span></span>

9.  <span data-ttu-id="3af07-132">单击“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3af07-132">Click **OK**.</span></span>

10. <span data-ttu-id="3af07-p106">在“未分配号码”\*\*\*\* 页上，确保未分配号码范围按照所需顺序排列。要更改号码范围在表中的位置，请在范围列表中单击一个或多个连续名称，然后单击向上箭头或向下箭头。</span><span class="sxs-lookup"><span data-stu-id="3af07-p106">On the **Unassigned Number** page, be sure that the unassigned number ranges are arranged in the order that you want. To change a range's position in the table, click one or more consecutive names in the list of ranges, and then click the up arrow or the down arrow.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3af07-135">Lync Server 从上到下搜索未分配号码表，并使用与未分配号码匹配的第一个区域。</span><span class="sxs-lookup"><span data-stu-id="3af07-135">Lync Server searches the unassigned number table from top to bottom and uses the first range that matches the unassigned number.</span></span> <span data-ttu-id="3af07-136">如果有重叠的范围并且有一个范围指定了最后的操作，请确保将该范围置于列表底部。</span><span class="sxs-lookup"><span data-stu-id="3af07-136">If you have overlapping ranges and one range specifies a last resort action, make sure that range is at the bottom of the list.</span></span>

    
    </div>

11. <span data-ttu-id="3af07-137">按照希望的顺序排列未分配号码范围后，单击“全部提交”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3af07-137">When you have the unassigned number ranges in the order that you want, click **Commit all**.</span></span>

</div>

<div>

## <a name="to-use-windows-powershell-to-configure-unassigned-phone-numbers"></a><span data-ttu-id="3af07-138">使用 Windows PowerShell 配置未分配的电话号码</span><span class="sxs-lookup"><span data-stu-id="3af07-138">To use Windows PowerShell to configure unassigned phone numbers</span></span>

1.  <span data-ttu-id="3af07-139">登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在 [Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。</span><span class="sxs-lookup"><span data-stu-id="3af07-139">Log on to the computer where Lync Server Management Shell is installed as a member of the RTCUniversalServerAdmins group or with the necessary user rights as described in [Delegate setup permissions in Lync Server 2013](lync-server-2013-delegate-setup-permissions.md).</span></span>

2.  <span data-ttu-id="3af07-140">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3af07-140">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="3af07-141">使用 **New-CsUnassignedNumber** 可创建新的未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="3af07-141">Use **New-CsUnassignedNumber** to create a new unassigned number range.</span></span> <span data-ttu-id="3af07-142">使用 **Set-CsUnassignedNumber** 可修改现有未分配号码范围。</span><span class="sxs-lookup"><span data-stu-id="3af07-142">Use **Set-CsUnassignedNumber** to modify an existing unassigned number range.</span></span>
    
    <div>
    

    > [!TIP]  
    > <span data-ttu-id="3af07-p109">如果您具有重叠的范围并希望按某个特定顺序应用这些范围，请包含 Priority 参数。优先级最高的范围将应用于呼叫。</span><span class="sxs-lookup"><span data-stu-id="3af07-p109">If you have overlapping ranges and want the ranges to be applied in a specific order, include the Priority parameter. The range with the highest priority will be applied to the call.</span></span>

    
    </div>
    
    <span data-ttu-id="3af07-145">在命令行中，执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3af07-145">At the command line, do one of the following:</span></span>
    
      - <span data-ttu-id="3af07-146">若要创建公告服务的号码范围，请运行：</span><span class="sxs-lookup"><span data-stu-id="3af07-146">To create a number range for an Announcement service, run:</span></span>
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - <span data-ttu-id="3af07-147">或者，若要创建 Exchange UM 自动助理的号码范围，请运行：</span><span class="sxs-lookup"><span data-stu-id="3af07-147">Or, to create a number range for Exchange UM Auto Attendant, run:</span></span>
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    <span data-ttu-id="3af07-148">例如：</span><span class="sxs-lookup"><span data-stu-id="3af07-148">For example:</span></span>
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    <span data-ttu-id="3af07-149">或</span><span class="sxs-lookup"><span data-stu-id="3af07-149">Or</span></span>
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    <span data-ttu-id="3af07-150">以下示例介绍如何修改现有未分配号码范围中的号码：</span><span class="sxs-lookup"><span data-stu-id="3af07-150">The following example shows how to modify the numbers in an existing unassigned number range:</span></span>
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="3af07-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3af07-151">See Also</span></span>


[<span data-ttu-id="3af07-152">在 Lync Server 2013 中删除未分配号码范围</span><span class="sxs-lookup"><span data-stu-id="3af07-152">Delete an unassigned number range in Lync Server 2013</span></span>](lync-server-2013-delete-an-unassigned-number-range.md)  


[<span data-ttu-id="3af07-153">新 CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="3af07-153">New-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsUnassignedNumber)  
[<span data-ttu-id="3af07-154">CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="3af07-154">Set-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Set-CsUnassignedNumber)  
[<span data-ttu-id="3af07-155">CsUnassignedNumber</span><span class="sxs-lookup"><span data-stu-id="3af07-155">Get-CsUnassignedNumber</span></span>](https://docs.microsoft.com/powershell/module/skype/Get-CsUnassignedNumber)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

