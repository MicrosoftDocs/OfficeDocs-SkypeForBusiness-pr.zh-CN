---
title: 强制电话锁定
TOCTitle: 强制电话锁定
ms:assetid: 1f89298b-aea9-4952-93ca-0270b565792b
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg520963(v=OCS.15)
ms:contentKeyID: 49312211
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 强制电话锁定

 

_**上一次修改主题：** 2013-02-23_

出于安全目的可将 Lync Phone Edition 设备锁定。如果您强制执行电话锁定，则运行 Lync Phone Edition 的设备将在您配置的时间段之后锁定。当电话锁定时，用户可以发出呼叫，但无法访问日历和联系信息、语音邮件或呼叫日志，也无法使用搜索。若要解锁电话，用户须输入 PIN。

若要强制执行电话锁定，可通过使用 Lync Server 控制面板或 Lync Server PowerShell cmdlet 来启用并进行配置。您可以在全局强制执行电话锁定，也可以仅在其所配置的站点中执行。

## 配置和强制执行电话锁定

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  单击“客户端”，然后单击“设备配置”。

4.  在“设备配置”选项卡上的设备配置列表中，双击要更改电话锁定设置的配置。

5.  在“编辑设备配置”对话框中，确认选中了“强制设备锁定”复选框。

6.  在“最小 PIN 长度”中，接受解锁 PIN 必须包含的最小数字位数的默认值，或者指定一个新值。PIN 长度的范围是 4 到 15 位数字，而默认长度为 6 位数字。

7.  在“电话锁定超时”中，接受电话自行锁定之前的最小时间长度的默认值，或者指定一个新值。超时范围是 0 到 60 分钟，而默认值是 10 分钟。按照 HH:MM:SS 格式输入值。

8.  单击“提交”。

## 使用 Windows PowerShell Cmdlet 强制执行电话锁定

可以使用 Set-CsUCPhoneConfiguration cmdlet 强制执行电话锁定。此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 启用电话锁定

  - 以下命令可为 Redmond 站点启用电话锁定。若要禁用电话锁定，请将 EnforcePhoneLock 属性设置为 False ($False)。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True

## 启用电话锁定并修改电话锁定超时

  - 此命令启用电话锁定，还将电话锁定超时设置为 30 分钟。
    
        Set-CsUCPhoneConfiguration -Identity" site:Redmond" -EnforcePhoneLock $True -PhoneLockTimeout "00:30:00"

## 在整个组织内启用电话锁定

  - 在此示例中，在组织内使用的所有 UC 电话配置设置中都启用了电话锁定。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration  -EnforcePhoneLock $True

有关详细信息，请参阅 [Set-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsUCPhoneConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 概念

[管理 Lync Server 2013 身份验证](lync-server-2013-managing-lync-server-authentication.md)  

#### 其他资源

[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)

