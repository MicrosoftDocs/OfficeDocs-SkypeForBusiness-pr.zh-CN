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
ms.openlocfilehash: 096603b48e6a3636a397c4abf7c19c2b4237f132
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41763314"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="request-certificates-for-edge-components-in-lync-server-2013"></a>在 Lync Server 2013 中请求边缘组件的证书

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2013-11-07_

支持外部用户访问所需的证书包括由公共证书颁发机构（CA）颁发的证书以及由内部企业 CA 颁发的证书：

  - 边缘服务器的外部接口所需的证书和反向代理必须由公共 CA 颁发。

  - 内部接口所需的证书可以由公共 CA 或内部企业 CA 颁发。 我们建议使用内部 Windows Server 2008 CA、Windows Server 2008 R2 CA、Windows Server 2012 CA 或 Windows Server 2012 R2 CA 来创建这些证书，从而节省使用公共证书的费用。

<div>


> [!IMPORTANT]  
> 处理证书请求（尤其是对公共 Ca 的请求）的时间可能需要花费一些时间，以便你可以在开始部署 Edge 服务器组件时，尽早为你的 Edge 服务器请求证书以确保它们可用。 有关边缘服务器的证书要求摘要，请参阅<A href="lync-server-2013-certificate-requirements-for-external-user-access.md">Lync Server 2013 中的外部用户访问的证书要求</A>。



</div>

尽管你可以选择对内部边缘证书使用公共 CA，但我们建议你将内部企业 CA 用于其他证书，以将证书的费用降到最低。 有关边缘服务器的证书要求摘要，请参阅[Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。

<div>


> [!NOTE]  
> 安装边缘服务器时，安装程序包括一个证书向导，可帮助请求、分配和安装证书的任务，如 "<A href="lync-server-2013-set-up-edge-certificates.md">设置 Lync Server 2013 的边缘证书</A>" 部分中所述。 如果要在安装边缘服务器之前请求证书（例如在边缘服务器组件的实际部署期间节省时间），则可以使用内部服务器执行此操作，前提是确保证书可导出且包含所有必需的主题备用名称。 本文档不提供使用内部服务器申请证书的过程。



</div>

<div>

## <a name="request-certificates-from-a-public-ca"></a>申请来自公共 CA 的证书

您的 Edge 服务器部署需要一个用于边缘服务器的外部接口的单个公共证书，用于访问边缘服务、Web 会议 Edge 服务以及 A/V 身份验证服务。 此证书必须具有可导出的私钥，以确保 A/V 身份验证服务在池中的所有边缘服务器上使用相同的密钥。 与 Microsoft Internet 安全和加速（ISA） Server 2006 或 Microsoft Forefront 威胁管理网关2010一起使用的反向代理还需要公共证书。

</div>

<div>

## <a name="request-certificates-from-an-internal-enterprise-ca"></a>申请来自内部企业 CA 的证书

内部边缘接口所需的证书可以由公共证书颁发机构（CA）或内部 CA 颁发。 您可以使用内部企业 CA 来帮助最大限度地减少证书的费用。 如果您的组织已部署内部 CA，则内部边缘的证书应由内部 CA 颁发。 对内部证书使用内部企业 CA 可以降低证书的费用。

有关 edge 组件的证书要求的摘要，请参阅[Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)。 有关使用公共 CA 获取证书的详细信息，请参阅[在 Lync Server 2013 中为 edge 组件申请证书](lync-server-2013-request-certificates-for-edge-components.md)。 有关请求、安装和分配证书的详细信息，请参阅[设置 Lync Server 2013 的边缘证书](lync-server-2013-set-up-edge-certificates.md)。

</div>

</div>

<span> </span>

</div>

</div>

</div>

