---
title: Lync Server 2013： (可选) 定义响应组假日集
description: Lync Server 2013： (可选) 定义响应组假日集。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Define Response Group holiday sets
ms:assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688063(v=OCS.15)
ms:contentKeyID: 49733657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d7ba735cc62efb9d5553c8bd6aad1aa9484f70f4
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48565758"
---
# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a><span data-ttu-id="c56dd-103"> (可选) 在 Lync Server 2013 中定义响应组假日集</span><span class="sxs-lookup"><span data-stu-id="c56dd-103">(Optional) Define Response Group holiday sets in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c56dd-104">_**上次修改的主题：** 2014-02-07_</span><span class="sxs-lookup"><span data-stu-id="c56dd-104">_**Topic Last Modified:** 2014-02-07_</span></span>

<span data-ttu-id="c56dd-p101">假日设置定义响应组停止办公的日期并指定在这些日期采取的操作。假日集是指适用于响应组的假日的集合。</span><span class="sxs-lookup"><span data-stu-id="c56dd-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="c56dd-107">如果将某个工作流定义为托管工作流，则分配了 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的假日。</span><span class="sxs-lookup"><span data-stu-id="c56dd-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span>



</div>

<div>

## <a name="to-create-a-holiday-set"></a><span data-ttu-id="c56dd-108">创建假日集</span><span class="sxs-lookup"><span data-stu-id="c56dd-108">To create a holiday set</span></span>

1.  <span data-ttu-id="c56dd-109">以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="c56dd-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>

2.  <span data-ttu-id="c56dd-110">启动 Lync Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\*、“Microsoft Lync Server 2013”\*\*\*\* 和“Lync Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c56dd-110">Start the Lync Server Management Shell: Click **Start**, click **All Programs**, click **Microsoft Lync Server 2013**, and then click **Lync Server Management Shell**.</span></span>

3.  <span data-ttu-id="c56dd-111">对于要定义的每个假日，请运行：</span><span class="sxs-lookup"><span data-stu-id="c56dd-111">For each holiday you want to define, run:</span></span>
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    <span data-ttu-id="c56dd-112">要创建包含您定义的假日的假日集，请运行：</span><span class="sxs-lookup"><span data-stu-id="c56dd-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    <span data-ttu-id="c56dd-113">以下示例显示一个包含两个假日的假日集：</span><span class="sxs-lookup"><span data-stu-id="c56dd-113">The following example shows a holiday set that includes two holidays:</span></span>
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="c56dd-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c56dd-114">See Also</span></span>


[<span data-ttu-id="c56dd-115">在 Lync Server 2013 中创建或修改智能寻线工作流</span><span class="sxs-lookup"><span data-stu-id="c56dd-115">Create or modify a hunt group workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[<span data-ttu-id="c56dd-116">在 Lync Server 2013 中创建或修改交互式工作流</span><span class="sxs-lookup"><span data-stu-id="c56dd-116">Create or modify an interactive workflow in Lync Server 2013</span></span>](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[<span data-ttu-id="c56dd-117">新 CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="c56dd-117">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[<span data-ttu-id="c56dd-118">新 CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="c56dd-118">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

