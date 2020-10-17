---
title: Lync Server 2013：查看有关推送通知设置的信息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Viewing information about push notification settings
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49733801
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 58602a2fed6faa03c7dd573b95345a0ee57aa607
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48523539"
---
# <a name="viewing-information-about-push-notification-settings-in-lync-server-2013"></a>查看 Lync Server 2013 中的推送通知设置的相关信息

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

即使移动应用程序处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。 推送通知会将一些事件（例如，新的或错过的 IM 邀请和语音邮件）告知用户。 您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序查看移动设备的信息推送通知设置。

<div>

## <a name="to-view-push-notification-information-from-lync-server-control-panel"></a>从 Lync Server 控制面板查看推送通知信息

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“推送通知配置”**** 导航按钮。

4.  在 " **推送通知配置** " 页上，单击要查看的网站，单击 " **编辑** " 菜单，然后单击 " **显示详细信息**"。

</div>

<div>

## <a name="viewing-push-notification-information-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 查看推送通知信息

您可以使用 Windows PowerShell 和 **CsPushNotificationConfiguration** cmdlet 查看推送通知配置设置。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上的 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876) 。

<div>

## <a name="to-view-push-notification-configuration-information"></a>查看推送通知配置信息

  - 若要查看有关所有推送通知配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER：
    
        Get-CsPushNotificationConfiguration
    
    这将返回与以下类似的信息：
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

</div>

有关详细信息，请参阅 [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet 的帮助主题。

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

