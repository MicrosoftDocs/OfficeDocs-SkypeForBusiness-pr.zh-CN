---
title: 'Lync Server 2013: 查看有关推送通知设置的信息'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: da9279d09ab3b344514a472f3fb0f38e7071aabd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34845323"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>查看有关 Lync Server 2013 中的推送通知设置的信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-23_

即使移动应用处于非活动状态, 推送通知 (以锁屏提醒、图标或警报形式) 也可以发送到移动设备。 推送通知通知用户诸如新的或错过的 IM 邀请和语音邮件等事件。 你可以使用 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳查看移动设备的信息推送通知设置。

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>从 Lync Server "控制面板" 查看推送通知信息

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**客户端**", 然后单击 "**推送通知配置**" 导航按钮。

4.  在 "**推送通知配置**" 页上, 单击要查看的网站, 单击 "**编辑**" 菜单, 然后单击 "**显示详细信息**"。

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看推送通知信息

你可以使用 Windows PowerShell 和**CsPushNotificationConfiguration** cmdlet 查看推送通知配置设置。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息, 请参阅 Lync Server Windows PowerShell 博客文章 "快速入门: 使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-view-push-notification-configuration-information"></a>查看推送通知配置信息

  - 若要查看有关所有推送通知配置设置的信息, 请在 Lync Server 命令行管理程序中键入以下命令, 然后按 ENTER:
    
        Get-CsPushNotificationConfiguration
    
    这将返回与以下类似的信息：
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

有关详细信息, 请参阅[CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet 的帮助主题。

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置推送通知](lync-server-2013-configuring-for-push-notifications.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

