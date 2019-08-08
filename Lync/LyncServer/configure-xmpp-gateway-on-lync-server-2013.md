---
title: 在 Lync Server 2013 上配置 XMPP 网关
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
audience: Admin
TOCTitle: Configure XMPP gateway on Lync Server 2013
ms:assetid: c70282e0-b502-47e2-a0be-a32eb1faf99d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721881(v=OCS.15)
ms:contentKeyID: 49733816
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 87564835404928a79f9c61974d9581bba68069cd
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/07/2019
ms.locfileid: "36233132"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-xmpp-gateway-on-lync-server-2013"></a>在 Lync Server 2013 上配置 XMPP 网关

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-28_

迁移 XMPP 网关的最终步骤是配置 Lync Server 2013 Edge 服务器的证书, 部署 Lync Server 2013 XMPP 网关, 并更新 XMPP 网关的 DNS 记录。 这些步骤应并行执行, 以最大限度地减少 XMPP 网关的停机时间。 在执行这些步骤之前, 必须将所有用户移到 Microsoft Lync Server 2013 部署。

<div class=" ">


> [!IMPORTANT]  
> 对于托管在 survivable 分支设备上的用户, 不支持 XMPP 联合身份验证。 这适用于查看状态信息和交换 IM 消息。



</div>

<div>

## <a name="configure-xmpp-gateway-certificates-on-the-lync-server-2013-edge-server"></a>在 Lync Server 2013 Edge 服务器上配置 XMPP 网关证书

1.  在边缘服务器上的 "部署向导" 中, 在 "**步骤 3: 请求、安装或分配证书**" 旁边, 再次单击 "**运行**"。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果你是首次部署 Edge 服务器, 你将看到 "运行", 而不是再次运行。

    
    </div>

2.  在“**可用的证书任务**”页上，单击“**创建新的证书请求**”。

3.  在 "**证书请求**" 页面上, 单击 "**外部边缘证书**"。

4.  在 "**延迟或立即请求**" 页面上, 选中 "**立即准备请求, 但稍后发送"** 复选框。

5.  在 "**证书请求文件**" 页面上, 键入要保存请求的文件的完整路径和文件名 (例如, c:\\cert\_外部\_edge)。

6.  在 "**指定备用证书模板**" 页面上, 若要使用默认 web 台模板之外的模板, 请选中 "**为所选证书颁发机构使用备用证书模板**" 复选框。

7.  在 "**名称和安全设置**" 页面上, 执行下列操作:
    
    1.  在 "**友好名称**" 中, 键入证书的显示名称。
    
    2.  在 "**位长度**" 中, 指定位长度 (通常为默认值 2048)。
    
    3.  验证 "将**证书私钥标记为可导出**" 复选框是否已选中。

8.  在 "**组织信息**" 页面上, 键入组织和组织单位的名称 (例如, "部门" 或 "部门")。

9.  在 "**地理信息**" 页面上, 指定位置信息。

10. 在 "**主题名称/主题备用名称**" 页面上, 将显示要由向导自动填充的信息。 如果需要其他主题备用名称, 请在接下来的两个步骤中进行指定。

11. 在 "**主题备用名称 (san)** " 页面上的 "SIP 域设置" 中, 选中 "域" 复选框以添加 SIP。\<sipdomain\>条目到 "主题备用名称" 列表。

12. 在 "**配置其他主题备用名称**" 页面上, 指定所需的任何其他主题备用名称。
    
    <div class=" ">
    

    > [!TIP]  
    > 如果 XMPP 代理已安装, 则默认情况下会在 SAN 条目中填充域名 (如 contoso.com)。 如果需要更多条目, 请在此步骤中添加这些条目。

    
    </div>

13. 在 "**请求摘要**" 页面上, 查看要用于生成请求的证书信息。

14. 命令完成运行后, 您可以**查看日志**, 或单击 "下一步" 继续。

15. 在 "**证书请求文件**" 页面上, 您可以通过单击 "**查看**或退出证书向导" 查看生成的证书签名请求 (CSR) 文件, 方法是单击 "**完成**"。

16. 将请求文件复制并提交到公共证书颁发机构。

17. 接收、导入和分配公共证书后, 必须停止并重新启动 Edge 服务器服务。 可通过在 Lync Server 管理控制台中键入以下内容来执行此操作:
    
        Stop-CsWindowsService

      &nbsp;
    
        Start-CsWindowsService

</div>

<div>

## <a name="configure-a-new-lync-server-2013-xmpp-gateway"></a>配置新的 Lync Server 2013 XMPP 网关

1.  打开“Lync Server 控制面板”。

2.  在左侧导航栏中, 单击 "**联盟和外部访问**", 然后单击 " **XMPP 联盟合作伙伴**"。

3.  若要创建新配置, 请单击 "**新建**"。

4.  定义以下设置:

5.  **主域**    (必需)。 主要域是 XMPP 合作伙伴的基础域。 例如, 你可以为 XMPP 合作伙伴域名输入**fabrikam.com** 。 这是一个必需的条目。

6.  **说明**   此说明适用于此特定配置的注释或其他标识信息。 此条目是可选的。

