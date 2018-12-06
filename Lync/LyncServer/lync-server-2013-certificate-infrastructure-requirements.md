---
title: Lync Server 2013 证书基础结构要求
TOCTitle: 证书基础结构要求
ms:assetid: 0051aa23-0bbe-4e72-9f29-e01c6bcc6190
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398066(v=OCS.15)
ms:contentKeyID: 49311795
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 的证书基础结构要求

 

_**上一次修改主题：** 2016-12-08_

Lync Server 2013 需要公钥基础结构 (PKI) 来支持 TLS 连接和相互 TLS (MTLS) 连接。

Lync Server 使用证书实现以下目的：

  - 客户端和服务器之间的 TLS 连接

  - 服务器之间的 MTLS 连接

  - 使用自动发现伙伴 DNS 的联盟

  - 远程用户访问即时消息 (IM)

  - 外部用户访问音频/视频 (A/V) 会话、应用程序共享和会议

  - 使用 Web 服务的自动发现的移动请求

对于 Lync Server，需要满足以下常见要求：

  - 所有服务器证书都必须支持服务器授权（服务器 EKU）。

  - 所有服务器证书都必须包含一个 CRL 分发点 (CDP)。

  - 所有证书必须使用操作系统支持的签名算法进行签名。Lync Server 2013 支持摘要大小（224、256、384 和 512 位）的 SHA-1 和 SHA-2 套件，可满足或超过操作系统的要求。有关操作系统支持，请参阅 [http://go.microsoft.com/fwlink/?LinkId=287002](http://go.microsoft.com/fwlink/?linkid=287002)。

  - 运行 Lync Server 的内部服务器支持自动注册。

  - Lync Server 边缘服务器不支持自动注册。

  - 向 Windows Server 2003 CA 提交基于 Web 的证书请求时，必须在运行 Windows Server 2003 SP2 或 Windows XP 的计算机上进行提交。
    
    请注意，虽然 KB922706 针对 Windows Server 2003 证书服务 Web 注册为解决 Web 证书注册问题提供支持，但这并不意味着可以使用 Windows Server 2008、Windows Vista 或 Windows 7 从 Windows Server 2003 CA 请求证书。

  - 加密密钥长度为 1024、2048 和 4096。建议使用密钥长度 2048 和更大值。

  - 默认的摘要式或哈希签名算法是 RSA。还支持 ECDH\_P256、ECDH\_P384 和 ECDH\_P521 算法。

## 本部分内容

  - [Lync Server 2013 中内部服务器的证书要求](lync-server-2013-certificate-requirements-for-internal-servers.md)

  - [Lync Server 2013 中外部用户访问的证书要求](lync-server-2013-certificate-requirements-for-external-user-access.md)

  - [Lync Server 2013 中持久聊天服务器的证书要求](lync-server-2013-certificate-requirements-for-persistent-chat-server.md)

  - [Lync Server 2013 中移动的证书要求](lync-server-2013-certificate-requirements-for-mobility.md)

