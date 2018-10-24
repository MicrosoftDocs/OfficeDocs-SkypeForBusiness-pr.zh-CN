---
title: 'Lync Server 2013：配置增强型 9-1-1 '
TOCTitle: 配置增强型 9-1-1
ms:assetid: 5967de00-c8b9-4923-86da-6ad3369a4cad
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398390(v=OCS.15)
ms:contentKeyID: 49312927
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置增强型 9-1-1

 

_**上一次修改主题：** 2013-02-24_

增强型 9-1-1 (E9-1-1) 是一种紧急通知功能，可以将呼叫者的电话号码与某个市政地址或街道地址相关联。使用此信息，公共安全应答点 (PSAP) 可以迅速向需要帮助的呼叫者提供紧急服务。

为了支持 E9-1-1，Lync Server 2013 必须能正确地将位置与客户端关联，然后确保可使用此信息将紧急呼叫路由到最近的 PSAP。

有关规划 E9-1-1 部署的详细信息，请参阅 [在 Lync Server 2013 中规划紧急服务 (E9-1-1)](lync-server-2013-planning-for-emergency-services-e9-1-1.md)。

> [!IMPORTANT]  
> Lync Server 2013 仅支持位于美国内部的 E9-1-1。若要部署 E9-1-1，您需要配置与已认证的 E9-1-1 服务提供商的 SIP 连接，或将紧急位置标识号 (ELIN) 网关部署到基于公用电话交换网 (PSTN) 的 E9-1-1 服务提供商。有关详细信息，请参阅 <a href="lync-server-2013-enhanced-9-1-1-e9-1-1-and-mediation-server.md">Lync Server 2013 中的增强型 9-1-1 (E9-1-1) 和中介服务器</a>。有关配置中继连接的详细信息，请参阅 <a href="lync-server-2013-configure-a-trunk-with-media-bypass.md">在 Lync Server 2013 中配置带媒体旁路的中继</a>。


## 本部分内容

  - [在 Lync Server 2013 中配置 E9-1-1 语音路由](lync-server-2013-configure-an-e9-1-1-voice-route.md)

  - [在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)

  - [在 Lync Server 2013 中为 E9-1-1 配置站点信息](lync-server-2013-configure-site-information-for-e9-1-1.md)

  - [在 Lync Server 2013 中配置位置数据库](lync-server-2013-configure-the-location-database.md)

  - [在 Lync Server 2013 中配置高级 E9-1-1 功能](lync-server-2013-configure-advanced-e9-1-1-features.md)

