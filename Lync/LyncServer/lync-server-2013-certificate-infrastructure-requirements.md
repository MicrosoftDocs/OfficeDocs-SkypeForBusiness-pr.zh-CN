---
title: Lync Server 2013 证书基础结构要求
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate infrastructure requirements
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398066(v=OCS.15)
ms:contentKeyID: 48183219
ms.date: 06/23/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 59089e9e44110809374ef0bf11fb2dc97705d0d1
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34837661"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-infrastructure-requirements-for-lync-server-2013"></a>Lync Server 2013 的证书基础结构要求

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2016-06-23_

Lync Server 2013 需要一个公钥基础结构 (PKI) 来支持 TLS 和相互 TLS (MTLS) 连接。

Lync 服务器出于以下目的使用证书:

  - 客户端和服务器之间的 TLS 连接

  - 服务器之间的 MTLS 连接

  - 使用合作伙伴的自动 DNS 发现的联盟

  - 远程用户访问即时消息 (IM)

  - 外部用户对音频/视频 (A/V) 会话、应用程序共享和会议的访问权限

  - 使用 Web 服务的自动发现的移动请求

对于 Lync Server, 需要遵守以下常见要求:

  - 所有服务器证书都必须支持服务器授权（服务器 EKU）。

  - 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。

  - 所有证书必须使用操作系统支持的签名算法进行签名。 Lync Server 2013 支持 SHA-1 和 SHA-1 系列的摘要大小 (224、256、384和 512), 并满足或超过操作系统要求。 有关操作系统支持, 请参阅[http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)。
    
    <div>
    

    > [!NOTE]  
    > 不支持使用 RSASSA-PSS 签名算法，否则可能导致登录错误、呼叫转接问题及其他问题。

    
    </div>

  - 对于运行 Lync Server 的内部服务器, 自动注册受支持。

  - Lync Server Edge 服务器不支持自动注册。

  - 将基于 web 的证书请求提交到 Windows Server 2003 CA 时, 必须从运行 Windows Server 2003 的计算机或 Windows XP 提交该证书请求。
    
    请注意, 虽然 KB922706 提供了对使用 Windows Server 2003 证书服务 web 注册注册 web 证书的问题的支持, 但不能使用 Windows Server 2008、Windows Vista 或 Windows 7 请求来自 Windows Server 2003 CA 的证书。

  - 加密密钥长度为 1024、2048 和 4096。 建议使用密钥长度 2048 和更大值。

  - 默认的摘要式或哈希签名算法是 RSA。 还支持\_ecdh P256、\_ecdh P384 和 ecdh\_P521 算法。 

<div>

## <a name="in-this-section"></a>本节内容

  - [Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中持久聊天服务器的证书要求](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 中移动的证书要求](lync-server-2013-certificate-requirements-for-mobility.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

