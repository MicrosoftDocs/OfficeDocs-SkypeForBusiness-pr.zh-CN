---
title: Lync Server 2013：查看 Lync Phone Edition 配置设置信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: View Lync Phone Edition configuration settings information
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49733564
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a58450b1d69ce757f40194d179606f332e152d7d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41765633"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="view-lync-phone-edition-configuration-settings-information-in-lync-server-2013"></a>在 Lync Server 2013 中查看 Lync Phone Edition 配置设置信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

你可以查看有关运行 Lync Phone Edition 的设备的配置信息。 信息组织到集合中。 安装 Lync Server 时，将获得适用于部署中所有运行 Lync Phone Edition 的设备的 Lync 手机版设置的集合。 您还可以为特定网站创建新的设置集合。 网站设置优先于全局设置。 每个设置集合均包括名称、范围（全局或网站）、SIP 安全设置、日志记录级别、语音服务质量（QoS）级别、电话锁定设置和电话锁定详细信息，即解锁个人标识的最小长度电话锁定自身之前的数字（PIN）和时间。

<div>

## <a name="to-view-configuration-information-about-devices-running-lync-phone-edition"></a>查看有关运行 Lync Phone Edition 的设备的配置信息

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**设备配置**" 导航按钮。

4.  在 "**设备配置**" 页面上，单击要查看其相关信息的设置的集合。 主页面上列出了名称、范围、SIP 安全设置、语音质量级别和电话锁定设置。 若要查看日志记录级别和电话锁定的详细信息，请单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。

</div>

<div>

## <a name="viewing-lync-phone-edition-configuration-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看 Lync 手机版配置信息

你可以使用 Lync Server 命令行管理程序和**CsUCPhoneConfiguration** Cmdlet 查看 Lync 手机版配置设置。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-lync-phone-edition-configuration-information"></a>查看 Lync Phone Edition 配置信息

  - 若要查看有关所有 Lync Phone Edition 配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsUCPhoneConfiguration
    
    该命令将返回类似于以下内容的信息：
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

</div>

有关详细信息，请参阅[CsUCPhoneConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsUCPhoneConfiguration)。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中创建或修改 Lync Phone Edition 配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[删除 Lync Server 2013 中的现有 Lync Phone Edition 配置设置集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[在 Lync Server 2013 中配置 Lync Phone Edition 的安全设置](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[在 Lync Server 2013 中强制执行电话锁定](lync-server-2013-enforce-phone-locking.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

