---
title: Lync Server 2013：发布更新的拓扑
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
ms.openlocfilehash: 4500d12c7b0a054ccce910f27c80f9aaa83eccaf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747062"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="publish-the-updated-topology-in-lync-server-2013"></a>在 Lync Server 2013 中发布更新的拓扑

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-01_

在拓扑生成器中更新拓扑后，必须先将拓扑发布到中央管理存储，然后才能配置和使用持久聊天服务器。 数据的只读副本将复制到拓扑中的所有服务器，使所有服务器与拓扑和其他配置更改保持同步。

<div>

## <a name="to-publish-an-updated-topology"></a>发布已更新的拓扑

在发布拓扑之前，请安装持久聊天服务器的数据库。 使用拓扑生成器，通过选择 "**操作**" 并**安装数据库**来安装数据库。

1.  在运行 Lync Server 2013 或安装了 Lync Server 管理工具的计算机上，使用 "**域管理员**" 组和 " **RTCUniversalServerAdmins** " 组的成员进行登录，并在要用于持久聊天服务器文件存储的文件存储上具有 "完全控制" 权限（即 "读取"、"写入" 和 "修改"），以便拓扑生成器可以配置所需的随机访问控制列表（dacl）或具有等效用户权限的帐户。

2.  启动拓扑生成器。 **从现有部署**中选择 "下载拓扑"，或者**从本地文件中打开拓扑**（如果在本地保存）。

3.  在控制台树中，右键单击 " **Lync Server 2013**"，然后单击 "**发布拓扑**"。

4.  在“**发布拓扑**”页上，单击“**下一步**”。

5.  在“**发布向导完成**”页上，确认已成功发布拓扑，然后单击“**完成**”。
    
    <div>
    

    > [!IMPORTANT]  
    > 发布拓扑后，您必须配置对持久聊天服务器的支持，然后才能存档任何内容。

    
    </div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

