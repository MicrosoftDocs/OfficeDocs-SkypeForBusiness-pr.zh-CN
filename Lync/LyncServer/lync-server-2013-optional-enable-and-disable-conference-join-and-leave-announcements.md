---
title: Lync Server 2013：（可选）启用和禁用会议加入和离开通知
TOCTitle: （可选）启用和禁用会议加入和离开通知
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398834(v=OCS.15)
ms:contentKeyID: 49314222
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# （可选）在 Lync Server 2013 中启用和禁用会议加入和离开通知

 

_**上一次修改主题：** 2012-09-30_

当电话拨入用户加入或离开会议时， 会议通知应用程序可以通过播放提示音或说出用户姓名来通知用户的进入或退出。您可以通过运行 cmdlet 来更改通知方式。此步骤是可选的。

## 修改会议加入和离开通知行为

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingConfiguration
    
    此 cmdlet 会检索有关与会者加入会议时是否需要记录其姓名的信息，以及有关与会者加入或离开电话拨入式会议时 Lync Server 如何响应的信息。

4.  在命令提示符下，运行以下内容：
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording** 确定在匿名参与者进入会议之前是否要求参与者记录其姓名。默认值为“$true”，即系统会提示匿名参与者在加入会议时说出其姓名。（经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。）
    
    **EntryExitAnnouncementsEnabledByDefault** 指示默认打开还是关闭通知。默认值为“$false”，即默认情况下，在参与者加入或离开会议时没有通知。会议组织者在安排会议时可以覆盖此设置。
    
    **EntryExitAnnouncementsType** 指示参与者加入或离开启用了通知的会议时将执行的操作。默认值为“UseNames”，即有通知，类似于：“Ken Myer 已加入会议”（如果已打开通知）。
    
    可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。
    
    例如：
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    在此示例中，在 site 作用域为 Redmond 配置设置。通知已打开，但在参与者加入会议时系统未提示他们说出姓名。参与者进入或离开会议时将播放提示音。

