---
title: Lync Server 2013：（可选）修改 DTMF 命令的键映射
TOCTitle: （可选）修改 DTMF 命令的键映射
ms:assetid: d753b78d-400c-4df2-957f-e7576b2019c2
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398943(v=OCS.15)
ms:contentKeyID: 49314396
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# （可选）在 Lync Server 2013 中修改 DTMF 命令的键映射

 

_**上一次修改主题：** 2012-09-30_

电话拨入式会议用户可以在电话小键盘上按键以执行双音多频 (DTMF) 命令。通过 DTMF 命令，拨入会议的用户可以使用其电话上的小键盘控制会议设置（例如，将自己静音和取消静音，或者锁定和解锁会议）。可以使用 cmdlet 修改用于 DTMF 命令的键。此步骤是可选的。

> [!NOTE]  
> 有关这些 cmdlet 和可能的 DTMF 选项的详细信息，请参阅 Lync Server 命令行管理程序文档或 Lync Server 命令行管理程序命令行帮助。



## 修改 DTMF 命令的键映射

1.  以 **RTCUniversalServerAdmins** 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”、“所有程序”和“Microsoft Lync Server 2013”，然后单击“Lync Server 命令行管理程序”。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingDtmfConfiguration
    
    此 cmdlet 可返回用于电话拨入式会议的 DTMF 设置。

4.  运行以下 cmdlet 并为要更改的每个选项指定要按的键：
    
        Set-CsDialinConferencingDtmfConfiguration [-Identity <global or site collection to be changed>]
        [-AdmitAll <default key is 8>] [-AudienceMuteCommand <default key is 4>]
        [-CommandCharacter <* (default) | #>] [-EnableDisableAnnouncementsCommand <default key is 9>]
        [-HelpCommand <default key is 1>] [-LockUnlockConferenceCommand <default key is 7>]
        [-MuteUnmuteCommand <default key is 6>] [-PrivateRollCallCommand <default key is 3>]
    
    此 cmdlet 可修改用于电话拨入式会议的 DTMF 设置。
    
    例如：
    
        Set-CsDialinConferencingDtmfConfiguration -EnableDisableAnnouncementsCommand 4 -AudienceMuteCommand 9
    
    此示例可使启用或禁用通知所按的键和将所有与会者静音和取消静音所按的键交换。由于未指定 Identity，因此这些更改将应用于全局 DTMF 设置。

5.  （可选）要为特定站点创建其他 DTMF 命令集，请使用带有站点 Identity 的 **New-CsDialinConferencingDtmfConfiguration** cmdlet。为站点创建新的 DTMF 设置后，站点设置将优先于全局设置。有关详细信息，请参阅 Lync Server 命令行管理程序文档或 Lync Server 命令行管理程序命令行帮助。

