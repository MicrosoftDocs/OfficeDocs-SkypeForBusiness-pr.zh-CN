---
title: （可选）启用和禁用会议加入和离开通知
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
ms.openlocfilehash: 8b8e75a0d2ed81a515540f2a8a1811998a85d44c
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755746"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="optional-enable-and-disable-conference-join-and-leave-announcements-in-lync-server-2013"></a>（可选）在 Lync Server 2013 中启用和禁用会议加入和离开通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-30_

当拨入用户加入或离开会议时，会议公告应用程序可以通过播放音频或说出其名称来宣布其进入或退出。 你可以通过运行 cmdlet 来更改通知的工作方式。 此步骤是可选的。

<div>

## <a name="to-modify-the-conference-join-and-leave-announcement-behavior"></a>修改会议加入和离开通知行为

1.  以 RTCUniversalServerAdmins 组成员的身份登录计算机，或者作为**Cs-ServerAdministrator**或**CsAdministrator**角色的成员登录到计算机。

2.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

3.  在命令提示符下，运行以下内容：
    
        Get-CsDialinConferencingConfiguration
    
    此 cmdlet 检索有关参与者是否需要在加入会议时记录其名称的信息，以及当参与者加入或离开电话拨入式会议时 Lync 服务器的响应方式。

4.  在命令提示符下，运行以下内容：
    
        Set-CsDialinConferencingConfiguration -Identity <identity of dial-in conferencing settings to be modified>
        [-EnableNameRecording <$true | $false>]
        [-EntryExitAnnouncementsEnabledByDefault <$true | $false>]
        [-EntryExitAnnouncementsType <UseNames | ToneOnly]
    
    **EnableNameRecording**   确定在进入会议之前是否要求匿名参与者录制其姓名。 默认值为 "$true"，这意味着在加入会议时，系统会提示匿名参与者声明其名称。 （经过身份验证的参与者不会记录其名称，因为将改为使用其显示名称。）
    
    **EntryExitAnnouncementsEnabledByDefault**   指示默认情况下是打开还是关闭公告。 默认值为“$false”，即默认情况下，在参与者加入或离开会议时没有通知。 会议组织者在安排会议时可以覆盖此设置。
    
    **EntryExitAnnouncementsType**   指示每当参与者加入或离开已启用公告的会议时所采取的操作。 默认值为“UseNames”，即有通知，类似于：“Ken Myer 已加入会议”（如果已打开通知）。
    
    可以在 global 作用域或 site 作用域配置这些设置。在 site 作用域配置的设置的优先于在 global 作用域配置的设置。
    
    例如：
    
        Set-CsDialinConferencingConfiguration -Identity site:Redmond
        -EnableNameRecording $false
        -EntryExitAnnouncementsEnabledByDefault $true
        -EntryExitAnnouncementsType ToneOnly
    
    在此示例中，"雷德蒙" 的网站范围配置了 "设置"。 通知已打开，但在参与者加入会议时系统未提示他们说出姓名。 当参与者进入或离开会议时，将会播放音调。

</div>

</div>

<span> </span>

</div>

</div>

</div>

