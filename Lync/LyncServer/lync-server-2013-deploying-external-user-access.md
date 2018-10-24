---
title: Lync Server 2013：部署外部用户访问
TOCTitle: 部署外部用户访问
ms:assetid: d40c9574-c16b-4fe6-b848-21ae0b7e4f0e
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398918(v=OCS.15)
ms:contentKeyID: 49314360
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中部署外部用户访问

 

_**上一次修改主题：** 2013-09-23_

通过为 Microsoft Lync Server 2013 部署边缘组件，未登录到您组织的内部网络的外部用户（包括经过身份验证的和匿名的远程用户、联盟合作伙伴（包括 XMPP 合作伙伴）、移动客户端以及公共即时消息 (IM) 服务的用户）可以使用 Lync Server 与您组织内的其他用户进行通信。 Lync Server 2013 的部署和配置过程与 Lync Server 2010 的部署和配置过程有显著的不同。用于安装和管理的工具与 Lync Server 2010 中的工具非常相似。

> [!IMPORTANT]
> Microsoft Lync Server 2013边缘服务器安装和配置可能是一个较为复杂的过程，它可能要求大量规划以及与您的内部团队进行协作，包括但不限于，安全、网络、防火墙、域名系统 (DNS)、负载平衡器以及公钥基础结构 (PKI) 注意事项。强烈建议您在部署外部访问组件之前，先查看和使用规划过程和提供的文档。这将帮助您限制在部署过程中出现的意外更改和问题的数目和频率。有关规划外部用户访问的信息，请参阅 <a href="lync-server-2013-planning-for-external-user-access.md">在 Lync Server 2013 中规划外部用户访问</a>。


## 本部分内容

  - [Lync Server 2013 中外部用户访问的部署清单](lync-server-2013-deployment-checklist-for-external-user-access.md)

  - [Lync Server 2013 的外部用户访问组件的系统要求](lync-server-2013-system-requirements-for-external-user-access-components.md)

  - [准备针对 Lync Server 2013 在外围网络中安装服务器](lync-server-2013-preparing-for-installation-of-servers-in-the-perimeter-network.md)

  - [在 Lync Server 2013 中构建边缘和控制器拓扑](lync-server-2013-building-an-edge-and-director-topology.md)

  - [在 Lync Server 2013 中设置控制器](lync-server-2013-setting-up-the-director.md)（可选）

  - [在 Lync Server 2013 中设置边缘服务器](lync-server-2013-setting-up-edge-servers.md)

  - [为 Lync Server 2013 设置反向代理服务器](lync-server-2013-setting-up-reverse-proxy-servers.md)

  - [在 Lync Server 2013 中配置对外部用户访问的支持](lync-server-2013-configuring-support-for-external-user-access.md)

  - [Lync Server 2013 中的 Lync-Skype 连接设置指南](lync-server-2013-provisioning-guide-for-lync-skype-connectivity.md)

  - [在 Lync Server 2013 中配置 SIP 联盟、XMPP 联盟和公共即时消息](lync-server-2013-configuring-sip-federation-xmpp-federation-and-public-instant-messaging.md)

  - [在 Lync Server 2013 中部署移动功能](lync-server-2013-deploying-mobility.md)

  - [在 Lync Server 2013 中验证边缘部署](lync-server-2013-verifying-your-edge-deployment.md)

