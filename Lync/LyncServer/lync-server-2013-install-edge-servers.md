---
title: Lync Server 2013：安装边缘服务器
description: Lync Server 2013：安装边缘服务器。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Install Edge Servers
ms:assetid: 1655ab69-3899-4ee4-a1cc-8243bc1bfa0f
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398230(v=OCS.15)
ms:contentKeyID: 48183503
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e699a7f41b0ee554bc85fb2d9a72a2d9a42870cb
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48559578"
---
# <a name="install-edge-servers-for-lync-server-2013"></a>安装适用于 Lync Server 2013 的边缘服务器

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

您可以使用 Lync Server 部署向导在边缘服务器上安装 Lync Server 2013。 通过在每台边缘服务器上运行部署向导，可以完成设置边缘服务器所需的大部分任务。 若要在边缘服务器上部署 Lync Server 2013，必须已运行拓扑生成器以定义和发布边缘服务器拓扑，并将其导出到边缘服务器上提供的媒体。 有关详细信息，请参阅 [Lync server 2013 中的外部用户访问应用场景](lync-server-2013-scenarios-for-external-user-access.md) 和 [导出 Lync server 2013 拓扑，并将其复制到外部媒体以进行边缘安装](lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md)。

使用部署向导安装每台边缘服务器、安装和分配所需的证书并启动所需的服务后，您可以使用在 [Lync server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md) 来启用和配置外部用户访问，以及在 [lync Server 2013 中验证边缘部署](lync-server-2013-verifying-your-edge-deployment.md) 中的信息来验证安装程序（包括服务器和客户端连接），以完成安装程序。

<div>

## <a name="to-install-an-edge-server"></a>安装边缘服务器

1.  以本地 Administrators 组成员的身份或使用具有等效用户权限的帐户登录到要安装边缘服务器的计算机。

2.  确保使用拓扑生成器创建的拓扑配置文件，然后将其导出并复制到外部媒体中，该文件在边缘服务器上可用 (例如，访问复制拓扑配置文件的 USB 驱动器，或验证对在其中复制文件) 的网络共享的访问权限。

3.  启动部署向导。
    
    <div>
    

    > [!NOTE]  
    > 如果收到需要安装 Microsoft Visual C++ 可再发行软件包的消息，请单击“是”<STRONG></STRONG>。在下一个对话框中，接受默认的“安装位置”<STRONG></STRONG>或单击“浏览”<STRONG></STRONG>选择备用位置，然后单击“安装”<STRONG></STRONG>。在下一个对话框中，选中“我接受许可协议中的条款”<STRONG></STRONG>复选框，然后单击“确定”<STRONG></STRONG>。

    
    </div>

4.  在部署向导中，单击“安装或更新 Lync Server 系统”****。

5.  向导确定部署状态后，对于“步骤 1. 安装本地配置存储”****，单击“运行”****，然后执行以下操作：
    
      - 在“配置中央管理存储的本地副本”**** 对话框中，单击“从文件导入(建议用于边缘服务器)”****，转到拓扑配置文件导出到的位置，选择 .zip 文件，单击“打开”****，然后单击“下一步”****。
    
      - 部署向导从配置文件读取配置信息，并将 XML 配置文件写入本地计算机。
    
      - “正在执行命令”**** 过程完成后，单击“完成”****。

6.  在部署向导中，单击 " **步骤2：设置" 或 "删除 Lync Server 组件** "，以安装在存储在本地计算机上的 XML 配置文件中指定的 lync server 2013 edge 组件。

7.  完成安装后，请使用为 [Lync Server 2013 设置边缘证书](lync-server-2013-set-up-edge-certificates.md) 中的信息，以便在启动服务之前安装和分配所需的证书。

</div>

</div>

<span> </span>

</div>

</div>

</div>

