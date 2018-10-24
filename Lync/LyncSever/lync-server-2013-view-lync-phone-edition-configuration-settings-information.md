---
title: 查看 Lync Phone Edition 配置设置信息
TOCTitle: 查看 Lync Phone Edition 配置设置信息
ms:assetid: 15f94478-651f-4063-9918-6a059f98df16
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ687976(v=OCS.15)
ms:contentKeyID: 49888312
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 查看 Lync Phone Edition 配置设置信息

 

_**上一次修改主题：** 2013-02-23_

可以查看有关运行 Lync Phone Edition 的设备的配置信息。信息以集合的形式来组织。当您安装 Lync Server 时，可获取适用于在部署中运行 Lync Phone Edition 的所有设备的 Lync Phone Edition 设置集合。还可以为特定站点创建新的设置集合。站点设置优先于全局设置。每个设置集合都包含名称、范围（全局或站点）、SIP 安全设置、日志记录级别、语音服务质量 (QoS) 级别、电话锁定设置和电话锁定详细信息，即解锁个人标识号 (PIN) 的最小长度和电话自行锁定之前的时间。

## 查看有关运行 Lync Phone Edition 的设备的配置信息

1.  使用分配给 CsUserAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“客户端”，然后单击“设备配置”导航按钮。

4.  在“设备配置”页上，单击要查看相关信息的设置的集合。主页中会列出名称、范围、SIP 安全设置、语音质量级别和电话锁定设置。若要查看日志记录级别和电话锁定详细信息，请单击“编辑”菜单，然后单击“显示详细信息”。

## 使用 Lync Server 命令行管理程序 cmdlet 查看 Lync Phone Edition 配置信息

还可以使用 Lync Server 命令行管理程序和 **Get-CsUCPhoneConfiguration** cmdlet 查看 Lync Phone Edition 配置设置。可从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 查看 Lync Phone Edition 配置信息

  - 若要查看有关所有 Lync Phone Edition 配置设置的信息，请在 Lync Server 命令行管理程序中键入以下命令，然后按 Enter：
    
        Get-CsUCPhoneConfiguration
    
    该命令将返回类似如下的信息：
    
        Identity             : Global
        CalendarPollInterval : 00:03:00
        EnforcePhoneLock     : True
        PhoneLockTimeout     : 00:10:00
        MinPhonePinLength    : 6
        SIPSecurityMode      : High
        VoiceDiffServTag     : 40
        Voice8021p           : 0
        LoggingLevel         : Off

有关详细信息，请参阅 [Get-CsUCPhoneConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsUCPhoneConfiguration)。

## 另请参阅

#### 任务

[创建或修改 Lync Phone Edition 配置设置的集合](lync-server-2013-create-or-modify-a-collection-of-lync-phone-edition-configuration-settings.md)  
[删除 Lync Phone Edition 配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-lync-phone-edition-configuration-settings.md)  
[配置 Lync Phone Edition 的安全设置](lync-server-2013-configure-security-settings-for-lync-phone-edition.md)  
[强制电话锁定](lync-server-2013-enforce-phone-locking.md)

