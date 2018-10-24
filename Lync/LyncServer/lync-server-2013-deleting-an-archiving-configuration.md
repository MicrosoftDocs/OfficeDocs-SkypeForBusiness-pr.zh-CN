---
title: 删除存档配置
TOCTitle: 删除存档配置
ms:assetid: a8744d39-5cf2-474c-9a99-a0f3a37f846f
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205167(v=OCS.15)
ms:contentKeyID: 49313858
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 删除存档配置

 

_**上一次修改主题：** 2013-02-23_

可以删除站点配置或池配置，但无法删除全局配置。如果删除了全局配置，则它会自动重置为默认值。有关如何实现存档配置（包括可指定的选项以及存档配置的层次结构）的详细信息，请参阅规划文档、部署文档或操作文档中的[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)。

## 删除要存档的站点或池配置

1.  使用分配给 CsArchivingAdministrator 或 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“监控和存档”，然后单击“存档配置”。

4.  在存档配置的列表中，单击要删除的站点或池配置，单击“编辑”，然后单击“删除”。

5.  单击“提交”。

## 使用 Lync Server 命令行管理程序 Cmdlet 删除存档配置设置

也可以使用 Windows PowerShell 和 Remove-CsArchivingConfiguration cmdlet 删除存档配置设置。可以从 Lync Server 2013 命令行管理程序或从 Windows PowerShell 的远程会话中运行此 cmdlet。

## 删除指定的存档配置设置集合

  - 以下命令会删除应用到 Redmond 站点的存档配置设置：
    
        Remove-CsArchivingConfiguration -Identity "site:Redmond"

## 删除应用到站点范围的所有存档配置设置

  - 此命令会删除应用到服务范围的所有存档配置设置：
    
        Get-CsArchivingConfiguration -Filter "site:*" | Remove-CsArchivingConfiguration

## 根据指定的属性值删除存档配置设置

  - 此命令会删除在其中已禁用 Exchange 存档的所有存档配置设置：
    
        Get-CsArchivingConfiguration | Where-Object {$_.EnableExchangeArchiving -eq $False} | Remove-CsArchivingConfiguration

有关详细信息，请参阅 [Remove-CsArchivingConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Remove-CsArchivingConfiguration) cmdlet 的帮助主题。

## 另请参阅

#### 概念

[Lync Server 2013 的存档工作原理](lync-server-2013-how-archiving-works.md)  

#### 其他资源

[在 Lync Server 2013 中管理内部通信和外部通信的存档](lync-server-2013-managing-the-archiving-of-internal-and-external-communications.md)

