---
title: 规划 Lync Server 和 Office 通信服务器联合
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for Lync Server and Office Communications Server federation
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205335(v=OCS.15)
ms:contentKeyID: 48185640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c683092b61d278d380ad68cef86795d496498fbf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824783"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-lync-server-2013-and-office-communications-server-federation"></a>规划 Lync Server 2013 和 Office 通信服务器联合

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-02-13_

Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器之间的联盟支持对等通信和多方通信。 对等对话可以升级到多方对话, 从而允许进行临时会议。 会议-网络会议或音频/视频/视频会议-可以安排在您的组织内以及与您联盟的合作伙伴中的联系人之间包括联系人。

联合身份验证首次出现在 Microsoft Office Live 通信服务器2005中, 并且支持一种类型的联盟和直接联盟。 直接联盟需要你了解联盟伙伴的会话初始协议 (SIP) 域和合作伙伴的边缘服务器的完全限定的域名 (FQDN)。 实时通信服务器 2005 (SP1 引入了其他联合类型), 所有必需的域名系统 (DNS) SRV 记录都将由联盟伙伴发布以找到其边缘服务器。 该版本的术语是:

  - *打开增强联盟*: 接受任何 SIP 域名, 并使用 DNS SRV 查找合作伙伴边缘服务器

  - *增强联盟*: 将合作伙伴的 SIP 域名配置为你的组织的联合身份验证合作伙伴, 并使用 DNS SRV 查找合作伙伴边缘服务器

  - *直接联盟*: 将合作伙伴的 SIP 域名和 FQDN 配置为合作伙伴的边缘服务器

  - *服务器允许列表*: 接受任何域, 使用 DNS SRV 查找托管提供商或公共即时消息 (IM) 连接提供程序的边缘服务器

Microsoft Office 通信服务器2007引入了对联合身份验证类型的更新命名, 以便更好地定义每个联合类型实际完成的内容:

  - 开放式增强联盟称为 "已*发现合作伙伴域*"

  - 增强联盟被称为 "*允许的伙伴域*"

  - 直接联盟被称为 "*允许的伙伴服务器*"

  - 服务器允许列表被称为*托管提供商*和*公共 IM 提供商*

Microsoft Lync Server 2010 根据 Microsoft Lync Online 2010 和 Microsoft Office 365 引入了更窄的托管提供程序的定义, 并且它遵守允许的伙伴域联合身份验证类型所定义的同一允许列表。

在 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器之间启用联盟将使用边缘服务器和反向代理来强制执行所定义的规则和允许的伙伴域。 从规划的角度来看, 与其他 Lync 服务器进行联盟, Office 通信服务器需要满足以下要求:

  - 在拓扑生成器中启用联盟。 有关详细信息, 请参阅[在 Lync Server 2013 中配置 SIP 联合、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)的部署主题。

  - 确定联合域发现的要求:
    
      - <span></span>  
        若要手动配置联盟, 你必须具有合作伙伴的边缘服务器和域名的完全限定域名 (FQDN), 或者在 Lync Server 控制面板、**联合身份验证和外部访问**、SIP 中输入的联机域名的完全限定的域名 (FQDN)。 **联盟域**。 创建**新**策略或**编辑**现有策略以允许或阻止 FQDN 域。
        
        <div>
        

        > [!WARNING]
        > 如果合作伙伴更改了其边缘服务器的 IP 地址, 则联合身份验证伙伴的边缘服务器的手动配置很容易出现故障。

        
        </div>
        
        <div>
        

        > [!NOTE]
        > 对于<STRONG>新的 SIP 联盟域</STRONG>, 您必须提供 Microsoft Lync Online、microsoft Office 365 的<STRONG>域名 (或 FQDN)</STRONG> 。 对于 Microsoft Lync Server 2013、Lync Server 2010 和 Office 通信服务器, 你还必须提供<STRONG>访问边缘服务 (FQDN)</STRONG>

        
        </div>
    
      - <span></span>  
        对于已发现的合作伙伴联盟 (合作伙伴可以在其中发现你的 Edge 服务器), 你可以在外部 DNS \_-sipfederationtls 中创建 SRV 记录。\_tcp.contoso.com-指向端口5061和边缘服务器的主机 (A) 记录
        
        <div>
        

        > [!IMPORTANT]
        > 如果你在 Windows Phone 或 Apple iPhone、iPad 或其他 Apple 设备上支持 Microsoft Lync 移动客户端, 并且使用的是推送通知服务或推送通知服务, 则必须为 _tcp _sipfederationtls。 &lt;您有&gt; Lync 移动客户端的每个 sip 域的 SIP 域 SRV 记录。 Android 和 Nokia Symbian Lync Mobile 不使用推送通知, 也不受此要求的制约。

        
        </div>

  - 配置外部用户访问策略以支持联盟域

  - 打开用于会话启动协议 (SIP)、web 会议和音频/视频的防火墙端口, 以适应你正在启用的联盟或联系人。 有关详细信息, 请参阅:[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

以下信息将帮助你为与 Microsoft Lync Server 2013 和 Lync Server 2010 的联合定义证书、端口/协议和 DNS 要求。

如果已计划或部署 Microsoft Lync Server 2013 Edge 服务器, 则为证书、防火墙和端口/协议要求以及 DNS 要求的规划通常是一个直连过程。 由于联盟是一个使用现有边缘服务器的附加功能, 因此规划要求一般由边缘服务器规划和部署来满足。 你应该使用下表确定满足你的要求, 并相应地在端口/协议和 DNS 中进行更改。

<div>


> [!IMPORTANT]
> 如果你有一个 Edge 服务器池, 并且正在与 Lync Server 2013 或 Lync Server 2010 合作伙伴联盟, 那么你可以在边缘服务器的内部和外部面向的方使用 DNS 负载平衡或硬件负载平衡器。 如果您要与 Office 通信服务器2007或 Office 通信服务器 2007 R2 进行联盟, 则硬件负载平衡将在 Edge 服务器的事件中提供故障转移支持。 Office 通信服务器2007和 Office 通信服务器 2007 R2 不支持 DNS 负载平衡。 合作伙伴边缘服务器将与你的池中的第一个边缘服务器建立通信, 以响应。 如果该边缘服务器出现故障, 通信不会自动故障转移。



</div>

证书要求通常通过规划所选边缘服务器或池边缘服务器计划的证书来满足。

<div>

## <a name="in-this-section"></a>本节内容

  - [证书摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [端口摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [DNS 摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

</div>

<div>

## <a name="see-also"></a>另请参阅


[在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)  


[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  


[在 Lync Server 2013 中管理您的组织的访问边缘配置](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

