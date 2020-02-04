---
title: Lync Server 2013：查看会议策略信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View conferencing policy information
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49733852
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e5c2cccd61d710acd9d2155412ec427c65eafc2a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757436"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-conferencing-policy-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看会议策略信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

在 Lync Server 2013 "控制面板" 中，使用会议策略控制在部署中实现会议的方式。 这包括以下会议策略：

  - 部署 Lync Server 2013 时默认创建的全局策略。

  - 可创建和使用的可选网站级和用户级策略，用于指定如何为特定的网站或用户实现会议。

<div>

## <a name="to-view-conferencing-policy-settings"></a>查看会议策略设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**会议**"，然后单击 "**会议策略**"。

4.  在“**会议策略**”页面上，双击你要查看的会议策略。

5.  在 "**编辑文件筛选器**" 中，选择 "**显示详细信息 ...** " 复选框。
    
    **编辑会议策略- \<将\> **打开显示所选策略的设置的策略。 有关配置设置的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)。

</div>

<div>

## <a name="viewing-conferencing-policies-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看会议策略

可以使用 Windows PowerShell 和 CsConferencingPolicy cmdlet 查看会议策略。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行，也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-conferencing-policies"></a>查看会议策略

  - 若要查看有关所有会议策略的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsConferencingPolicy
    
    这将返回与以下类似的信息：
    
        Identity                                  : Global
        AllowIPAudio                              : True
        AllowIPVideo                              : True
        AllowMultiView                            : True
        Description                               :
        AllowParticipantControl                   : True
        AllowAnnotations                          : True
        DisablePowerPointAnnotations              : False
        AllowUserToScheduleMeetingsWithAppSharing : True
        AllowNonEnterpriseVoiceUsersToDialOut     : False
        AllowAnonymousUsersToDialOut              : False
        AllowAnonymousParticipantsInMeetings      : True
        AllowExternalUsersToSaveContent           : True
        AllowExternalUserControl                  : False
        AllowExternalUsersToRecordMeeting         : False
        AllowPolls                                : True
        AllowSharedNotes                          : True
        EnableDialInConferencing                  : True
        EnableAppDesktopSharing                   : Desktop
        AllowConferenceRecording                  : False
        EnableP2PRecording                        : False
        EnableFileTransfer                        : True
        EnableP2PFileTransfer                     : True
        EnableP2PVideo                            : True
        AllowLargeMeetings                        : False
        EnableDataCollaboration                   : True
        MaxVideoConferenceResolution              : VGA
        MaxMeetingSize                            : 250
        AudioBitRateKb                            : 200
        VideoBitRateKb                            : 50000
        AppSharingBitRateKb                       : 50000
        FileTransferBitRateKb                     : 50000
        TotalReceiveVideoBitRateKb                : 6000
        EnableMultiViewJoin                       : True

</div>

有关详细信息，请参阅[CsConferencingPolicy](https://docs.microsoft.com/powershell/module/skype/Get-CsConferencingPolicy) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

