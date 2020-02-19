---
title: 在 Lync Server 2013 上配置 XMPP 网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 60896937432df17bb743a0feafc187cbf7d9df61
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135989"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>在 Lync Server 2013 上配置 XMPP 网关

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-10-28_

迁移 XMPP 网关的最后一步是为 Lync Server 2013 Edge 服务器配置证书，部署 Lync Server 2013 XMPP 网关，并更新 XMPP 网关的 DNS 记录。 这些步骤应该并行执行，以尽可能缩短 XMPP 网关的停机时间。 在执行这些步骤之前，必须将所有用户移到 Microsoft Lync Server 2013 部署中。

<div class=" ">


> [!IMPORTANT]  
> 对于驻留在 survivable 分支设备上的用户，不支持 XMPP 联盟。 这适用于查看状态信息和交换 IM 消息。



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 边缘服务器上配置 XMPP 网关证书。

1.  在边缘服务器上，单击部署向导中“步骤 3：请求、安装或分配证书”**** 旁边的“再次运行”****。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果您第一次部署边缘服务器，您将看到“运行”而不是“再次运行”。

    
    </div>

2.  在“可用的证书任务”**** 页上，单击“创建新的证书请求”****。

3.  在“证书请求”**** 页上，单击“外部边缘证书”****。

4.  在“延迟的请求或即时请求”**** 页上，选中“立即准备请求，但是稍后发送”**** 复选框。

5.  在 "**证书请求文件**" 页上，键入要将请求保存到的文件的完整路径和文件名（例如，c：\\cert\_外部\_edge）。

6.  在“指定替代证书模板”**** 页上，要使用除默认 WebServer 模板之外的模板，请选中“对选定的证书颁发机构使用替代证书模板”**** 复选框。

7.  在“名称和安全设置”**** 页上，执行以下操作：
    
    1.  在“友好名称”**** 中，键入证书的显示名称。
    
    2.  在“位长度”**** 中，指定位长度（通常默认值为 2048）。
    
    3.  验证是否选中了“将证书私钥标记为可导出”**** 复选框。

8.  在“组织信息”**** 页上，键入组织和组织单位（例如分部或部门）的名称。

9.  在“地理信息”**** 页上，指定位置信息。

10. 在“使用者名称/使用者替代名称”**** 页上，将显示向导自动填充的信息。如果需要其他使用者替代名称，可以在接下来的两个步骤中指定。

11. 在 "**使用者替代名称（san）的 SIP 域设置**" 页上，选中 "域" 复选框以添加 sip。\<sipdomain\>条目到 "主题备用名称" 列表。

12. 在“配置其他使用者替代名称”**** 页上，指定所需的任何其他使用者替代名称。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果安装了 XMPP 代理，则默认情况下域名（如 contoso.com）填充在 SAN 条目中。如果您需要更多条目，请在此步骤中添加它们。

    
    </div>

13. 在“请求摘要”**** 页上，检查要用于生成请求的证书信息。

14. 在命令运行完毕后，您可以“查看日志”****，或单击“下一步”继续操作。

15. 在“证书请求文件”**** 页上，您可以通过单击“查看”**** 来查看生成的证书签名请求 (CSR) 文件，或通过单击“完成”**** 来退出证书向导。

16. 复制请求文件并提交至公共证书颁发机构。

17. 在接收、导入和分配公共证书后，您必须停止边缘服务器服务，然后重新启动它。为此，请在 Lync Server 管理控制台中键入：
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>配置新的 Lync Server 2013 XMPP 网关

1.  打开“Lync Server 控制面板”。

2.  在左侧导航栏中，单击“联盟和外部访问”****，然后单击“XMPP 联盟伙伴”****。

3.  要创建新配置，请单击“新建”****。

4.  定义以下设置：

5.  **主域**    （必需）。 主域是 XMPP 合作伙伴的基本域。 例如，可为 XMPP 合作伙伴域名输入 **fabrikam.com**。 这是必填项。

6.  **Description**   说明针对此特定配置的注释或其他标识信息。 此条目是可选的。

7.  **其他域**   其他域是作为 XMPP 合作伙伴的域的一部分的域，应作为允许的 XMPP 通信的一部分包括在内。 例如，如果主域为**fabrikam.com**，则将列出位于 fabrikam.com 中的所有其他域，您将使用 XMPP 的方式进行通信。

