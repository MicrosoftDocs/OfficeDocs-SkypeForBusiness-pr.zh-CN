---
title: Lync Server 2013：（可选）定义响应组假日集
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
ms.openlocfilehash: 1f5ae5c10bda4383917a4f3a27ef8dffec2abbef
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153432"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-define-response-group-holiday-sets-in-lync-server-2013"></a>Optional在 Lync Server 2013 中定义响应组假日集

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-02-07_

假日设置定义响应组停止办公的日期并指定在这些日期采取的操作。假日集是指适用于响应组的假日的集合。

<div>


> [!NOTE]  
> 如果将某个工作流定义为托管工作流，则分配了 CsResponseGroupManager 角色的任何用户均可设置和修改其管理的工作流的假日。



</div>

<div>

## <a name="to-create-a-holiday-set"></a>创建假日集

1.  以 RTCUniversalServerAdmins 组成员的身份登录，或以支持响应组的预定义管理角色之一的成员身份登录。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  对于要定义的每个假日，请运行：
    
        $x = New-CsRgsHoliday [-Name <holiday name>] -StartDate <starting date of holiday> -EndDate <ending date of holiday>
    
    要创建包含您定义的假日的假日集，请运行：
    
        New-CsRgsHolidaySet -Parent <service where the workflow is hosted> -Name <unique name for holiday set> -HolidayList <one or more holidays to be included in the holiday set>
    
    以下示例显示一个包含两个假日的假日集：
    
        $a = New-CsRgsHoliday -Name "New Year's Day" -StartDate "1/1/2013 12:00 AM" -EndDate "1/1/2013 12:00 AM" 
        $b = New-CsRgsHoliday -Name "Independence Day" -StartDate "7/4/2013 12:00 AM" -EndDate "7/5/2013 12:00 AM" 
        New-CsRgsHolidaySet -Parent "ApplicationServer:Redmond.contoso.com -Name "2013 Holidays" -HolidayList ($a, $b)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改智能寻线工作流](lync-server-2013-create-or-modify-a-hunt-group-workflow.md)  
[在 Lync Server 2013 中创建或修改交互式工作流](lync-server-2013-create-or-modify-an-interactive-workflow.md)  


[新 CsRgsHoliday](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHoliday)  
[新 CsRgsHolidaySet](https://docs.microsoft.com/powershell/module/skype/New-CsRgsHolidaySet)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

