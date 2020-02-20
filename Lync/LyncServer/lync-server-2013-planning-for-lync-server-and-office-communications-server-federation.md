---
title: 规划 Lync Server 和 Office 通信服务器联合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 838664dbbc34182d1c1eb5ec48f523480a891379
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42152770"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>规划 Lync Server 2013 和 Office 通信服务器联盟

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2013-02-13_

Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器之间的联合支持对等通信和多方通信。 对等对话可升级为多方会话，从而允许临时会议。 可以安排会议（即 Web 会议或音频/视频会议）以包含您组织内的联系人以及您的联盟合作伙伴内的联系人。

联合身份验证首次出现在 Microsoft Office Live 通信服务器2005中，并支持一种联合联合，即直接联盟。 直接联盟需要您知道联盟伙伴的会话初始协议（SIP）域和合作伙伴的边缘服务器的完全限定域名（FQDN）。 Live 通信服务器 2005 SP1 引入了其他联合类型，所有必需的域名系统（DNS） SRV 记录都将由联盟伙伴发布，以找到其边缘服务器。 该版本的术语有：

  - *打开增强联盟*：接受任何 SIP 域名并使用 DNS SRV 查找合作伙伴边缘服务器

  - *增强联盟*：将合作伙伴的 SIP 域名配置为组织的联盟伙伴，并使用 DNS SRV 查找合作伙伴边缘服务器

  - *直接联盟*：将合作伙伴的 SIP 域名和 FQDN 配置为合作伙伴的边缘服务器

  - *服务器允许列表*：接受任何域，使用 DNS SRV 查找承载提供程序或公共即时消息（IM）连接提供程序的边缘服务器

Microsoft Office 通信服务器2007引入了联合身份验证类型的更新命名，以便更好地定义每个联合类型实际完成的操作：

  - 开放增强联盟变为*已发现的伙伴域*

  - 增强联盟变为*允许的伙伴域*

  - 直接联盟变为*允许的伙伴服务器*

  - 服务器允许列表变为*宿主提供程序* 和*公共 IM 提供程序*

Microsoft Lync Server 2010 根据 Microsoft Lync Online 2010 和 Microsoft Office 365 引入了更窄的托管提供程序定义，同时还使其遵守允许的合作伙伴域联合类型定义的相同允许列表。

启用 Microsoft Lync Server 2013 之间的联盟。 Lync Server 2010 和 Office 通信服务器使用边缘服务器和反向代理来强制实施所定义的规则和允许的合作伙伴域。 从规划的角度来看，与其他 Lync Server 进行联盟，Office 通信服务器需要满足以下条件：

  - 在拓扑生成器中启用联盟。 有关详细信息，请参阅部署主题[在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。

  - 确定您的联盟域发现的要求：
    
      - <span></span>  
        若要手动配置联盟，您必须具有合作伙伴的边缘服务器和域名（FQDN）的完全限定域名（FQDN），或者在 Lync Server 控制面板、**联合访问和外部访问**（ **SIP 联盟域**）中输入的联机域名。 创建“新”**** 策略或“编辑”**** 现有策略以通过 FQDN 允许或阻止域。
        
        <div>
        

        > [!WARNING]
        > 如果合作伙伴更改了其边缘服务器的 IP 地址，则联合合作伙伴的边缘服务器的手动配置容易出现故障。

        
        </div>
        
        <div>
        

        > [!NOTE]
        > 对于<STRONG>新的 SIP 联盟域</STRONG>，您必须为 Microsoft Lync Online （microsoft Office 365 <STRONG>）提供域名（或 FQDN）</STRONG> 。 对于 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器，你还必须提供<STRONG>访问边缘服务（FQDN）</STRONG>

        
        </div>
    
      - <span></span>  
        对于已发现的合作伙伴联盟（合作伙伴可以在其中发现你的边缘服务器），请在外部 DNS- \_sipfederationtls 中创建一个 SRV 记录。\_tcp.contoso.com –指向边缘服务器的端口5061和主机（A）记录
        
        <div>
        

        > [!IMPORTANT]
        > 如果要在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 设备上支持 Microsoft Lync 移动客户端，并且使用的是推送通知服务或推送通知服务，则必须规划 _sipfederationtls _tcp。 &lt;您拥有&gt; Lync 移动客户端的每个 sip 域的 SIP 域 SRV 记录。 Android 和 Nokia Symbian Lync Mobile 不使用推送通知，也不受此要求的制约。

        
        </div>

  - 配置外部用户访问策略以支持联盟域

  - 开放会话初始协议 (SIP)、Web 会议和音频/视频会议的防火墙端口以适应您启用的联盟或联系人。 有关详细信息，请参阅：[确定外部 A/V 防火墙和端口要求（针对 Lync Server 2013](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md) ）

以下信息将帮助您定义证书、端口/协议以及与 Microsoft Lync Server 2013 和 Lync Server 2010 联合的 DNS 要求。

如果计划或部署了 Microsoft Lync Server 2013 边缘服务器，则在规划证书、防火墙和端口/协议要求以及 DNS 要求时，通常是一个直接的转发过程。 由于联盟是另一个使用现有边缘服务器的功能，因此规划要求通常由边缘服务器规划和部署所满足。 您应使用下表确定是否已满足您的要求并相应地更改端口/协议和 DNS。

<div>


> [!IMPORTANT]
> 如果您有一池的边缘服务器，并且要与 Lync Server 2013 或 Lync Server 2010 合作伙伴进行联盟，则可以在边缘服务器的内部边缘和外部面上使用 DNS 负载平衡或硬件负载平衡器。 如果要与 Office 通信服务器2007或 Office 通信服务器 2007 R2 进行联盟，则硬件负载平衡将在边缘服务器的事件中提供故障转移支持。 Office 通信服务器2007和 Office 通信服务器 2007 R2 不是 DNS 负载平衡感知。 合作伙伴边缘服务器将与池中的第一台边缘服务器建立通信，以进行响应。 如果该边缘服务器出现故障，通信不会自动进行故障转移。



</div>

证书要求通常通过规划所选边缘服务器或池边缘服务器计划的证书来满足。

<div>

## <a name="in-this-section"></a>本部分内容

  - [Lync Server 2013 中的证书摘要-SIP、XMPP 联合身份验证和公共即时消息](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013 中的端口摘要-SIP、XMPP 联合身份验证和公共即时消息](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [Lync Server 2013 中的 DNS 摘要-SIP、XMPP 联合身份验证和公共即时消息](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置用于控制联合用户访问的策略](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  


[在 Lync Server 2013 中管理您的组织的访问边缘配置](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联合提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

