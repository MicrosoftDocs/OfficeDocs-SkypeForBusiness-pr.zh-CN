---
title: Lync Server 2013：创建或编辑 XMPP 合作伙伴配置
TOCTitle: 创建或编辑 XMPP 合作伙伴配置
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ552447(v=OCS.15)
ms:contentKeyID: 49312479
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中创建或编辑 XMPP 合作伙伴配置

 

_**上一次修改主题：** 2016-12-08_

Microsoft Lync Server 2013 集成了 边缘服务器上的可扩展消息传递和状态协议 (XMPP) 代理以及 前端服务器或 前端池上的 XMPP 网关。若要允许从其他 XMPP 部署建立连接，您必须在 Lync Server 控制面板中配置 XMPP。您可以基于 XMPP 域配置相关设置。若要创建新的合作伙伴关联，请执行以下操作：

## 创建新的联盟伙伴或编辑现有配置

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理 URL 以打开 Lync Server 控制面板。有关可以用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅[打开 Lync Server 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中，单击“联盟和外部访问”，然后单击“XMPP 联盟伙伴”。

4.  若要创建新配置，请单击“新建”。

5.  若要编辑现有配置，请选择相应的配置，然后单击“编辑”

6.  若要为“XMPP 联盟伙伴”创建或编辑配置，请定义以下设置：

7.  “主域”（必需）。主域是 XMPP 伙伴的基域。例如，您输入 **fabrikam.com** 作为 XMPP 伙伴的域名。这是必需条目。

8.  “描述”。描述提供有关特定配置的说明或其他标识信息。此条目为可选。

9.  “其他域”。其他域是应在进行允许的 XMPP 通信时包括的 XMPP 合作伙伴域的一部分。例如，如果主域是 **fabrikam.com**，则可列出 fabrikam.com 下您将通过 XMPP 与之通信的其他所有域。例如，您可以在 fabrikam.com 的主 XMPP 域下为企业 XMPP 域和信息技术 XMPP 域分别输入 **corp.fabrikam.com** 和 **it.fabrikam.com**。

10. “合作伙伴类型”。 “合作伙伴类型”是一项必需设置，使您能够在下拉菜单中选择三个选项。您必须选择下列选项之一来描述可添加哪些联系人并强制实施此添加操作。您可以从下列选项中进行选择：
    
      - “联盟”。“联盟”合作伙伴类型是 Lync Server 或 Office Communications Server 2007 R2 合作伙伴部署之间的受信任连接。
    
      - “已公开验证”。当提供程序已经验证了属于部署一部分的联系人时，可将“已公开验证”合作伙伴添加到您的用户的联系人列表中。可以通过 Lync 用户发送邀请或者 Lync 用户也可以接受来自合作伙伴联系人的邀请。
    
      - “未公开验证”。 “未公开验证”关系表示两个部署之间不存在既定的可验证状态。Lync 用户必须邀请未经验证的联系人，该联系人才能够将 Lync 用户添加到其联系人列表中。例如，对于 Lync Server 而言，Google GTalk 不是经验证的公共 XMPP 服务。除非收到来自 Lync 用户的明确邀请，否则 GTalk 用户无法将 Lync 用户添加为联系人。

11. 有关流协商和安全机制传输层安全性 (TLS) 及软件身份验证和安全层 (SASL) 的说明：
    
    **XMPP Standards Foundation** (XSF) 和 **Internet 工程任务组** (IETF) 定义了一组使用和管理 TLS 客户端证书、TLS 服务器证书和 SASL 机制的规则和标准。使用 TLS 和 SASL 是保护 XMPP 流所必需的过程。根据 XMPP Standards 文档 **XEP-0178**，“指定将 SASL EXTERNAL 机制用于 PKIX 证书的建议的协议流，尤其是当 XMPP 服务指示将强制进行 TLS 协商时。”如 XSF 文档中所述，PKIX 是指公钥基础结构，又称 PKI。
    
    有关 XMPP 要求的更详细的信息，请参阅 XSF 文档 XEP-0178。有关详细信息，请参阅“XEP-0178：将 SASL EXTERNAL 用于证书的最佳实践”，网址为 http://xmpp.org/extensions/xep-0178.html。
    
    请参阅 IETF 文档“可扩展消息传递和状态协议 (XMPP)：核心”的 5.0 节 STARTTLS 协商，网址为 <http://tools.ietf.org/html/rfc6120>。
    
      - “TLS 协商”。 定义 TLS 协商规则。XMPP 服务可能需要 TLS，可以将 TLS 设置为可选，或者将 TLS 定义为不受支持。选择“可选”表明可以根据需要为 XMPP 服务选择强制协商选项。若要查看 SASL、TLS 和回拨协商的所有可能设置和详细信息（包括无效和已知的错误配置），请参阅 [Lync Server 2013 中 XMPP 联盟伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。
        
           “必需”。XMPP 服务需要 TLS 协商。
        
           “可选”。XMPP 服务指示 TLS 是否必须协商。
        
           “不支持”。XMPP 服务不支持 TLS。
    
      - “SASL 协商”。定义 SASL 协商规则。XMPP 服务可能需要 SASL，可以将 SASL 设置为可选，或者将 SASL 定义为不受支持。选择“可选”表明可以根据需要为合作伙伴 XMPP 服务选择强制协商选项。
        
        > [!WARNING]  
		> SASL 需要 TLS。若要使用 SASL，TLS 必须为必需或可选项。任何将 SASL 定义为“必需”或“可选”的配置都必须提供 TLS 支持。当单击“提交”保存更改时，如果未将 TLS 设为“必需”或“可选”，将警告您 SASL 必须提供 TLS 支持且无法保存您的更改。若要处理该错误，请将 TLS 设为“必需”或“可选”。如果 SASL 的使用是可选的且无法实现 TLS 协商支持，则您必须将 SASL 协商设为“不支持”。通过 XMPP 服务确认必须建立哪些适当的 TLS 和 SASL 协商流，否则将发生服务中断。
        
           “必需”。XMPP 服务需要 SASL 协商。
        
           “可选”。XMPP 服务指示 SASL 是否必须协商。
        
           “不支持”。XMPP 服务不支持 SASL。
    
      - “回拨协商”。 回拨协商由 XSF 在文档 **XEP-220：服务器回拨**<http://xmpp.org/extensions/xep-0220.html> 中定义。服务器回拨过程使用域名系统 (DNS) 和授权服务器验证请求是否来自有效的 XMPP 合作伙伴。为此，发起服务器会使用生成的回拨密钥创建一则特定类型的消息并在 DNS 中查找接收服务器。发起服务器会通过 XML 流将密钥发送到生成的 DNS 查找（可能是接收服务器）。收到通过 XML 流发送的密钥后，接收服务器不会响应发起服务器，但会将该密钥发送到已知的授权服务器。授权服务器会验证该密钥的有效性。如果无效，那么接收服务器不会响应发起服务器，如果密钥有效，则接收服务器会通知发起服务器标识和密钥有效，可以开始对话。
        
        **回拨协商**有两种有效状态：
        
           “True”。如果应从发起服务器接收请求，则 XMPP 服务器将配置为使用回拨协商
        
           “False”。XMPP 服务器不配置为使用回拨协商，并且如果应从发起服务器接收请求，将忽略该状态

