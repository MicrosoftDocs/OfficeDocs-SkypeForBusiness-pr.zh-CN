---
title: Lync Server 2013：创建或修改组内呼叫应答号码范围
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or modify a Group Call Pickup number range
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ945627(v=OCS.15)
ms:contentKeyID: 51541472
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d215fe6959b169ec5f092757174d105a75a5402a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42145521"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>在 Lync Server 2013 中创建或修改组内呼叫装货号码范围

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-01-30_

使用以下过程可在呼叫寄存通道表中创建或修改呼叫应答组号码范围。

<div>


> [!NOTE]  
> 必须使用 Lync Server 命令行管理程序在呼叫寄存通道表中创建、修改、删除和查看组内呼叫应答号码范围。 组内呼叫应答号码范围在 Lync Server 控制面板中不可用。



</div>

<div>


> [!IMPORTANT]  
> 必须为呼叫应答组号码范围分配一种类型的 GroupPickup。 仅当用户分配的组编号为类型 GroupPickup 时，才会为其启用组呼叫应答。



</div>

呼叫应答组号码范围必须符合以下规则：

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

  - 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

  - 如果数字范围以字符\*或\#开头，则该范围必须大于100。

  - 有效值：必须与正则表达式字符串（\[\\\*|\#\]？\[1-9\]\\d{0,7}） |（\[1-9\]\\d{0,8}）。 这意味着值必须是以字符\*或\#数字1到9开头的字符串（第一个字符不能为零）。 如果第一个字符是\*或\#，则以下字符必须是1到9之间的数字（不能为零）。 后续字符可以是0到9之间的任何数字，最多七个其他字符（\#例如，"6000\*"、"92000\*"、"95551212" 和 "915551212"）。 如果第一个字符不\*是或\#，则第一个字符必须是数字1到9（不能为零），后跟八个字符，每个字符的数字0到9（例如，"915551212"，"41212"，"300"）。

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>创建或修改呼叫装货组范围

1.  登录到安装了 Lync Server 命令行管理程序的计算机，作为 RTCUniversalServerAdmins 组的成员或具有必要的用户权限（如在[Lync Server 2013 中委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述）。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  使用**CsCallParkOrbit**创建一个新的呼叫应答组号码范围。 使用**CsCallParkOrbit**可修改现有的呼叫装货号码范围。
    
    在命令行中运行：
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    下面的示例演示如何将号码范围从呼叫寄存轨道式更改为呼叫应答组。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 仅当最初指定了不正确的类型且组范围尚未使用时，才能使用此 cmdlet 更改分配给号码范围的类型。 如果将号码范围从 CallPark 更改为 GroupPickup，反之亦然，而号码范围已在使用中，则呼叫寄存或 Group Call Pickup 将停止对该号码范围的工作。 例如，如果将号码范围从 CallPark 更改为 GroupPick，则呼叫寄存应用程序无法再将该范围的轨道式用于寄存呼叫。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除呼叫寄存通道范围](lync-server-2013-delete-a-call-park-orbit-range.md)  


[新 CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

