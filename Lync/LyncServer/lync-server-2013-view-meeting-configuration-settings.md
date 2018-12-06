---
title: 查看会议配置设置
TOCTitle: 查看会议配置设置
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49888622
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看会议配置设置

 

_**上一次修改主题：** 2013-02-23_

在 Lync Server 2013 控制面板中，使用会议配置设置来控制在部署中实现会议的方式。其中包括以下会议配置：

  - 在部署 Lync Server 2013 时默认创建的全局配置。

  - 您可以创建并用来指定如何针对特定站点或用户实施会议的可选站点级别和用户级别配置。

## 查看会议配置设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“会议”，然后单击“会议配置”。

4.  在“会议配置”页上，单击要查看的会议配置。

5.  在“编辑文件筛选器”中，选中“显示详细信息...”复选框。
    
    **编辑会议配置 - \<策略\>** 打开后将显示所选策略的设置。有关配置设置的详细信息，请参阅[在 Lync Server 2013 中创建或修改会议配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。

## 使用 Lync Server PowerShell Cmdlet 查看会议配置信息

还可以使用 Lync Server PowerShell 和 Get-CsMeetingConfiguration cmdlet 查看会议配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看会议配置信息

  - 要查看所有会议配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsMeetingConfiguration
    
    这将返回类似如下的信息：
    
        Identity                        : Global
        PstnCallersBypassLobby          : True
        EnableAssignedConferenceType    : True
        DesignateAsPresenter            : Company
        AssignedConferenceTypeByDefault : True
        AdmitAnonymousUsersByDefault    : True
        RequireRoomSystemsAuthorization : False
        LogoURL                         :
        LegalURL                        :
        HelpURL                         :
        CustomFooterText                :
        AllowConferenceRecording        : True

有关详细信息，请参阅 [Get-CsMeetingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet 的帮助主题。

