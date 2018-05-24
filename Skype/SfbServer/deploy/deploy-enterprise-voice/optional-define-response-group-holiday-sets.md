---
title: （可选）在 Skype for Business 2015 中定义响应组假日集
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 56c37b3b-6517-49b9-86b7-ae48cc349119
description: 创建或修改业务 Server 企业语音的 Skype 中的响应组假日集。
ms.openlocfilehash: 0ee6ffa0afdff32096845d7450fa92ff6e720022
ms.sourcegitcommit: 68e68c96c18d854afc0158920e6d9d738f276d91
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/24/2018
---
# <a name="optional-define-response-group-holiday-sets-in-skype-for-business-2015"></a>（可选）在 Skype for Business 2015 中定义响应组假日集
 
创建或修改业务 Server 企业语音的 Skype 中的响应组假日集。
  
假日设置定义响应组停止办公的日期并指定在这些日期采取的操作。假日集是指适用于响应组的假日的集合。
  
> [!NOTE]
> 如果将某个工作流定义为托管工作流，则分配了 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的假日。 
  
### <a name="to-create-a-holiday-set"></a>创建假日集

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 对于要定义的每个假日，请运行：
    
   ```
   $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
   ```

    要创建包含您定义的假日的假日集，请运行：
    
   ```
   New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
   ```

    以下示例显示一个包含两个假日的假日集：
    
   ```
   $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2018 12:00 AM" -EndDate "1/2/2018 12:00 AM" 
   $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2018 12:00 AM" -EndDate "7/5/2018 12:00 AM" 
   New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com" -Name "2018 Holidays" -HolidayList ($a, $b)
   ```

## <a name="see-also"></a>另请参阅

[设计和创建响应组工作流中的业务 2015 Skype](designing-and-creating-response-group-workflows.md)

[New-csrgsholiday](https://docs.microsoft.com/powershell/module/skype/new-csrgsholiday?view=skype-ps)

[New-csrgsholidayset](https://docs.microsoft.com/powershell/module/skype/new-csrgsholidayset?view=skype-ps)
