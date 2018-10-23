---
title: 确认拓扑信息
TOCTitle: 确认拓扑信息
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205151(v=OCS.15)
ms:contentKeyID: 49313881
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 确认拓扑信息

 

_**上一次修改主题：** 2012-09-26_

验证合并是否成功完成的第一步是查看与 Lync Server 2013 合并的 Office Communications Server 2007 R2 拓扑信息。在拓扑生成器中， **BackCompatSite** 节点显示您合并的每个 Office Communications Server 2007 R2 池和服务器的完全限定的域名 (FQDN)。

## 在拓扑生成器中查看 BackCompatSite

1.  在 Office Communications Server 2007 R2 环境中，打开 Office Communications Server 2007 R2 管理工具，并记下旧版池和服务器的 FQDN。

2.  在 Lync Server 2013 环境中，打开拓扑生成器，然后展开“BackCompatSite”节点。

3.  验证您合并的池和服务器的 FQDN 是否显示。
    
    > [!NOTE]
    > 在前端服务器或 Standard Edition Server 上并置的服务器角色的 <strong>BackCompatSite</strong> 中不会显示任何信息。仅会显示在 Office Communications Server 2007 R2 和 Lync Server 2013 之间实现互操作性所需的服务器角色。


![拓扑生成器 -“BackCompatSite”对话框](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "拓扑生成器 -“BackCompatSite”对话框")

您还可以使用 Lync Server 2013 控制面板查看合并的拓扑。在 Lync Server 2013 控制面板中，可以查看所合并的拓扑的每个服务器 FQDN、池 FQDN 和站点名称。合并的服务器的“站点”名称为“BackCompatSite”。

## 在 Lync Server 2013 控制面板中查看合并的拓扑

1.  打开 Lync Server 2013 控制面板。

2.  单击“拓扑”。

3.  在“状态”选项卡上，通过在“站点”列中查找“BackCompatSite”来验证合并的服务器和池是否显示。

![显示合并的拓扑的 Lync Server 控制面板](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "显示合并的拓扑的 Lync Server 控制面板")

要查看有关合并的池的更多详细信息，请使用 **Get-CsPool** cmdlet。除拓扑生成器和 Lync Server 2013 控制面板中提供的信息外，此 cmdlet 还显示在 Lync Server 2013 池上运行的服务。

> [!NOTE]  
> 在拓扑生成器中运行合并向导后发布拓扑时，会议目录将合并到 Lync Server 2013。可通过运行 <strong>Get-CsConferenceDirectory</strong> cmdlet 来验证会议目录。


## 查看合并的池中的服务

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    例如：
    
        Get-CsPool -Identity pool02.contoso.net

## 验证合并的会议目录

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsConferenceDirectory

3.  验证要合并的池或服务器的所有会议目录现在是否在 Lync Server 2013 中。

