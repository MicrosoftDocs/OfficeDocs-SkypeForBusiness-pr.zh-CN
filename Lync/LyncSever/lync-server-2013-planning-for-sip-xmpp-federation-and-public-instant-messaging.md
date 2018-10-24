---
title: 规划 SIP、XMPP 联盟和公共即时消息
TOCTitle: 规划 SIP、XMPP 联盟和公共即时消息
ms:assetid: 3b234d92-b9ff-4b1d-910e-084c6f17e751
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204825(v=OCS.15)
ms:contentKeyID: 49312550
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 规划 SIP、XMPP 联盟和公共即时消息

 

_**上一次修改主题：** 2013-10-28_

可以将边缘服务器配置为允许您的内部和外部用户访问合作伙伴组织中的联系人或服务。在这些合作伙伴协议已知的情况下，联盟可以将任何或所有以下功能提供给加入伙伴联盟的贵组织中的联系人，或与贵组织联盟的合作伙伴组织中的联系人：

  - 即时消息和状态

  - 协作和会议，例如 Web 会议

  - 音频会议和/或视频会议

在某些情况下，通信（例如 Microsoft Lync Server 2013 和可扩展消息传递和状态协议 (XMPP) 联系人之间的即时消息 (IM) 和状态）只能是对等的，并且仅支持在您和联盟伙伴的联系人之间进行。在其他情况下（例如 Lync Server、Lync Server 2010 到 Lync Server 2013 联盟），则可以邀请多个参与者加入对话。

## Lync Server 和 Office Communications Server 联盟

Microsoft Lync Server 2013、 Lync Server 2010 和 Office Communications Server 之间的联盟支持对等和多方通信。对等对话可升级为多方会话，从而允许临时会议。可以安排会议（即 Web 会议或音频/视频会议）以包含您组织内的联系人以及您的联盟合作伙伴内的联系人。

联盟首次出现于 Microsoft Office Live Communications Server 2005 并且仅有直接联盟这一种联盟收到支持。直接联盟要求您知道联盟伙伴的会话初始协议 (SIP) 域以及伙伴的 边缘服务器的完全限定域名 (FQDN)。 Live Communications Server 2005 SP1 引入了更多联盟类型，所有联盟类型都要求联盟伙伴发布域名系统 (DNS) SRV 记录以查找其 边缘服务器。该版本的术语有：

  - *开放增强联盟* ：接受任何 SIP 域名并使用 DNS SRV 查找伙伴 边缘服务器

  - *增强联盟* ：将伙伴的 SIP 域名配置为组织的联盟伙伴，并使用 DNS SRV 查找伙伴 边缘服务器

  - *直接联盟* ：将伙伴的 SIP 域名和 FQDN 配置为伙伴的 边缘服务器

  - *服务器允许列表* ：接受任何域，使用 DNS SRV 查找宿主提供程序或公共即时消息 (IM) 连接提供程序的 边缘服务器

Microsoft Office Communications Server 2007 引入了更新的联盟类型命名方式，以更好地定义各种联盟类型实际实现的内容：

  - 开放增强联盟变为 *已发现的伙伴域*

  - 增强联盟变为 *允许的伙伴域*

  - 直接联盟变为 *允许的伙伴服务器*

  - 服务器允许列表变为 *宿主提供程序* 和 *公共 IM 提供程序*

Microsoft Lync Server 2010 引入了与 Microsoft Lync Online 2010 和 Microsoft Office 365 一致的更狭窄的宿主提供程序定义，同时使其受到“允许的伙伴域”联盟类型定义的相同允许列表的限制。

一旦启用 Microsoft Lync Server 2013、 Lync Server 2010 和 Office Communications Server 之间的联盟，将使用 边缘服务器和反向代理以强制实施您定义的规则和允许的伙伴域。从规划的角度来看，与其他 Lync Server 和 Office Communications Server 联盟需要执行以下操作：

  - 在拓扑生成器中启用联盟。有关详细信息，请参阅部署主题 [在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)。

  - 确定您的联盟域发现的要求：
    
       要手动配置联盟，您必须拥有伙伴的 边缘服务器的完全限定域名 (FQDN) 以及域名或联机域名，后者在 Lync Server 控制面板、“联盟和外部访问”、“SIP 联盟域”中输入。创建**新**策略或**编辑**现有策略以通过 FQDN 允许或阻止域。
        
       > [!WARNING]
       > 当联盟伙伴更改其 边缘服务器的 IP 地址时，手动配置联盟伙伴的 边缘服务器很容易失败。
        
       > [!NOTE]
       > 对于<strong>新的 SIP 联盟域</strong>，必须提供 Microsoft Lync Online 和 Microsoft Office 365 的<strong>域名（或 FQDN）</strong>。对于 Microsoft Lync Server 2013、 Lync Server 2010 和 Office Communications Server，还必须提供<strong>访问边缘服务 (FQDN)</strong>
        
       对于已发现的伙伴联盟（其中的伙伴可发现您的 边缘服务器），您在外部 DNS (\_sipfederationtls.\_tcp.contoso.com) 中创建一条 SRV 记录（指向端口 5061）和 边缘服务器的主机 (A) 记录
        
       > [!IMPORTANT]
       > 如果您要在 Windows Phone 或者 Apple iPhone、iPad 或其他 Apple 设备上支持 Microsoft Lync Mobile 客户端，并且使用 推送通知服务或 推送通知服务，则必须为每个含有_ Lync Mobile 客户端的 SIP 域计划 _sipfederationtls._tcp. <em>&lt;SIP 域&gt;</em> SRV 记录。Android 和 Nokia Symbian Lync Mobile 不使用推送服务，不受此要求的影响。

  - 配置外部用户访问策略以支持联盟域

  - 开放会话初始协议 (SIP)、Web 会议和音频/视频会议的防火墙端口以适应您启用的联盟或联系人。有关详细信息，请参阅： [确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)

