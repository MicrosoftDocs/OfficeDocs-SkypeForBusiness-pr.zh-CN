---
title: 'Lync Server 2013：提前请求证书 (可选) '
description: Lync Server 2013：提前请求证书 (可选) 。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates in advance (optional)
ms:assetid: 9d6d7de6-ff2a-46da-b1b7-a354c8e383e4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412733(v=OCS.15)
ms:contentKeyID: 48184915
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7d92ac9b68012487d07f25f08649689611117202
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48579028"
---
# <a name="request-certificates-in-advance-optional-for-lync-server-2013"></a> (Lync Server 2013 的可选) 提前请求证书

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-21_

所有运行 Lync Server 2013 的内部服务器都需要证书，包括每个 Enterprise Edition 前端服务器、Standard Edition server、Director、Edge 服务器和独立中介服务器。 虽然建议对内部服务器使用内部企业证书颁发机构 (CA)，但您也可以使用公共 CA。 有关证书要求和公用 CA 使用的详细信息，请参阅规划文档中的 [Lync Server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md) 。

Lync Server 2013 安装程序包括证书向导，该向导可促进在部署过程中请求、分配和安装证书的任务。 如果要在安装服务器之前请求证书 (例如，为了在服务器的实际部署) 中节省时间，您可以通过使用安装了 Lync Server 2013 管理工具的计算机或使用组织中定义的证书请求过程来执行此操作，前提是确保证书是可导出的并包含所有必需的主题备用名称。 提前请求证书是可选的。 如果你未提前请求，则必须将其作为需要证书的每个服务器的安装程序的一部分进行请求。

此部署文档提供了使用证书向导作为安装过程的一部分请求证书的过程，如在 lync server [2013 中配置服务器的证书](lync-server-2013-configure-certificates-for-servers.md)、 [在 lync server 2013 中为控制器配置证书](lync-server-2013-configure-certificates-for-the-director.md)以及在此部署文档的 [Lync Server 2013 部分中安装中介服务器的文件](lync-server-2013-install-the-files-for-mediation-server.md) 中所述。 如果提前请求证书，则必须适当修改上述各节中的证书部署过程，以导入和分配证书，而不是在部署时请求证书。

<div>


> [!NOTE]  
> Lync Server 2013 支持从运行 Windows Vista、Windows Server &nbsp; 2008、Windows server 2008 R2 和 Windows 7 操作系统的客户端连接到 SHA-256 证书， &nbsp; &nbsp; 以及 lync Phone Edition。 要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。



</div>

</div>

<span> </span>

</div>

</div>

</div>

