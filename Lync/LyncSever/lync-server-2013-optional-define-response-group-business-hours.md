---
title: Lync Server 2013：（可选）定义响应组工作时间
TOCTitle: （可选）定义响应组工作时间
ms:assetid: d62551b2-1847-4e1b-abe8-683b72aa94d5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205291(v=OCS.15)
ms:contentKeyID: 49314379
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# （可选）在 Lync Server 2013 中定义响应组工作时间

 

_**上一次修改主题：** 2012-11-01_

## 定义工作时间

工作时间设置定义工作流何时可以应答呼叫并指定对非工作时间的呼叫所采取的操作。响应组管理员可以使用 **New-CsRgsHoursOfBusiness** cmdlet 来创建可用于任意数目的响应组的预定义日程表。

> [!TIP]
> 创建或修改工作流时，可以指定仅适用于该工作流的自定义日程表。有关详细信息，请参阅 <a href="lync-server-2013-create-or-modify-a-hunt-group-workflow.md">在 Lync Server 2013 中创建或修改智能寻线工作流</a>或 <a href="lync-server-2013-create-or-modify-an-interactive-workflow.md">在 Lync Server 2013 中创建或修改互动工作流</a>。


> [!NOTE]  
> 如果已将某个工作流定义为托管工作流，则被分配 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的工作时间。



> [!IMPORTANT]
> 以下 cmdlet 中的参数采用 24 小时制表示（例如，20:00=8:00 P.M.）。


## 创建预定义工作时间集合

1.  以 RTCUniversalServerAdmins 组成员的身份，或支持响应组的某个预定义管理角色的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  对于要定义的每个唯一时间范围，请运行：
    
        $x = New-CsRgsTimeRange [-Name <name of time range>] -OpenTime <time when business hours begin> -CloseTime <time when business hours end>
    
    要创建使用定义的范围的工作时间集合，请运行：
    
        New-CsRgsHoursOfBusiness -Parent <service where the workflow is hosted> -Name <unique name for collection> [-MondayHours1 <first set of opening and closing times for Monday>] [-MondayHours2 <second set of opening and closing times for Monday>] [-TuesdayHours1 <first set of opening and closing times for Tuesday>] [-TuesdayHours2 <second set of opening and closing times for Tuesday>] [-WednesdayHours1 <first set of opening and closing times for Wednesday>] [-WednesdayHours2 <second set of opening and closing times for Wednesday>] [-ThursdayHours1 <first set of opening and closing times for Thursday>] [-ThursdayHours2 <second set of opening and closing times for Thursday>] [-FridayHours1 <first set of opening and closing times for Friday>] [-FridayHours2 <second set of opening and closing times for Friday>] [-SaturdayHours1 <first set of opening and closing times for Saturday>] [-SaturdayHours2 <second set of opening and closing times for Saturday>] [-SundayHours1 <first set of opening and closing times for Sunday>] [-SundayHours2 <second set of opening and closing times for Sunday>]
    
    以下示例将工作时间指定为工作日上午 9:00 到下午 5:00，周六上午 8:00 到 10:00 以及下午 2:00 到 6:00，周日全天休息：
    
        $a = NewRgsTimeRange -Name "Weekday Hours" -OpenTime "9:00" -CloseTime "17:00"
        $b = NewRgsTimeRange -Name "Saturday Morning Hours" -OpenTime "8:00" -CloseTime "10:00" 
        $c = NewRgsTimeRange -Name "Saturday Afternoon Hours" -OpenTime "14:00" -CloseTime "18:00" 
        New-CsRgsHoursOfBusiness -Parent "ApplicationServer:Redmond.contoso.com" -Name "Help Desk Business Hours" -MondayHours1 $a -TuesdayHours1 $a -WednesdayHours1 $a -ThursdayHours1 $a -FridayHours1 $a -SaturdayHours1 $b -SaturdayHours2 $c

## 另请参阅

#### 概念

[在 Lync Server 2013 中创建或修改智能寻线工作流](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[在 Lync Server 2013 中创建或修改互动工作流](lync-server-2013-create-or-modify-an-interactive-workflow.md)  

#### 其他资源

[New-CsRgsTimeRange](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsTimeRange)  
[New-CsRgsHoursOfBusiness](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsRgsHoursOfBusiness)

