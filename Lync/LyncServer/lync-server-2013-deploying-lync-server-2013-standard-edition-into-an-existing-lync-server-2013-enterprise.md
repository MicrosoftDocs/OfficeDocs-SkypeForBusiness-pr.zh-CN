---
title: Lync Server 2013：将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 企业版
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Deploying Lync Server 2013 Standard Edition into an existing Lync Server 2013 Enterprise
ms:assetid: 05ea128d-6c94-49b3-b28b-477367196425
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398112(v=OCS.15)
ms:contentKeyID: 48183297
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 733dcadc52550c665cc74407a81cddbfbd5ea640
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42195365"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 企业版

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

将 Standard Edition 服务器部署到现有的企业版部署类似于部署其他服务器角色。 可以将 Standard Edition 服务器部署到另一个站点，从而允许该站点中的用户驻留在标准版服务器（而不是跨广域网（WAN）的前端池）上。 在[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)文档的其他部分中已定义了在该网站中安装新网站和服务器的过程。

<div id="sectionSection0" class="section">

**定义新站点**

1.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中，右键单击 " **Lync Server 2013**"，然后单击 "**新建中央站点**"。

3.  在“标识站点”**** 页上，命名站点并选填说明。

4.  按照相应的过程定义站点拓扑的其余部分。 有关详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

5.  发布更新的拓扑。 有关详细信息，请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。

6.  设置和安装 Standard Edition server。
    
    <div>
    

    > [!Caution]  
    > 如果已使用 Standard Edition server 部署了环境，则可以通过使用 "<STRONG>准备第一个 Standard edition server</STRONG> " 链接从 Lync Server 部署向导开始安装过程，具体方法是将初始数据库文件安装到新的 Standard edition server。 将 Standard Edition 服务器安装到现有 Lync Server 2013 部署中时，<STRONG>请勿</STRONG>遵循此过程。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

