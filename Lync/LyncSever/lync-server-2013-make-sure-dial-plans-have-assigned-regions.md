---
title: 'Lync Server 2013：确保已为拨号计划分配区域  '
TOCTitle: '确保已为拨号计划分配区域  '
ms:assetid: 3da3a907-0dbf-4440-b12f-370f94dd4c17
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg425903(v=OCS.15)
ms:contentKeyID: 49312593
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中确保已为拨号计划分配区域

 

_**上一次修改主题：** 2010-11-02_

用于电话拨入式会议的拨号计划需要指定一个“电话拨入式会议区域”来将电话拨入式会议访问号码与相应的拨号计划相关联。设置拨号计划时，指定应用于拨号计划的电话拨入式会议区域。然后，在创建电话拨入式访问号码时，选择将访问号码与相应拨号计划相关联的区域。

因为为所有拨号计划指定区域非常重要，我们建议您使用此过程验证是否所有拨号计划均有区域。此步骤是可选的。

使用 **Get-CsDialPlan** cmdlet 验证是否为所有电话拨入式会议拨号计划设置了区域。如果拨号计划中缺少区域，可使用 **Set-CsDialPlan** cmdlet 设置区域。还可使用 Lync Server 控制面板更新现有拨号计划中的区域。有关使用 Lync Server 控制面板的详细信息，请参阅 [在 Lync Server 2013 中修改拨号计划](lync-server-2013-modify-a-dial-plan.md)。

## 验证拨号计划是否设置了 region 属性

1.  以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator** 、 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialPlan [-Identity <Identifier of the dial plans to be retrieved>]
    
    例如：
    
        Get-CsDialPlan
    
    在此例中，返回为组织配置的所有拨号计划。

4.  查看返回的拨号计划，标识缺少电话拨入式会议区域的任何拨号计划。有关详细信息，请参阅 Lync Server 命令行管理程序文档。

## 设置拨号计划的 region 属性

1.  以 RTCUniversalServerAdmins 组成员或 **Cs-VoiceAdministrator** 、 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  对于缺少电话拨入式会议区域的任何拨号计划，请运行：
    
        Set-CsDialPlan [-Identity <Identity of the dial plan to be modified>] -DialinConferencingRegion "<new region>"
    
    例如：
    
        Set-CsDialPlan -Identity Redmond -DialinConferencingRegion "US West Coast"
    
    在此例中，对 Identity 为 Redmond 的拨号计划进行修改，将 DialinConferencingRegion 属性设置为“US West Coast”。有关详细信息，请参阅 Lync Server 命令行管理程序文档。

