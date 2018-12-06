---
title: 在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟
TOCTitle: 在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟
ms:assetid: 952b33e2-1f58-4831-9a39-1dfec2a316ad
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205107(v=OCS.15)
ms:contentKeyID: 49313642
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中规划可扩展消息和状态协议 (XMPP) 联盟

 

_**上一次修改主题：** 2012-10-22_

之前的 Lync Server 和 Office Communications Server 版本中提供了可扩展消息传递和状态协议 (XMPP) 网关，可将该网关作为单独的服务器角色部署以允许与 XMPP 部署联盟。在 Microsoft Lync Server 2013 中，XMPP 功能可作为功能部署。XMPP 功能在两个部分中安装：在边缘服务器上运行的 XMPP 代理和在前端服务器上运行的 XMPP 网关。

[在 Lync Server 2013 中部署外部用户访问](lync-server-2013-deploying-external-user-access.md)中涵盖了 XMPP 的部署和配置。通过在防火墙上定义端口和协议规则、配置证书和添加 DNS 记录来规划组织中的 XMPP 支持。本节中的以下主题总结了成功为部署规划 XMPP 联盟所需的信息。

> [!IMPORTANT]
> Microsoft 已测试 Lync Server 2013 的 XMPP 功能，并且支持该功能与 Google Talk 进行即时消息传递联盟。对于任何其他 XMPP 系统，请与第三方供应商联系，以确认它们是否支持与 Lync Server 2013 联盟以及获取任何部署或疑难解答建议。


## 本部分内容

  - [证书摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟](lync-server-2013-certificate-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [端口摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟](lync-server-2013-port-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

  - [DNS 摘要 - 可扩展消息传递和状态协议 (XMPP) 联盟](lync-server-2013-dns-summary-extensible-messaging-and-presence-protocol-xmpp-federation.md)

## 另请参阅

#### 任务

[在 Lync Server 2013 中设置 XMPP 联盟](lync-server-2013-setting-up-xmpp-federation.md)  
[在 Lync Server 2013 中配置策略以控制 XMPP 联盟用户访问](lync-server-2013-configure-policies-to-control-xmpp-federated-user-access.md)  

#### 其他资源

[在 Lync Server 2013 中管理组织的 XMPP 联盟伙伴](lync-server-2013-manage-xmpp-federated-partners-for-your-organization.md)  
[Get-CsExternalAccessPolicy](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsExternalAccessPolicy)  
[Get-CsXmppAllowedPartner](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppAllowedPartner)  
[Get-CsXmppGatewayConfiguration](https://docs.microsoft.com/en-us/powershell/module/skype/Get-CsXmppGatewayConfiguration)

