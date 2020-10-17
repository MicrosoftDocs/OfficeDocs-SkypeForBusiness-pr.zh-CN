---
title: 导出拓扑并将其复制到外部媒体以进行边缘安装
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
ms.openlocfilehash: 5dd461e6a8ce184e5e418feddede258af68d2c25
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528369"
---
# <a name="export-your-lync-server-2013-topology-and-copy-it-to-external-media-for-edge-installation"></a>导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

发布拓扑后，Lync Server 部署向导需要访问中央管理存储数据，以便在服务器上启动部署过程。 在内部网络中，数据可直接来自服务器，但不在内部域中的边缘服务器将无法访问数据。 若要使拓扑配置数据可用于边缘服务器部署，必须将拓扑数据导出到一个文件，并将其复制到外部媒体 (例如，在边缘服务器上运行 Lync Server 部署向导之前，在边缘服务器上提供的 USB 驱动器或网络共享) 。 使用以下过程可使拓扑配置数据在要部署的边缘服务器上可用。

<div>


> [!NOTE]
> 在边缘服务器上安装 Lync Server 2013 之后，可以使用内部网络中的管理工具管理边缘服务器，这会自动将配置复制到部署中的任何边缘服务器上。 唯一的例外是分配并安装证书，并停止和启动服务，这两种情况都必须在边缘服务器上完成。



</div>

<div>

## <a name="to-make-your-topology-data-available-on-an-edge-server-by-using-lync-server-management-shell"></a>使用 Lync Server 命令行管理程序使拓扑数据在边缘服务器上可用

1.  启动 Lync Server 命令行管理程序：依次单击“开始”****、“所有程序”****、“Microsoft Lync Server 2013”**** 和“Lync Server 命令行管理程序”****。

2.  在 Lync Server 命令行管理程序中，运行以下 cmdlet：
    
        Export-CsConfiguration -FileName <ConfigurationFilePath.zip>

3.  将导出的文件复制到外部媒体 (例如，在部署) 期间，从边缘服务器获取的 USB 驱动器或网络共享。

</div>

</div>

<span> </span>

</div>

</div>

</div>

