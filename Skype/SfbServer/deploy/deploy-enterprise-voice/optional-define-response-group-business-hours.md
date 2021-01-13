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
description: 在 Skype for Business Server 服务中创建或修改响应组企业语音。
ms.openlocfilehash: dcd2f7174a75eb68ef8d35759a1e454ede976bde
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2021
ms.locfileid: "49830992"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a> (Skype for Business) 定义响应组工作时间的可选选项 
 
在 Skype for Business Server 服务中创建或修改响应组企业语音。
  
## <a name="defining-business-hours"></a>定义工作时间

工作时间设置定义工作流何时可以应答呼叫并指定对非工作时间的呼叫所采取的操作。 响应组管理员可以使用 **New-CsRgsHoursOfBusiness** cmdlet 来创建可用于任意数目的响应组的预定义日程表。
  
> [!TIP]
> 创建或修改工作流时，可以指定仅适用于该工作流的自定义日程表。 有关详细信息，请参阅在 Skype for Business 中 [设计和创建响应组工作流](designing-and-creating-response-group-workflows.md)。 
  
> [!NOTE]
> 如果已将某个工作流定义为托管工作流，则被分配 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的工作时间。 
  
> [!IMPORTANT]
> 以下 cmdlet 中的参数采用 24 小时制表示（例如，20:00=8:00 P.M.）。 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>创建预定义工作时间集合

1. 以 RTCUniversalServerAdmins 组的成员或支持响应组的预定义管理角色之一的成员登录。
    
2. 启动 Skype for Business Server命令行管理程序：单击"开始"，**单击"所有** 程序"，再单击 **"Skype for Business 2015"，** 然后单击 **"Skype for Business Server 命令行管理程序"。**
    
3. 对于要定义的每个唯一时间范围，请运行：
    
   ```powershell
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    要创建使用定义的范围的工作时间集合，请运行：
    
   ```powershell
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    以下示例将工作时间指定为工作日上午 9:00 到下午 5:00，周六上午 8:00 到 10:00 以及下午 2:00 到 6:00，周日全天休息：
    
   ```powershell
   $a = New-CSRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = New-CSRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = New-CSRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>另请参阅

[New-CsRgsTimeRange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)
