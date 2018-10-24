---
title: Lync Server 2013：配置中继
TOCTitle: 配置中继
ms:assetid: 0c339511-a185-484e-94f0-dbe918b7e48a
ms:mtpsurl: https://technet.microsoft.com/zh-cn/library/Gg398170(v=OCS.15)
ms:contentKeyID: 49311973
ms.date: 05/19/2016
mtps_version: v=OCS.15
ms.translationtype: HT
---

# 在 Lync Server 2013 中配置中继

 

_**上一次修改主题：** 2012-11-01_

作为 企业语音部署的一部分，在中介服务器与以下一项或多项之间配置中继，以便为组织中的 企业语音客户端和设备提供公用电话交换网 (PSTN) 连接：

  - 到 Internet 电话服务提供商 (ITSP) 的 SIP 中继连接

  - PSTN 网关

  - 专用交换机 (PBX)

有关详细信息，请参阅规划文档中的[在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)。

> [!IMPORTANT]
> 开始中继配置之前，请验证是否已创建拓扑，是否已按照部署文档中的 <a href="lync-server-2013-define-a-gateway-in-topology-builder.md">在 Lync Server 2013 拓扑生成器中定义网关</a>所述配置中介服务器及其对等方并彼此关联。


> [!NOTE]  
> 在配置中继的过程中，可以启用 Lync Server 2013 媒体旁路功能，以允许媒体绕过中介服务器。配置中继时可以启用媒体旁路，也可以不启用媒体旁路，但我们强烈建议您启用该功能。有关详细信息，请参阅规划文档中的 <a href="lync-server-2013-planning-for-media-bypass.md">在 Lync Server 2013 中规划媒体旁路</a>。



## 本部分内容

  - [Lync Server 2013 中的多中继支持](lync-server-2013-multiple-trunk-support.md)

  - [Lync Server 2013 中的中继间路由](lync-server-2013-inter-trunk-routing.md)

  - [在 Lync Server 2013 中查看中继配置信息](lync-server-2013-view-trunk-configuration-information.md)

  - [在 Lync Server 2013 中配置带媒体旁路的中继](lync-server-2013-configure-a-trunk-with-media-bypass.md)

  - [在 Lync Server 2013 中配置无媒体旁路功能的中继](lync-server-2013-configure-a-trunk-without-media-bypass.md)

  - [在 Lync Server 2013 中创建中继配置设置的新集合](lync-server-2013-create-a-new-collection-of-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中删除 SIP 中继配置设置的现有集合](lync-server-2013-delete-an-existing-collection-of-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中修改 SIP 中继配置设置](lync-server-2013-modify-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中测试 SIP 中继配置设置](lync-server-2013-test-sip-trunk-configuration-settings.md)

  - [在 Lync Server 2013 中查看有关各个 SIP 中继的信息](lync-server-2013-view-information-about-individual-sip-trunks.md)

## 另请参阅

#### 任务

[在 Lync Server 2013 拓扑生成器中定义网关](lync-server-2013-define-a-gateway-in-topology-builder.md)  

#### 其他资源

[在 Lync Server 2013 中规划 PSTN 连接](lync-server-2013-planning-for-pstn-connectivity.md)  
[在 Lync Server 2013 中规划媒体旁路](lync-server-2013-planning-for-media-bypass.md)

