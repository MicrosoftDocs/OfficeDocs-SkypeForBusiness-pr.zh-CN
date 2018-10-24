---
title: Lync Server 2013：中介服务器的组件和拓扑
TOCTitle: 中介服务器的组件和拓扑
ms:assetid: 71397168-36c3-4d21-b8ef-db6a751634ee
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398537(v=OCS.15)
ms:contentKeyID: 49313208
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# Lync Server 2013 中中介服务器的组件和拓扑

 

_**上一次修改主题：** 2012-09-21_

本主题介绍 中介服务器所依赖的组件和可在其中部署 中介服务器的拓扑

## 依赖项

中介服务器具有以下依赖项：

  - **注册器。** 必需。注册器是 中介服务器与 Lync Server 2013 网络之间交互信号的下一个跃点。请注意， 中介服务器除了可以安装在仅由 中介服务器组成的独立池中，还可以与注册器一起并置在 前端服务器上。注册器与 中介服务器和 PSTN 网关一起并置在 Survivable Branch Appliance 上。

  - **监控服务器。** 可选，但强烈建议。 监控服务器允许 中介服务器记录与其媒体会话关联的质量指标。

  - **边缘服务器。** 外部用户支持的必需项。 边缘服务器允许 中介服务器与位于 NAT 或防火墙之后的用户进行交互。

## 拓扑

默认情况下， Lync Server 2013中介服务器与注册器的实例并置在 Standard Edition Server、 前端池或 Survivable Branch Appliance 上。 前端池中的所有 中介服务器必须进行相同的配置。

存在性能问题时，在专用的独立池中部署一台或多台 中介服务器或许是更好的做法。或者，如果要部署 SIP 中继，则建议您部署独立的 中介服务器池。

如果部署与支持媒体旁路和 DNS 负载平衡的合格 PSTN 网关的直接 SIP 连接，则不必使用独立的 中介服务器池，因为合格网关可以对 中介服务器池进行 DNS 负载平衡，并且可以接收来自池中任何 中介服务器的通信。

只要满意任一以下条件，我们还建议您在部署 IP-PBX 之后在 前端池上并置 中介服务器，或者连接到 Internet 电话服务提供商的会话边界控制器 (SBC)：

  - IP-PBX 或 SBC 已配置为接收来自池中的任何 中介服务器的通信，并且可将通信统一路由到池中的所有 中介服务器。

  - IP-PBX 不支持媒体旁路，但承载 中介服务器的 前端池可为不适用媒体旁路的呼叫处理语音代码转换。

您可以使用 Microsoft Lync Server 2013 规划工具来评估要并置 中介服务器的 前端池是否能够处理负载。如果您的环境不能满足这些要求，则必须部署独立的 中介服务器池。

有关要部署的拓扑的详细信息，请参阅 [Lync Server 2013 中介服务器部署准则](lync-server-2013-deployment-guidelines-for-mediation-server.md)。

下图显示了由通过 WAN 链路连接的两个站点组成的简单拓扑。 中介服务器与注册器并置在站点 1 的 前端池上。站点 1 的 中介服务器同时控制站点 1 的 PSTN 网关和站点 2 的网关。在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到每个 PSTN 网关（GW1 和 GW2）的中继都已启用旁路。

**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PSTN 网关相连接的站点示例**

![带中介服务器 WAN 网关的语音拓扑](images/Gg398537.67872e61-1444-447b-918c-abe89abc3004(OCS.15).jpg "带中介服务器 WAN 网关的语音拓扑")

下图显示了一个简单拓扑，其中， 中介服务器与注册器并置在站点 1 的 前端池上，且具有连接到站点 1 的 IP-PBX 的直接 SIP 连接。在此图中， 中介服务器也能控制站点 2 的 PSTN 网关。假定站点 1 和 2 上都存在 Lync 用户。同时假定 IP-PBX 具有关联的媒体处理器，来自 Lync 终结点的所有媒体在发送到由 IP-PBX 控制的媒体终结点之前，必须遍历该处理器。在此拓扑中，已在全局范围内启用媒体旁路以使用站点和区域信息，并且到 PBX 和 PSTN 网关的中继已启用媒体旁路。

**通过 WAN 链路与站点 1 的中介服务器和站点 2 的 PBX 相连接的站点的示例**

![语音拓扑中介服务器 WAN PBX](images/Gg398537.df6c8a5b-8431-4187-907d-ff5ca26eeeec(OCS.15).jpg "语音拓扑中介服务器 WAN PBX")

有关规划 PBX 拓扑的详细信息，请参阅 [Lync Server 2013 中介服务器部署准则](lync-server-2013-deployment-guidelines-for-mediation-server.md)和 [Lync Server 2013 中的直接 SIP 部署选项](lync-server-2013-direct-sip-deployment-options.md)。

本主题中的最后一幅图显示了 中介服务器与 Internet 电话服务提供商的 SBC 相连接的拓扑。有关 SIP 中继拓扑的详细信息，请参阅 [Lync Server 2013 中的 SIP 中继](lync-server-2013-sip-trunking.md)。

