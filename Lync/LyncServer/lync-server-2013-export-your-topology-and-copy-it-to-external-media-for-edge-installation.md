---
title: 导出拓扑并将其复制到外部媒体以用于边缘安装
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Export your topology and copy it to external media for edge installation
ms:assetid: def9f416-c519-4a72-b242-7d3057d9c1fd
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398983(v=OCS.15)
ms:contentKeyID: 48185615
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 8eb8f20e7af8cbfd772226917b027a33a688a4a5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756206"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>导出 Lync Server 2013 拓扑并将其复制到外部媒体以用于边缘安装

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-09-08_

发布拓扑后，Lync Server 部署向导需要访问中央管理存储数据才能在服务器上启动部署过程。 在内部网络中，数据直接来自服务器，但是不在内部域中的边缘服务器无法访问数据。 若要使拓扑配置数据可用于 Edge 服务器部署，必须将拓扑数据导出到一个文件，然后在运行 Lync Server Dep 之前将其复制到外部媒体（例如，从 Edge 服务器提供的 USB 驱动器或网络共享）边缘服务器上的 loyment 向导。 使用以下过程可使拓扑配置数据在要部署的边缘服务器上可用。

<div>


> [!NOTE]
> 在边缘服务器上安装 Lync Server 2013 后，可以使用内部网络中的管理工具管理边缘服务器，这会自动将配置复制到部署中的任何边缘服务器。 唯一的例外是分配和安装证书以及停止和启动服务，这两者都必须在 Edge 服务器上完成。



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序使拓扑数据在 Edge 服务器上可用

1.  启动 Lync Server 命令行管理程序：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server Management shell**"。

2.  在 Lync Server 命令行管理器中，运行以下 cmdlet：
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  将导出的文件复制到外部媒体（例如，在部署期间从 Edge 服务器中可用的 USB 驱动器或网络共享）。

</div>

</div>

<span> </span>

</div>

</div>

</div>

