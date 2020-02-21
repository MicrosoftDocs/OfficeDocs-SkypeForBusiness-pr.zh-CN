---
title: Lync Server 2013 证书基础结构支持
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure support
ms:assetid: 47aa5c95-eb60-4d4b-81d5-7fdaef1a1145
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425950(v=OCS.15)
ms:contentKeyID: 48184047
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dea4ea71564feca6c23c6d9e16b4ca336fa95e87
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191005"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-support-in-lync-server-2013"></a>Lync Server 2013 中的证书基础结构支持

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-11-07_

Lync Server 2013 要求使用公钥基础结构（PKI）来支持传输层安全性（TLS）和相互 TLS （MTLS）连接。 默认情况下，Lync Server 2013 配置为对客户端到服务器连接使用 TLS。 MTLS 用于服务器之间的连接。

MTLS 证书必须由适用于 Lync Server 2013 的受信任证书颁发机构（Ca）颁发。 Lync Server 支持从以下 Ca 颁发的证书：

  - 从内部 CA 颁发的证书：
    
      - Windows Server 2003 操作系统 CA
    
      - Windows Server 2008 操作系统 CA
    
      - Windows Server 2008 R2 操作系统 CA
    
      - Windows Server 2012 操作系统 CA
    
      - Windows Server 2012 R2 操作系统 CA

  - 从公共 CA 颁发的证书

与其他应用程序和服务器（如 Exchange 2013）的通信需要其他应用程序和产品支持的证书。 对于2013版本，Lync Server 2013 和其他 Microsoft Server 产品（包括 Exchange 2013 和 SharePoint Server）支持用于服务器到服务器身份验证和授权的开放授权（OAuth）协议。 有关详细信息，请参阅部署文档或操作文档中的[管理 Lync server 2013 中的服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。

对于运行 Windows 7 操作系统、Windows Server 2008 R2 操作系统和 Microsoft Office Communicator 2007 Phone Edition 的客户端的连接，Lync Server 2013 支持使用 SHA-256 对（但不需要）证书进行签名加密哈希函数。 要支持使用 SHA-256 进行外部访问，外部证书必须由公共 CA 使用 SHA-256 颁发。

有关证书要求的详细信息，请参阅规划文档中的[Lync Server 2013 的证书基础结构要求](lync-server-2013-certificate-infrastructure-requirements.md)。 有关在证书中使用通配符的详细信息，请参阅可支持性文档中的[Lync Server 2013 中的通配符证书支持](lync-server-2013-wildcard-certificate-support.md)。

</div>

<span> </span>

</div>

</div>

</div>

