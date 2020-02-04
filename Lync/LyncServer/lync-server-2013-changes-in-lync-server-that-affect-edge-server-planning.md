---
title: Lync Server 2013：Lync Server 中影响边缘服务器规划的更改
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
ms.openlocfilehash: 73eda15acbce7eb4b47a0a52602776e8fc830b0e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/04/2020
ms.locfileid: "41730142"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="changes-in-lync-server-2013-that-affect-edge-server-planning"></a>Lync Server 2013 中影响边缘服务器规划的更改

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**主题上次修改时间：** 2012-10-22_

Lync Server 2013 引入了新功能，可为你的用户扩展功能和通信方法。 此外，Lync Server 2013 引入了对现有服务的更改，以便更好地集成和扩展你的组织可使用的服务。 下面是可能影响您规划和部署 Lync Server 2013 Edge 服务器服务的更改的摘要。

<div>

## <a name="support-for-ipv6-addressing"></a>对 IPv6 寻址的支持

Lync Server 2013 支持所有 Edge 服务器服务的 IPv6 寻址。 如果你已通过 Windows Server 中的配置为接口提供 IPv6 地址，则可以在 Edge 服务器配置中通过拓扑生成器中的 IP 地址配置使用 IPv6 地址。 此外，可扩展消息和状态协议（XMPP）支持 IPv6。 不需要额外的配置。 如果在拓扑中配置了 IPv6，XMPP 将使用 IPv6 （如果需要）。

对在 Lync Server 2013 中支持 IPv6 的增加的要求是为必须发现和解析为 IPv6 地址的记录创建域名系统记录。 IPv6 DNS 使用定义为**AAAA**的主机记录和名为 "quad A" 的主机记录。 其他记录类型与它们的 IPv4 对应项一致。

</div>

<div>

## <a name="support-for-extensible-messaging-and-presence-protocol-xmpp-deployment"></a>对可扩展消息和状态协议（XMPP）部署的支持

Edge 服务器引入了完全集成的 XMPP 代理（部署在 Edge 服务器上）和 XMPP 网关（部署在前端服务器上）。 你可以将 XMPP 联盟部署为可选组件。 通过添加和配置 XMPP 代理和 XMPP 网关，你可以允许 Microsoft Lync 2013 用户添加来自基于 XMPP 的合作伙伴的联系人，以便发送即时消息（IM）和状态。

<div>


> [!NOTE]  
> 目前，Edge 服务器中的 XMPP 服务仅在 Lync Server 客户端和基于 XMPP 的联系人之间提供即时消息和状态。 此外，XMPP 仅托管在一个网站中。



</div>

<div>


> [!IMPORTANT]  
> Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。



</div>

</div>

<div>

## <a name="support-for-rolling-audiovideo-authentication-and-server-to-server-authentication-certificates"></a>支持将音频/视频身份验证和服务器滚动到服务器身份验证证书

证书用于生成颁发给客户和 A/V 身份验证服务的其他使用者以及服务器到服务器身份验证的令牌。 音频/视频身份验证证书的类型为*AudioVideoAuthentication* ，服务器到服务器身份验证证书的类型为*OAuthTokenIssuer*。

对于音频/视频身份验证，令牌用于对端口分配请求进行身份验证，令牌缓存最多8小时-令牌的默认生存期。 在 "正常操作" 下，这是创建并将身份验证材料分发给 A/V 消费者的非常可靠的方法。 但是，证书具有有限的生命周期，并在预定义的日期和时间（基于创建证书的证书颁发机构（通常是两年），这种类型的证书的创建日期和策略过期。 当证书到期时，由过期证书创建并由使用者缓存的任何令牌均无效。 任何使用已过期证书创建的令牌的尝试都将导致媒体中继分配失败，并且所有当前音频/视频会话将失败。 客户端需要获取有效证书创建的新令牌才能恢复正常的音频和视频功能。

