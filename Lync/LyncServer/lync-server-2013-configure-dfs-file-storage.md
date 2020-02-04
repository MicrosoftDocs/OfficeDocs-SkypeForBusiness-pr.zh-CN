---
title: Lync Server 2013：配置文件存储
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DFS file storage
ms:assetid: a985be20-5a00-4f38-b45b-83dc82de3827
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205150(v=OCS.15)
ms:contentKeyID: 48185037
ms.date: 05/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1bbb932a602ad1fc49907be9c5ab2777bc7a415f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739332"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dfs-file-storage-for-lync-server-2013"></a>为 Lync Server 2013 配置文件存储

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2016-05-23_

Lync Server 2013 支持在分布式文件系统（DFS）上使用文件共享。 有关 DFS for Windows Server 2008 的详细信息，请参阅 Windows Server 2008 的 DFS 分步指南[http://go.microsoft.com/fwlink/p/?linkId=202835](http://go.microsoft.com/fwlink/p/?linkid=202835)。要使用 DFS，Lync Server 2013 需要满足以下要求：

  - 命名空间是基于域的

  - 所有命名空间服务器至少运行 Windows 2008

Lync Server 2013 安装程序要求共享文件夹的权限允许对管理员拥有完全访问权限。 然后，Lync Server 2013 将使用 NTFS 文件权限来对文件夹进行 ACL。 继承的 DFS 共享权限将不会用于限制访问。

有关文件共享要求的更多详细信息，请参阅支持文档中的[Lync Server 2013 中的文件存储支持](lync-server-2013-file-storage-support.md)。

<div>


> [!NOTE]  
> 您可能正在寻找有关配置非 DFS 共享的信息。 如果是，请查看<A href="lync-server-2013-hardware-setup.md">Lync Server 2013 的硬件设置</A>。



</div>

以下过程介绍了如何使用 DFS 命名空间向导正确配置共享文件夹权限（如 DFS 安装指南中所述）。

<div>

## <a name="to-configure-shared-folder-permissions"></a>配置共享文件夹权限

1.  单击 "**开始**"，指向 "**所有程序**"，指向 "**管理工具**"，然后单击 " **DFS 管理**"。

2.  在 "DFS 管理" 管理单元的控制台树中，右键单击命名空间服务器（例如 filesrv1.contoso.com），然后单击 "**编辑设置**"。

3.  选择 "**共享文件夹权限**"。

4.  选择 "**使用自定义权限**"。

5.  对于 "管理员" 组，在 "**允许**" 下选择下列内容：
    
      - **完全控制**
    
      - **更改**
    
      - **继续**

6.  单击 "**应用**"，然后单击 **"确定"**。

</div>

</div>

<span> </span>

</div>

</div>

</div>

