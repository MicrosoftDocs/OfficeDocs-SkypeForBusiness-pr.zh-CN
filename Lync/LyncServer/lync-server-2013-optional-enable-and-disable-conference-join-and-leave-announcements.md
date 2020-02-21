---
title: Optional启用和禁用会议加入和离开通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: (Optional) Enable and disable conference join and leave announcements
ms:assetid: c9529568-e66c-48d8-aef2-9072f9c336ff
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398834(v=OCS.15)
ms:contentKeyID: 48185403
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c5007ec14ad197afb2cfb8d2c73baa41ed144a4e
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42216498"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>Optional在 Lync Server 2013 中启用和禁用会议加入和离开通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-30_

当电话拨入用户加入会议或离开会议时，会议通知应用程序可以通过播放声音或说出其名称来宣布进入或退出。 您可以通过运行 cmdlet 来更改通知方式。 此步骤是可选的。

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改会议加入和离开通知行为

1.  以 RTCUniversalServerAdmins 组成员或者 **Cs-ServerAdministrator** 或 **CsAdministrator** 角色成员的身份登录计算机。

2.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingConfiguration
    
    此 cmdlet 检索有关参与者在加入会议时是否需要记录其名称的信息，以及当参与者加入或离开电话拨入式会议时，Lync Server 如何响应。

4.  在命令提示符下，运行以下内容：
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   确定在进入会议之前是否要求匿名参与者录制其姓名。 （经过身份验证的参与者不会记录他们的姓名，因为将使用他们的显示名称。 ）
    
    **EntryExitAnnouncementsEnabledByDefault**   指示默认情况下是打开还是关闭通知。 默认值为 "$false"，这意味着当参与者加入或离开会议时，默认情况下没有通知。 会议组织者在安排会议时可以覆盖此设置。
    
    **EntryExitAnnouncementsType**   指示每当参与者加入或离开启用了通知的会议时执行的操作。 默认值为 "UseNames"，这意味着与以下内容类似的通知： "Ken Myer 已加入会议"。当通知打开时。
    
    可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。
    
    例如：
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    在此示例中，在 site 作用域为 Redmond 配置设置。通知已打开，但在参与者加入会议时系统未提示他们说出姓名。参与者进入或离开会议时将播放提示音。

</div>

</div>

<span> </span>

</div>

</div>

</div>

