---
title: Lync Server 2013：准备 Active Directory 架构
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing the Active Directory schema
ms:assetid: 067726ae-fd3f-4133-a32f-26d2603ac674
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398119(v=OCS.15)
ms:contentKeyID: 48183300
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4d98f7ba4ac0f2efe8a78ebcaacdc966ac5fdf3a
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050494"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-the-active-directory-schema-in-lync-server-2013"></a>在 Lync Server 2013 中准备 Active Directory 架构

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-08-27_

在开始准备 Active Directory 域服务之前，可以使用文本编辑器（如 Windows 记事本）打开架构文件，或者查看[Lync server 2013 使用的 Active directory 架构扩展、类和属性](lync-server-2013-active-directory-schema-extensions-classes-and-attributes-used-by-lync-server.md)，以检查将为 Lync server 2013 修改的所有 Active Directory 域服务架构扩展。 Lync Server 使用四个架构文件：

  - ExternalSchema 用于与 Microsoft Exchange Server 的互操作性

  - ServerSchema，它是主 Lync Server 2013 架构文件

  - BackCompatSchema.ldf，用于实现与以前版本中任何组件的互操作性

  - VersionSchema.ldf，用于所准备架构的版本信息

所有 .ldf 文件都是在架构准备期间安装的，无论是从以前的版本中进行迁移还是执行全新安装。 这些架构文件按上列表中显示的顺序安装，位于安装媒体上的 " \\支持\\架构" 文件夹中。

Lync Server 架构扩展在所有域之间进行复制，这会影响网络流量。 请在网络利用率较低时运行架构准备。

<div>


> [!NOTE]  
> 如果需要将 Microsoft® Office Communicator Mobile 2007 R2 for Java 和 Microsoft® Office Communicator Mobile for Nokia 1.0 移动客户端添加到 Lync Server 2013 部署的支持，您需要为 Microsoft Office 准备 Active Directory 架构在安装 Lync Server 2013 期间通信服务器 2007 R2。 有关必需的软件和文档，请<A href="http://go.microsoft.com/fwlink/p/?linkid=207172">http://go.microsoft.com/fwlink/p/?linkId=207172</A>参阅。



</div>

<div>

## <a name="adsi-edit"></a>ADSI Edit

Active Directory Service Interfaces Editor (ADSI Edit) 是一个 AD DS 管理工具，可以用来验证架构准备和复制。

安装 AD DS 角色以使服务器成为域控制器时，会默认安装 ADSI Edit。 对于 Windows Server 2008 和 Windows Server 2008 R2，ADSI 编辑（adsiedit）包含在远程服务器管理工具（RSAT）中。 还可以在域成员服务器或独立服务器上安装 RSAT。 默认情况下，RSAT 包会在安装 Windows 时复制到这些服务器，但默认情况下不安装该包。 请使用服务器管理器安装各个工具。 ADSI Edit 包括在 **“角色管理工具”**、**“Active Directory 域服务工具”**、**“Active Directory 域控制器工具”** 下。

对于 Windows Server 2003，ADSI Edit 随附在支持工具中。 支持工具可从 Windows Server 2003 CD 中的 "支持\\\\工具" 文件夹中获取，也可从 "Windows server 2003 Service Pack 2 32-位支持工具" 下载。 [http://go.microsoft.com/fwlink/p/?linkId=125770](http://go.microsoft.com/fwlink/p/?linkid=125770) 有关从产品 CD 安装支持工具的说明，可参阅 "安装 Windows 支持工具" [http://go.microsoft.com/fwlink/p/?linkId=125771](http://go.microsoft.com/fwlink/p/?linkid=125771)。 安装支持工具时，Adsiedit.dll 会自动注册。 但是，如果已经将文件复制到您的计算机，则您必须在您可运行工具之前运行 **regsvr32** 命令注册 adsiedit.dll 文件。

</div>

<div>

## <a name="in-this-section"></a>本部分内容

  - [在 Lync Server 2013 中运行 Active Directory 架构准备](lync-server-2013-running-schema-preparation.md)

  - [在 Lync Server 2013 中验证 Active Directory 架构复制](lync-server-2013-verifying-schema-replication.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[准备 Lync Server 2013 的林](lync-server-2013-preparing-the-forest.md)  
[准备 Lync Server 2013 的域](lync-server-2013-preparing-domains.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

