---
title: Lync Server 2013：Lync Server 中影响边缘服务器规划的更改
TOCTitle: Lync Server 2013 中影响边缘服务器规划的更改
ms:assetid: 66305160-c9b8-4bc4-9f24-8ee8d9a294f7
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ204965(v=OCS.15)
ms:contentKeyID: 49313086
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中影响边缘服务器规划的更改

 

_**上一次修改主题：** 2012-10-22_

Lync Server 2013 引入了扩展用户的功能和通信方式的新功能。而且， Lync Server 2013 引入了对现有服务的更改，以便更好地集成和扩展可供组织使用的服务。下面是可能会影响 Lync Server 2013  边缘服务器服务的规划和部署的更改的摘要。

## 对 IPv6 寻址的支持

Lync Server 2013 支持用于所有 边缘服务器服务的 IPv6 寻址。如果您已通过 Windows Server 中的配置为接口提供了 IPv6 地址，则可在通过 拓扑生成器的 IP 地址配置的 边缘服务器配置中使用 IPv6 地址。此外，可扩展消息传递和状态协议 (XMPP) 也支持 IPv6。无需其他配置。如果在拓扑中配置了 IPv6，则 XMPP 将使用 IPv6（根据需要）。

在 Lync Server 2013 中支持 IPv6 的一个新增要求是为必须发现和解析为 IPv6 地址的记录创建域名系统记录。IPv6 DNS 使用定义为“AAAA”且称为“quad-A”的主机记录。其他记录类型与其对应 IPv4 一致。

## 对可扩展消息传递和状态协议 (XMPP) 部署的支持

边缘服务器引入了完全集成的 XMPP 代理（部署在边缘服务器上）和 XMPP 网关（部署在前端服务器上）。可将 XMPP 联盟作为可选组件来部署。添加和配置 XMPP 代理和 XMPP 网关将允许 Microsoft Lync 2013 用户从基于 XMPP 的合作伙伴中为即时消息 (IM) 和状态添加联系人。

> [!NOTE]  
> 当前， 边缘服务器中的 XMPP 服务只在 Lync Server 客户端与基于 XMPP 的联系人之间提供 IM 和状态。此外，只在一个站点中承载 XMPP。



> [!IMPORTANT]  
> Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。


## 对回滚音频/视频身份验证和服务器到服务器身份验证证书的支持

证书用于生成颁发给客户端和其他 A/V 身份验证服务的使用者以及用于服务器到服务器身份验证的令牌。音频/视频身份验证证书的类型为 *AudioVideoAuthentication* ，而服务器到服务器身份验证证书的类型为 *OAuthTokenIssuer* 。

对于音频/视频身份验证，令牌用于验证端口分配请求的身份，并且最多缓存令牌 8 个小时（令牌的默认生存期）。在常规操作下，这是非常可靠的创建身份验证材料并将其分发给 A/V 使用者的方法。但是，证书的生存期有限，将在预定义的日期和时间到期（基于创建日期和创建证书的证书颁发机构强制实施的策略，一般此类型的证书的生存期为 2 年）。证书过期后，过期证书创建的以及使用者缓存的任何令牌都将变得无效。任何使用过期证书创建的令牌的尝试都将导致失败的媒体中继分配并且任何当前音频/视频会话将失败。客户端将需要获取有效证书创建的新令牌才能恢复标准音频和视频功能。

服务器到服务器身份验证由请求并应用于部署中所有服务器的全局证书管理。此证书负责验证 Lync Server 2013 中服务器的身份以及验证 Exchange 2013 和 Microsoft SharePoint Server 2013 的身份。有关服务器到服务器身份验证的工作原理的详细信息，请参阅 [在 Lync Server 2013 中管理服务器到服务器身份验证 (Oauth) 和合作伙伴应用程序](lync-server-2013-managing-server-to-server-authentication-oauth-and-partner-applications.md)。音频/视频身份验证过程和服务器到服务器身份验证过程之间一个非常重要的差异是身份验证或令牌的生存期。对于音频/视频身份验证，身份验证将在 8 小时之后过期。服务器到服务器身份验证的生存期为 24 小时。您必须针对每种证书类型进行相应规划。

