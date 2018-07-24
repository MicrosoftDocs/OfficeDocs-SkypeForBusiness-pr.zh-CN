---
title: （可选）Skype for Business 中定义响应组工作时间
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
description: 创建或修改工作时间，业务 Server 企业语音的 Skype 的响应组。
ms.openlocfilehash: 3044d649bed946e14ff0459491c5df709d88c7f7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2018
ms.locfileid: "20965644"
---
# <a name="optional-define-response-group-business-hours-in-skype-for-business"></a>（可选）Skype for Business 中定义响应组工作时间 
 
创建或修改工作时间，业务 Server 企业语音的 Skype 的响应组。
  
## <a name="defining-business-hours"></a>定义工作时间

工作时间设置定义工作流何时可以应答呼叫并指定对非工作时间的呼叫所采取的操作。 响应组管理员可以使用**新建 CsRgsHoursOfBusiness** cmdlet 以创建可用于任意数量的响应组的预定义的计划。
  
> [!TIP]
> 创建或修改工作流时，可以指定仅适用于该工作流的自定义日程表。 有关详细信息，请参阅[设计和创建响应组工作流中的业务的 Skype](designing-and-creating-response-group-workflows.md)。 
  
> [!NOTE]
> 如果已将某个工作流定义为托管工作流，则被分配 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的工作时间。 
  
> [!IMPORTANT]
> 以下 cmdlet 中的参数采用 24 小时制表示（例如，20:00=8:00 P.M.）。 
  
### <a name="to-create-a-predefined-business-hours-collection"></a>创建预定义工作时间集合

1. 以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。
    
2. 启动 Skype for Business Server 命令行管理程序：依次单击“**开始**”、“**所有程序**”和“**Skype for Business 2015**”，然后单击“**Skype for Business Server 命令行管理程序**”。
    
3. 对于要定义的每个唯一时间范围，请运行：
    
   ```
   $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
   ```

    要创建使用定义的范围的工作时间集合，请运行：
    
   ```
   New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
   ```

    以下示例将工作时间指定为工作日上午 9:00 到下午 5:00，周六上午 8:00 到 10:00 以及下午 2:00 到 6:00，周日全天休息：
    
   ```
   $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
   $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
   $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
   New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c
   ```

## <a name="see-also"></a>另请参阅

[New-csrgstimerange](https://docs.microsoft.com/powershell/module/skype/new-csrgstimerange?view=skype-ps)
  
[新 CsRgsHoursOfBusiness](https://docs.microsoft.com/powershell/module/skype/new-csrgshoursofbusiness?view=skype-ps)