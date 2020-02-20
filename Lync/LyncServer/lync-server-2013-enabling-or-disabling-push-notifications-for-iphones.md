---
title: Lync Server 2013：为 Iphone 启用或禁用推送通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for iPhones
ms:assetid: 8bbf531a-807f-4a8f-814a-94bfed8f97ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688122(v=OCS.15)
ms:contentKeyID: 49733719
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9af351e2d5710d3263faf0afeb6ab8aa36d5e568
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146385"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-iphones-in-lync-server-2013"></a>在 Lync Server 2013 中为 Iphone 启用或禁用推送通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-23_

即使移动应用程序处于非活动状态，也可以将徽章、图标或警报等推送通知发送到 iPhone。 推送通知会将一些事件（例如，新的或错过的 IM 邀请和语音邮件）告知用户。 您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序启用或禁用针对 iPhone 的推送通知。

<div>

## <a name="to-enable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板为 iPhone 启用推送通知

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“推送通知配置”**** 导航按钮。

4.  在 "**推送通知配置**" 页上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。

5.  单击“启用 Apple 推送通知”**** 复选框。

6.  单击“提交”****。

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone-by-using-lync-server-control-panel"></a>使用 Lync Server 控制面板禁用 iPhone 的推送通知

1.  使用分配给 CsUserAdministrator 角色或 CsAdministrator 角色的用户帐户登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“客户端”****，然后单击“推送通知配置”**** 导航按钮。

4.  在 "**推送通知配置**" 页上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。

5.  清除“启用 Apple 推送通知”**** 复选框。

6.  单击“提交”****。

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-to-iphone-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用向 iPhone 的推送通知

可以使用**CsPushNotificationConfiguration** cmdlet 启用或禁用将通知推送到 Apple iPhone。 您可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅在上[https://go.microsoft.com/fwlink/p/?linkId=255876](https://go.microsoft.com/fwlink/p/?linkid=255876)的 Lync Server Windows powershell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010"。

<div>

## <a name="to-enable-push-notifications-for-iphone"></a>为 iPhone 启用推送通知

  - 若要为 iPhone 启用推送通知，请将 EnableApplePushNotificationService 属性的值设置为 True （$True）。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-iphone"></a>禁用 iPhone 的推送通知

  - 若要禁用针对 iPhone 的推送通知，请将 EnableApplePushNotificationService 属性的值设置为 False （$False）。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableApplePushNotificationService $False

</div>

有关详细信息，请参阅 [Set-CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet 的帮助主题。

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

