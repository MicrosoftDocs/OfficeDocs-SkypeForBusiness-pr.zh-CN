---
title: 从现有部署下载拓扑
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 66b68459a1923fcb4a066cafe02c5226b24f9321
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2020
ms.locfileid: "42006408"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>从现有部署下载拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-09-29_

创建 Lync Server 2013 池时，将使用与 Lync Server 2010 关联的中央管理存储。 因第一次使用而启动拓扑生成器并随后编辑会话时，系统会提示您要使拓扑生成器加载当前配置文档的位置。 由于已定义了 Lync Server 2010 拓扑，并且已建立了中央管理存储，因此应选择从现有部署下载拓扑。 拓扑生成器将读取数据库并检索当前的定义。

**从现有部署下载拓扑**

1.  打开“Lync Server 部署向导”****。

2.  从“Lync Server 2013 – 部署向导”**** 页面，单击“安装管理工具”****。

3.  启动拓扑生成器：依次单击 "**开始**"、"**所有程序**"、" **Microsoft Lync server 2013** "，然后单击 " **Lync server 拓扑生成器**"。

4.  选择“从现有部署下载拓扑”****。
    
    ![部署向导拓扑生成器设置](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "部署向导拓扑生成器设置")

5.  使用默认的 .tbxml 文件类型选择文件名并保存该拓扑。

6.  展开 Lync Server 节点（如图所示），在部署中查看各种服务器角色。
    
    ![拓扑生成器服务器角色常规属性](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "拓扑生成器服务器角色常规属性")

</div>

<span> </span>

</div>

</div>

</div>

