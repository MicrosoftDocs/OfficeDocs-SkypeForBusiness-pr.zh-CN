---
title: 规划 Lync Server 和 Office Communications Server 联盟
TOCTitle: 规划 Lync Server 和 Office Communications Server 联盟
ms:assetid: c9eaf06b-054f-41a4-ad0c-499400d6c4c7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205335(v=OCS.15)
ms:contentKeyID: 49314250
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 规划 Lync Server 和 Office Communications Server 联盟

 

_**上一次修改主题：** 2013-02-13_

Microsoft Lync Server 2013、Lync Server 2010 和 Office Communications Server 之间的联盟支持对等和多方通信。对等对话可升级为多方会话，从而允许临时会议。可以安排会议（即 Web 会议或音频/视频会议）以包含您组织内的联系人以及您的联盟合作伙伴内的联系人。

联盟首次出现于 Microsoft Office Live Communications Server 2005 并且仅有直接联盟这一种联盟收到支持。直接联盟要求您知道联盟伙伴的会话初始协议 (SIP) 域以及伙伴的边缘服务器的完全限定域名 (FQDN)。Live Communications Server 2005 SP1 引入了更多联盟类型，所有联盟类型都要求联盟伙伴发布域名系统 (DNS) SRV 记录以查找其边缘服务器。该版本的术语有：

  - *开放增强联盟*：接受任何 SIP 域名并使用 DNS SRV 查找伙伴边缘服务器

  - *增强联盟*：将伙伴的 SIP 域名配置为组织的联盟伙伴，并使用 DNS SRV 查找伙伴边缘服务器

  - *直接联盟*：将伙伴的 SIP 域名和 FQDN 配置为伙伴的边缘服务器

  - *服务器允许列表*：接受任何域，使用 DNS SRV 查找宿主提供程序或公共即时消息 (IM) 连接提供程序的边缘服务器

Microsoft Office Communications Server 2007 引入了更新的联盟类型命名方式，以更好地定义各种联盟类型实际实现的内容：

  - 开放增强联盟变为*已发现的伙伴域*

  - 增强联盟变为*允许的伙伴域*

  - 直接联盟变为*允许的伙伴服务器*

  - 服务器允许列表变为*宿主提供程序* 和*公共 IM 提供程序*

Microsoft Lync Server 2010 引入了与 Microsoft Lync Online 2010 和 Microsoft Office 365 一致的更狭窄的宿主提供程序定义，同时使其受到“允许的伙伴域”联盟类型定义的相同允许列表的限制。

一旦启用 Microsoft Lync Server 2013、Lync Server 2010 和 Office Communications Server 之间的联盟，将使用边缘服务器和反向代理以强制实施您定义的规则和允许的伙伴域。从规划的角度来看，与其他 Lync Server 和 Office Communications Server 联盟需要执行以下操作：

  - 在拓扑生成器中启用联盟。有关详细信息，请参阅部署主题[在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。

  - 确定您的联盟域发现的要求：
    
       要手动配置联盟，您必须拥有伙伴的边缘服务器的完全限定域名 (FQDN) 以及域名或联机域名，后者在 Lync Server 控制面板、“联盟和外部访问”、“SIP 联盟域”中输入。创建“新”策略或“编辑”现有策略以通过 FQDN 允许或阻止域。
        
       > [!WARNING]
       > 当联盟伙伴更改其边缘服务器的 IP 地址时，手动配置联盟伙伴的边缘服务器很容易失败。
        
       > [!NOTE]
       > 对于“新的 SIP 联盟域”，必须提供 Microsoft Lync Online 和 Microsoft Office 365 的“域名（或 FQDN）”。对于 Microsoft Lync Server 2013、Lync Server 2010 和 Office Communications Server，还必须提供“访问边缘服务 (FQDN)”
        
       对于已发现的伙伴联盟（其中的伙伴可发现您的边缘服务器），您在外部 DNS (\_sipfederationtls.\_tcp.contoso.com) 中创建一条 SRV 记录（指向端口 5061）和边缘服务器的主机 (A) 记录
        
       > [!IMPORTANT]
       > 如果您要在 Windows Phone 或者 Apple iPhone、iPad 或其他 Apple 设备上支持 Microsoft Lync Mobile 客户端，并且使用推送通知服务或推送通知服务，则必须为每个含有_Lync Mobile 客户端的 SIP 域计划 _sipfederationtls._tcp. <em>&lt;SIP 域&gt;</em> SRV 记录。Android 和 Nokia Symbian Lync Mobile 不使用推送服务，不受此要求的影响。

  - 配置外部用户访问策略以支持联盟域

  - 开放会话初始协议 (SIP)、Web 会议和音频/视频会议的防火墙端口以适应您启用的联盟或联系人。有关详细信息，请参阅：[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

以下信息将帮助您定义针对 Microsoft Lync Server 2013 与 Lync Server 2010 的联盟的证书、端口/协议和 DNS 要求。

如果您已规划或部署 Microsoft Lync Server 2013 边缘服务器，则规划证书、防火墙和端口/协议要求以及 DNS 要求通常是一个非常简单直观的过程。由于联盟是使用现有边缘服务器的一项额外功能，因此，边缘服务器规划和部署通常可满足规划要求。您应使用下表确定是否已满足您的要求并相应地更改端口/协议和 DNS。

> [!IMPORTANT]
> 如果您有一个边缘服务器池且正在与 Lync Server 2013 或 Lync Server 2010 合作伙伴联盟，则您可以在边缘服务器的内部端或外部端上使用 DNS 负载平衡或硬件负载平衡。如果您正在与 Office Communications Server 2007 或 Office Communications Server 2007 R2 联盟，则硬件负载平衡将为边缘服务器提供故障转移支持。DNS 负载平衡 Office Communications Server 2007 和 Office Communications Server 2007 R2 不是 DNS 负载平衡感知的。合作伙伴边缘服务器将建立与您的池中第一个边缘服务器的通信。如果该边缘服务器失败，则通信将不会自动进行故障转移。

通常，通过规划所选边缘服务器的证书或池化的边缘服务器计划满足证书要求。

## 本部分内容

  - [证书摘要 - SIP、XMPP 联盟和公共即时消息](lync-server-2013-certificate-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [端口摘要 - SIP、XMPP 联盟和公共即时消息](lync-server-2013-port-summary-sip-xmpp-federation-and-public-instant-messaging.md)

  - [DNS 摘要 - SIP、XMPP 联盟和公共即时消息](lync-server-2013-dns-summary-sip-xmpp-federation-and-public-instant-messaging.md)

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置策略以控制联盟用户访问](lync-server-2013-configure-policies-to-control-federated-user-access.md)  

#### 概念

[Lync Server 2013 中的外部用户访问方案](lync-server-2013-scenarios-for-external-user-access.md)  
[确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)  
[确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)  

#### 其他资源

[在 Lync Server 2013 中管理您的组织的访问边缘配置](lync-server-2013-manage-access-edge-configuration-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联盟域](lync-server-2013-manage-sip-federated-domains-for-your-organization.md)  
[在 Lync Server 2013 中管理组织的 SIP 联盟提供程序](lync-server-2013-manage-sip-federated-providers-for-your-organization.md)

