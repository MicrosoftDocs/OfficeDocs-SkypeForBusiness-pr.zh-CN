---
title: Lync Server 2013：准备 Active Directory 架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5479bfbb0774ddd68015de470de082f0cc185b98
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823957"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>在 Lync Server 2013 中准备 Active Directory 架构

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2012-08-27_

在开始准备 Active Directory 域服务之前, 可以使用文本编辑器 (如 Windows 记事本) 打开架构文件, 或者查看[由 Lync Server 2013 使用的 Active Directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)以查看所有活动将针对 Lync Server 2013 进行修改的 Directory 域服务架构扩展。 Lync 服务器使用四个架构文件:

  - ExternalSchema 用于与 Microsoft Exchange Server 的互操作性

  - ServerSchema, 它是主 Lync Server 2013 架构文件

  - BackCompatSchema 用于与以前版本中的任何组件的互操作性

  - VersionSchema 用于预准备架构的版本信息

无论是从以前的版本迁移还是执行全新安装, 都将在架构准备期间安装所有 .ldf 文件。 这些架构文件按照前面列表中显示的顺序安装, 位于安装媒体上的 " \\支持\\架构" 文件夹中。

Lync Server 架构扩展跨所有域复制, 这会影响网络流量。 当网络使用率较低时, 请一次运行架构准备。

<div>


> [!NOTE]  
> 如果需要将 Microsoft® Office Communicator Mobile 2007 R2 for Java 和 Microsoft® Office Communicator Mobile for Nokia 1.0 移动客户端的支持添加到 Lync Server 2013 部署, 你需要准备 Active Directory 架构 for Microsoft Office在安装 Lync Server 2013 期间通信服务器 2007 R2。 有关必需的软件和文档, 请<A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>参阅。



</div>

<div>

## <a name="adsi-edit"></a>ADSI 编辑器

Active Directory 服务界面编辑器 (ADSI Edit) 是一个 AD DS 管理工具, 可用于验证架构准备和复制。

安装 AD DS 角色以使服务器成为域控制器时, 默认情况下会安装 "ADSI 编辑"。 对于 Windows Server 2008 和 Windows Server 2008 R2, "ADSI 编辑" (adsiedit) 将包含在远程服务器管理工具 (RSAT) 中。 您也可以在域成员服务器或独立服务器上安装 RSAT。 默认情况下, 将在安装 Windows 时将 RSAT 程序包复制到这些服务器, 但默认情况下不会安装该程序包。 使用服务器管理器安装单个工具。 "**角色管理工具**"、" **Active Directory 域服务工具**"、" **active directory 域控制器工具**" 下包含 "ADSI 编辑"。

对于 Windows Server 2003, "支持工具" 中附带了 "ADSI 编辑"。 支持工具可从 Windows Server 2003 CD 的 "支持\\\\工具" 文件夹中获得, 也可从 "Windows server 2003 Service Pack 2 32 位支持工具" 下载。 [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770) 有关从产品 CD 安装支持工具的说明, 请访问 "安装 Windows 支持工具" [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)。 在安装支持工具时, 将自动注册 Adsiedit。 但是, 如果您已将文件复制到计算机, 则必须运行**regsvr32**命令来注册 adsiedit .dll 文件, 然后才能运行该工具。

</div>

<div>

## <a name="in-this-section"></a>本节内容

  - [在 Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md)

  - [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[为 Lync Server 2013 准备林](lync-server-2013-preparing-the-forest.md)  
[为 Lync Server 2013 准备域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

