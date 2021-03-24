---
title: " (Skype for Business) 定义响应组工作时间的可选选项"
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
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: Create or modify Response Group business hours， in Skype for Business Server 企业语音.
ms.openlocfilehash: d4a8101749e7fde06fc4c3d88ab343eb6e4d0f1d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103668"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a><span data-ttu-id="e9181-103"> (Skype for Business) 定义响应组工作时间的可选选项</span><span class="sxs-lookup"><span data-stu-id="e9181-103">(Optional) Define Response Group business hours in Skype for Business</span></span> 
 
<span data-ttu-id="e9181-104">Create or modify Response Group business hours， in Skype for Business Server 企业语音.</span><span class="sxs-lookup"><span data-stu-id="e9181-104">Create or modify Response Group business hours, in Skype for Business Server Enterprise Voice.</span></span>
  
## <a name="defining-business-hours"></a><span data-ttu-id="e9181-105">定义工作时间</span><span class="sxs-lookup"><span data-stu-id="e9181-105">Defining Business Hours</span></span>

<span data-ttu-id="e9181-106">工作时间设置定义工作流何时可以应答呼叫并指定对非工作时间的呼叫所采取的操作。</span><span class="sxs-lookup"><span data-stu-id="e9181-106">Business hour settings define when the workflow is available to answer calls and specify the actions to take for calls outside of business hours.</span></span> <span data-ttu-id="e9181-107">响应组管理员可以使用 **New-CsRgsHoursOfBusiness** cmdlet 来创建可用于任意数目的响应组的预定义日程表。</span><span class="sxs-lookup"><span data-stu-id="e9181-107">Response Group administrators can use the **New-CsRgsHoursOfBusiness** cmdlet to create predefined schedules that you can use for any number of response groups.</span></span>
  
> [!TIP]
> <span data-ttu-id="e9181-108">创建或修改工作流时，可以指定仅适用于该工作流的自定义日程表。</span><span class="sxs-lookup"><span data-stu-id="e9181-108">When you create or modify a workflow, you can specify a custom schedule that applies only to that workflow.</span></span> <span data-ttu-id="e9181-109">有关详细信息，请参阅[Dinging and creating response group workflows in Skype for Business。](designing-and-creating-response-group-workflows.md)</span><span class="sxs-lookup"><span data-stu-id="e9181-109">For details, see [Designing and creating response group workflows in Skype for Business](designing-and-creating-response-group-workflows.md).</span></span> 
  
> [!NOTE]
> <span data-ttu-id="e9181-110">如果已将某个工作流定义为托管工作流，则被分配 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的工作时间。</span><span class="sxs-lookup"><span data-stu-id="e9181-110">If a workflow is defined as a Managed workflow, then any user who is assigned the CsResponseGroupManager role can set and modify custom business hours for workflows that they manage.</span></span> 
  
> [!IMPORTANT]
> <span data-ttu-id="e9181-111">以下 cmdlet 中的参数采用 24 小时制表示（例如，20:00=8:00 P.M.）。</span><span class="sxs-lookup"><span data-stu-id="e9181-111">Use 24-hour notation for the parameters in the following cmdlets (for example, 20:00=8:00 P.M.).</span></span> 
  
### <a name="to-create-a-predefined-business-hours-collection"></a><span data-ttu-id="e9181-112">创建预定义工作时间集合</span><span class="sxs-lookup"><span data-stu-id="e9181-112">To create a predefined business hours collection</span></span>

1. <span data-ttu-id="e9181-113">以 RTCUniversalServerAdmins 组的成员或支持响应组的预定义管理角色之一的成员登录。</span><span class="sxs-lookup"><span data-stu-id="e9181-113">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="e9181-114">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="e9181-114">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="e9181-115">对于要定义的每个唯一时间范围，请运行：</span><span class="sxs-lookup"><span data-stu-id="e9181-115">For each unique range of hours you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    <span data-ttu-id="e9181-116">要创建使用定义的范围的工作时间集合，请运行：</span><span class="sxs-lookup"><span data-stu-id="e9181-116">To create the business hours collection that uses the ranges you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    <span data-ttu-id="e9181-p103">以下示例将工作时间指定为工作日上午 9:00 到下午 5:00，周六上午 8:00 到 10:00 以及下午 2:00 到 6:00，周日全天休息：</span><span class="sxs-lookup"><span data-stu-id="e9181-p103">The following example specifies business hours of 9:00 A.M. to 5:00 P.M. for weekdays, 8:00 A.M. to 10:00 A.M. and again from 2:00 P.M. to 6:00 P.M. for Saturdays, and no business hours for Sundays:</span></span>
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a><span data-ttu-id="e9181-124">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e9181-124">See also</span></span>

[<span data-ttu-id="e9181-125">New-CsRgsTimeRange</span><span class="sxs-lookup"><span data-stu-id="e9181-125">New-CsRgsTimeRange</span></span>](/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[<span data-ttu-id="e9181-126">New-CsRgsHoursOfBusiness</span><span class="sxs-lookup"><span data-stu-id="e9181-126">New-CsRgsHoursOfBusiness</span></span>](/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)