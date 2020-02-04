---
title: Lync Server 2013：创建或修改组呼叫装货号码范围
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
ms.openlocfilehash: d5a644cb6008976894c88de570aa9cb6530e10c3
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758066"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-modify-a-group-call-pickup-number-range-in-lync-server-2013"></a>Create or modify a Group Call Pickup number range in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-01-30_

使用下面的过程在呼叫寄存轨道表中创建或修改呼叫应答组号码范围。

<div>


> [!NOTE]  
> 您必须使用 Lync Server Management Shell 在 "呼叫公园轨道" 表中创建、修改、删除和查看组呼叫的装货号码范围。 组呼叫装货号码范围在 Lync Server 控制面板中不可用。



</div>

<div>


> [!IMPORTANT]  
> 必须为呼叫装货组号码范围分配一种类型的 GroupPickup。 仅当用户分配的组编号为 "类型 GroupPickup" 时，才启用组呼叫装货。



</div>

呼叫应答组号码范围必须符合以下规则：

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

  - 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

  - 如果数字范围以字符\*开头\#，则范围必须大于100。

  - 有效值：必须与正则表达式字符串（\[\\\*|\#\]？\[1-9\]\\d{0,7}） |（\[1-9\]\\d{0,8}）。 这意味着该值必须是以字符\*或\#数字1到9开头的字符串（第一个字符不能为零）。 如果第一个字符是\*或\#，则以下字符必须是1到9的数字（不能为零）。 后续字符可以是0到9的任何数字，最多可有7个附加字符\#（例如 "6000\*"、"92000\*"、"95551212" 和 "915551212"）。 如果第一个字符不\*是或\#，则第一个字符必须是数字1到9（不能为零），后跟八个字符，每个字符都是0到9的数字（例如，"915551212"、"41212"、"300"）。

<div>

## <a name="to-create-or-modify-a-call-pickup-group-range"></a>创建或修改呼叫应答组范围

1.  以 RTCUniversalServerAdmins 组成员的身份或必要的用户权限登录到安装了 Lync Server 管理外壳的计算机，如在[Lync Server 2013 中的 "委派设置权限](lync-server-2013-delegate-setup-permissions.md)" 中所述。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  使用 **New-CsCallParkOrbit** 创建呼叫应答组号码的新范围。 使用 **Set-CsCallParkOrbit** 修改呼叫应答号码的现有范围。
    
    在命令行中运行：
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    下面的示例演示如何将号码范围从呼叫寄存轨道更改为呼叫应答组。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    <div>
    

    > [!IMPORTANT]  
    > 仅在你最初指定了错误的类型并且组范围尚未使用时，才能使用此 cmdlet 更改分配到号码范围的类型。 如果你将号码范围从 CallPark 更改为 GroupPickup 或相反，并且号码范围已在使用中，则呼叫寄存或组内呼叫应答将不再对该号码范围起作用。 例如，如果将数字范围从 CallPark 更改为 GroupPick，则调用寄存应用程序无法再将该范围的轨道式转到寄存通话。

    
    </div>

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中删除呼叫寄存轨道范围](lync-server-2013-delete-a-call-park-orbit-range.md)  


[新-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/powershell/module/skype/Set-CsCallParkOrbit)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

