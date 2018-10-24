---
title: 迁移公用区域电话
TOCTitle: 迁移公用区域电话
ms:assetid: 31bd26fc-861b-45c6-8221-18df16e575de
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688015(v=OCS.15)
ms:contentKeyID: 49888365
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移公用区域电话

 

_**上一次修改主题：** 2012-09-29_

公共区域电话是最常位于共享工作区或公共区域（例如会议厅、厨房或工厂车间）的 IP 电话。公共区域电话无需连接到计算机即可提供 Lync Server UC 功能。在将 Lync Server 2010 部署迁移到 Lync Server 2013 后，您还必须迁移与旧公共区域电话关联的联系对象。使用 Lync Server 命令行管理程序，您可以首先检索与 Lync Server 2010 公共区域电话关联的所有联系对象，然后将这些对象移动到 Lync Server 2013 池中。

**迁移公共区域电话**

1.  从 Lync Server 2013 前端服务器中，打开 Lync Server 命令行管理程序。

2.  从命令行键入：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool01.contoso.net"} | Move-CsCommonAreaPhone -Target pool02.contoso.net

3.  若要验证是否已将所有联系对象移动到 Lync Server 2013 池，请从 Lync Server 命令行管理程序中键入以下命令：
    
        Get-CsCommonAreaPhone -Filter {RegistrarPool -eq "pool02.contoso.net"}
    
    验证所有联系对象现在是否与 Lync Server 2013 池关联。