8.  **合作伙伴类型**   **合作伙伴类型**是必需的设置。 您必须选择以下项之一来描述和强制添加可添加的联系人。 您可以从以下选项中进行选择：
    
      - **联合**   **联盟**伙伴类型表示 Lync Server 部署与 XMPP 合作伙伴之间的高信任级别。建议使用此合作伙伴类型与同一企业内的 XMPP 服务器进行联盟，或者存在已建立的业务关系。联盟伙伴中的 XMPP 联系人可以执行以下操作：
        
        1.  添加 Lync 联系人并查看其状态，而无需明确的 Lync 用户授权。
        
        2.  向 Lync 联系人发送即时消息，无论 Lync 用户是否已将他们添加到其联系人列表。
        
        3.  查看 Lync 用户的状态注释。
    
      - **公共验证**   **公共验证**合作伙伴是一个公开的公共 XMPP 提供程序，可信任它来验证其用户的身份。公共验证的网络中的 XMPP 联系人可以添加 Lync 联系人并查看它们的状态，并向其发送即时消息，而无需通过 Lync 用户的认证。公共验证的网络中的 XMPP 联系人永远不会看到 Lync 用户的状态笔记。建议不要使用此设置。
    
      - **公共**   未验证**公用的未经**验证的合作伙伴是一个公共 XMPP 提供程序，不受信任以验证其用户的身份。公共未验证网络上的 XMPP 用户无法与 Lync 用户通信，除非 Lync 用户已通过将其添加到联系人列表中进行了明确授权。公共未验证网络上的 XMPP 用户永远不会看到 Lync 用户的状态说明。对于具有公共 XMPP 提供商（如 Google 谈话）的任何联盟，建议使用此设置。

9.  **连接类型：** 定义各种规则和回拨设置。
    
      - **Tls 协商**   定义 tls 协商规则。 XMPP 服务可能需要 TLS，可以使 TLS 成为可选的，也可以定义不支持 TLS。 选择 "可选" 将要求留给 XMPP 服务进行强制性协商决策。 若要查看所有可能的设置和有关 SASL、TLS 和回拨的详细信息（包括无效和已知的错误配置），请参阅[Lync Server 2013 中的 XMPP 联盟伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。
        
          - <span></span>  
            **必需**   的 XMPP 服务需要 TLS 协商。
        
          - <span></span>  
            **可选**   ： XMPP 服务指示 TLS 是强制性的协商。
        
          - <span></span>  
            **不支持**   XMPP 服务不支持 TLS。
    
      - **Sasl 协商**   定义 sasl 协商规则。 XMPP 服务可能需要 SASL，可以使 SASL 成为可选的，也可以定义不支持 SASL。 选择 "可选" 将要求留给合作伙伴 XMPP 服务进行强制性的协商决策。
        
          - <span></span>  
            **必需**   的 XMPP 服务需要 SASL 协商。
        
          - <span></span>  
            **可选**   ： XMPP 服务指示 SASL 是强制性协商的。
        
          - <span></span>  
            **不支持**   XMPP 服务不支持 SASL。
    
      - **支持服务器回拨协商**支持服务器回拨协商进程使用域名系统（DNS）和权威服务器来验证请求是否来自有效的 XMPP 合作伙伴。 若要执行此操作，起始服务器将使用生成的回拨密钥创建特定类型的邮件，并在 DNS 中查找接收服务器。 源服务器将 XML 流中的密钥发送到生成的 DNS 查找，大概是接收服务器。 在 XML 流上收到密钥后，接收服务器不会响应原始服务器，但会将密钥发送到已知的权威服务器。 权威服务器验证密钥有效或无效。 如果无效，则接收服务器不会对原始服务器做出响应。 如果密钥有效，则接收服务器会通知发起服务器标识和密钥有效，并且会话可以开始。
        
        **回拨协商**具有两种有效状态：
        
          - <span></span>  
            **True**   如果应收到来自发起服务器的请求，则将 XMPP 服务器配置为使用回拨协商。
        
          - <span></span>  
            **False**   未将 XMPP 服务器配置为使用回拨协商，如果应收到来自发起服务器的请求，则将忽略该请求。

10. 单击“提交”**** 保存对站点或用户策略的更改。

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>更新 Lync Server 2013 XMPP 网关的 DNS 记录

1.  若要为 XMPP 联合配置 DNS，请将以下 SRV 记录添加到外部 DNS：\_XMPP-server。\_tcp。\<域名 SRV 记录将解析为边缘服务器的访问边缘 FQDN，端口值为\> 5269。

</div>

</div>

<span> </span>

</div>

</div>

</div>

