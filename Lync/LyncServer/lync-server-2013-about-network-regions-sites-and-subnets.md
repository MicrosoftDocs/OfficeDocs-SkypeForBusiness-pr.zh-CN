---
title: Lync Server 2013：关于网络区域、站点和子网
TOCTitle: 关于网络区域、站点和子网
ms:assetid: 6662123a-d011-408c-a290-92b2a8589943
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398467(v=OCS.15)
ms:contentKeyID: 49313087
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 关于 Lync Server 2013 中的网络区域、站点和子网

 

_**上一次修改主题：** 2013-02-24_

本节所述的高级企业语音功能共享了网络区域、网络站点和子网的某些配置要求。例如，三种高级功能都要求拓扑中的每个子网与特定 *网络站点* 关联，而每个网络站点必须与 *网络区域* 关联。

> [!IMPORTANT]  
> 对呼叫允许控制、E9-1-1 或媒体旁路开始进行网络配置之前，请确保您已经查看了规划文档的<a href="lync-server-2013-network-settings-for-the-advanced-enterprise-voice-features.md">Lync Server 2013 中高级企业语音功能的网络设置</a>主题中有关网络设置的其他信息。有关网络配置（主要是呼叫允许控制）的详细信息，另请参阅规划文档中的<a href="lync-server-2013-defining-your-requirements-for-call-admission-control.md">在 Lync Server 2013 中定义呼叫允许控制要求</a>。


呼叫允许控制和 E9-1-1 对网络站点具有其他配置要求：

  - 呼叫允许控制要求为由 WAN 带宽限制限定的每个站点指定 *带宽策略配置文件* 。如果计划部署呼叫允许控制，则必须在配置网络站点之前 [创建带宽策略配置文件](lync-server-2013-create-bandwidth-policy-profiles.md)。

  - E9-1-1 要求为每个站点指定 *位置策略* 。如果计划部署 E9-1-1，则必须在配置网络站点之前 [在 Lync Server 2013 中创建位置策略](lync-server-2013-create-location-policies.md)。

## 创建或修改网络区域、网络站点和子网

以下主题提供有关创建或修改网络区域和网络站点，以及将子网与网络站点关联的步骤。这些主题不特定于任何特定高级企业语音功能。

  - [在 Lync Server 2013 中创建或修改网络区域](lync-server-2013-create-or-modify-a-network-region.md)

  - [在 Lync Server 2013 中创建或修改网络站点](lync-server-2013-create-or-modify-a-network-site.md)

  - [在 Lync Server 2013 中将子网与网络站点相关联](lync-server-2013-associate-a-subnet-with-a-network-site.md)

