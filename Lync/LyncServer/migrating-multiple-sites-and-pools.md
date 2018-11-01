---
title: 迁移多个站点和池
TOCTitle: 迁移多个站点和池
ms:assetid: a6d726d2-564d-4b39-a97c-5656a673292a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ205165(v=OCS.15)
ms:contentKeyID: 49313839
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移多个站点和池

 

_**上一次修改主题：** 2012-09-17_

Lync Server 2013 支持多站点和多池部署。从 Lync Server 2010 向 Lync Server 2013 迁移多个池时需要注意以下事项：

1.  部署 Lync Server 2013 试点池后，需要定义将移动到 Lync Server 2013 池的一部分试点用户，并确定用于验证用户功能的方法。例如，在将用户移动到试点池之后，请确认该用户的会议策略已移动到 Lync Server 2013。

2.  在试点池中部署边缘服务器后，需要验证外部用户是否能与 Lync Server 2013 池进行通信。

3.  将联盟路由从 Lync Server 2010 边缘服务器切换到试点 Lync Server 2013 边缘服务器后，需要验证联盟用户是否能与 Lync Server 2013 池进行通信。

4.  移动所有用户和非用户联系人对象后，需要验证 Lync Server 2010 池是否为空。

5.  确认 Lync Server 2010 池为空后，即可停用该池。
    
    有关如何停用旧式 Lync Server 2010 池和服务器的详细信息，请参阅 [第 8 阶段：停用旧池](phase-8-decommission-legacy-pools.md)。

