---
title: Lync Server 2013：创建或修改呼叫寄存通道范围
TOCTitle: 创建或修改呼叫寄存通道范围
ms:assetid: 549ec118-eee5-4333-9416-80929ec057e0
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398361(v=OCS.15)
ms:contentKeyID: 49312872
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改呼叫寄存通道范围

 

_**上一次修改主题：** 2012-11-01_

使用下列过程之一可创建或修改呼叫寄存通道范围。

## 使用 Lync Server 控制面板可创建或修改寄存呼叫的号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音功能”，然后单击“呼叫寄存”。

4.  在“呼叫寄存”页上，执行下列操作之一：
    
      - 若要创建新的通道范围，请单击“新建”。在“名称”中，键入此号码范围的标识名称。
        
        > [!NOTE]  
		> 在将通道范围提交到数据库后，将无法更改该名称。
        
    
      - 若要修改现有通道范围，请在搜索字段中键入通道范围的全部或部分名称。在通道的结果列表中，单击所需的通道，再单击“编辑”，然后单击“显示详细信息”。

5.  在第一个“号码范围”字段中，键入此呼叫寄存通道的分机范围中的起始号码，在第二个“号码范围”字段中，键入该范围的结束号码。
    
    > [!NOTE]  
    > <ul><li><p>该范围的起始号码必须小于或等于该范围的结束号码。</p></li>
    > <li><p>该范围的起始号码值的长度必须与该范围结束号码值的长度相同。</p></li>
    > <li><p>通道范围必须是唯一的。该范围不能与其他任何范围重叠。</p></li>
    > <li><p>如果通道范围以字符 * 或 # 开头，则该范围必须大于 100。</p></li>
    > <li><p>有效值：必须与正则表达式字符串 ([\*|#]?[1-9]\d{0,7})|([1-9]\d{0,8}) 匹配。这意味着该值必须是一个以字符 * 或 # 或者 1 到 9 之间的一个数字开头的字符串（第一个字符不能为零）。如果第一个字符是 * 或 #，则下一个字符必须是 1 到 9 之间的一个数字（不能为零）。后续字符可以是 0 到 9 之间的任何数字，最多还可以包括 7 个其他字符（例如，“#6000”、“*92000”、“*95551212”和“915551212”）。如果第一个字符不是 * 或 #，则必须是 1 到 9 之间的数字（不能为零），后跟最多八个字符，其中每个字符都是介于 0 到 9 之间的数字（例如，“915551212”、“41212”、“300”）。</p></li>
    > <li><p>每个池不应包含 50,000 个以上的通道。每个通道范围包含的通道数通常不超过 100，但是该数目可以更大，只要不超过 10,000。例如，不要将起始号码指定为“7000000”并将结束号码指定为“8000000”，而考虑将起始号码指定为“7000000”并将结束号码指定为“7000100”。</p></li></ul>
    


6.  在“目标服务器的 FQDN”中，单击承载 呼叫寄存应用程序的应用程序服务的完全限定域名 (FQDN) 或服务 ID。寄存在由通道范围中的起始号码和结束号码指定的范围内的号码的所有呼叫都将路由到此服务器或池。

7.  单击“提交”。

## 使用 Windows PowerShell可创建或修改寄存呼叫的号码范围

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  使用 **New-CsCallParkOrbit** 可创建通道号码的新范围。使用 **Set-CsCallParkOrbit** 可修改通道号码的现有范围。
    
    在该命令行处，运行：
    
        New-CsCallParkOrbit -Identity <name of orbit range> -NumberRangeStart <first number in orbit range> -NumberRangeEnd <last number in orbit range> -CallParkService <FQDN or service ID of the Application service that hosts the Call Park application>
    
    例如：
    
        New-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 100 -NumberRangeEnd 199 -CallParkService redmond-applicationserver-1
    
    以下示例说明如何修改现有通道范围中的号码。
    
        Set-CsCallParkOrbit -Identity "Redmond orbit 1" -NumberRangeStart 500 -NumberRangeEnd 699

## 另请参阅

#### 任务

[在 Lync Server 2013 中删除呼叫寄存通道范围](lync-server-2013-delete-a-call-park-orbit-range.md)  

#### 其他资源

[New-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsCallParkOrbit)  
[Set-CsCallParkOrbit](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCallParkOrbit)

