---
title: Lync Server 2013：发布拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish your topology
ms:assetid: bfed3829-7a54-4b5c-a7cb-28871acd35e7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412935(v=OCS.15)
ms:contentKeyID: 48185287
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 591942ae8b3df74e14e254e984cd322239c4d7e6
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42138953"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="publish-your-topology-in-lync-server-2013"></a>在 Lync Server 2013 中发布拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-08_

每次使用拓扑生成器构建拓扑时，都必须将拓扑发布到中央管理存储中的数据库，以便可以使用这些数据来部署 Lync Server 2013。 请使用以下过程发布拓扑。

<div>

## <a name="to-publish-the-topology"></a>发布拓扑

1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在拓扑生成器中的控制台树中，右键单击 " **Lync 2013**"，然后单击 "**发布拓扑**"。

3.  在向导的“欢迎”**** 页上，单击“下一步”****。

4.  在“拓扑生成器找到 CMS 存储”**** 页上，单击“下一步”****。

5.  在“创建其他数据库”**** 页上，单击“下一步”****。

6.  当状态指示成功创建数据库时，执行以下操作：
    
      - 要查看日志，请单击“查看日志”****。
    
      - 要关闭向导，请单击“完成”****。
        
        <div>
        

        > [!IMPORTANT]  
        > 如果这是边缘服务器或边缘池的全新安装，则必须从现有前端服务器、前端池或 Standard Edition 服务器导出边缘服务器配置。 若要导出配置，请参阅<A href="lync-server-2013-export-your-topology-and-copy-it-to-external-media-for-edge-installation.md">导出 Lync Server 2013 拓扑并将其复制到外部媒体以进行边缘安装</A>。 您将通过 Lync Server 部署向导在边缘服务器的安装和部署阶段导入外部媒体或网络共享中的配置文件。<BR>在边缘服务器可正常运行且本地配置管理存储数据库与内部部署进行复制之后，将发布对 Lync Server 2013 配置的后续更新并将其复制到边缘服务器。

        
        </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