服务器到服务器身份验证由请求和应用于部署中所有服务器的全局证书管理。 证书负责在 Lync Server 2013 中验证服务器以及对 Exchange 2013 和 Microsoft SharePoint Server 2013 进行身份验证。 有关服务器到服务器身份验证的工作方式的详细信息，请参阅[在 Lync server 2013 中管理服务器到服务器身份验证（OAuth）和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。 音频/视频身份验证过程与服务器到服务器身份验证过程之间的一个非常重要的区别是身份验证或令牌的生命周期。 对于音频/视频身份验证，身份验证将在八个小时后到期。 服务器到服务器身份验证的生命周期为24小时。 您必须针对每种证书类型进行相应规划。

Lync Server 2013 的新增功能是在当前证书到期之前将替换音频/视频身份验证证书和服务器转移到服务器身份验证证书的功能。 然后，新证书用于生成新的令牌或新的身份验证请求。 但保留用于验证当前会话和身份验证的旧证书。 完成此操作的目标是有效地避免因令牌和证书到期而导致几乎所有失败。 有关此功能的详细信息以及如何配置它，请参阅[在 CsCertificate 中使用-滚在 Lync Server 2013 中暂存 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/powershell/module/skype/Set-CsCertificate)

</div>

<div>

## <a name="reduced-reliance-on-cookie-based-affinity"></a>减少了对基于 Cookie 的相似性的依赖

在早期版本的 Lync Server 和 Office 通信服务器中，Web 服务使用基于 cookie 的相关性以确保客户端和 Web 服务会话状态已维护。 Lync Server 2013 Web 服务使用内置的关联机制，可消除基于 cookie 的相似性的大多数要求。

<div>


> [!WARNING]  
> Microsoft Lync 2010 移动客户端仍然必须使用基于 cookie 的相似性，并且需要配置基于 cookie 的相似性，直到将所有客户端迁移到即将发布的 Microsoft Lync 移动客户端（尚未确定的发布日期）。



</div>

有关 Lync Server 2013 中基于 cookie 的相关性的详细信息，请参阅[Lync server 2013 中的外部用户访问所需的组件](lync-server-2013-components-required-for-external-user-access.md)。

</div>

<div>

## <a name="autodiscover-enhancements"></a>自动发现增强

Lync Server 2013 中的自动发现功能使客户能够找到可用于通信的附加功能。 自动发现功能是 Lync Server 2010 的累积更新中第一次引入的2011：移动版和 Microsoft Lync 2010 移动版的累积更新。 自动发现功能（也称为 DNS 记录名称 LyncDiscover 和 LyncDiscoverInternal）允许客户查找和使用移动服务（适用于 Microsoft Lync 2010 移动客户端）、Microsoft Lync Web App 和 Lync Web 计划程序以及与 Microsoft Exchange Server 和 SharePoint Server 的通信。 自动发现作为基础结构和 Lync Server 2013 服务器的设置和部署的正常部分进行安装。 拓扑生成器和 Lync Server 部署向导可消除 Lync Server 2010 的累积更新中所需的大部分配置任务：2011年11月。

</div>

<div>

## <a name="services-for-mobile-clients"></a>适用于移动客户端的服务

在 Lync Server 2010 的累积更新中引入：年 11 2011 月，Lync Server 中的移动服务2013启用使用支持的 Apple iOS、Android、Windows Phone 或 Nokia 移动设备运行 Lync Mobile 和平板电脑设备的移动电话活动，例如发送和接收即时消息、查看联系人和查看状态。 此外，移动设备支持某些企业语音功能，例如单击以加入会议、通过工作、单号码到达、语音邮件和错过的呼叫通知进行呼叫。

<div>


> [!NOTE]  
> 移动服务使用部署在前端服务器上的反向代理和发布的服务。 不需要对边缘服务器进行任何更改。 您最少需要出站 SIP/TCP/5061from 运行 Lync Server Access Edge 服务的服务器。



</div>

</div>

<div>

## <a name="director-role-is-optional"></a>主管角色是可选的

Lync Server 2013 拓扑中 Director 服务器的角色未更改。 它仍托管 web 服务，preauthenticates 传入的用户请求，并将外部用户定向到其主池。 通过将 Director 从推荐的角色更改为可选角色，Microsoft 不打算降低 Director 的价值。 目的是减少服务器数量和其他硬件要求（例如，控制器的硬件负载平衡器），而不影响功能和功能。 由于前端服务器可以执行与提供的服务不受影响的控制器相同的作业，因此，如果你选择，则可以部署控制器。 您可以放心地排除 Director，前端服务器将提供相同的服务来代替 Director。

</div>

</div>

<span> </span>

</div>

</div>

</div>

