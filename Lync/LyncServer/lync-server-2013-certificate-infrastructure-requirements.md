---
title: Lync Server 2013 证书基础结构要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6e8c96c6b4ad5e19abf2d1f41024932c710786cb
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/21/2020
ms.locfileid: "42191045"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的证书基础结构要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2016-06-23_

Lync Server 2013 需要一个公钥基础结构（PKI）来支持 TLS 和相互 TLS （MTLS）连接。

Lync Server 使用证书实现以下目的：

  - 客户端和服务器之间的 TLS 连接

  - 服务器之间的 MTLS 连接

  - 使用自动发现伙伴 DNS 的联盟

  - 远程用户访问即时消息 (IM)

  - 外部用户访问音频/视频 (A/V) 会话、应用程序共享和会议

  - 使用 Web 服务的自动发现的移动请求

对于 Lync Server，以下常见要求适用：

  - 所有服务器证书都必须支持服务器授权（服务器 EKU）。

  - 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。

  - 必须使用操作系统支持的签名算法对所有证书进行签名。 Lync Server 2013 支持 SHA-1 和 SHA-1 套件的摘要大小（224、256、384和512），并满足或超过操作系统要求。 有关操作系统支持，请参阅[https://go.microsoft.com/fwlink/?LinkId=287002](https://go.microsoft.com/fwlink/?linkid=287002)。
    
    <div>
    

    > [!NOTE]  
    > 不支持使用 RSASSA-PSS 签名算法，这可能会导致登录和呼叫转发问题，以及其他问题中的错误。

    
    </div>

  - 运行 Lync Server 的内部服务器支持自动注册。

  - Lync Server Edge 服务器不支持自动注册。

  - 向 Windows Server 2003 CA 提交基于 Web 的证书请求时，必须在运行 Windows Server 2003 SP2 或 Windows XP 的计算机上进行提交。
    
    请注意，虽然 KB922706 针对 Windows Server 2003 证书服务 Web 注册为解决 Web 证书注册问题提供支持，但这并不意味着可以使用 Windows Server 2008、Windows Vista 或 Windows 7 从 Windows Server 2003 CA 请求证书。

  - 支持的加密密钥长度为1024、2048和4096。 建议使用大于或等于2048的密钥长度。

  - 默认摘要或哈希签名算法为 RSA。 此外，\_还支持 ecdh\_P256、ecdh P384\_和 ECDH P521 算法。 

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中的外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中持久聊天服务器的证书要求](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 中的移动性证书要求](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

