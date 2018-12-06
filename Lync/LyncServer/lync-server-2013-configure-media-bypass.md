---
title: Lync Server 2013：配置媒体绕过
TOCTitle: 配置媒体绕过
ms:assetid: f50a7a13-c6a0-48f1-bee1-e45fa2b2f9b8
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg413028(v=OCS.15)
ms:contentKeyID: 49314754
ms.date: 12/10/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置媒体绕过

 

_**上一次修改主题：** 2016-12-08_

本节假设您已经发布并配置了至少一台或多台中介服务器（分别如 [在 Lync Server 2013 拓扑生成器中定义中介服务器](lync-server-2013-define-a-mediation-server-in-topology-builder.md)和 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)或 [在 Lync Server 2013 中定义和配置前端池或 Standard Edition 服务器](lync-server-2013-define-and-configure-a-front-end-pool-or-standard-edition-server.md)和 [在 Lync Server 2013 中发布拓扑](lync-server-2013-publish-the-topology.md)中所述，以上信息都包含在部署文档中）。

本节还假设您已定义了至少一个对等网关来提供 PSTN 连接，如[在 Lync Server 2013 拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)中所述。如果您连接到的对等方是 SIP 中继提供商的 SBC，请确保该提供商是合格的提供商，且支持媒体旁路。例如，很多 SIP 中继提供商仅允许其 SBC 接收来自中介服务器的流量。如果这样，则不得为出现故障的中继启用旁路。同时，只有您的组织向 SIP 中继提供商显示其内部网络 IP 地址后，您才能启用媒体旁路。

> [!NOTE]  
> 媒体旁路将不会与每个 PSTN 网关、IP-PBX 和 SBC 进行交互操作。Microsoft 与认证合作伙伴一起对一组 PSTN 网关和 SBC 进行了测试，另外也对 Cisco IP-PBX 进行了一些测试。媒体旁路仅支持 <a href="http://go.microsoft.com/fwlink/p/?linkid=214406">http://go.microsoft.com/fwlink/p/?linkId=214406</a> 上的“统一通信开放式互操作性程序 – Lync Server”中列出的产品和版本。



本节介绍如何启用媒体旁路，以减少中介服务器所需的处理。启用媒体旁路之前，请确保您的环境符合支持媒体旁路所需的条件，如规划文档中的[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)中所述。同时确保使用[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)中的信息决定是否启用媒体旁路全局设置，从而始终绕过中介服务器，或使用站点和区域信息决定是否绕过中介服务器。

如果您已选择配置呼叫允许控制 (CAC)（企业语音的另一种高级功能），请注意，呼叫允许控制所执行的带宽保留不会应用于已应用媒体旁路的任何呼叫。首先验证是否应用了媒体旁路，如果已经应用，则不会对该呼叫使用呼叫允许控制；仅当媒体旁路检查失败时，才会检查呼叫允许控制。因此，对于路由至 PSTN 的任何特定呼叫，这两种功能是相互排斥的。这是符合逻辑的，因为媒体旁路假设呼叫中的媒体终结点间不存在带宽约束；无法在带宽受限的链接上执行媒体旁路。因此，会将以下情形之一应用于 PSTN 呼叫：a) 媒体绕过中介服务器，呼叫允许控制不为呼叫保留带宽；或者，b) 呼叫允许控制将带宽保留应用于呼叫，媒体由呼叫中涉及的中介服务器处理。

## 后续步骤：在中继连接上启用媒体旁路

配置 PSTN 连接的初始设置（拨号计划、语音策略、PSTN 用法记录、出站呼叫路由和转换规则）后，按照 [在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)中的步骤启用媒体旁路。

## 另请参阅

#### 任务

[在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)  
[配置媒体绕过以始终绕过中介服务器](lync-server-2013-configure-media-bypass-to-always-bypass-the-mediation-server.md)  
[配置媒体绕过全局设置以使用站点和区域信息](lync-server-2013-configure-media-bypass-global-settings-to-use-site-and-region-information.md)  

#### 概念

[全局媒体绕过选项](lync-server-2013-global-media-bypass-options.md)  

#### 其他资源

[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

