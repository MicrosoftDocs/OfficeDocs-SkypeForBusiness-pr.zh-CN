---
title: （可选）Skype for Business 中定义响应组假日集
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 创建或修改业务 Server 企业语音的 Skype 中的响应组假日集。
ms.openlocfilehash: d78eaeee9b447dfd0c9f4f7250b6f34aee298594
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "33894703"
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business"></a><span data-ttu-id="71aaa-103">（可选）Skype for Business 中定义响应组假日集</span><span class="sxs-lookup"><span data-stu-id="71aaa-103">(Optional) Define Response Group holiday sets in Skype for Business</span></span>
 
<span data-ttu-id="71aaa-104">创建或修改业务 Server 企业语音的 Skype 中的响应组假日集。</span><span class="sxs-lookup"><span data-stu-id="71aaa-104">Create or modify Response Group holiday sets, in Skype for Business Server Enterprise Voice.</span></span>
  
<span data-ttu-id="71aaa-p101">假日设置定义响应组停止办公的日期并指定在这些日期采取的操作。假日集是指适用于响应组的假日的集合。</span><span class="sxs-lookup"><span data-stu-id="71aaa-p101">Holiday settings define the days that a response group is closed for business and specify the action to take on those days. A holiday set is the collection of holidays that apply to a response group.</span></span>
  
> [!NOTE]
> <span data-ttu-id="71aaa-107">如果将某个工作流定义为托管工作流，则分配了 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的假日。</span><span class="sxs-lookup"><span data-stu-id="71aaa-107">If a workflow is defined as a Managed workflow, then any user is assigned the CsResponseGroupManager role can set and modify holidays for workflows that they manage.</span></span> 
  
### <a name="to-create-a-holiday-set"></a><span data-ttu-id="71aaa-108">创建假日集</span><span class="sxs-lookup"><span data-stu-id="71aaa-108">To create a holiday set</span></span>

1. <span data-ttu-id="71aaa-109">以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。</span><span class="sxs-lookup"><span data-stu-id="71aaa-109">Log on as a member of the RTCUniversalServerAdmins group, or as a member of one of the predefined administrative roles that support Response Group.</span></span>
    
2. <span data-ttu-id="71aaa-110">启动 Skype for Business Server 命令行管理程序：依次单击“开始”\*\*\*\*、“所有程序”\*\*\*\* 和“Skype for Business 2015”\*\*\*\*，然后单击“Skype for Business Server 命令行管理程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="71aaa-110">Start the Skype for Business Server Management Shell: Click **Start**, click **All Programs**, click **Skype for Business 2015**, and then click **Skype for Business Server Management Shell**.</span></span>
    
3. <span data-ttu-id="71aaa-111">对于要定义的每个假日，请运行：</span><span class="sxs-lookup"><span data-stu-id="71aaa-111">For each holiday you want to define, run:</span></span>
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    <span data-ttu-id="71aaa-112">要创建包含您定义的假日的假日集，请运行：</span><span class="sxs-lookup"><span data-stu-id="71aaa-112">To create the holiday set that contains the holidays you defined, run:</span></span>
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    <span data-ttu-id="71aaa-113">以下示例显示一个包含两个假日的假日集：</span><span class="sxs-lookup"><span data-stu-id="71aaa-113">The following example shows a holiday set that includes two holidays:</span></span>
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a><span data-ttu-id="71aaa-114">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71aaa-114">See also</span></span>

[<span data-ttu-id="71aaa-115">设计和 Skype for Business 中创建响应组工作流</span><span class="sxs-lookup"><span data-stu-id="71aaa-115">Designing and creating response group workflows in Skype for Business</span></span>](designing-and-creating-response-group-workflows.md)

[<span data-ttu-id="71aaa-116">New-csrgsholiday</span><span class="sxs-lookup"><span data-stu-id="71aaa-116">New-CsRgsHoliday</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[<span data-ttu-id="71aaa-117">New-CsRgsHolidaySet</span><span class="sxs-lookup"><span data-stu-id="71aaa-117">New-CsRgsHolidaySet</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
