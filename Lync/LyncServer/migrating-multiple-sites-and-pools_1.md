---
title: 迁移多个站点和池
TOCTitle: 迁移多个站点和池
ms:assetid: 3bf677d4-a5af-4f73-8fad-1abf5b668cc1
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/JJ688025(v=OCS.15)
ms:contentKeyID: 49888379
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 迁移多个站点和池

 

_**上一次修改主题：** 2012-08-26_

Lync Server 2013 支持多站点和多池部署。从 Office Communications Server 2007 R2 向 Lync Server 2013 迁移多个池时需要注意以下事项：

1.  部署 Lync Server 2013 试点池后，需要定义将移动到 Lync Server 2013 池的一部分试点用户，并确定用于验证用户功能的方法。

2.  在试点池中部署边缘服务器后，需要验证外部用户是否能与 Lync Server 2013 池进行通信。

3.  将联盟路由从 Office Communications Server 2007 R2 边缘服务器切换到试点 Lync Server 2013 边缘服务器后，需要验证联盟用户是否能与 Lync Server 2013 池进行通信。

4.  移动所有用户和非用户联系人对象后，需要验证 Office Communications Server 2007 R2 池是否为空。

5.  确认 Office Communications Server 2007 R2 池为空后，即可停用该池。
    
    有关如何停用旧式 Office Communications Server 2007 R2 池和服务器的详细信息，请参阅 [第 10 阶段：停用旧站点](phase-10-decommission-legacy-site.md)。

