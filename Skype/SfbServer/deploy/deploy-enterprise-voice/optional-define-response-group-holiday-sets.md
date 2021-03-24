---
title: " (Skype for Business) 定义响应组假日集的可选选项"
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
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: Create or modify Response Group holiday sets， in Skype for Business Server 企业语音.
ms.openlocfilehash: 3a8173964cf32c148146ffc4c501861b35bf6077
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51103678"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="7509d-103"> (Skype for Business) 定义响应组假日集的可选选项</span><span class="sxs-lookup"><span data-stu-id="7509d-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="7509d-104">Create or modify Response Group holiday sets， in Skype for Business Server 企业语音.</span><span class="sxs-lookup"><span data-stu-id="7509d-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="7509d-p101">假日设置定义响应组停止办公的日期并指定在这些日期采取的操作。假日集是指适用于响应组的假日的集合。</span><span class="sxs-lookup"><span data-stu-id="7509d-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="7509d-107">如果将某个工作流定义为托管工作流，则分配了 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的假日。</span><span class="sxs-lookup"><span data-stu-id="7509d-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="7509d-108">创建假日集</span><span class="sxs-lookup"><span data-stu-id="7509d-108">To create a holiday set</span></span>

1. <span data-ttu-id="7509d-109">以 RTCUniversalServerAdmins 组的成员或支持响应组的预定义管理角色之一的成员登录。</span><span class="sxs-lookup"><span data-stu-id="7509d-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="7509d-110">启动 Skype for Business Server命令行管理程序：单击"开始"，单击"所有程序"，单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**</span><span class="sxs-lookup"><span data-stu-id="7509d-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="7509d-111">对于要定义的每个假日，请运行：</span><span class="sxs-lookup"><span data-stu-id="7509d-111">For each holiday you want to define, run:</span></span>
    
   ```powershell
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="7509d-112">要创建包含您定义的假日的假日集，请运行：</span><span class="sxs-lookup"><span data-stu-id="7509d-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```powershell
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="7509d-113">以下示例显示一个包含两个假日的假日集：</span><span class="sxs-lookup"><span data-stu-id="7509d-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```powershell
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="7509d-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7509d-114">See also</span></span>

[<span data-ttu-id="7509d-115">在 Skype for Business 中设计和创建响应组工作流</span><span class="sxs-lookup"><span data-stu-id="7509d-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="7509d-116">New-CsRgsHoliday</span><span class="sxs-lookup"><span data-stu-id="7509d-116">New-CsRgsHoliday</span></span>](/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="7509d-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="7509d-117">New-CsRgsHolidaySet</span></span>](/powershell/module/skype/new-csrgsholidayset?view=skype-ps)