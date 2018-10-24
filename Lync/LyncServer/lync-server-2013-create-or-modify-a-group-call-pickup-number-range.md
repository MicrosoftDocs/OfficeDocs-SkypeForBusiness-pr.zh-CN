---
title: 创建或修改组内呼叫应答号码范围
TOCTitle: 创建或修改组内呼叫应答号码范围
ms:assetid: 4b442b98-df6b-4e50-8254-b3be9cde21dd
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ945627(v=OCS.15)
ms:contentKeyID: 52061009
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 创建或修改组内呼叫应答号码范围

 

_**上一次修改主题：** 2013-01-30_

使用下面的过程在呼叫寄存轨道表中创建或修改呼叫应答组号码范围。

> [!NOTE]  
> 您必须使用 Lync Server 命令行管理程序在呼叫寄存轨道表中创建、修改、移除和查看组内呼叫应答号码范围。组内呼叫应答号码范围在 Lync Server 控制面板中不可用。



> [!IMPORTANT]
> 必须为呼叫应答组号码范围分配 GroupPickup 类型。仅当为用户分配的组号码是 GroupPickup 类型时，才为用户启用组内呼叫应答。


呼叫应答组号码范围必须符合以下规则：

  - 该范围的起始号码必须小于或等于该范围的结束号码。

  - 该范围的起始号码值的长度必须与该范围结束号码值的长度相同。

  - 号码范围必须是唯一的。该范围不能与其他任何范围重叠。

  - 如果号码范围以字符 \* 或 \# 开头，则该范围必须大于 100。

  - 有效值：必须与正则表达式字符串 (\[\\\*|\#\]?\[1-9\]\\d{0,7})|(\[1-9\]\\d{0,8}) 匹配。这意味着该值必须是一个以字符 \* 或 \# 或者 1 到 9 之间的一个数字开头的字符串（第一个字符不能为零）。如果第一个字符是 \* 或 \#，则下一个字符必须是 1 到 9 之间的一个数字（不能为零）。后续字符可以是 0 到 9 之间的任何数字，最多还可以包括 7 个其他字符（例如，“\#6000”、“\*92000”、“\*95551212”和“915551212”）。如果第一个字符不是 \* 或 \#，则必须是 1 到 9 之间的数字（不能为零），后跟最多八个字符，其中每个字符都是介于 0 到 9 之间的数字（例如，“915551212”、“41212”、“300”）。

## 创建或修改呼叫应答组范围

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  使用 **New-CsCallParkOrbit** 创建呼叫应答组号码的新范围。使用 **Set-CsCallParkOrbit** 修改呼叫应答号码的现有范围。
    
    在该命令行处，运行：
    
        New-CsCallParkOrbit -Identity <name of call pickup group range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application> -Type GroupPickup
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond call pickup" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1 -Type GroupPickup
    
    下面的示例演示如何将号码范围从呼叫寄存轨道更改为呼叫应答组。
    
        Set-CsCallParkOrbit -Identity "Redmond call pickup" -Type GroupPickup
    
    > [!IMPORTANT]
    > 仅在您最初指定了错误的类型并且组范围尚未使用时，才能使用此 cmdlet 更改分配到号码范围的类型。如果您将号码范围从 CallPark 更改为 GroupPickup 或相反，并且号码范围已在使用中，则呼叫寄存或组内呼叫应答将不再对该号码范围起作用。例如，如果您将号码范围从 CallPark 更改为 GroupPick，则呼叫寄存应用程序将无法再使用该轨道范围来寄存呼叫。


## 另请参阅

#### 任务

[在 Lync Server 2013 中删除呼叫寄存通道范围](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### 其他资源

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)

