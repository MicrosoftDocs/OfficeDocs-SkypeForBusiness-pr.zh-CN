---
title: Lync Server 2013：创建或修改未分配号码范围
TOCTitle: 创建或修改未分配号码范围
ms:assetid: a102b226-0460-4d5c-82f9-79b8444fa958
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg412748(v=OCS.15)
ms:contentKeyID: 49313777
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或修改未分配号码范围

 

_**上一次修改主题：** 2012-11-01_

使用下列过程之一配置 通知应用程序的未分配号码范围。

> [!IMPORTANT]
> 在配置未分配号码表之前，必须已定义一个或多个通知，或已设置 Exchange 统一消息 (UM) 自动助理。


## 使用 Lync Server 控制面板配置未分配电话号码

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“语音功能”，然后单击“未分配号码”。

4.  在“未分配号码”页上，执行下列操作之一：
    
      - 若要创建新的号码范围，请单击“新建”。在“名称”中，键入此号码范围的标识名称。
        
        > [!NOTE]  
        > 新的未分配号码范围提交到数据库后，将无法更改该名称。
        
    
      - 若要修改现有号码范围，请在搜索字段中键入号码范围的全部或部分名称。在号码范围的结果列表中，单击所需的名称，再单击“编辑”，然后单击“显示详细信息”。

5.  在第一个“号码范围”字段中，键入号码范围的起始号码，在第二个“号码范围”字段中，键入该范围的结束号码。
    
    > [!NOTE]  
    > <ul><li><p>该范围的起始号码必须小于或等于该范围的结束号码。</p></li>
    > <li><p>如果号码范围的起始号码或结束号码包含分机号，那么号码范围的起始号码和结束号码都必须包含分机号，并且起始号码和结束号码的分机号必须相同。</p></li>
    > <li><p>此号码必须符合正则表达式 (tel:)?(\+)?[1-9]\d{0,17}(;ext=[1-9]\d{0,9})?。这意味着此号码可能以字符串 tel:（如果没有指定此字符串，将自动为您添加）、加号 (+) 以及一个 1 到 9 之间的数字开头。电话号码最长为 17 位数，并可以后跟分机号，格式为 ;ext= 后跟分机号。</p></li></ul>
    


6.  在“通知服务”中，执行下列操作之一：
    
      - 单击“通知”。
    
      - 单击“Exchange UM”。

7.  如果在上一步中单击了“通知”，则执行下列操作：
    
    1.  在“目标服务器的 FQDN”下，单击“选择”，再单击运行 通知应用程序的应用程序服务的服务 ID（该通知应用程序将处理此未分配号码范围的传入呼叫），然后单击“确定”。
    
    2.  在“通知”中，单击要为此未分配号码范围播放的通知。

8.  如果在上一步中单击了“Exchange UM”，则在“自动助理电话号码”下，单击“选择”，再单击将用于此未分配号码范围的电话号码，然后单击“确定”。

9.  单击“确定”。

10. 在“未分配号码”页上，确保未分配号码范围按照所需顺序排列。要更改号码范围在表中的位置，请在范围列表中单击一个或多个连续名称，然后单击向上箭头或向下箭头。
    
    > [!TIP]
    > Lync Server 从上至下搜索未分配号码表，并使用第一个匹配未分配号码的范围。如果有重叠的范围并且有一个范围指定了最后的操作，请确保将该范围置于列表底部。


11. 按照希望的顺序排列未分配号码范围后，单击“全部提交”。

## 使用 Windows PowerShell配置未分配电话号码

1.  以 RTCUniversalServerAdmins 组成员的身份或利用[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)中所述的必要用户权限登录安装了 Lync Server 命令行管理程序的计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  使用 **New-CsUnassignedNumber** 可创建新的未分配号码范围。使用 **Set-CsUnassignedNumber** 可修改现有未分配号码范围。
    
    > [!TIP]
    > 如果您具有重叠的范围并希望按某个特定顺序应用这些范围，请包含 Priority 参数。优先级最高的范围将应用于呼叫。
    
    在命令行中，执行下列操作之一：
    
      - 若要创建公告服务的号码范围，请运行：
        
            New-CsUnassignedNumber -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range> -AnnouncementName <announcement name> -AnnouncementService <FQDN or service ID of the Announcement service>
    
      - 或者，若要创建 Exchange UM 自动助理的号码范围，请运行：
        
            New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber <phone number> -Identity <unique identifier for unassigned number range> -NumberRangeStart <first number in range> -NumberRangeEnd <last number in range>
    
    例如：
    
        New-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100" -AnnouncementName "Welcome Announcement" -AnnouncementService ApplicationServer:Redmond.contoso.com
    
    或
    
        New-CsUnassignedNumber -ExUmAutoAttendantPhoneNumber "+12065551234" -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551100"
    
    以下示例介绍如何修改现有未分配号码范围中的号码：
    
        Set-CsUnassignedNumber -Identity "Unassigned range 1" -NumberRangeStart "+14255551000" -NumberRangeEnd "+14255551900"

## 另请参阅

#### 任务

[删除未分配号码范围](lync-server-2013-delete-an-unassigned-number-range.md)  

#### 其他资源

[New-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/New-CsUnassignedNumber)  
[Set-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUnassignedNumber)  
[Get-CsUnassignedNumber](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUnassignedNumber)

