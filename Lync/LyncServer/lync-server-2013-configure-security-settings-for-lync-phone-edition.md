---
title: 配置 Lync Phone Edition 的安全设置
TOCTitle: 配置 Lync Phone Edition 的安全设置
ms:assetid: 6e7cec17-8a79-4428-9300-8821256c46cf
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg521014(v=OCS.15)
ms:contentKeyID: 49313191
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 配置 Lync Phone Edition 的安全设置

 

_**上一次修改主题：** 2013-02-23_

通过您的 SIP 安全设置和电话锁定设置来帮助增强运行 Lync Phone Edition 的设备的安全性。

## 为 Lync Phone Edition 配置安全设置

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备配置”。

4.  在“设备配置”页上的设备配置列表中，双击要更改安全设置的配置。

5.  在“编辑设备配置”的“SIP 安全”中，指定 SIP 安全级别。默认级别为“高”，建议使用此级别。

6.  在“编辑设备配置”中的“电话锁定”下，选中或清除“强制设备锁定”复选框（默认为选中）并指定最小 PIN 长度（默认为 6 个字符）和超时期限（默认为 10 分钟）。建议使用这些默认值或增加 PIN 长度和/或减小超时期限。
    
    > [!NOTE]  
    > 有关详细信息，请参阅<a href="lync-server-2013-enforce-phone-locking.md">强制电话锁定</a>。
    


## 使用 Lync Server 命令行管理程序 cmdlet 为 Lync Phone Edition 电话配置安全设置

还可以使用 Lync Server 命令行管理程序和 **Get-CsUCPhoneConfiguration** cmdlet 管理安全设置。此 cmdlet 可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 修改 SIP 安全模式

  - 此命令将 UC 电话设置全局集合的 SIPSecurityMode 设置为“中”。还可以将 SIP 安全性设置为“低”或“高”（默认值）。
    
        Set-CsUCPhoneConfiguration -Identity global -SIPSecurityMode "Medium"

## 修改最小 PIN 长度

  - 在此示例中，会将所有 UC 电话设置修改为需要 7 位最小 PIN 长度。
    
        Get-CsUCPhoneConfiguration | Set-CsUCPhoneConfiguration -MinPhonePinLength 7

有关详细信息，请参阅 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration)。

## 另请参阅

#### 概念

[管理 Lync Server 2013 身份验证](lync-server-2013-managing-lync-server-authentication.md)  

#### 其他资源

[在 Lync Server 2013 中管理设备、电话和客户端应用程序](lync-server-2013-managing-devices-phones-and-client-applications.md)