Lync Server 2013 的新增功能是在当前证书过期前提供替换的音频/视频身份验证证书和服务器到服务器身份验证证书。之后将使用新证书生成新的令牌或新的身份验证请求，但保留旧证书来验证当前会话和身份验证。此功能适用于有效阻止令牌和证书过期导致的几乎所有故障。有关此功能以及其配置方式的详细信息，请参阅 [在 Set-CsCertificate 中使用滚动分期 AV 和 OAuth 证书](lync-server-2013-staging-av-and-oauth-certificates-using-roll-in-https://docs.microsoft.com/en-us/powershell/module/skype/Set-CsCertificate)

## 减少对基于 Cookie 的关联的依赖

在之前版本的 Lync Server 和 Office Communications Server 中，基于 Cookie 的关联由 Web 服务用于确保维持客户端和 Web 服务会话的状态。 Lync Server 2013 Web 服务使用内置关联机制来评估基于 Cookie 的关联的大部分要求。

> [!WARNING]
> 在将所有客户端迁移到即将到来的 Microsoft Lync Mobile 客户端之前， Microsoft Lync 2010 Mobile 客户端必须使用基于 Cookie 的关联并且需要配置基于 Cookie 的关联（尚未确定发布日期）。


有关 Lync Server 2013 中基于 Cookie 的关联的详细信息，请参阅 [Lync Server 2013 中外部用户访问所需的组件](lync-server-2013-components-required-for-external-user-access.md)。

## 自动发现增强功能

Lync Server 2013 中的自动发现功能使客户端可查找可用于通信的其他功能。自动发现最初是在 2011 年 11 月版的 Lync Server 2010 累积更新中为 Mobility 和 Microsoft Lync 2010 Mobile 引入的。自动发现功能（也称为 DNS 记录名称 LyncDiscover 和 LyncDiscoverInternal）允许客户端查找和使用 Mobility Service（对于 Microsoft Lync 2010 Mobile 客户端）、 Microsoft Lync Web App 和 Lync Web 计划程序以及与 Microsoft Exchange Server 和 SharePoint Server 的通信。自动发现是作为您的基础结构和 Lync Server 2013 服务器的正常的设置和部署部分安装的。 拓扑生成器和 Lync Server 部署向导评估 2011 年 11 月版的 Lync Server 2010 的累积更新中所需的大部分配置任务。

## 适用于移动客户端的服务

在 2011 年 11 月版的 Lync Server 2010 的累积更新中引入，Lync Server 2013 中的 Mobility Service 允许使用受支持的 Apple iOS、Android、Windows Phone 运行 Lync Mobile 的移动电话和平板设备或 Nokia 移动设备执行发送和接收即时消息、查看联系人和查看状态等活动。此外，移动设备还支持某些企业语音功能，例如，“单击加入会议”、“单位电话呼叫”、“一号通”、“语音邮件”和“错过的呼叫通知”。

> [!NOTE]  
> Mobility Service 使用反向代理和在前端服务器上部署的已发布服务。无需对边缘服务器进行任何更改。至少需要来自运行 Lync Server 访问边缘服务的服务器的出站 SIP/TCP/5061。



## 控制器角色为可选角色

Lync Server 2013 拓扑中的 控制器服务器角色未更改。它仍承载 Web 服务，对传入的用户请求进行预身份验证，并将外部用户定向到其主池。将 控制器由建议角色更改为可选角色，Microsoft 不会降低 控制器的价值。目的在于减少服务器计数和其他硬件要求（例如，用于 控制器的硬件负载平衡器），而不会影响特性和功能。由于 前端服务器可与 控制器执行相同的工作，并且不会影响所提供的服务，因此可根据您的选择部署控制器。您可以安全地排除 控制器，并确信 前端服务器将会代替 控制器提供相同的服务。

