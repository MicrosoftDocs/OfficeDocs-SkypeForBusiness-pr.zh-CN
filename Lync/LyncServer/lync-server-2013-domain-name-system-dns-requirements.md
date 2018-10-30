---
title: 域名系统 (DNS) 要求
TOCTitle: 域名系统 (DNS) 要求
ms:assetid: 586cf18e-0080-4eb1-aee5-56843277fdfc
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398386(v=OCS.15)
ms:contentKeyID: 49312926
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 域名系统 (DNS) 要求

 

_**上一次修改主题：** 2012-06-18_

要部署 Lync Server，必须创建域名系统 (DNS) 记录，该记录可启用客户端和服务器发现，并可以选择支持自动客户端登录（如果组织希望支持该功能）。

Lync Server 通过以下方式使用 DNS：

  - 发现内部服务器或池以进行服务器至服务器的通信。

  - 使客户端可以发现用于各种 SIP 事务的前端池或 Standard Edition Server。

  - 使未登录的统一通信 (UC) 设备可以发现运行设备更新 Web 服务的前端池或 Standard Edition Server，获得更新和发送日志。

  - 使外部服务器和客户端可以连接至用于即时消息 (IM) 或会议的边缘服务器或 HTTP 反向代理。

  - 使外部 UC 设备可以通过边缘服务器或 HTTP 反向代理连接至设备更新 Web 服务以及获得更新。

  - 使移动客户端可以自动发现 Web 服务资源，而无需用户在设备设置中手动输入 URL。

## 本部分内容

  - [确定 Lync Server 2013 的 DNS 要求](lync-server-2013-determine-dns-requirements.md)

  - [前端池的 DNS 要求](lync-server-2013-dns-requirements-for-front-end-pools.md)

  - [Standard Edition Server 的 DNS 要求](lync-server-2013-dns-requirements-for-standard-edition-servers.md)

  - [Lync Server 2013 中简单 URL 的 DNS 要求](lync-server-2013-dns-requirements-for-simple-urls.md)

  - [自动客户端登录的 DNS 要求](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)

  - [移动的 DNS 要求](lync-server-2013-dns-requirements-for-mobility.md)

  - [Lync Server 2013 中的 DNS 负载平衡](lync-server-2013-dns-load-balancing.md)

