---
title: 删除用户体验质量配置设置
TOCTitle: 删除用户体验质量配置设置
ms:assetid: fd0c4c2f-3bfb-42cb-9b6a-f0f8d5aa9e81
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg182613(v=OCS.15)
ms:contentKeyID: 49314851
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除用户体验质量配置设置

 

_**上一次修改主题：** 2013-02-23_

用户体验质量 (QoE) 指标用于跟踪组织中发出的语音和视频呼叫的质量，包括网络数据包丢失数目、背景噪音、“抖动”量（数据包延迟的差异）等。这些指标与其他数据（如呼叫详细信息记录）分开存储在一个数据库中，这样您就可以独立于其他数据记录启用和禁用 QoE。

安装 Microsoft Lync Server 2013 时，就会为您创建一个 QoE 配置设置的单一全局集合。管理员还可以选择可应用于各个站点的自定义设置集合。根据设计，在站点作用域配置的设置优先于在全局作用域配置的设置。如果您删除站点作用域设置，则将通过使用全局设置在该站点管理 QoE。

请注意，您还可以“删除”全局设置。但将不会实际删除全局设置。不过，该集合中的所有属性将重置为其默认值。例如，在 QoE 配置设置的集合中启用了默认清除功能。假定您修改了全局集合，这样就会禁用清除功能。如果稍后删除全局设置，则会将这些属性全部重置为其默认值。在这种情况下，这意味着又重新启用清除功能。

可以通过使用 Lync Server 控制面板或[Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration) cmdlet 删除 QoE 配置设置。

## 使用 Lync Server 控制面板 删除 QoE 配置设置

1.  以 RTCUniversalServerAdmins 组成员的身份或者以 CsVoiceAdministrator、CsServerAdministrator 或 CsAdministrator 角色成员的身份登录计算机。有关详细信息，请参阅[Lync Server 2013 中的委派安装权限](lync-server-2013-delegate-setup-permissions.md)。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“用户体验质量数据”。

4.  在“用户体验质量数据”上，单击所需的策略，单击“编辑”，然后单击“删除”。

5.  单击“确定”。

## 使用 Lync Server 命令行管理程序 Cmdlet 删除 QoE 配置设置

还可以通过使用 Lync Server 命令行管理程序和 **Remove-CsQoEConfiguration** cmdlet 删除 QoE 配置设置。可从 Lync Server 2013 命令行管理程序 或从 Windows PowerShell 的远程会话运行此 cmdlet。有关使用远程 Windows PowerShell 连接到 Lync Server 的详细信息，请参阅 Lync Server Windows PowerShell 博客文章“快速入门：使用远程 PowerShell 管理 Microsoft Lync Server 2010”，网址为 [http://go.microsoft.com/fwlink/p/?linkId=255876](http://go.microsoft.com/fwlink/p/?linkid=255876)。

## 删除 QoE 配置设置的指定的集合

  - 此命令可用于删除应用于 Redmond 站点的 QoE 配置设置：
    
        Remove-CsQoEConfiguration -Identity "site:Redmond"

## 删除应用于该站点作用域的所有 QoE 配置设置

  - 此命令可用于删除应用于该站点作用域的所有 QoE 配置设置：
    
        Get-CsQoEConfiguration -Filter "site:*" | Remove-CsQoEConfiguration

## 删除禁用 QoE 监控处的所有 QoE 配置设置

  - 此命令用于删除已禁用 QoE 监控处的所有 QoE 配置设置：
    
        Get-CsQoEConfiguration | Where-Object {$_.EnableQoE -eq $False} | Remove-CsQoEConfiguration

有关详细信息，请参阅 [Remove-CsQoEConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsQoEConfiguration)。

