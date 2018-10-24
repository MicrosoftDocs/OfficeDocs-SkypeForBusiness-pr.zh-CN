---
title: 查看有关推送通知设置的信息
TOCTitle: 查看有关推送通知设置的信息
ms:assetid: be5c6b01-4294-4d17-9772-fed40201e8a5
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ721868(v=OCS.15)
ms:contentKeyID: 49888587
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看有关推送通知设置的信息

 

_**上一次修改主题：** 2013-02-23_

即使移动应用程序处于非活动状态，也可以向移动设备发送推送通知（以徽章、图标或警告的形式）。推送通知会将一些事件（例如，新的或错过的 IM 邀请和语音邮件）告知用户。您可以使用 Lync Server 2013 控制面板或 Lync Server 2013 命令行管理程序来查看移动设备的信息推送通知设置。

## 从 Lync Server 控制面板中查看推送通知信息

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“推送通知配置”导航按钮。

4.  在“推送通知配置”页上，单击要查看的站点，再单击“编辑”菜单，然后单击“显示详细信息”。

## 使用 Windows PowerShell cmdlet 查看推送通知配置信息

您也可以使用 Lync Server 命令行管理程序和 **Get-CsPushNotificationConfiguration** cmdlet 来查看推送通知配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看推送通知配置信息

  - 要查看有关所有推送通知配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 ENTER 键：
    
        Get-CsPushNotificationConfiguration
    
    这将返回与以下类似的信息：
    
        Identity                               : Global
        EnableApplePushNotificationService     : False
        EnableMicrosoftPushNotificationService : False

有关详细信息，请参阅 [Get-CsPushNotificationConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsPushNotificationConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置推送通知](lync-server-2013-configuring-for-push-notifications.md)

