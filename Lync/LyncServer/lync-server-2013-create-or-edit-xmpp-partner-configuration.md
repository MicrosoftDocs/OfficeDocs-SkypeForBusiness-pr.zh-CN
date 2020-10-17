---
title: Lync Server 2013：创建或编辑 XMPP 合作伙伴配置
description: Lync Server 2013：创建或编辑 XMPP 合作伙伴配置。
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 19289df1920287984f104bb1bdfa214d6f83f5cf
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553868"
---
# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中创建或编辑 XMPP 合作伙伴配置

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2014-09-03_

Microsoft Lync Server 2013 集成了可扩展消息和状态协议 (XMPP 的边缘服务器上的代理) 代理，以及前端服务器或前端池上的 XMPP 网关。 若要允许来自其他 XMPP 部署的连接，必须在 Lync Server 控制面板中配置 XMPP。 您可以基于 XMPP 域配置相关设置。 若要创建新的合作伙伴关联，请执行以下操作：

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>创建新的联盟伙伴或编辑现有配置

1.  从作为 RTCUniversalServerAdmins 组成员的用户帐户 (或具有等效的用户权限) 或分配给 CsAdministrator 角色，请登录到内部部署中的任何计算机。

2.  打开浏览器窗口，然后输入管理员 URL 以打开 "Lync Server 控制面板"。 有关可用于启动 Lync Server 控制面板的不同方法的详细信息，请参阅 [Open Lync server 2013 "管理工具](lync-server-2013-open-lync-server-administrative-tools.md)"。

3.  在左侧导航栏中，单击“联盟和外部访问”****，然后单击“XMPP 联盟伙伴”****。

4.  若要创建新配置，请单击“新建”****。

5.  若要编辑现有配置，请选择相应的配置，然后单击“编辑”****

6.  若要为“XMPP 联盟伙伴”**** 创建或编辑配置，请定义以下设置：

7.  **主域** (必需的) 。 主域是 XMPP 合作伙伴的基本域。 例如，可为 XMPP 合作伙伴域名输入 **fabrikam.com**。 这是必填项。

8.  **说明**。 该说明针对此特定配置的注释或其他标识信息。 此条目是可选的。

9.  **其他域**。 其他域是作为 XMPP 合作伙伴的域一部分的域，应作为允许的 XMPP 通信的一部分包括在内。 例如，如果主域为 **fabrikam.com**，则将列出位于 fabrikam.com 中的所有其他域，您将使用 XMPP 的方式进行通信。 例如，可以在 fabrikam .com 的主 XMPP 域下输入公司 XMPP 域和信息技术 XMPP 域的 **corp.fabrikam.com** 和 **it.fabrikam.com** 。

10. **合作伙伴类型**。 " **合作伙伴类型** " 是必需的设置，可让您选择下拉菜单中的三个选项。 您必须选择以下项之一来描述和强制添加可添加的联系人。 您可以从以下选项中进行选择：
    
      - **联合**。 **联合**合作伙伴类型是 Lync Server 或 Office 通信服务器 2007 R2 合作伙伴部署之间的受信任连接。
    
      - **公共验证**。 已 **验证公众** 的合作伙伴是指由提供商验证的部署中的联系人可以添加到用户的联系人列表中。 可以从 Lync 用户发送邀请，也可以通过 Lync 用户接受来自合作伙伴联系人的邀请。
    
      - **公共未验证**。 **公共未验证**关系表示两个部署之间没有已建立且可验证的状态。 Lync 用户必须邀请该联系人的未验证联系人能够将 Lync 用户添加到其联系人列表。 例如，Google GTalk 不是一个公开验证的 XMPP 服务，因为它与 Lync Server 相关。 除非从 Lync 用户发送了明确的邀请，否则 GTalk 用户将无法将 Lync 用户添加为联系人。

11. 有关流协商和安全机制传输层安全性 (TLS) 及软件身份验证和安全层 (SASL) 的说明：
    
    **XMPP Standards Foundation** (XSF) 和 **Internet 工程任务组** (IETF) 定义了一组使用和管理 TLS 客户端证书、TLS 服务器证书和 SASL 机制的规则和标准。使用 TLS 和 SASL 是保护 XMPP 流所必需的过程。根据 XMPP Standards 文档 **XEP-0178**，“指定将 SASL EXTERNAL 机制用于 PKIX 证书的建议的协议流，尤其是当 XMPP 服务指示将强制进行 TLS 协商时。”如 XSF 文档中所述，PKIX 是指公钥基础结构，又称 PKI。
    
    有关 XMPP 要求的详细信息，请参阅 XSF 文档 XEP-0178。 有关详细信息，请参阅 "XEP-0178：使用 SASL EXTERNAL with 证书" 的最佳实践。 <http://xmpp.org/extensions/xep-0178.html>
    
    请参阅 IETF document "可扩展消息和状态协议 (XMPP) ： Core"，5.0 节，STARTTLS 协商 <https://tools.ietf.org/html/rfc6120> 。
    
      - **TLS 协商**。 定义 TLS 协商规则。 XMPP 服务可能需要 TLS，可以使 TLS 成为可选的，也可以定义不支持 TLS。 选择 "可选" 将要求留给 XMPP 服务进行强制性协商决策。 若要查看所有可能的设置和有关 SASL、TLS 和回拨的详细信息（包括无效和已知的错误配置），请参阅 [Lync Server 2013 中的 XMPP 联盟伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。
        
          - <span></span>  
            **** 必需。 XMPP 服务需要 TLS 协商。
        
          - <span></span>  
            **可选**。 XMPP 服务指示将强制进行 TLS 协商。
        
          - <span></span>  
            **不支持**。 XMPP 服务不支持 TLS。
    
      - **SASL 协商**。 定义 SASL 协商规则。 XMPP 服务可能需要 SASL，可以使 SASL 成为可选的，也可以定义不支持 SASL。 选择 "可选" 将要求留给合作伙伴 XMPP 服务进行强制性的协商决策。
        
        <div>
        

        > [!WARNING]  
        > SASL 需要 TLS。若要使用 SASL，TLS 必须为必需或可选项。任何将 SASL 定义为“必需”或“可选”的配置都必须提供 TLS 支持。当单击“提交”<STRONG></STRONG>保存更改时，如果未将 TLS 设为“必需”或“可选”，将警告您 SASL 必须提供 TLS 支持且无法保存您的更改。若要处理该错误，请将 TLS 设为“必需”<STRONG></STRONG>或“可选”<STRONG></STRONG>。如果 SASL 的使用是可选的且无法实现 TLS 协商支持，则您必须将 SASL 协商设为“不支持”<STRONG></STRONG>。通过 XMPP 服务确认必须建立哪些适当的 TLS 和 SASL 协商流，否则将发生服务中断。

        
        </div>
        
          - <span></span>  
            **** 必需。 XMPP 服务需要 SASL 协商。
        
          - <span></span>  
            **可选**。 XMPP 服务指示将强制进行 SASL 协商。
        
          - <span></span>  
            **不支持**。 XMPP 服务不支持 SASL。
    
      - **回拨协商**。 回拨协商由 document **XEP-220： Server 回拨**中的 XSF 定义 <http://xmpp.org/extensions/xep-0220.html> 。 服务器回拨进程使用域名系统 (DNS) 和权威服务器来验证请求是否来自有效的 XMPP 合作伙伴。 若要执行此操作，起始服务器将使用生成的回拨密钥创建特定类型的邮件，并在 DNS 中查找接收服务器。 源服务器将 XML 流中的密钥发送到生成的 DNS 查找，大概是接收服务器。 在 XML 流上收到密钥后，接收服务器不会响应原始服务器，但会将密钥发送到已知的权威服务器。 权威服务器验证密钥有效或无效。 如果无效，则接收服务器不会对原始服务器做出响应。 如果密钥有效，则接收服务器会通知发起服务器标识和密钥有效，并且会话可以开始。
        
        **回拨协商**具有两种有效状态：
        
          - <span></span>  
            **True**。 如果应收到来自发起服务器的请求，则将 XMPP 服务器配置为使用回拨协商。
        
          - <span></span>  
            **False**。 XMPP 服务器不配置为使用回拨协商，并且如果应从发起服务器接收请求，将忽略该状态

</div>

</div>

<span> </span>

</div>

</div>

</div>

