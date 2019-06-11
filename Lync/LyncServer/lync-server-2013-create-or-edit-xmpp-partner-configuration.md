---
title: Lync Server 2013：创建或编辑 XMPP 合作伙伴配置
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Create or edit XMPP partner configuration
ms:assetid: 362dbe5e-8ee9-4aba-8c26-5907312b4a60
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ552447(v=OCS.15)
ms:contentKeyID: 48679558
ms.date: 09/03/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 488fa84a3f24133c6ebcde4467cacdbdcffe7ff8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34830836"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="create-or-edit-xmpp-partner-configuration-in-lync-server-2013"></a>在 Lync Server 2013 中创建或编辑 XMPP 合作伙伴配置

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2014-09-03_

Microsoft Lync Server 2013 集成了边缘服务器上的可扩展消息和状态协议 (XMPP) 代理和前端服务器或前端池中的 XMPP 网关。 若要允许来自其他 XMPP 部署的连接, 必须在 Lync Server 控制面板中配置 XMPP。 您可以在 XMPP 域基础上配置设置。 若要创建新的合作伙伴关联, 请执行以下操作:

<div>

## <a name="to-create-a-new-federated-partner-or-edit-an-existing-configuration"></a>创建新联盟合作伙伴或编辑现有配置

1.  使用 RTCUniversalServerAdmins 组成员（或具有同等用户权限）的用户帐户，或分配给 CsAdministrator 角色的用户帐户，登录到内部部署中的任何计算机。

2.  打开一个浏览器窗口, 然后输入 "管理员" URL 以打开 Lync Server "控制面板"。 有关可用于启动 Lync Server "控制面板" 的不同方法的详细信息, 请参阅[打开 Lync server 2013 管理工具](lync-server-2013-open-lync-server-administrative-tools.md)。

3.  在左侧导航栏中, 单击 "**联盟和外部访问**", 然后单击 " **XMPP 联盟合作伙伴**"。

4.  若要创建新配置, 请单击 "**新建**"

5.  若要编辑现有配置, 请选择配置, 然后单击 "**编辑**"

6.  若要创建或编辑**XMPP 联盟合作伙伴**的配置, 请定义以下设置:

7.  **主要域**(必需)。 主要域是 XMPP 合作伙伴的基础域。 例如, 你可以为 XMPP 合作伙伴域名输入**fabrikam.com** 。 这是一个必需的条目。

8.  **说明**。 说明适用于此特定配置的注释或其他标识信息。 此条目是可选的。

9.  **其他域**。 其他域是 XMPP 合作伙伴的域的一部分, 应包括在允许的 XMPP 通信中。 例如, 如果主域是**fabrikam.com**, 则会列出您将通过 XMPP 进行通信的 fabrikam.com 下的所有其他域。 例如, 你可以在 fabrikam 的主 XMPP 域下为企业 XMPP 域和信息技术 XMPP 域输入**corp.fabrikam.com**和**it.fabrikam.com** 。

10. **合作伙伴类型**。 **合作伙伴类型**是所需的设置, 可在下拉菜单中选择三个选项。 您必须选择下列内容之一来描述和强制执行哪些联系人可以添加。 您可以选择:
    
      - **联盟**。 **联盟**伙伴类型是 Lync Server 或 Office 通信服务器 2007 R2 合作伙伴部署之间的受信任连接。
    
      - **已验证公共**。 已**验证的公共**合作伙伴是指由提供商验证的部署中的联系人可以添加到用户的联系人列表。 可以从 Lync 用户发送邀请, 或者 Lync 用户可以接受来自合作伙伴联系人的邀请。
    
      - **公共未验证**。 公共的未**验证**关系表示两个部署之间没有已建立且可验证的状态。 Lync 用户必须邀请该联系人的未验证联系人能够将 Lync 用户添加到其联系人列表。 例如, Google GTalk 不是一个公共验证的 XMPP 服务, 因为它与 Lync 服务器相关。 GTalk 用户将无法将 Lync 用户添加为联系人, 除非有直接从 Lync 用户发送的邀请。

