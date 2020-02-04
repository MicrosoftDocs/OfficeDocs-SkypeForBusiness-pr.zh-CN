---
title: Lync Server 2013：为 Windows 手机启用或禁用推送通知
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling or disabling push notifications for Windows Phones
ms:assetid: a34f0c5c-4228-40e3-9d93-bc0b5df4895d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688162(v=OCS.15)
ms:contentKeyID: 49733767
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d1b4c8f1f86fa1456230ad4695de0f5b8c56d406
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-or-disabling-push-notifications-for-windows-phones-in-lync-server-2013"></a>在 Lync Server 2013 中启用或禁用 Windows 手机的推送通知

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-02-23_

即使移动应用程序处于非活动状态，推送通知（以锁屏提醒、图标或通知的形式）也可以发送到 Windows Phone。 推送通知通知用户诸如新的或错过的 IM 邀请和语音邮件等事件。 你可以通过使用 Lync Server 2013 控制面板或 Lync Server 2013 管理外壳程序启用或禁用 Windows Phone 设备的推送通知。

<div>

## <a name="to-enable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 启用 Windows Phone 推送通知

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**推送通知配置**" 导航按钮。

4.  在 "**推送通知配置**" 页面上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。

5.  单击 "**启用 Microsoft 推送通知**" 复选框。

6.  单击“**提交**”。

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone-by-using-lync-server-control-panel"></a>使用 Lync Server "控制面板" 禁用 Windows Phone 推送通知

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口，然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息，请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击 "**客户端**"，然后单击 "**推送通知配置**" 导航按钮。

4.  在 "**推送通知配置**" 页面上，单击要编辑的网站，单击 "**编辑**" 菜单，然后单击 "**显示详细信息**"。

5.  清除 "**启用 Microsoft 推送通知**" 复选框。

6.  单击“**提交**”。

</div>

<div>

## <a name="enabling-or-disabling-push-notifications-for-windows-phone-by-using-windows-powershell-cmdlets"></a>使用 Windows PowerShell Cmdlet 启用或禁用 Windows Phone 推送通知

你可以使用**CsPushNotificationConfiguration** cmdlet 启用或禁用 Windows Phone 推送通知。 你可以从 Lync Server 2013 命令行管理程序或 Windows PowerShell 的远程会话运行此 cmdlet。 有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章 "快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010" [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

<div>

## <a name="to-enable-push-notifications-for-windows-phone"></a>为 Windows Phone 启用推送通知

  - 若要启用 Windows Phone 推送通知，请将 EnableMicrosoftPushNotificationService 属性的值设置为 True （$True）。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $True

</div>

<div>

## <a name="to-disable-push-notifications-for-windows-phone"></a>禁用 Windows Phone 推送通知

  - 若要禁用 Windows Phone 推送通知，请将 EnableMicrosoftPushNotificationService 属性的值设置为 False （$False）。 例如：
    
        Set-CsPushNotificationConfiguration -Identity "site:Redmond" -EnableMicrosoftPushNotificationService $False

</div>

有关详细信息，请参阅[CsPushNotificationConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsPushNotificationConfiguration) cmdlet 的帮助主题。

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