7.  **其他域**   其他域是 XMPP 合作伙伴所在域的一部分的域, 应包括在允许的 XMPP 通信中。 例如, 如果主域是**fabrikam.com**, 则会列出您将通过 XMPP 进行通信的 fabrikam.com 下的所有其他域。

8.  **合作伙伴类型**   **合作伙伴类型**是必需的设置。 您必须选择下列内容之一来描述和强制执行哪些联系人可以添加。 您可以选择:
    
      - **联合**   **联盟**合作伙伴类型表示 Lync Server 部署与 XMPP 合作伙伴之间的高信任级别。若要与同一企业内的 XMPP 服务器联盟或已建立的业务关系, 建议使用此类合作伙伴。联盟合作伙伴中的 XMPP 联系人可以:
        
        1.  添加 Lync 联系人并在不通过 Lync 用户快速授权的情况下查看其状态。
        
        2.  向 Lync 联系人发送即时消息, 无论 Lync 用户是否已将其添加到其联系人列表中。
        
        3.  查看 Lync 用户的状态笔记。
    
      - **公共验证**   的**** 公共验证合作伙伴是受信任的公共 XMPP 提供商, 可用于验证其用户的身份。XMPP 公共验证网络中的联系人可以添加 Lync 联系人并查看其状态, 并向他们发送即时消息, 而无需从 Lync 用户进行快速授权。公共验证网络中的 XMPP 联系人永远不会看到 Lync 用户的状态笔记。不建议使用此设置。
    
      - **公共**   未验证**公共未经**验证的合作伙伴是不受信任的公共 XMPP 提供程序, 无法验证其用户的身份。XMPP 公共未经验证的网络上的用户无法与 Lync 用户通信, 除非 Lync 用户已通过将其添加到联系人列表中进行了明确授权。公共未经验证的网络上的 XMPP 用户永远不会看到 Lync 用户的状态笔记。对于具有公共 XMPP 提供商 (如 Google 通话) 的任何联盟, 建议使用此设置。

9.  **连接类型:** 定义各种规则和回拨设置。
    
      - **Tls 协商**   定义 tls 协商规则。 XMPP 服务可能需要 TLS, 可以使 TLS 可选, 也可以定义不支持 TLS。 选择 "可选" 将对 XMPP 服务的要求留给必要的协商决策。 若要查看有关 SASL、TLS 和回拨协商的所有可能设置和详细信息-包括无效的已知错误配置, 请参阅[Lync Server 2013 中 XMPP 联盟合作伙伴的协商设置](lync-server-2013-negotiation-settings-for-xmpp-federated-partners.md)。
        
          - <span></span>  
            **必需**   的 XMPP 服务需要 TLS 协商。
        
          - <span></span>  
            **可选**   : XMPP 服务指示 TLS 必须进行协商。
        
          - <span></span>  
            **不支持**   XMPP 服务不支持 TLS。
    
      - **Sasl 协商**   定义 sasl 协商规则。 XMPP 服务可能需要 SASL, 可以使 SASL 成为可选的, 也可以定义不支持 SASL。 选择 "可选" 将要求提供给合作伙伴 XMPP 服务, 以便进行强制性的协商决策。
        
          - <span></span>  
            **必需**   的 XMPP 服务需要 SASL 协商。
        
          - <span></span>  
            **可选**   : XMPP 服务指示 SASL 必须进行协商。
        
          - <span></span>  
            **不支持**   XMPP 服务不支持 SASL。
    
      - **支持服务器回拨协商**支持服务器回拨协商进程使用域名系统 (DNS) 和权威服务器验证请求是否来自有效的 XMPP 合作伙伴。 为此, 始发服务器使用生成的回拨密钥创建一个特定类型的消息, 并在 DNS 中查找接收服务器。 始发服务器将 XML 流中的密钥发送到生成的 DNS 查找, 这是接收服务器。 在通过 XML 流接收密钥时, 接收服务器不会响应始发服务器, 而是将密钥发送到已知的权威服务器。 授权服务器验证密钥是否有效或无效。 如果无效, 接收方服务器不会响应始发服务器。 如果密钥有效, 接收方服务器将通知发起服务器标识和密钥有效且可以开始对话。
        
        **回拨协商**有两个有效状态:
        
          - <span></span>  
            ****   如果应从发起服务器接收请求, 则将 XMPP 服务器配置为使用回拨协商。
        
          - <span></span>  
            **False**   未将 XMPP 服务器配置为使用回拨协商, 如果应收到来自发起服务器的请求, 则会忽略它。

10. 单击 "**提交**" 将更改保存到 "网站" 或 "用户策略"。

</div>

<div>

## <a name="update-dns-records-for-lync-server-2013-xmpp-gateway"></a>更新 Lync Server 2013 XMPP 网关的 DNS 记录

1.  若要为 XMPP 联盟配置 DNS, 请将以下 SRV 记录添加到外部 DNS:\_XMPP-server。\_tcp。\<域名 SRV 记录将解析为 Edge 服务器的访问边缘 FQDN, 其端口值为\> 5269。

</div>

</div>

<span> </span>

</div>

</div>

</div>

