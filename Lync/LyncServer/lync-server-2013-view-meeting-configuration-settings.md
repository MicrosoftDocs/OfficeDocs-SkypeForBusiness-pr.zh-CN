---
title: 'Lync Server 2013: 查看会议配置设置'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: View meeting configuration settings
ms:assetid: d03a4684-9d8b-4728-917d-5b5c91511e2c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721894(v=OCS.15)
ms:contentKeyID: 49733828
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4b3107045d62b244c7ee89dbb47228bc5dd72583
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845345"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-meeting-configuration-settings-in-lync-server-2013"></a>在 Lync Server 2013 中查看会议配置设置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

在 Lync Server 2013 控制面板中, 使用 "会议配置" 设置来控制在部署中实现会议的方式。 这包括以下会议配置:

  - 部署 Lync Server 2013 时默认创建的全局配置。

  - 可创建和使用的可选网站级和用户级配置, 用于指定如何为特定网站或用户实现会议。

<div>

## <a name="to-view-meeting-configuration-settings"></a>查看会议配置设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**会议**", 然后单击 "**会议配置**"。

4.  在“**会议配置**”页上，单击要查看的会议配置。

5.  在 "**编辑文件筛选器**" 中, 选择 "**显示详细信息 ...** " 复选框。
    
    **编辑会议配置- \<策略\> **将打开, 显示所选策略的设置。 有关配置设置的详细信息, 请参阅[在 Lync Server 2013 中创建或修改会议配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-meeting-configuration-settings.md)。

</div>

<div>

## <a name="viewing-meeting-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看会议配置信息

可使用 Windows PowerShell 和 CsMeetingConfiguration cmdlet 查看会议配置设置。 此 cmdlet 既可以从 Lync Server 2013 管理外壳运行, 也可以从 Windows PowerShell 的远程会话运行。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-meeting-configuration-information"></a>查看会议配置信息

  - 若要查看有关所有会议配置设置的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
        Get-CsMeetingConfiguration
    
    这将返回与以下类似的信息：
    
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

</div>

有关详细信息, 请参阅[CsMeetingConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsMeetingConfiguration) cmdlet 的帮助主题。

</div>

</div>

<span> </span>

</div>

</div>

</div>

