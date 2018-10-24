---
title: Lync Server 2013：配置呼叫允许控制
TOCTitle: 配置呼叫允许控制
ms:assetid: ce3e6e71-1e33-4cff-849a-c0468e61fef6
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398870(v=OCS.15)
ms:contentKeyID: 49314274
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置呼叫允许控制

 

_**上一次修改主题：** 2012-09-21_

呼叫允许控制 (CAC) 是一种解决方案，它基于可用带宽确定是否可以建立实时会话，从而有助于防止在拥堵网络上为用户提供的音频/视频质量欠佳。CAC 仅控制音频和视频的实时流量，并不影响数据流量。如果默认 WAN 路径没有所需的带宽，CAC 可能会通过 Internet 路径路由呼叫。有关详细信息，请参阅规划文档中的 [在 Lync Server 2013 中规划呼叫允许控制](lync-server-2013-planning-for-call-admission-control.md)。

本节提供一组说明如何在网络中部署和管理 CAC 的示例过程。

> [!IMPORTANT]  
> 在开始 CAC 部署之前，必须收集企业网络拓扑所需的所有信息，如规划文档的 <a href="lync-server-2013-example-of-gathering-your-requirements-for-call-admission-control.md">示例：在 Lync Server 2013 中收集呼叫允许控制要求</a>中所述。此外，请确保已安装并激活 CAC 组件，如部署文档中的 <a href="lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md">在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器</a>中所述。


> [!NOTE]  
> 本节中的所有 CAC 部署和管理示例都是通过使用 Lync Server 命令行管理程序来执行的。作为替代方法，您也可以使用 Lync Server 控制面板的“网络配置”部分来管理 CAC。



## 本部分内容

  - [为 CAC 配置网络区域](lync-server-2013-configure-network-regions-for-cac.md)

  - [创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)

  - [在 Lync Server 2013 中为 CAC 配置网络站点](lync-server-2013-configure-network-sites-for-cac.md)

  - [将子网与网络站点相关联以启用 CAC](lync-server-2013-associate-subnets-with-network-sites-for-cac.md)

  - [创建网络区域链接](lync-server-2013-create-network-region-links.md)

  - [创建网络区域间路由](lync-server-2013;-create-network-interregion-routes.md)

  - [在 Lync Server 2013 中创建网络站点间策略](lync-server-2013-create-network-intersite-policies.md)

  - [启用呼叫允许控制](lync-server-2013-enable-call-admission-control.md)

  - [呼叫允许控制部署检查表](lync-server-2013-call-admission-control-deployment-checklist.md)

