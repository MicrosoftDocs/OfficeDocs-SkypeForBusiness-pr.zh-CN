---
title: 查看会议策略信息
TOCTitle: 查看会议策略信息
ms:assetid: e99fdc4d-926a-4e36-ac99-ab5035568847
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721918(v=OCS.15)
ms:contentKeyID: 49888654
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看会议策略信息

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，使用会议策略控制在部署中实施会议的方式。这包括下列会议策略：

  - 部署 Lync Server 2013 时默认创建的全局策略。

  - 您可以创建并用来指定如何针对特定站点或用户实施会议的可选站点级别和用户级别策略。

## 查看会议策略设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议策略”。

4.  在“会议策略”页面上，双击您要查看的会议策略。

5.  在“编辑文件筛选器”中，选中“显示详细信息…”复选框。
    
    **编辑会议策略 - \<策略\>** 会打开，显示所选策略的设置。有关配置设置的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议策略](lync-server-2013-create-or-modify-a-conferencing-policy.md)。

## 通过使用 Lync Server PowerShell Cmdlet 查看会议策略

还可以通过使用 Lync Server PowerShell 和 Get-CsConferencingPolicy cmdlet 查看会议策略。此 cmdlet 可从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看会议策略

  - 要查看有关所有会议策略的信息，在 Lync Server 命令行管理程序 中输入下列命令，然后按 Enter：
    
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

有关详细信息，请参阅[Get-CsConferencingPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsConferencingPolicy) cmdlet 的帮助主题。

