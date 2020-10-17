---
title: Lync Server 2013：发布更新后的拓扑
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Publish the updated topology
ms:assetid: 59455dd1-6a9e-433f-a714-d3636c068100
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204910(v=OCS.15)
ms:contentKeyID: 48184203
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2f696b06f317ac20b98a14734f1eaf076105dbd8
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48512309"
---
# <a name="publish-the-updated-topology-in-lync-server-2013"></a>在 Lync Server 2013 中发布更新后的拓扑

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-01_

在拓扑生成器中更新拓扑之后，您必须先将拓扑发布到中央管理存储，然后才能配置和使用持久聊天服务器。 数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。

<div>

## <a name="to-publish-an-updated-topology"></a>发布更新后的拓扑

在发布拓扑之前，请安装持久聊天服务器的数据库。 使用拓扑生成器，通过选择 " **操作** " 和 " **安装数据库**" 来安装数据库。

1.  在运行 Lync Server 2013 或安装了 Lync Server 管理工具的计算机上，使用属于 **Domain Admins** 组和 **RTCUniversalServerAdmins** 组成员的帐户登录。并且具有完全控制权限 (该文件存储中的) 用于持久聊天服务器文件存储 (，以便拓扑生成器可以配置所需的任意自由访问控制列表 (dacl) # A5 或具有等效用户权限的帐户。

2.  启动拓扑生成器。 选择“从现有部署下载拓扑”**** 或“从本地文件打开拓扑”****（如果在本地保存它）。

3.  在控制台树中，右键单击 " **Lync Server 2013**"，然后单击 " **发布拓扑**"。

4.  在“发布拓扑”**** 页上，单击“下一步”****。

5.  在“发布向导完成”**** 页上，确认已成功发布拓扑，然后单击“完成”****。
    
    <div>
    

    > [!IMPORTANT]  
    > 发布拓扑后，您必须先配置持久聊天服务器的支持，然后才能存档任何内容。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

