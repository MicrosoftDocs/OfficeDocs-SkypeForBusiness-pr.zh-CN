---
title: 验证拓扑信息
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify topology information
ms:assetid: aa4c424e-f87c-4be6-8df6-a0cd193b11fc
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205151(v=OCS.15)
ms:contentKeyID: 48185046
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5987dc071abb888f8d1f6eca0d3082f2a8ab7523
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42036270"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>验证拓扑信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-26_

成功完成合并验证的第一步是查看与 Lync Server 2013 合并的 Office 通信服务器 2007 R2 拓扑信息。 在拓扑生成器中， **BackCompatSite**节点显示您合并的每个 Office 通信服务器 2007 R2 池和服务器的完全限定域名（FQDN）。

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>在拓扑生成器中查看 BackCompatSite

1.  在 Office 通信服务器 2007 R2 环境中，打开 Office 通信服务器 2007 R2 管理工具，并记下旧版池和服务器的 Fqdn。

2.  在 Lync Server 2013 环境中，打开拓扑生成器，然后展开 " **BackCompatSite** " 节点。

3.  验证您合并的池和服务器的 FQDN 是否显示。
    
    <div>
    

    > [!NOTE]  
    > 您不会在<STRONG>BackCompatSite</STRONG>中看到在前端服务器或 Standard Edition server 上并置的服务器角色的任何信息。 仅显示 Office 通信服务器 2007 R2 和 Lync Server 2013 之间的互操作性所需的服务器角色。

    
    </div>

!["拓扑生成器 BackCompatSite" 对话框](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg ""拓扑生成器 BackCompatSite" 对话框")

您还可以使用 Lync Server 2013 控制面板查看合并的拓扑。 在 Lync Server 2013 控制面板中，可以看到合并拓扑的每个服务器 FQDN、池 FQDN 和站点名称。 合并的服务器的“站点”**** 名称为“BackCompatSite”****。

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 "控制面板" 中查看合并的拓扑

1.  打开 "Lync Server 2013 控制面板"。

2.  单击“拓扑”****。

3.  在“状态”**** 选项卡上，通过在“站点”**** 列中查找 **BackCompatSite** 来验证合并的服务器和池是否显示。

![显示合并拓扑的 "Lync Server 控制面板"](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "显示合并拓扑的 "Lync Server 控制面板"")

要查看有关合并的池的更多详细信息，请使用 **Get-CsPool** cmdlet。 除了拓扑生成器和 Lync Server 2013 控制面板中提供的信息外，此 cmdlet 还会显示在 Lync Server 2013 池中运行的服务。

<div>


> [!NOTE]  
> 在拓扑生成器中运行合并向导之后发布拓扑时，会议目录将合并到 Lync Server 2013。 可以通过运行<STRONG>new-csconferencedirectory</STRONG> cmdlet 来验证会议目录。



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>查看合并的池中的服务

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    例如：
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>验证合并的会议目录

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsConferenceDirectory

3.  验证正在合并的池或服务器的所有会议目录现在是否在 Lync Server 2013 中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

