---
title: 计划 SIP、XMPP 联盟和公共即时消息
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Planning for SIP, XMPP federation, and public instant messaging
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204825(v=OCS.15)
ms:contentKeyID: 48183918
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 88aa8c6f3f2f11b303a7e25eed96d5f0d7243cb4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2019
ms.locfileid: "34824146"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="planning-for-sip-xmpp-federation-and-public-instant-messaging-in-lync-server-2013"></a>在 Lync Server 2013 中规划 SIP、XMPP 联盟和公共即时消息

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间:** 2013-10-28_

可以将 Edge 服务器配置为允许内部和外部用户访问合作伙伴组织或服务的联系人。 联合身份验证 (如这些合作伙伴协议), 可向组织中的组织中的联系人提供以下任何或所有联系人:

  - 即时消息和状态

  - 协作和会议, 例如 Web 会议

  - 音频会议和/或视频会议

在某些情况下, 通信 (例如即时消息 (IM) 和在 Microsoft Lync Server 2013 和可扩展消息和状态协议 (XMPP) 联系人之间的状态为 "仅对等"-仅支持您和联盟的联系人配偶. 在其他情况下 (如 Lync 服务器、Lync server 2010 至 Lync Server 2013 联盟), 可以邀请多个参与者加入对话。

<div>

## <a name="lync-server-and-office-communications-server-federation"></a>Lync Server 和 Office 通信服务器联合

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

</div>

<div>

## <a name="public-instant-messaging-connectivity"></a>公共即时消息连接

公用即时消息连接是一种联盟类, 并配置为允许您的内部和外部 Lync Server 2013 用户从以下任何内容添加联系人:

  - Messenger 联系人

  - Yahoo\! 联系人

  - 美国在线 (AOL) 联系人

<div>


> [!IMPORTANT]
> <UL>
> <LI>
> <P>从2012年9月1日起, Microsoft Lync 公共 IM 连接用户订购许可证 (PIC USL) 不再可用于购买新的或续订协议。 具有活动许可证的客户将能够继续与 Yahoo! 进行联盟 Messenger 直到服务关闭日期 (准确日期仍将决定, 但不早于6月 2013)。</P>
> <LI>
> <P>PIC USL 是 Lync Server 或 Office 通信服务器与 Yahoo! 联合所需的每用户、每月订阅许可证。 Messenger. Microsoft 提供此服务的能力已由 Yahoo! 的支持 (将不会续订的底层协议) 提供。</P>
> <LI>
> <P>Lync 比以往更多, 是一种强大的工具, 用于跨组织和全球各地的人员进行连接。 与 Windows Live Messenger 的联盟不需要除 Lync 标准 CAL 之外的其他用户/设备许可证。 Skype 联盟将添加到此列表, 使 Lync 用户可以通过 IM 和语音与成百上千人联系。</P></LI></UL>



</div>

此类联合需要以下规划注意事项:

  - 除了即时消息外, Windows Live Messenger 用户可以与 Lync Server 2013 用户进行对等音频/视频通信。 边缘服务器必须满足特定的端口和协议要求。 有关详细信息, 请参阅[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - Yahoo 即时消息没有独特的要求, 除了通常用于提供联合的典型边缘服务器的规划和部署中。

  - 北美洲联机要求分配给 Access Edge 服务的 Edge 服务器证书具有客户端增强型密钥用法 (EKU)。

</div>

<div>

## <a name="extensible-messaging-and-presence-protocol-xmpp-federation"></a>可扩展消息和状态协议 (XMPP) 联合身份验证

以前版本的 Lync Server 和 Office 通信服务器提供了可扩展消息和状态协议 (XMPP) 网关, 可将其部署为单独的服务器角色, 以允许与 XMPP 部署进行联盟。 在 Microsoft Lync Server 2013 中, XMPP 功能可以部署为功能。 XMPP 功能在两个部分中安装: 在边缘服务器上运行的 XMPP 代理和在前端服务器上运行的 XMPP 网关。

在[Lync Server 2013 中部署外部用户访问权限](lync-server-2013-deploying-external-user-access.md)涵盖 XMPP 的部署和配置在你的防火墙上部署外部用户访问时, 可通过在防火墙上定义端口和协议规则、配置证书以及添加 DNS 来支持 XMPP。记录. 本节中的以下主题概述了为部署成功规划 XMPP 联合所需的信息。

<div>


> [!IMPORTANT]
> Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。



</div>

<div>


> [!IMPORTANT]
> 对于托管在 survivable 分支设备上的用户, 不支持 XMPP 联合身份验证。 这适用于查看状态信息和交换 IM 消息。



</div>

</div>

<div id="sectionSection3" class="section">

以下主题包含为受支持的联合身份验证方案的类型定义证书、防火墙端口和 DNS 条目的指南。

  - <span></span>  
    [证书摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [端口摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - <span></span>  
    [DNS 摘要-Lync Server 2013 中的 SIP、XMPP 联盟和公共即时消息](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

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