以下信息将帮助您定义针对 Microsoft Lync Server 2013 与 Lync Server 2010 的联盟的证书、端口/协议和 DNS 要求。

如果您已规划或部署 Microsoft Lync Server 2013  边缘服务器，则规划证书、防火墙和端口/协议要求以及 DNS 要求通常是一个非常简单直观的过程。由于联盟是使用现有 边缘服务器的一项额外功能，因此， 边缘服务器规划和部署通常可满足规划要求。您应使用下表确定是否已满足您的要求并相应地更改端口/协议和 DNS。

> [!IMPORTANT]
> 如果您有一个 边缘服务器池且正在与 Lync Server 2013 或 Lync Server 2010 合作伙伴联盟，则您可以在 边缘服务器的内部端或外部端上使用 DNS 负载平衡或硬件负载平衡。如果您正在与 Office Communications Server 2007 或 Office Communications Server 2007 R2 联盟，则硬件负载平衡将为 边缘服务器提供故障转移支持。DNS 负载平衡 Office Communications Server 2007 和 Office Communications Server 2007 R2 不是 DNS 负载平衡感知的。合作伙伴 边缘服务器将建立与您的池中第一个 边缘服务器的通信。如果该 边缘服务器失败，则通信将不会自动进行故障转移。


通常，通过规划所选 边缘服务器的证书或池化的 边缘服务器计划满足证书要求。

## 公共即时消息连接

公共即时消息连接是一类联盟，配置该连接是为了允许内外部 Lync Server 2013 用户从以下任何用户中添加联系人：

  - Messenger 联系人

  - Yahoo\! 联系人

  - America Online (AOL) 联系人

> [!IMPORTANT]
> <ul>
> <li>自 2012 年 9 月 1 日起，Microsoft Lync 公共 IM 连接用户订阅许可证 (PIC USL) 将不再用于购买新的或续订协议。具有活动许可证的客户将能继续与 Yahoo! Messenger 联盟，直到服务关闭日期（具体日期仍有待决定，但不会早于 2013 年 6 月）。</li>
> <li>PIC USL 是 Lync Server 或 Office Communications Server 与 Yahoo! Messenger 联盟所必需的每用户、每月订阅许可证。Microsoft 是否能够提供此服务视 Yahoo! 的支持而定，将不续订 Yahoo! 的底层协议。</li>
> <li>与以往相比，Lync 是一个更强大的工具，可用于跨多个组织进行联系以及与世界各地的各个用户进行联系。与 Windows Live Messenger 联盟无需 Lync Standard CAL 之外的其他任何用户/设备许可证。Skype 联盟将添加到此列表，使 Lync 用户能够通过 IM 和语音与数亿人联系。</li>
> </ul>

此类联盟需要规划以下注意事项：

  - Windows Live Messenger 用户可与 Lync Server 2013 用户进行对等音频/可视通信以及即时消息传递。您的 边缘服务器必须满足特定端口和协议要求。有关详细信息，请参阅 [确定 Lync Server 2013 的外部 A/V 防火墙和端口要求](lync-server-2013-determine-external-a-v-firewall-and-port-requirements.md)。

  - Yahoo 即时消息除通常在规划和部署提供联盟的典型 边缘服务器时使用的要求之外，没有其他独特要求。

  - America Online 要求分配到 访问边缘服务 的 边缘服务器 证书具有一个客户端增强型密钥使用 (EKU)。

## 可扩展消息和状态协议 (XMPP) 联盟

之前的 Lync Server 和 Office Communications Server 版本中提供了可扩展消息传递和状态协议 (XMPP) 网关，可将该网关作为单独的服务器角色部署以允许与 XMPP 部署联盟。在 Microsoft Lync Server 2013 中，XMPP 功能可作为功能部署。XMPP 功能在两个部分中安装：在 边缘服务器上运行的 XMPP 代理和在 前端服务器上运行的 XMPP 网关。

[在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)中涵盖了 XMPP 的部署和配置。通过在防火墙上定义端口和协议规则、配置证书和添加 DNS 记录来规划组织中的 XMPP 支持。本节中的以下主题总结了成功为部署规划 XMPP 联盟所需的信息。

> [!IMPORTANT]
> Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。

> [!IMPORTANT]
> 对于驻留在 Survivable Branch Appliance 上的用户不支持 XMPP 联盟。这适用于查看状态信息和交换 IM 消息。

以下主题包含为支持的联盟方案类型定义证书、防火墙端口和 DNS 条目相关的指导。

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