11. 有关流协商和安全方法传输层安全 (TLS) 和软件身份验证和安全层 (SASL) 的说明:
    
    **XMPP 标准基金会**(XSF) 和**Internet 工程任务**组 (IETF) 定义一组用于使用和管理 tls 客户端证书、TLS 服务器证书和 SASL 机制的规则和标准。 使用 TLS 和 SASL 是保护 XMPP 流所需的过程。 从 XMPP 标准文档**XEP-0178**中, "指定推荐的协议流, 用于使用具有 PKIX 证书的 SASL 外部机制, 特别是当 XMPP 服务指示 TLS 必须协商时。" PKIX (如 XSF 文档中所述), 指公钥基础结构, 也称为 PKI。
    
    有关 XMPP 要求的详细信息, 请参阅 XSF 文档 XEP-0178。 有关详细信息, 请参阅 "XEP-0178: 使用 SASL 外部证书的最佳做法"。 <http://xmpp.org/extensions/xep-0178.html>
    
    请参阅 IETF 文档 "可扩展消息和状态协议 (XMPP): Core", Section 5.0, STARTTLS 协商<http://tools.ietf.org/html/rfc6120>。
    
      - **TLS 协商**。 定义 TLS 协商规则。 XMPP 服务可能需要 TLS, 可以使 TLS 可选, 也可以定义不支持 TLS。 选择 "可选" 将对 XMPP 服务的要求留给必要的协商决策。 若要查看有关 SASL、TLS 和回拨协商的所有可能设置和详细信息-包括无效的已知错误配置, 请参阅[Lync Server 2013 中 XMPP 联盟合作伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。
        
          - <span></span>  
            **必需**。 XMPP 服务需要 TLS 协商。
        
          - <span></span>  
            **可选**。 XMPP 服务指示 TLS 必须进行协商。
        
          - <span></span>  
            **不受支持**。 XMPP 服务不支持 TLS。
    
      - **SASL 协商**。 定义 SASL 协商规则。 XMPP 服务可能需要 SASL, 可以使 SASL 成为可选的, 也可以定义不支持 SASL。 选择 "可选" 将要求提供给合作伙伴 XMPP 服务, 以便进行强制性的协商决策。
        
        <div>
        

        > [!WARNING]  
        > SASL 需要 TLS。 若要使用 SASL, TLS 必须是必需的或可选的。 将 SASL 定义为 "必需" 或 "可选" 的任何配置都必须具有 TLS 支持。 单击 "<STRONG>提交</STRONG>" 以保存所做的更改时, 如果未将 tls 设置为 "必需" 或 "可选", 则系统会警告 SASL 必须具有 TLS 支持, 并且不会保存所做的更改。 若要解决此错误, 请将 TLS 设置为<STRONG>必需</STRONG>或<STRONG>可选</STRONG>。 如果使用 SASL 是可选的, 并且不可能支持 TLS 协商支持, 则必须将 SASL 协商设置为<STRONG>不受支持</STRONG>。 通过 XMPP 服务确认哪些正确的协商流必须用于 TLS 和 SASL, 否则将出现服务中断。

        
        </div>
        
          - <span></span>  
            **必需**。 XMPP 服务需要 SASL 协商。
        
          - <span></span>  
            **可选**。 XMPP 服务指示 SASL 必须进行协商。
        
          - <span></span>  
            **不受支持**。 XMPP 服务不支持 SASL。
    
      - **回拨协商**。 回拨协商由文档 XEP 中的 XSF 定义 **-220: 服务器回拨** <http://xmpp.org/extensions/xep-0220.html>。 服务器回拨进程使用域名系统 (DNS) 和权威服务器验证请求是否来自有效的 XMPP 合作伙伴。 为此, 始发服务器使用生成的回拨密钥创建一个特定类型的消息, 并在 DNS 中查找接收服务器。 始发服务器将 XML 流中的密钥发送到生成的 DNS 查找, 这是接收服务器。 在通过 XML 流接收密钥时, 接收服务器不会响应始发服务器, 而是将密钥发送到已知的权威服务器。 授权服务器验证密钥是否有效或无效。 如果无效, 接收方服务器不会响应始发服务器。 如果密钥有效, 接收方服务器将通知发起服务器标识和密钥有效且可以开始对话。
        
        **回拨协商**有两个有效状态:
        
          - <span></span>  
            **True**。 如果应收到来自发起服务器的请求, 则将 XMPP 服务器配置为使用回拨协商
        
          - <span></span>  
            **False**。 XMPP 服务器未配置为使用回拨协商, 如果应收到来自发起服务器的请求, 则会忽略它

</div>

</div>

<span> </span>

</div>

</div>

</div>

