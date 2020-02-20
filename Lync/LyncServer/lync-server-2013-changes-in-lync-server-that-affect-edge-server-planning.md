---
title: Lync Server 2013： Lync Server 中影响边缘服务器规划的更改
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Changes in Lync Server 2013 that affect Edge Server planning
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204965(v=OCS.15)
ms:contentKeyID: 48184378
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be2944125e5338dcc9b90b54f19fac003ec07287
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/19/2020
ms.locfileid: "42151052"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Lync Server 2013 中影响边缘服务器规划的更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**上次修改的主题：** 2012-10-22_

Lync Server 2013 引入了新功能，用于扩展用户的功能和通信方法。 另外，Lync Server 2013 引入了对现有服务所做的更改，以便更好地集成和扩展可供您的组织使用的服务。 以下是可能影响您规划和部署 Lync Server 2013 Edge Server 服务的更改的摘要。

<div>

## <a name="support-for-ipv6-addressing"></a>对 IPv6 寻址的支持

Lync Server 2013 支持所有边缘服务器服务的 IPv6 寻址。 如果已通过 Windows Server 中的配置为接口提供了 IPv6 地址，则可以通过拓扑生成器中的 IP 地址配置来使用边缘服务器配置中的 IPv6 地址。 此外，可扩展消息传递和状态协议 (XMPP) 也支持 IPv6。 无需其他配置。 如果在拓扑中配置了 IPv6，则 XMPP 将使用 IPv6（根据需要）。

在 Lync Server 2013 中支持 IPv6 的新增要求是为必须发现和解析为 IPv6 地址的记录创建域名系统记录。 IPv6 DNS 使用定义为“AAAA”**** 且称为“quad-A”的主机记录。 其他记录类型与其对应 IPv4 一致。

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>对可扩展消息传递和状态协议 (XMPP) 部署的支持

边缘服务器引入了完全集成的 XMPP 代理（部署在边缘服务器上）和 XMPP 网关（部署在前端服务器上）。 可将 XMPP 联盟作为可选组件来部署。 通过添加和配置 XMPP 代理和 XMPP 网关，可以使 Microsoft Lync 2013 用户能够从基于 XMPP 的合作伙伴中添加联系人，以实现即时消息（IM）和状态。

<div>


> [!NOTE]  
> 目前，边缘服务器中的 XMPP 服务仅在 Lync Server 客户端和基于 XMPP 的联系人之间提供 IM 和状态。 此外，只在一个站点中承载 XMPP。



</div>

<div>


> [!IMPORTANT]  
> Microsoft 对 Lync Server 2013 的 XMPP 功能进行了测试，并支持 Microsoft 实现与 Google 谈话的即时消息联盟。 对于任何其他 XMPP 系统，请联系第三方供应商以验证它们是否支持与 Lync Server 2013 联合，以及任何部署或疑难解答建议。



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>对回滚音频/视频身份验证和服务器到服务器身份验证证书的支持

证书用于生成颁发给客户端和其他 A/V 身份验证服务的使用者以及用于服务器到服务器身份验证的令牌。音频/视频身份验证证书的类型为 *AudioVideoAuthentication*，而服务器到服务器身份验证证书的类型为 *OAuthTokenIssuer*。

对于音频/视频身份验证，令牌用于验证端口分配请求的身份，并且最多缓存令牌 8 个小时（令牌的默认生存期）。在常规操作下，这是非常可靠的创建身份验证材料并将其分发给 A/V 使用者的方法。但是，证书的生存期有限，将在预定义的日期和时间到期（基于创建日期和创建证书的证书颁发机构强制实施的策略，一般此类型的证书的生存期为 2 年）。证书过期后，过期证书创建的以及使用者缓存的任何令牌都将变得无效。任何使用过期证书创建的令牌的尝试都将导致失败的媒体中继分配并且任何当前音频/视频会话将失败。客户端将需要获取有效证书创建的新令牌才能恢复标准音频和视频功能。

