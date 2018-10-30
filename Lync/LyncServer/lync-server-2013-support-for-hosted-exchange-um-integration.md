---
title: 托管 Exchange UM 集成的 Lync Server 2013 支持
TOCTitle: 托管 Exchange UM 集成支持
ms:assetid: c7573ec3-013c-48d9-b59b-2a5427e6da35
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398821(v=OCS.15)
ms:contentKeyID: 49314206
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中的托管 Exchange UM 集成支持

 

_**上一次修改主题：** 2012-09-21_

Lync Server 2013 ExUM 路由应用程序支持在以下环境中与 Exchange 统一消息 (UM) 集成： Lync Server 2013 和 Exchange UM 均本地安装在企业内部的内部环境，或具有由下图中所示的服务提供商托管的 Exchange UM 的环境。

![内部 Lync Server Exchange UM 部署](images/Gg398821.d6498eb9-87ee-40f3-8ecd-852f91546590(OCS.15).jpg "内部 Lync Server Exchange UM 部署")

支持以下模式：

  - **内部部署模式**Lync Server 2013 和 Exchange UM 均部署在企业内部的本地服务器上。

  - **交叉部署模式**Lync Server 2013 部署在企业内部的本地服务器上，而 Exchange UM 承载在联机服务提供商的设备上，如 Microsoft Exchange Online 数据中心。

  - **混合模式**Lync Server 2013 部署中的一些用户邮箱驻留在企业内部运行 Microsoft Exchange Server 的本地服务器上，而另外一些则驻留在承载 Exchange 服务数据中心。
    
    > [!NOTE]
    > 混合模式可用作评估用户和将用户逐步迁移至承载 Exchange UM 期间的过渡性解决方案，或者，如果选择在迁移其他用户之后将某些用户的 Exchange UM 服务保留在内部，则混合模式可用作永久性解决方案。


要将 Lync Server 2013 与承载 Exchange UM 集成，必须配置共享 *SIP 地址空间* （也称为 *拆分域* ）。在此配置中， Lync Server 2013 和第三方托管的 Exchange UM 服务提供商可访问相同的 SIP 域地址空间。有关详细信息，请参阅规划文档中的 [Lync Server 2013 中的托管 Exchange UM 集成体系结构](lync-server-2013-hosted-exchange-um-integration-architecture.md)。

