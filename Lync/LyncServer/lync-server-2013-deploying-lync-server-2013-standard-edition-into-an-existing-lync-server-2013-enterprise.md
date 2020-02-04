---
title: Lync Server 2013：将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 Enterprise 中
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
ms.openlocfilehash: 6467ae9eb3c4d5159181a2d022c060b0b9f1fec9
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758016"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="deploying-lync-server-2013-standard-edition-into-an-existing-lync-server-2013-enterprise"></a>将 Lync Server 2013 Standard Edition 部署到现有 Lync Server 2013 Enterprise 中

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

将标准版服务器部署到现有企业版部署类似于部署其他服务器角色。 标准版服务器可能会部署到另一个网站，允许该网站中的用户驻留在标准版服务器上，而不是在广域网（WAN）上的前端池。 在[部署 Lync Server 2013](lync-server-2013-deploying-lync-server.md)文档的其他部分中已定义了在该网站中安装新网站和服务器的过程。

<div id="sectionSection0" class="section">

**定义新网站**

1.  启动拓扑生成器：单击 "**开始**"，单击 "**所有程序**"，单击 " **Microsoft Lync server 2013**"，然后单击 " **Lync server 拓扑生成器**"。

2.  在控制台树中，右键单击 " **Lync Server 2013**"，然后单击 "**新建中心网站**"。

3.  在 "**标识网站**" 页面上，为网站提供一个名称，并选择 "输入说明"。

4.  按照定义网站拓扑的其余部分中的过程操作。 有关详细信息，请参阅[在 Lync Server 2013 中定义和配置拓扑](lync-server-2013-defining-and-configuring-the-topology.md)。

5.  发布更新后的拓扑。 有关详细信息，请参阅[在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)。

6.  设置和安装标准版服务器。
    
    <div>
    

    > [!Caution]  
    > 如果你已使用标准版服务器部署了环境，你将从 Lync Server 部署向导开始安装过程，方法是使用 "<STRONG>准备第一个标准版服务器</STRONG>" 链接将初始数据库文件安装到新的标准版服务器。 在将标准版服务器安装到现有 Lync Server 2013 部署中时<STRONG>，请不要执行此</STRONG>过程。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

