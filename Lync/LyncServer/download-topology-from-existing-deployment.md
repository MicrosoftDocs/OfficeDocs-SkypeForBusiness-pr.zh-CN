---
title: 从现有部署下载拓扑
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Download topology from existing deployment
ms:assetid: e39065a2-d4b0-4f27-8c49-f56be78fa55b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721913(v=OCS.15)
ms:contentKeyID: 49733847
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 26c47e6d78d3bd9522b8f0369924f05f8f939037
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837875"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="download-topology-from-existing-deployment"></a>从现有部署下载拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-09-29_

创建 Lync Server 2013 池时, 将使用与 Lync Server 2010 相关联的中央管理存储。 在首次使用时启动拓扑生成器和后续编辑会话时, 系统会提示你输入希望拓扑生成器加载当前配置文档的位置。 因为你已定义了 Lync Server 2010 拓扑, 并且已建立中央管理存储, 因此你应该选择从现有部署下载拓扑。 拓扑生成器将读取数据库并检索当前定义。

**从现有部署下载拓扑**

1.  打开**Lync Server 部署向导**。

2.  在 " **Lync Server 2013-部署向导**" 页面上, 单击 "**安装管理工具**"。

3.  启动拓扑生成器: 单击 "**开始**", 单击 "**所有程序**", 单击 " **Microsoft Lync server 2013** ", 然后单击 " **Lync server 拓扑生成器**"。

4.  **从现有部署中选择 "下载拓扑**"。
    
    ![部署向导拓扑生成器设置](images/JJ721913.d5b39fd9-3c13-422e-a06c-25d2568fe781(OCS.15).jpg "部署向导拓扑生成器设置")

5.  选择文件名, 并使用默认的 tbxml 文件类型保存拓扑。

6.  如图所示展开 Lync 服务器节点, 以显示部署中的各种服务器角色。
    
    ![拓扑生成器服务器角色常规属性](images/JJ721913.af99ead3-676b-47fd-8369-5a5f9717383f(OCS.15).jpg "拓扑生成器服务器角色常规属性")

</div>

<span> </span>

</div>

</div>

</div>

