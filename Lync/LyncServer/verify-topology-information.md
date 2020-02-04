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
ms.openlocfilehash: ec6c73f274cb67b527aaf1147f20e83959487255
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730832"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-topology-information"></a>验证拓扑信息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-26_

成功完成合并验证的第一步是查看您与 Lync Server 2013 合并的 Office 通信服务器 2007 R2 拓扑信息。 在拓扑生成器中， **BackCompatSite**节点显示你合并的每个 Office 通信服务器 2007 R2 池和服务器的完全限定的域名（FQDN）。

<div>

## <a name="to-view-backcompatsite-in-topology-builder"></a>在拓扑生成器中查看 BackCompatSite

1.  在 Office 通信服务器 2007 R2 环境中，打开 Office 通信服务器 2007 R2 管理工具并注意旧池和服务器的 Fqdn。

2.  在 Lync Server 2013 环境中，打开拓扑生成器，然后展开 " **BackCompatSite** " 节点。

3.  验证是否显示你合并的池和服务器的 Fqdn。
    
    <div>
    

    > [!NOTE]  
    > 对于 collocated 在前端服务器或标准版服务器上的服务器角色，你看不到<STRONG>BackCompatSite</STRONG>中的任何信息。 仅显示 Office 通信服务器 2007 R2 与 Lync Server 2013 之间的互操作性所需的服务器角色。

    
    </div>

![拓扑生成器 "BackCompatSite" 对话框](images/JJ205243.62751c76-f018-4c6d-bb48-c61ef8974d31(OCS.15).jpg "拓扑生成器 "BackCompatSite" 对话框")

您也可以使用 Lync Server 2013 控制面板查看合并拓扑。 在 Lync Server 2013 控制面板中，你可以查看你的合并拓扑的每个服务器 FQDN、池 FQDN 和网站名称。 合并服务器具有**BackCompatSite**的**网站**名称。

</div>

<div>

## <a name="to-view-the-merged-topology-in-lync-server-2013-control-panel"></a>在 Lync Server 2013 "控制面板" 中查看合并的拓扑

1.  打开 "Lync Server 2013 控制面板"。

2.  单击 "**拓扑**"。

3.  在 "**状态**" 选项卡上，通过查找 "**网站**" 列中的 " **BackCompatSite** " 验证是否显示已合并的服务器和池。

![显示合并拓扑的 Lync Server "控制面板"](images/JJ205151.f986ddd4-2040-454d-9389-7f6154b59cc9(OCS.15).jpg "显示合并拓扑的 Lync Server "控制面板"")

若要查看有关合并池的更多详细信息，请使用**CsPool** cmdlet。 除了拓扑生成器和 Lync Server 2013 控制面板中提供的信息外，此 cmdlet 还会显示在 Lync Server 2013 池中运行的服务。

<div>


> [!NOTE]  
> 在拓扑生成器中运行合并向导后发布拓扑时，会议目录将合并到 Lync Server 2013。 可以通过运行<STRONG>CsConferenceDirectory</STRONG> cmdlet 来验证会议目录。



</div>

</div>

<div>

## <a name="to-view-services-on-a-merged-pool"></a>查看合并池上的服务

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsPool [-Identity <FQDN of the pool>]
    
    例如：
    
        Get-CsPool -Identity pool02.contoso.net

</div>

<div>

## <a name="to-verify-conference-directories-merged"></a>验证已合并的会议目录

1.  打开 Lync Server 2013 命令行管理程序。

2.  在命令行中键入：
    
        Get-CsConferenceDirectory

3.  验证正在合并的池或服务器的所有会议目录是否现在位于 Lync Server 2013 中。

</div>

</div>

<span> </span>

</div>

</div>

</div>