服务器到服务器身份验证由请求并应用于部署中所有服务器的全局证书管理。 证书负责在 Lync Server 2013 中对服务器进行身份验证，并对 Exchange 2013 和 Microsoft SharePoint Server 2013 进行身份验证。 有关服务器到服务器身份验证的工作方式的详细信息，请参阅[在 Lync server 2013 中管理服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。 音频/视频身份验证过程和服务器到服务器身份验证过程之间一个非常重要的差异是身份验证或令牌的生存期。 对于音频/视频身份验证，身份验证将在 8 小时之后过期。 服务器到服务器身份验证的生存期为 24 小时。 您必须针对每种证书类型进行相应规划。

Lync Server 2013 的新增功能是在当前证书到期之前将替换的音频/视频身份验证证书和服务器暂存到服务器身份验证证书的功能。 然后，使用新证书来生成新令牌或新的身份验证请求。 但保留用于验证当前会话和身份验证的旧证书。。 完成此操作的目标是有效避免令牌和证书过期导致的几乎所有故障。 有关此功能以及如何对其进行配置的详细信息，请参阅[set-cscertificate 中的使用的暂存 AV 和 OAuth 证书在 Lync Server 2013 中](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>减少对基于 Cookie 的关联的依赖

在早期版本的 Lync Server 和 Office 通信服务器中，Web 服务使用基于 cookie 的相关性，以确保维护客户端和 Web 服务会话状态。 Lync Server 2013 Web 服务使用内置的关联机制，消除了基于 cookie 的相关性的大部分要求。

<div>


> [!WARNING]  
> Microsoft Lync 2010 移动客户端仍必须使用基于 cookie 的相关性，并且需要配置基于 cookie 的相关性，直到将所有客户端迁移到即将发布的 Microsoft Lync 移动客户端（尚未确定的发布日期）。



</div>

有关 Lync Server 2013 中基于 cookie 的相关性的详细信息，请参阅[Lync server 2013 中的外部用户访问所需的组件](lync-server-2013-components-required-for-external-user-access.md)。

</div>

<div>

## <a name="autodiscover-enhancements"></a>自动发现增强功能

Lync Server 2013 中的自动发现功能使客户端能够查找可用于通信的其他功能。 自动发现在 Lync Server 2010 的累积更新中首次引入：移动性和 Microsoft Lync 2010 移动的11月2011。 自动发现功能（也称为 DNS 记录名称 Lyncdiscover. 和 Lyncdiscoverinternal.）允许客户端查找和使用移动服务（适用于 Microsoft Lync 2010 移动客户端）、Microsoft Lync Web App 和 Lync Web 计划，以及与 Microsoft Exchange Server 和 SharePoint Server 的通信。 自动发现作为基础结构和 Lync Server 2013 服务器的安装和部署的正常部分进行安装。 拓扑生成器和 Lync Server 部署向导消除了 Lync Server 2010 的累积更新中所需的大部分配置任务：2011年11月。

</div>

<div>

## <a name="services-for-mobile-clients"></a>适用于移动客户端的服务

在 Lync Server 2010 的累积更新中引入：2011年11月，Lync Server 中的移动服务2013使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备运行 Lync Mobile 和平板电脑设备的移动电话，以执行发送和接收即时消息、查看联系人和查看状态等活动。 此外，移动设备支持某些企业语音功能，例如，通过单击加入会议、通过工作、单号码到达、语音邮件和未接来电通知进行呼叫。

<div>


> [!NOTE]  
> Mobility Service 使用反向代理和在前端服务器上部署的已发布服务。 无需对边缘服务器进行任何更改。 至少您需要出站 SIP/TCP/5061from 运行 Lync Server 访问边缘服务的服务器。



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>控制器角色为可选角色

Lync Server 2013 拓扑中的控制器服务器角色未发生更改。 它仍承载 Web 服务，对传入的用户请求进行预身份验证，并将外部用户定向到其主池。 通过将控制器从推荐的角色更改为可选角色，Microsoft 不打算降低 Director 的价值。 目的是减少服务器数量和其他硬件要求（例如，控制器的硬件负载平衡器），而不会影响功能和功能。 由于前端服务器可以执行与提供的服务不受影响的控制器，因此，如果您选择，则可以部署控制器。 您可以放心地排除 Director，前端服务器将提供相同的服务来取代控制器。

</div>

</div>

<span> </span>

</div>

</div>

</div>

