---
title: Lync Server 2013：请求边缘组件的证书
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Request certificates for edge components
ms:assetid: 8c72b877-febc-428f-89dc-389e7a7ac849
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398708(v=OCS.15)
ms:contentKeyID: 48184779
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 473d526bbdf8f556f167c80cc3b654f336f78070
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42144929"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>在 Lync Server 2013 中请求边缘组件的证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

支持外部用户访问所需的证书包括公共证书颁发机构 (CA) 颁发的证书和内部企业 CA 颁发的证书：

  - 边缘服务器和反向代理的外部接口所需的证书必须由公共 CA 颁发。

  - 内部接口所需的证书可以由公共 CA 或内部企业 CA 颁发。 我们建议使用内部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA 或 Windows Server 2012 R2 CA 来创建这些证书，以使用公用证书的费用保存。

<div>


> [!IMPORTANT]  
> 处理证书请求可能需要花费一些时间（特别是向公共 CA 提交的请求），因此应提前请求边缘服务器的证书，以确保开始部署边缘服务器组件时证书可用。 有关边缘服务器的证书要求摘要，请参阅<A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中的外部用户访问的证书要求</A>。



</div>

虽然可以选择将公共 CA 用于内部边缘证书，但是我们建议您将内部企业 CA 用于其他证书，以将证书的成本降到最低。 有关边缘服务器的证书要求摘要，请参阅[Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>


> [!NOTE]  
> 安装边缘服务器时，安装程序会提供证书向导，以促进请求、分配和安装证书的任务，如为<A href="lync-server-2013-set-up-edge-certificates.md">Lync Server 2013 设置边缘证书</A>一节中所述。 如果要在安装边缘服务器之前请求证书（例如，在边缘服务器组件的实际部署过程中节省时间），则可以使用内部服务器执行此操作，前提是确保证书是可导出的并包含所有必需的主题备用名称。 本文档不提供使用内部服务器请求证书的过程。



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>从公共 CA 请求证书

您的边缘服务器部署需要一个公共证书，用于边缘服务器的外部接口，用于访问边缘服务、Web 会议边缘服务和 A/V 身份验证服务。 此证书必须具有可导出的私钥，以确保 A/V 身份验证服务在池中的所有边缘服务器上使用相同的密钥。 与 Microsoft Internet 安全性和加速（ISA） Server 2006 或 Microsoft Forefront 威胁管理网关2010一起使用的反向代理也需要公共证书。

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>从内部企业 CA 请求证书

内部边缘接口所需的证书可由公共证书颁发机构 (CA) 或内部 CA 颁发。使用内部企业 CA 可以帮助最大限度地降低证书成本。如果组织部署了内部 CA，则应由内部 CA 颁发内部边缘的证书。对内部证书使用内部企业 CA 可降低证书成本。

有关边缘组件的证书要求摘要，请参阅[Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。 有关使用公用 CA 获取证书的详细信息，请参阅[Lync Server 2013 中的请求证书的边缘组件](lync-server-2013-request-certificates-for-edge-components.md)。 有关请求、安装和分配证书的详细信息，请参阅[设置适用于 Lync Server 2013 的边缘证书](lync-server-2013-set-up-edge-certificates.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

